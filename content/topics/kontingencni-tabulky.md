---
title: "Kontingenční tabulky"
course: mask
type: topic
tags: [mask, statistika, kontingencni-tabulka, chi-kvadrat-test, mcnemaruv-test, r]
sources: [raw/mask/05 kontingenční tabulky.pdf, raw/mask/05 kontingenční tabulky přednáška.pdf, raw/mask/05 kontingenční tabulky - návod R.pdf, raw/mask/příklady 04 a 05.docx, raw/mask/04 05 příklady.docx, raw/mask/příklady kontingenční tabulky.zip]
created: 2026-10-02
updated: 2026-11-06
---

# Kontingenční tabulky

> [!tldr] V kostce
> - Kontingenční tabulka ukáže počty pozorování v kombinacích dvou kategorií.
> - Test nezávislosti porovná skutečné počty s těmi, které bychom očekávali, kdyby spolu znaky nesouvisely.
> - Cramérův koeficient popisuje sílu souvislosti ve výběru.
> - Pro porovnání odpovědí ano/ne u stejných lidí před změnou a po ní používáme McNemarův test.

## Kontingenční tabulka

Při průzkumu nákupu potravin na internetu známe u každého respondenta vzdělání
a odpověď na otázku o nákupu. Odpovědi můžeme uspořádat do tabulky: řádky označí vzdělání, sloupce zkušenost
s nákupem a políčka počty respondentů v dané kombinaci. Tak vzniká **kontingenční tabulka**.

Pomocí [[testovani-hypotez|testování statistických hypotéz]] pak posoudíme, zda údaje ukazují na souvislost
obou vlastností. Jde o jednu z [[mask|metod aplikované statistiky]].

Vzdělání je **kvalitativní neboli kategoriální znak**: hodnotou je příslušnost ke kategorii.
Naproti tomu stáří nebo stav tachometru jsou **kvantitativní znaky**, protože udávají číselnou velikost.
Kvalitativní znak se dvěma variantami, například kuřák/nekuřák nebo vada ano/ne, nazýváme **alternativní**.
Má-li více než dvě varianty, například svobodný/rozvedený/ženatý, je **množný**.

Obecně máme $n$ pozorování dvou kvalitativních znaků $A$ s variantami $A_1,\dots,A_r$ a $B$
s variantami $B_1,\dots,B_s$. V políčku $(i,j)$ tabulky je **simultánní neboli společná četnost** $n_{ij}$:
počet pozorování, která mají variantu $A_i$ a současně variantu $B_j$.
Sečtením řádku dostaneme počet pozorování dané řádkové kategorie bez ohledu na sloupec.
Totéž platí pro sloupcové součty. Tyto součty nazýváme **marginální četnosti**:

$$
n_{i\bullet} = \sum_{j=1}^{s} n_{ij}, \qquad n_{\bullet j} = \sum_{i=1}^{r} n_{ij}, \qquad n = \sum_{i=1}^r\sum_{j=1}^s n_{ij}
$$

| $A \backslash B$ | $B_1$ | $B_2$ | … | $B_s$ | $n_{i\bullet}$ |
|---|---|---|---|---|---|
| $A_1$ | $n_{11}$ | $n_{12}$ | … | $n_{1s}$ | $n_{1\bullet}$ |
| $A_2$ | $n_{21}$ | $n_{22}$ | … | $n_{2s}$ | $n_{2\bullet}$ |
| ⋮ | ⋮ | ⋮ | ⋱ | ⋮ | ⋮ |
| $A_r$ | $n_{r1}$ | $n_{r2}$ | … | $n_{rs}$ | $n_{r\bullet}$ |
| $n_{\bullet j}$ | $n_{\bullet 1}$ | $n_{\bullet 2}$ | … | $n_{\bullet s}$ | $n$ |

Vydělíme-li počty celkovým počtem pozorování $n$, získáme podíly, tedy relativní četnosti.
Ty slouží jako odhady pravděpodobností jednotlivých kombinací i řádkových a sloupcových kategorií:

$$
\hat p_{ij} = \frac{n_{ij}}{n}, \qquad \hat p_{i\bullet} = \frac{n_{i\bullet}}{n}, \qquad \hat p_{\bullet j} = \frac{n_{\bullet j}}{n}
$$

## Test nezávislosti dvou kvalitativních znaků

Pokud jsou znaky $A$ a $B$ nezávislé, znalost jednoho nám nepomůže určit druhý. V příkladu se vzděláním
by pak podíly odpovědí o nákupu byly v jednotlivých vzdělanostních skupinách stejné.
Pravděpodobnost společného výskytu se při nezávislosti rovná součinu pravděpodobností obou kategorií.
Test porovnává takto očekávané počty s těmi, které skutečně pozorujeme.

Rozdíly v jednotlivých políčkách shrne do jednoho testového kritéria. Čím více se skutečné počty od očekávaných
odchylují, tím větší kritérium vychází a tím méně data odpovídají představě nezávislosti.

**Postup testu:**

1. $H_0: p_{ij} = p_{i\bullet}\,p_{\bullet j}$ pro všechna $i = 1,\dots,r$, $j = 1,\dots,s$ (znaky jsou na sobě
   nezávislé) proti $H_1$: znaky jsou závislé.
2. Testové kritérium

   $$
   \chi^2 = \sum_{i=1}^{r}\sum_{j=1}^{s} \frac{(n_{ij} - n\hat p_{ij})^2}{n\hat p_{ij}}, \qquad \hat p_{ij} = \hat p_{i\bullet}\,\hat p_{\bullet j}
   $$

   má pro dostatečně velké očekávané četnosti přibližně Pearsonovo ($\chi^2$) rozdělení o $(r-1)(s-1)$ stupních volnosti. Hodnota $n\hat p_{ij} = \dfrac{n_{i\bullet}n_{\bullet j}}{n}$ je **očekávaná četnost** políčka $(i,j)$. Získáme ji vynásobením řádkového a sloupcového součtu a vydělením celkovým počtem pozorování. Je to počet, který bychom v políčku čekali, kdyby platila $H_0$.
3. Kritický obor: $W = \{\chi^2 : \chi^2 \ge \chi^2_{1-\alpha}((r-1)(s-1))\}$.
4. Leží-li vypočtené kritérium v $W$, jsou rozdíly příliš velké, než abychom je na hladině $\alpha$ přičetli náhodě při nezávislosti. Zamítáme hypotézu nezávislosti ve prospěch
   $H_1$. Jinak $H_0$ nezamítáme; nezávislost tím ale nedokazujeme.

V následujícím příkladu máme odpovědi už sečtené. Do R proto přepíšeme přímo počty z tabulky
a necháme je porovnat funkcí `chisq.test()`. Ta vypočítá výsledek testu; doplněk `$expected` zobrazí
očekávané počty, které potřebujeme zkontrolovat.

> [!example] Příklad: nákup potravin na internetu a vzdělání
> Posuďte, zda zkušenost s nákupem potravin na internetu souvisí se vzděláním respondenta
> (n = 385 respondentů).
>
> Základním souborem jsou respondenti, k nimž chceme závěr vztáhnout. Výběr tvoří ti, kteří odpověděli.
> U každého známe znak A, tedy vzdělání, a znak B, tedy způsob nákupu.
>
> | vzdělání \ nákup | ano | ne, ale plánuji | ne, neplánuji | $n_{i\bullet}$ |
> |---|---|---|---|---|
> | SŠ bez maturity | 4 | 13 | 12 | 29 |
> | SŠ s maturitou, VOŠ | 31 | 62 | 71 | 164 |
> | VŠ | 44 | 58 | 66 | 168 |
> | ZŠ | 3 | 9 | 12 | 24 |
> | $n_{\bullet j}$ | 82 | 142 | 161 | 385 |
>
> $H_0: p_{ij} = p_{i\bullet}p_{\bullet j}$ — vzdělání a způsob nákupu jsou na sobě nezávislé.

Řádky tabulky patří vzdělanostním skupinám, sloupce jednotlivým odpovědím. Každé políčko říká,
kolik lidí má dané vzdělání a zároveň zvolilo danou odpověď. Pomocí `matrix()` přeneseme tyto počty
do R ve stejném uspořádání; `byrow = TRUE` znamená, že je zapisujeme po řádcích.

```r
tab1 <- matrix(c(4, 13, 12,
                 31, 62, 71,
                 44, 58, 66,
                 3,  9, 12),
               nrow = 4, byrow = TRUE,
               dimnames = list(
                 vzdelani = c("SS bez maturity", "SS s maturitou nebo VOS", "VS", "ZS"),
                 nakup    = c("ano", "ne, ale planuji", "ne, neplanuji")))
```

Na připravené tabulce provedeme test a z téhož výsledku přečteme očekávané četnosti:

```r
test1 <- chisq.test(tab1)
test1
test1$expected
```

```text
	Pearson's Chi-squared test

data:  tab1
X-squared = 5.4875, df = 6, p-value = 0.483

                         nakup
vzdelani                        ano ne, ale planuji ne, neplanuji
  SS bez maturity          6.176623       10.696104      12.12727
  SS s maturitou nebo VOS 34.929870       60.488312      68.58182
  VS                      35.781818       61.963636      70.25455
  ZS                       5.111688        8.851948      10.03636
```

Ve výpisu očekávaných četností jsou všechny hodnoty nad 5, takže je můžeme použít pro přibližný test.
Testové kritérium $\chi^2 = 5{,}49$ s $6$ stupni volnosti dává p-hodnotu $0{,}483 > 0{,}05$.
Proto $H_0$ nezamítáme: souvislost zkušenosti s nákupem potravin na internetu a vzdělání se neprokázala.

> [!example] Příklad: vzdělání a zveřejňování citlivých údajů na Facebooku
> Mezi 221 osobami bylo zaznamenáno vzdělání a zda zveřejňují na Facebooku citlivé údaje. Proveďte test
> nezávislosti.
>
> | zveřejňuje \ vzdělání | SŠ | VŠ | ZŠ |
> |---|---|---|---|
> | ne | 20 | 33 | 39 |
> | ano | 25 | 28 | 76 |
>
> $H_0: p_{ij} = p_{i\bullet}p_{\bullet j}$ — vzdělání a zveřejňování citlivých údajů jsou na sobě nezávislé.

```r
tab2 <- matrix(c(20, 33, 39,
                 25, 28, 76),
               nrow = 2, byrow = TRUE,
               dimnames = list(
                 zverejnuje = c("ne", "ano"),
                 vzdelani   = c("SS", "VS", "ZS")))
```

```r
test2 <- chisq.test(tab2)
test2
test2$expected
```

```text
	Pearson's Chi-squared test

data:  tab2
X-squared = 6.8677, df = 2, p-value = 0.03226

          vzdelani
zverejnuje       SS       VS      ZS
       ne  18.73303 25.39367 47.8733
       ano 26.26697 35.60633 67.1267
```

I zde jsou všechny očekávané četnosti nad 5. Testové kritérium $\chi^2 = 6{,}87$ s $2$ stupni volnosti dává
p-hodnotu $0{,}032 < 0{,}05$: $H_0$ zamítáme — mezi vzděláním a zveřejňováním
citlivých údajů na Facebooku se prokázala statisticky významná závislost.

Graf porovnává skutečné a očekávané počty v obou příkladech. V prvním nejsou rozdíly dost velké k zamítnutí
$H_0$. Ve druhém jsou odchylky výraznější, zejména ve skupině se základním vzděláním:

![[mask-kt-observed-expected.png|Grupované sloupce pozorovaných a očekávaných četností pro oba příklady: u nákupu potravin se pozorované a očekávané četnosti v každé kategorii téměř shodují, u zveřejňování údajů se u ZŠ výrazně liší]]

Na dalším obrázku vidíme vypočtené hodnoty v rozdělení testového kritéria. V prvním příkladu leží $\chi^2$
pod kritickou hodnotou, ve druhém uvnitř kritického oboru $W$:

![[mask-kt-chi2-kriticky-obor.png|Hustota χ² rozdělení s vyznačeným kritickým oborem a pozorovanou hodnotou testového kritéria pro nákup potravin (mimo kritický obor) a zveřejňování údajů (uvnitř kritického oboru)]]

## Cramérův koeficient kontingence

Statisticky významná souvislost může být slabá. P-hodnota nám její sílu neřekne.
K tomu použijeme **Cramérův koeficient kontingence**:

$$
V = \sqrt{\frac{\chi^2}{n(m-1)}}, \qquad m = \min(r, s)
$$

kde $\chi^2$ je hodnota testového kritéria z testu nezávislosti. $V = 0$ odpovídá úplné nezávislosti znaků,
$V = 1$ jejich úplné závislosti.

```r
V1 <- sqrt(test1$statistic / (sum(tab1) * 2))
V2 <- sqrt(test2$statistic / sum(tab2))
V1
V2
```

```text
 X-squared 
0.08441958 
X-squared 
0.1762822 
```

![[mask-kt-cramerovo-v.png|Cramérův koeficient kontingence V pro nákup potravin (0,084) a zveřejňování údajů (0,176) na škále od 0 (úplná nezávislost) do 1 (úplná závislost)]]

U nákupu potravin vychází $V = 0{,}084$, tedy zanedbatelná síla vztahu; test také $H_0$ nezamítl.
U zveřejňování údajů je $V = 0{,}176$. Přestože jsme $H_0$ zamítli, vztah je stále slabý.

## Příjem domácnosti a financování nákupů

U 240 domácností byl zaznamenán čistý měsíční příjem a převažující způsob financování větších nákupů:
kreditní karta, odložená platba, spotřebitelský úvěr nebo vlastní úspory. Na hladině $\alpha = 0{,}05$
posoudíme, zda způsob financování souvisí s příjmovou skupinou. Pro porovnání skupin vypočítáme
řádkové relativní četnosti a pro sílu vztahu Cramérovo $V$. Také zkontrolujeme očekávané četnosti.

$H_0$: příjmová skupina domácnosti a způsob financování jsou nezávislé. $H_1$: znaky jsou závislé.
V tabulce je každá příjmová skupina zastoupena 60 domácnostmi; příjmy jsou v tisících Kč za měsíc.

Počty domácností uložíme do tabulky nazvané `tab_prijem`. Řádkové relativní četnosti pak ukážou, jaký podíl
domácností uvnitř jedné příjmové skupiny používá každý způsob financování. Funkce `prop.table(tab_prijem, 1)` vydělí každé políčko součtem jeho řádku. Podíly v řádku pak dávají
dohromady 1. Zápis `prop.table(tab_prijem)` by je naopak dělil počtem všech domácností a ukazoval podíly v celém výběru.

Zde jsou počty opět zadány přímo. Pokud bychom měli místo součtů seznam jednotlivých domácností, kde každý
řádek obsahuje příjem a způsob financování jedné domácnosti, vytvořil by tabulku počtů příkaz
`table(data$prijem, data$financovani)`. Zde `data` označuje tabulku jednotlivých domácností a zápisy za znakem `$` vybírají její sloupce.

```r
tab_prijem <- matrix(c(8, 14, 20, 18,
                       12, 8, 16, 24,
                       12, 5, 9, 34,
                       10, 3, 5, 42),
                     nrow = 4, byrow = TRUE,
                     dimnames = list(
                       prijem = c("do 30 tis.", "30-50 tis.", "50-70 tis.", "nad 70 tis."),
                       financovani = c("karta", "odlozena", "uver", "uspory")))
tab_prijem
```

```text
             financovani
prijem        karta odlozena uver uspory
  do 30 tis.      8       14   20     18
  30-50 tis.     12        8   16     24
  50-70 tis.     12        5    9     34
  nad 70 tis.    10        3    5     42
```

Řádkové podíly odpovídají otázce, jak se financování liší uvnitř jednotlivých příjmových skupin:

```r
round(prop.table(tab_prijem, 1), 4)
```

```text
             financovani
prijem         karta odlozena   uver uspory
  do 30 tis.  0.1333   0.2333 0.3333 0.3000
  30-50 tis.  0.2000   0.1333 0.2667 0.4000
  50-70 tis.  0.2000   0.0833 0.1500 0.5667
  nad 70 tis. 0.1667   0.0500 0.0833 0.7000
```

Test nezávislosti a jeho očekávané četnosti získáme z jediného objektu:

```r
test_prijem <- chisq.test(tab_prijem)
test_prijem
test_prijem$expected
```

```text
	Pearson's Chi-squared test

data:  tab_prijem
X-squared = 32.699, df = 9, p-value = 0.0001507

             financovani
prijem        karta odlozena uver uspory
  do 30 tis.   10.5      7.5 12.5   29.5
  30-50 tis.   10.5      7.5 12.5   29.5
  50-70 tis.   10.5      7.5 12.5   29.5
  nad 70 tis.  10.5      7.5 12.5   29.5
```

Tabulka má čtyři řádky a čtyři sloupce, proto je ve jmenovateli Cramérova koeficientu faktor $m-1=3$:

```r
V_prijem <- sqrt(test_prijem$statistic / (sum(tab_prijem) * 3))
V_prijem
```

```text
X-squared 
0.2131091 
```

Nejmenší očekávaná četnost je $7{,}5$, všechny jsou tedy nad 5. Pro přibližný test jsou dostatečně velké.
Předpokládáme také, že pozorování jednotlivých domácností jsou navzájem nezávislá.
Při $\chi^2 = 32{,}699$ a $9$ stupních volnosti vychází $p = 0{,}0001507 < 0{,}05$: $H_0$ zamítáme.
Mezi příjmovou skupinou a převažujícím způsobem financování se prokázala statisticky významná závislost.
Hodnota $V = 0{,}213$ ukazuje, že vztah je slabý.

Z řádkových podílů vidíme, jak se financování mezi skupinami liší. Podíl domácností,
které větší nákupy hradí převážně z vlastních úspor, roste od $30\,\%$ v nejnižší skupině
přes $40\,\%$ a přibližně $56{,}7\,\%$ až na $70\,\%$ v nejvyšší skupině. Spotřebitelský úvěr
naopak převažuje u přibližně $33{,}3\,\%$ nejnižší skupiny a $8{,}3\,\%$ nejvyšší skupiny.
Jde o souvislost v průzkumu; test sám neprokazuje, že změna příjmu způsobuje změnu financování.

## Velikost podniku a využívání umělé inteligence

U 221 podniků byla zaznamenána velikost a četnost využívání nástrojů umělé inteligence při administrativních
činnostech: pravidelně, příležitostně nebo vůbec. Na hladině $\alpha = 0{,}05$ posoudíme, zda využívání AI
souvisí s velikostí podniku. Tabulka četností ukáže počty podniků a řádkové relativní četnosti umožní
porovnat podíly mezi velikostními skupinami. Sílu vztahu vyjádříme Cramérovým $V$ a zkontrolujeme předpoklady testu.

$H_0$: velikost podniku a četnost využívání AI jsou nezávislé. $H_1$: znaky jsou závislé.

```r
tab_ai <- matrix(c(23, 20, 14,
                   17, 25, 20,
                   20, 11, 13,
                   29, 10, 19),
                 nrow = 4, byrow = TRUE,
                 dimnames = list(
                   podnik = c("mikro", "maly", "stredni", "velky"),
                   AI = c("pravidelne", "prilezitostne", "vubec")))
tab_ai
```

```text
         AI
podnik    pravidelne prilezitostne vubec
  mikro           23            20    14
  maly            17            25    20
  stredni         20            11    13
  velky           29            10    19
```

```r
round(prop.table(tab_ai, 1), 4)
```

```text
         AI
podnik    pravidelne prilezitostne  vubec
  mikro       0.4035        0.3509 0.2456
  maly        0.2742        0.4032 0.3226
  stredni     0.4545        0.2500 0.2955
  velky       0.5000        0.1724 0.3276
```

```r
test_ai <- chisq.test(tab_ai)
test_ai
test_ai$expected
```

```text
	Pearson's Chi-squared test

data:  tab_ai
X-squared = 11.254, df = 6, p-value = 0.08083

         AI
podnik    pravidelne prilezitostne    vubec
  mikro     22.95475      17.02262 17.02262
  maly      24.96833      18.51584 18.51584
  stredni   17.71946      13.14027 13.14027
  velky     23.35747      17.32127 17.32127
```

Tabulka má čtyři řádky a tři sloupce, takže $m-1=2$:

```r
V_ai <- sqrt(test_ai$statistic / (sum(tab_ai) * 2))
V_ai
```

```text
X-squared 
0.1595679 
```

Všechny očekávané četnosti jsou nad 5; nejmenší je přibližně $13{,}14$. Pro přibližný test jsou dostatečně velké.
Předpokládáme také, že jednotlivé podniky představují nezávislá pozorování.
Při $\chi^2 = 11{,}254$ a $6$ stupních volnosti vychází $p = 0{,}08083 > 0{,}05$: $H_0$ nezamítáme.
Na pětiprocentní hladině se závislost mezi velikostí podniku a četností využívání AI neprokázala;
tento výsledek nepotvrzuje nezávislost znaků.

V naměřených datech využívá AI pravidelně $50\,\%$ velkých podniků a přibližně $27{,}4\,\%$ malých podniků.
Rozdíl tedy ve výběru vidíme, ale test ho na zvolené hladině nevyhodnotil jako statisticky významný.
Hodnota $V = 0{,}160$ popisuje slabý vztah v tomto výběru; výsledek testu nezávislosti tím nemění.

## Čtyřpolní tabulka

Pokud mají oba znaky $A$ i $B$ jen dvě varianty, vznikne **čtyřpolní tabulka**
($r = s = 2$):

| $A \backslash B$ | $B_1$ | $B_2$ | $n_{i\bullet}$ |
|---|---|---|---|
| $A_1$ | $n_{11}$ | $n_{12}$ | $n_{1\bullet}$ |
| $A_2$ | $n_{21}$ | $n_{22}$ | $n_{2\bullet}$ |
| $n_{\bullet j}$ | $n_{\bullet 1}$ | $n_{\bullet 2}$ | $n$ |

Pro $n > 40$ se místo obecného vzorce používá zjednodušená varianta testového kritéria:

$$
\chi^2 = n\,\frac{(n_{11}n_{22} - n_{12}n_{21})^2}{n_{1\bullet}n_{2\bullet}n_{\bullet 1}n_{\bullet 2}}
$$

s kritickým oborem $W_\alpha = \{\chi^2 : \chi^2 \ge \chi^2_{1-\alpha}(1)\}$. Je to stejný test nezávislosti,
jen zjednodušený pro $(r-1)(s-1) = 1$ stupeň volnosti. Stejnou hodnotu v R získáme příkazem
`chisq.test(tab, correct = FALSE)`. Bez `correct = FALSE` R u tabulky 2 × 2 použije Yatesovu korekci
na kontinuitu, tedy úpravu výpočtu, která dává menší testové kritérium.

## McNemarův test

U stejných lidí můžeme zjistit odpověď ano/ne před informační kampaní a potom znovu po ní.
Každý člověk tak poskytuje dvojici odpovědí: máme **párová data**. Nesledujeme dva různé znaky jako vzdělání
a způsob nákupu, ale tentýž alternativní znak ve dvou měřeních.

**McNemarův test** posuzuje, zda se mezi měřeními změnily podíly obou odpovědí. Využívá přitom informaci,
kteří lidé odpověď změnili a kterým směrem.

Kontingenční tabulka před/po má tvar:

| před \ po | + | − | $n_{i\bullet}$ |
|---|---|---|---|
| + | $n_{11}$ | $n_{12}$ | $n_{1\bullet}$ |
| − | $n_{21}$ | $n_{22}$ | $n_{2\bullet}$ |
| $n_{\bullet j}$ | $n_{\bullet 1}$ | $n_{\bullet 2}$ | $n$ |

Pole $n_{11}$ a $n_{22}$ obsahují lidi, kteří odpověď nezměnili; označujeme je jako **shodná**.
Pole $n_{12}$ a $n_{21}$ obsahují změny v opačných směrech, a proto jsou **diskordantní neboli neshodná**.
Jen tato pole rozhodují o výsledku testu: porovnáváme, zda přechodů jedním směrem je výrazně více než druhým.

![[mask-kt-mcnemar-tabulka.png|2×2 tabulka McNemarova testu s počty 24, 68, 28, 50; diskordantní pole b = n12 a c = n21 jsou zvýrazněna červeně, shodná pole n11 a n22 fialově]]

**Postup testu:**

1. $H_0: p_{12} = p_{21}$ — pravděpodobnost přechodu z varianty (+) do (−) je stejná jako pravděpodobnost
   přechodu z (−) do (+). Podíly variant se tedy mezi měřeními nemění.
2. Testové kritérium

   $$
   \chi^2 = \frac{(n_{12} - n_{21})^2}{n_{12} + n_{21}}
   $$

   má přibližně Pearsonovo rozdělení o $1$ stupni volnosti.
3. Kritický obor: $W = \{\chi^2 : \chi^2 \ge \chi^2_{1-\alpha}(1)\}$.
4. Leží-li testové kritérium v $W$, zamítáme $H_0$ ve prospěch $H_1$: podíly variant se mezi měřeními změnily.

V R použijeme funkci `mcnemar.test()`. Argumentem `correct = FALSE` vypneme korekci na kontinuitu,
aby výpočet odpovídal vzorci výše.

> [!example] Příklad: informační kampaň a zveřejňování na Facebooku
> U 170 studentů bylo zjišťováno, zda zveřejňují své údaje na Facebooku. Poté proběhla informační kampaň o
> rizicích zveřejňování a zjišťování se opakovalo. Posuďte, zda se podíl zveřejňujících studentů mezi měřeními změnil.
>
> Závěr vztahujeme ke studentům jako základnímu souboru. Výběr tvoří studenti, u nichž máme obě měření.
> Sledovaným znakem je zveřejňování údajů (ano / ne).
>
> | před \ po | nezveřejňuje | zveřejňuje | $n_{i\bullet}$ |
> |---|---|---|---|
> | nezveřejňuje | 24 | 68 | 92 |
> | zveřejňuje | 28 | 50 | 78 |
> | $n_{\bullet j}$ | 52 | 118 | 170 |
>
> $H_0: p_{12} = p_{21}$ — podíl zveřejňujících studentů je před kampaní a po ní stejný.

```r
tab3 <- matrix(c(24, 68,
                 28, 50),
               nrow = 2, byrow = TRUE,
               dimnames = list(
                 pred = c("nezverejnuje", "zverejnuje"),
                 po   = c("nezverejnuje", "zverejnuje")))
mcnemar.test(tab3, correct = FALSE)
```

```text
	McNemar's Chi-squared test

data:  tab3
McNemar's chi-squared = 16.667, df = 1, p-value = 4.456e-05
```

P-hodnota $0{,}00004456 < 0{,}05$ vede k zamítnutí $H_0$ ve prospěch $H_1$.
Podíl zveřejňujících studentů se mezi měřeními statisticky významně změnil.
Samotné porovnání před kampaní a po ní ale neprokazuje, že změnu způsobila právě kampaň.

## Časté chyby

> [!warning] Test nezávislosti místo testu změny u párových dat
> Stejná tabulka může svádět k použití `chisq.test()`. Ten by ale zkoumal, zda odpověď před kampaní
> souvisí s odpovědí po ní. McNemarův test zjišťuje, zda se změnil podíl zveřejňujících studentů.
> Jsou to různé otázky, a proto mohou testy na stejné tabulce vést k různým výsledkům.

```r
chisq.test(tab3)
```

```text
	Pearson's Chi-squared test with Yates' continuity correction

data:  tab3
X-squared = 1.4793, df = 1, p-value = 0.2239
```

P-hodnota $0{,}224 > 0{,}05$ znamená, že nezamítáme hypotézu nezávislosti odpovědí před kampaní a po ní.
O změně podílu zveřejňujících tento výsledek nerozhoduje. K ní patří výše použitý `mcnemar.test()`.

> [!warning] Výchozí korekce na kontinuitu v `mcnemar.test()`
> Pokud argument `correct` nezadáme, R provede výpočet s Yatesovou korekcí na kontinuitu.
> Proto dostaneme jinou p-hodnotu než podle vzorce uvedeného výše.

```r
mcnemar.test(tab3)
```

```text
	McNemar's Chi-squared test with continuity correction

data:  tab3
McNemar's chi-squared = 15.844, df = 1, p-value = 6.879e-05
```

Místo nekorigované hodnoty $p = 0{,}00004456$ dostaneme $p = 0{,}00006879$. Zde se rozhodnutí nemění.
Kdyby ale p-hodnota ležela blízko hranice $\alpha$, korekce by ho změnit mohla.
Pro výpočet podle nekorigovaného vzorce použijeme `mcnemar.test(x, correct = FALSE)`.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[testovani-hypotez|Testování statistických hypotéz]]
- [[popisna-statistika|Popisná statistika a datové soubory]]
- [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]]
- [[regresni-a-korelacni-analyza|Regresní a korelační analýza]]
- [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]]
- [[mask-r-tahak|Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.
