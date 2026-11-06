---
title: "masK — Tahák pro R"
course: mask
type: output
tags: [mask, r, statistika, testovani-hypotez, regrese, regulacni-diagramy]
sources: ["raw/mask/01 náhodné veličiny - návod R.pdf", "raw/mask/02 datové soubory - návod R.pdf", "raw/mask/03 testování hypotéz - návod R 01.pdf", "raw/mask/03 testování hypotéz - návod R 02.pdf", "raw/mask/04 regresní analýza - návod R.pdf", "raw/mask/05 kontingenční tabulky - návod R.pdf", "raw/mask/návod 06 a 07.pdf", "raw/mask/04 05 příklady.docx", "raw/mask/příklady regrese.zip", "raw/mask/příklady kontingenční tabulky.zip", "raw/mask/test VZOR.docx", "raw/mask/6_1.txt", "raw/mask/6_3.txt", "raw/mask/6_5.txt", "raw/mask/6_6.txt"]
created: 2026-10-02
updated: 2026-11-06
---

# masK — Tahák pro R

> [!abstract] V kostce
> R umí spočítat průměr, provést statistický test nebo odhadnout regresní model. Příkazy jsou zde rozdělené podle těchto úloh. Podrobné vysvětlení a řešené příklady obsahují [[mask|Metody aplikované statistiky]].

## Načtení dat

Jednu řadu měření lze zapsat přímo za sebe. Takové posloupnosti hodnot se v R říká **vektor**. Příkaz `c()` jednotlivé hodnoty spojí a šipka je uloží pod jménem `x`. Další možností je načíst měření ze souboru:

```r
x <- c(4.1, 4.0, 3.8, 3.9, 3.8, 3.8, 3.5, 3.7, 4.0, 4.0)   # přímé zadání hodnot
# x <- read.table("data.txt")[, 1]     # první sloupec souboru v pracovním adresáři
# x <- read.table(file.choose())[, 1]  # první sloupec souboru vybraného v dialogovém okně
```

Znak `#` označuje komentář; R tyto řádky neprovádí. Po jeho odstranění může `read.table()` načíst soubor z pracovního adresáře, případně `file.choose()` otevře výběr souboru.

Načtený soubor má podobu tabulky (`data.frame`). Každý sloupec může obsahovat jinou veličinu. Pro výpočet průměru jedné veličiny proto nejprve vybereme její sloupec pomocí `[, 1]`. Bez tohoto kroku by `mean(x)` dostal celou tabulku a vrátil `NA`; `shapiro.test(x)` by skončil chybou.

U regrese se například načte celá tabulka příkazem `d <- read.table("data.txt")`. Sloupce se pak vyberou jako `x <- d[, 1]` a `y <- d[, 2]`. Pokud soubor neobsahuje záhlaví, R sloupce pojmenuje `V1`, `V2`, … První řádek se jmény sloupců načte volba `read.table("data.txt", header = TRUE)`. Pojmenovaný sloupec lze vybrat také zápisem `d$x`.

## Volba testu podle počtu výběrů, závislosti a normality dat

Před volbou testu záleží na tom, zda porovnáváme jednu skupinu, různé skupiny, nebo opakovaná měření týchž objektů. U párového t-testu se předpoklad normality vztahuje k rozdílům uvnitř dvojic. Tabulka pak pomáhá najít odpovídající příkaz a položku ve výstupu.

![[mask-ilu-volba-testu.png|Rozhodovací strom pro volbu testu podle počtu výběrů, závislosti a normality dat]]

| Situace | Test | R volání | Co odečíst z výstupu |
|---|---|---|---|
| Jeden výběr, normální data — test střední hodnoty | jednovýběrový t-test | `t.test(x, mu = ..., alternative = ...)` | `p-value`, interval spolehlivosti, `mean of x` |
| Jeden výběr, přibližně souměrná data — test mediánu | jednovýběrový Wilcoxonův test | `wilcox.test(x, mu = c, alternative = ...)` | `p-value` |
| Párová měření, diference normální | párový t-test | `t.test(x, y, paired = TRUE)` | `p-value`, `mean difference` |
| Párová měření, přibližně souměrné rozdíly | párový Wilcoxonův test | `wilcox.test(x, y, paired = TRUE, mu = c)` | `p-value` |
| Dva nezávislé výběry — shoda rozptylů (krok 1) | F-test | `var.test(x, y)` | `p-value` → volba `var.equal` pro následující t-test |
| Dva nezávislé výběry, normální data — shoda středních hodnot (krok 2) | dvouvýběrový t-test | `t.test(x, y, var.equal = TRUE/FALSE)` | `p-value`, `mean of x`, `mean of y` |
| Dva nezávislé výběry, data nejsou normální | dvouvýběrový Wilcoxonův test | `wilcox.test(x, y)` | `p-value` |
| Víc než dva nezávislé výběry, data nejsou normální | Kruskalův-Wallisův test | `kruskal.test(y ~ faktor, data)` | `p-value` |
| Víc než dva závislé výběry (dvojné třídění) | Friedmanův test | `friedman.test(y ~ A \| B, data)` | `p-value` |
| Ověření normality dat před volbou testu | Shapiro-Wilkův test | `shapiro.test(x)` | `p-value` |
| Shoda dat s rozdělením o předem známých parametrech | Kolmogorovův-Smirnovův test | `ks.test(x, "pnorm", mu, sigma)` | `p-value` |

Wilcoxonův test pro jeden výběr předpokládá přibližně souměrné rozdělení hodnot; u párových měření se souměrnost týká rozdílů ve dvojicích. U dvou nezávislých skupin lze jeho výsledek vykládat jako porovnání mediánů, pokud se rozdělení liší jen posunutím. Kolmogorovův-Smirnovův test potřebuje parametry známé předem, nikoli odhadnuté z testovaných dat. Tyto podmínky podrobněji vysvětluje [[testovani-hypotez|kapitola o testech]].

H0 je výchozí hypotéza, například o shodě středních hodnot. Na hladině významnosti 0,05 ji zamítáme, pokud je `p-value` nejvýše 0,05. Při vyšší hodnotě ji nezamítáme: data neposkytla dostatečný důkaz proti ní. U testu normality to dovoluje s normálním rozdělením dále pracovat, ale neprokazuje je.

## Funkce podle kapitol

### [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]]

První písmeno názvu funkce říká, co se počítá: `d` jednotlivou pravděpodobnost nebo hustotu, `p` pravděpodobnost do zadané hranice a `q` kvantil. V tabulce se tyto funkce mění podle zvoleného rozdělení.

| Rozdělení | $P(X = k)$, hustota $f(x)$ | $P(X \le k)$, $F(x)$ | $P(X > k)$, $1 - F(x)$ | Kvantil $x_P$ |
|---|---|---|---|---|
| Binomické $Bi(n,p)$ | `dbinom(k, n, p)` | `pbinom(k, n, p)` | `pbinom(k, n, p, FALSE)` | `qbinom(P, n, p)` |
| Poissonovo $Po(\lambda)$ | `dpois(k, lambda)` | `ppois(k, lambda)` | `ppois(k, lambda, FALSE)` | `qpois(P, lambda)` |
| Geometrické $G(p)$ | `dgeom(k, p)` | `pgeom(k, p)` | `pgeom(k, p, FALSE)` | `qgeom(P, p)` |
| Hypergeometrické $H(N,M,n)$ | `dhyper(k, M, N-M, n)` | `phyper(k, M, N-M, n)` | `phyper(k, M, N-M, n, FALSE)` | `qhyper(P, M, N-M, n)` |
| Normální $N(\mu,\sigma^2)$ | `dnorm(x, mu, sigma)` | `pnorm(x, mu, sigma)` | `pnorm(x, mu, sigma, FALSE)` | `qnorm(P, mu, sigma)` |
| Exponenciální $E(\delta)$ | `dexp(x, 1/delta)` | `pexp(x, 1/delta)` | `pexp(x, 1/delta, FALSE)` | `qexp(P, 1/delta)` |
| Studentovo $t(k)$ | `dt(x, df = k)` | `pt(x, df = k)` | `pt(x, df = k, lower.tail = FALSE)` | `qt(P, df = k)` |
| Pearsonovo $\chi^2(k)$ | `dchisq(x, df = k)` | `pchisq(x, df = k)` | `pchisq(x, df = k, lower.tail = FALSE)` | `qchisq(P, df = k)` |
| Fisherovo-Snedecorovo $F(k_1,k_2)$ | `df(x, df1 = k1, df2 = k2)` | `pf(x, df1 = k1, df2 = k2)` | `pf(x, df1 = k1, df2 = k2, lower.tail = FALSE)` | `qf(P, df1 = k1, df2 = k2)` |

- Normální rozdělení se zadává směrodatnou odchylkou $\sigma$. Při dosazování je proto potřeba odlišit ji od rozptylu $\sigma^2$.
- Exponenciální rozdělení používá parametr `1/delta`, kde $\delta$ je střední hodnota.
- U geometrického rozdělení `dgeom(k, p)` znamená $k$ počet neúspěchů před prvním úspěchem.
- Pravděpodobnost nad zadanou hodnotou vrací `lower.tail = FALSE`. Samotné `FALSE` musí být na správném místě mezi argumenty. U rozdělení $t$, $\chi^2$ a $F$ je hned za parametry rozdělení argument `ncp` pro necentralitu, takže se zde `lower.tail` uvádí jménem.
- U spojité veličiny je $P(X = x) = 0$. Funkce `d*` zde vrací výšku hustoty; pravděpodobnost se určuje pro interval hodnot.

### [[popisna-statistika|Popisná statistika a datové soubory]]

Průměr a medián popisují polohu měření. Rozptyl a směrodatná odchylka vyjadřují, jak moc se hodnoty liší. Histogram a empirická distribuční funkce ukazují rozložení celého souboru. Následující příkazy pracují s jedním vybraným sloupcem měření `x`.

| Funkce | Co vrací |
|---|---|
| `length(x)` | rozsah souboru $n$ |
| `min(x)`, `max(x)` | nejmenší a největší hodnota |
| `mean(x)` | výběrový průměr |
| `var(x)` | výběrový rozptyl |
| `sd(x)` | výběrová směrodatná odchylka |
| `median(x)` | výběrový medián (stejně jako `quantile(x, 0.5, type = 6)`) |
| `quantile(x, p, type = 6)` | výběrový $p$-kvantil s uvedenou metodou interpolace |
| `sort(x)` / `sort(x, decreasing = TRUE)` | hodnoty seřazené vzestupně/sestupně |
| `boxplot(x)` | krabicový graf |
| `h <- hist(x, br = seq(38, 46, by = 1))` | histogram s danými hranicemi tříd; výsledek třídění v `h` |
| `h$counts`, `h$breaks`, `h$mids` | četnosti tříd, hranice tříd, středy tříd |
| `h$density` | četnost třídy dělená $n$ a šířkou třídy (při šířce 1 relativní četnost) |
| `f <- ecdf(x)` | empirická distribuční funkce |
| `f(k)` | hodnota empirické distribuční funkce v bodě $k$ |
| `knots(f)` | vzestupně seřazené různé hodnoty souboru |

### [[testovani-hypotez|Testování statistických hypotéz]]

Test se volí podle povahy výběrů a hypotézy, kterou ověřujeme. `paired = TRUE` označuje měření spojená do dvojic. U dvou nezávislých normálních výběrů se rozlišuje postup se společným rozptylem a Welchův postup; volbu určuje `var.equal`.

| Funkce | Použití |
|---|---|
| `t.test(x, mu = ..., alternative = ...)` | jednovýběrový t-test |
| `t.test(x, y, paired = TRUE)` | párový t-test |
| `t.test(x, y, var.equal = TRUE/FALSE)` | dvouvýběrový t-test |
| `var.test(x, y)` | F-test shody rozptylů |
| `shapiro.test(x)` | Shapiro-Wilkův test normality |
| `ks.test(x, "pnorm", mu, sigma)` | Kolmogorovův-Smirnovův test shody s normálním rozdělením |
| `ks.test(x, "pexp", 1/delta)` | Kolmogorovův-Smirnovův test shody s exponenciálním rozdělením |
| `wilcox.test(x, mu = c, alternative = ...)` | jednovýběrový Wilcoxonův test |
| `wilcox.test(x, y, paired = TRUE, mu = c)` | párový Wilcoxonův test |
| `wilcox.test(x, y)` | dvouvýběrový Wilcoxonův test |
| `kruskal.test(y ~ faktor, data)` | Kruskalův-Wallisův test |
| `library(agricolae); Median.test(y, faktor)` | mediánový test (alternativa ke Kruskalovu-Wallisovu) |
| `friedman.test(y ~ A \| B, data)` | Friedmanův test (`friedman.test(y, A, B)` jen pro samostatné vektory) |

### [[regresni-a-korelacni-analyza|Regresní a korelační analýza]]

Regrese popisuje, jak se sledovaná veličina mění s vysvětlujícími veličinami. Zápis `y ~ x` vyjadřuje, že hodnotu `y` vysvětlujeme pomocí `x`. Základní postup tvoří `model <- lm(y ~ x)` a `summary(model)`: standardní souhrn už obsahuje parametry, jejich testy, $R^2$, upravené $R^2$ i F-test celého modelu. Další funkce použijeme jen pro konkrétní navazující otázku.

| Funkce | Použití |
|---|---|
| `lm(y ~ x)` | lineární regrese (přímka) |
| `lm(y ~ log(x))` | logaritmická regrese; hodnoty $x$ musí být kladné |
| `lm(y ~ x + I(x^2))` | parabolická regrese |
| `lm(y ~ I(1/x))` | hyperbolická regrese |
| `library(nls2); nls2(y ~ b1 * exp(b2 * x))` | exponenciální regrese $y = b_1 e^{b_2 x}$ |
| `nls2(y ~ b1 * b2^x)` | alternativní exponenciální parametrizace $y = b_1 b_2^{x}$ s kladným základem $b_2 > 0$ |
| `summary(model)` | odhady parametrů, jejich významnost, koeficient determinace |
| `coef(model)` | odhadnuté parametry $b_0, b_1, \dots$ |
| `fitted(model)` | odhady hodnot $\hat y_i$ pro pozorované $x_i$ |
| `residuals(model)` | rezidua $e_i = y_i - \hat y_i$ |
| `confint(model, level = 0.95)` | intervaly spolehlivosti pro parametry modelu |
| `predict(model, interval = "confidence", level = 0.95)` | interval spolehlivosti pro střední hodnotu $\hat y$ |
| `predict(model, interval = "prediction", level = 0.95)` | predikční interval pro jednotlivou hodnotu $y$ |
| `predict(model, newdata = data.frame(x = c(7, 8)), interval = "confidence")` | totéž pro nové hodnoty $x$; sloupec se musí jmenovat jako proměnná v modelu |
| `cor(x, y)` | korelační koeficient |
| `cor(x, y, method = "spearman")` | korelační koeficient pořadových čísel |
| `step(model, direction = "both")` | postupný výběr proměnných podle AIC |
| `library(car); vif(model)` | ukazatel multikolinearity, tedy vzájemné závislosti vysvětlujících veličin |
| `library(lmtest); dwtest(model)` | Durbin-Watsonův test autokorelace, tedy závislosti sousedních reziduí |
| `library(whitestrap); white_test(model)` | Whiteův test stálosti rozptylu reziduí |
| `shapiro.test(residuals(model))` | test normality reziduí |

Předpověď se počítá pro konkrétní hodnoty vysvětlujících veličin. Jejich sloupce v `newdata` musí mít stejná jména jako v modelu. Pro `lm(y1 ~ x1, data = d)` se tedy použije `predict(model, newdata = data.frame(x1 = 34))`. Jméno `x1` propojí novou hodnotu se správnou veličinou; sloupec nazvaný `x` by to nezajistil.

### [[kontingencni-tabulky|Kontingenční tabulky]]

Při práci s kategoriemi se nejprve sestaví tabulka počtů. `table()` přiřadí každé pozorování podle jeho dvojice kategorií. Následující příkazy počítají podíly, doplňují součty a vyhodnocují vztah mezi kategoriemi.

| Funkce | Použití |
|---|---|
| `table(prijem, financovani)` | kontingenční tabulka z dvojic kategorií; oba vektory obsahují stejná pozorování |
| `prop.table(tab, margin = 1)` | řádkové relativní četnosti; součet každého řádku je 1 |
| `addmargins(tab)` | tabulka doplněná o marginální součty |
| `test <- chisq.test(tab, correct = FALSE); test` | test nezávislosti bez Yatesovy korekce a jeho standardní výstup |
| `test$expected` | očekávané četnosti za platnosti nezávislosti |
| `sqrt(test$statistic / (sum(tab) * (min(dim(tab)) - 1)))` | Cramérův koeficient kontingence $V$; `test` je výsledek testu bez korekce |
| `mcnemar.test(tab, correct = FALSE)` | McNemarův test pro párovaná kvalitativní data |

V kontingenční tabulce je každé pozorování zařazeno do řádku a sloupce podle dvou kategorií. Test nezávislosti potřebuje počty takto zařazených pozorování, tedy absolutní četnosti. Podíly vypočtené pomocí `prop.table()` slouží k porovnávání zastoupení kategorií. Před hodnocením p-hodnoty se ověří dostatečné očekávané četnosti. Cramérův koeficient pak popisuje sílu vztahu ve výběru, zatímco test řeší jeho statistickou významnost.

Pro Cramérův koeficient potřebujeme výsledek bez Yatesovy korekce. První příkaz v tabulce proto výslovně zadává `correct = FALSE`; tentýž objekt `test` pak použijeme i ve vzorci pro $V$. U větších tabulek se korekce neuplatňuje.

### [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]]

Regulační diagram zachovává pořadí odběrů a hledá známky změny procesu. Volba příkazu záleží na tom, zda zapisujeme rozměry, počty vad, nebo počty vadných kusů. Samotné `qcc(...)` diagram rovnou vykreslí; signály se proto nejprve čtou z grafu. Až po ověření stability lze porovnat kolísání měření s tolerancemi pomocí `process.capability()`.

| Funkce | Použití |
|---|---|
| `library(qcc)` | balíček pro regulační diagramy a indexy způsobilosti |
| `qcc.groups(x, sample)` | seskupení měření `x` podle označení odběru v `sample` |
| `qcc(data, type = "R")` | diagram rozpětí $R$; rozdíl největšího a nejmenšího měření v každé podskupině |
| `qcc(data, type = "xbar")` | regulační diagram průměrů $\bar x$ |
| `qcc(data, type = "S")` | regulační diagram výběrových směrodatných odchylek $s$ |
| `qcc(x, type = "xbar.one")` | diagram individuálních hodnot $x_i$ (jedno měření v podskupině, $\sigma$ z klouzavých rozpětí) |
| `qcc(c_i, type = "c")` | diagram počtu neshod $c$ |
| `qcc(pocty_neshod, type = "u", sizes = rozsahy)` | diagram počtu neshod na jednotku $u$; vstupem jsou počty neshod a rozsahy podskupin |
| `qcc(np_i, type = "np", sizes = n)` | diagram počtu neshodných jednotek $np$ (stejné rozsahy $n$) |
| `qcc(pocty_neshodnych, type = "p", sizes = rozsahy)` | diagram podílu neshodných jednotek $p$; vstupem jsou počty neshodných kusů, rozsahy smějí být různé |
| `q <- qcc(data, type = "xbar")` | uložení diagramu pro výpočet indexů způsobilosti |
| `process.capability(q, spec.limits = c(LSL, USL), target = T, std.dev = sd(data))` | indexy $C_p$, $C_{pk}$ a $C_{pm}$ s výběrovou směrodatnou odchylkou všech měření |

Při měření délek výrobků patří do jednoho řádku délky z téhož odběru. Další řádek obsahuje měření z následujícího odběru. Taková skupina měření se nazývá logická podskupina. Pro `qcc()` se délky uloží do číselné tabulky, v R označované jako matice `data`. Číslo podskupiny je pouze její označení; do sloupců s naměřenými délkami se nepřidává.

U desek s různou plochou porovnává diagram $u$ počet suků na jednotku plochy. Dostane počty suků a plochy desek v `sizes`. U různě velkých sérií tabletů porovnává diagram $p$ podíl vadných kusů. Dostane počty vadných tabletů a velikosti sérií v `sizes`. V obou případech provede dělení funkce `qcc()` sama.

Bod mimo meze pomáhá najít odběr, u kterého je třeba hledat změnu procesu. Z výpočtu jej lze vyřadit až po zjištění a odstranění konkrétní příčiny. Indexy způsobilosti navazují na ověření statistické zvládnutosti; samotný výpočet `process.capability()` stabilitu nekontroluje.

## Výchozí nastavení R, která mění výsledek

Výsledek příkazu závisí také na volbách, které se v krátkém zápisu nemusí objevit. Následující tabulka shrnuje, jaké nastavení R použije samo a kdy je třeba zadat jinou hodnotu.

| Parametr | Výchozí hodnota v R | Co se změní při jiném nastavení |
|---|---|---|
| `correct` v `mcnemar.test()` | `TRUE` (Yatesova korekce na kontinuitu) | `correct = FALSE` vypočte statistiku bez korekce na kontinuitu |
| `correct` v `chisq.test()` | `TRUE`, uplatní se jen u tabulky 2 × 2 | `correct = FALSE` vypočte statistiku pro čtyřpolní tabulku bez korekce |
| `var.equal` v `t.test()` | `FALSE` (Welchova varianta) | `TRUE` použije klasickou dvouvýběrovou statistiku se společným rozptylem — volí se podle výsledku F-testu |
| `alternative` v `t.test()` / `wilcox.test()` / `var.test()` | `"two.sided"` | `"greater"` / `"less"` testuje jednostrannou alternativu — musí odpovídat formulaci $H_1$ |
| `paired` v `t.test()` / `wilcox.test()` | `FALSE` | `TRUE` testuje dvojice závislých měření (diference), ne dva nezávislé výběry |
| `conf.level` v `t.test()` / `var.test()` | `0.95` | určuje spolehlivost intervalu uvedeného ve výstupu testu ($1 - \alpha$) |
| `conf.int` v `wilcox.test()` | `FALSE` | `wilcox.test()` vypíše interval spolehlivosti jen s `conf.int = TRUE`; samotné `conf.level` výstup nezmění |
| `type` v `quantile()` | `7` | `type = 6` zvolí jiný způsob interpolace mezi seřazenými hodnotami |
| `right` v `hist()` | `TRUE` (třídy zleva otevřené, zprava uzavřené) | `right = FALSE` otočí hranice tříd na zleva uzavřené, zprava otevřené |
| `plot` v `qcc()` | `TRUE` (diagram se vykreslí) | `plot = FALSE` jen spočítá meze a vrátí objekt bez vykreslení grafu |
| `std.dev` v `process.capability()` | směrodatná odchylka z regulačního diagramu `q` (z rozpětí nebo směrodatných odchylek v podskupinách) | `std.dev = sd(data)` použije výběrovou směrodatnou odchylku všech dat; indexy vyjdou jinak |
| `target` v `process.capability()` | střed tolerance $(LSL + USL)/2$ | jiná cílová hodnota $T$ změní $C_{pm}$ |

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]]
- [[popisna-statistika|Popisná statistika a datové soubory]]
- [[testovani-hypotez|Testování statistických hypotéz]]
- [[regresni-a-korelacni-analyza|Regresní a korelační analýza]]
- [[kontingencni-tabulky|Kontingenční tabulky]]
- [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.

MONTGOMERY, D. C. *Introduction to Statistical Quality Control*. 6. vyd. Hoboken: Wiley, 2009.

KUPKA, K. *Statistické řízení jakosti*. Pardubice: TriloByte, 1997.
