---
title: "Kontingenční tabulky"
course: mask
type: topic
tags: [mask, statistika, kontingencni-tabulka, chi-kvadrat-test, mcnemaruv-test, r]
sources: [raw/mask/05 kontingenční tabulky.pdf, raw/mask/příklady 04 a 05.docx]
created: 2026-10-02
updated: 2026-10-02
---

# Kontingenční tabulky

> [!tldr] V kostce
> - Kontingenční tabulka zaznamenává **simultánní četnosti** dvou kvalitativních znaků naměřených na stejném souboru.
> - **Test nezávislosti** srovnává pozorované četnosti s očekávanými za platnosti $H_0$ pomocí statistiky $\chi^2$; rozhoduje kritický obor $W$, prakticky p-hodnota.
> - Aproximace $\chi^2$ rozdělením platí jen tehdy, když jsou očekávané četnosti dostatečně velké — proto se vždy kontrolují.
> - Zamítnutí $H_0$ samo o sobě neříká, jak silná závislost je — na to slouží **Cramérův koeficient kontingence** $V$.
> - **Čtyřpolní tabulka** (2×2) je speciální případ s vlastním zjednodušeným vzorcem pro $n>40$.
> - Pro **párová data** (stejné prvky měřené dvakrát, např. před/po zásahu) se používá **McNemarův test**, ne obyčejný test nezávislosti.

## Kontingenční tabulka

V rámci [[mask|Metody aplikované statistiky]] navazují kontingenční tabulky na
[[testovani-hypotez|testování statistických hypotéz]]: místo jedné náhodné veličiny teď sledujeme dva
**kvalitativní** (kategoriální) znaky současně a ptáme se, zda spolu souvisí.

Znak je **kvantitativní**, pokud nabývá číselných hodnot (stáří, stav tachometru), a **kvalitativní**
(kategoriální), pokud nabývá slovních variant (vzdělání, kuřák/nekuřák). Kvalitativní znaky dále dělíme na
**alternativní** (dvě varianty, např. vada ano/ne) a **množné** (více než dvě varianty, např. svobodný/rozvedený/ženatý).

Mějme $n$ opakování pokusu, při nichž sledujeme dva kvalitativní znaky $A$ (varianty $A_1,\dots,A_r$) a $B$
(varianty $B_1,\dots,B_s$). Výsledky zapíšeme do **kontingenční tabulky**: v políčku $(i,j)$ je **simultánní
četnost** $n_{ij}$, tedy počet pokusů s variantou $A_i$ zároveň s variantou $B_j$. Řádkové a sloupcové součty
jsou **marginální četnosti**:

$$n_{i\bullet} = \sum_{j=1}^{s} n_{ij}, \qquad n_{\bullet j} = \sum_{i=1}^{r} n_{ij}, \qquad n = \sum_{i=1}^r\sum_{j=1}^s n_{ij}$$

| $A \backslash B$ | $B_1$ | $B_2$ | … | $B_s$ | $n_{i\bullet}$ |
|---|---|---|---|---|---|
| $A_1$ | $n_{11}$ | $n_{12}$ | … | $n_{1s}$ | $n_{1\bullet}$ |
| $A_2$ | $n_{21}$ | $n_{22}$ | … | $n_{2s}$ | $n_{2\bullet}$ |
| ⋮ | ⋮ | ⋮ | ⋱ | ⋮ | ⋮ |
| $A_r$ | $n_{r1}$ | $n_{r2}$ | … | $n_{rs}$ | $n_{r\bullet}$ |
| $n_{\bullet j}$ | $n_{\bullet 1}$ | $n_{\bullet 2}$ | … | $n_{\bullet s}$ | $n$ |

Vydělením četností počtem opakování $n$ dostaneme odhady pravděpodobností:

$$\hat p_{ij} = \frac{n_{ij}}{n}, \qquad \hat p_{i\bullet} = \frac{n_{i\bullet}}{n}, \qquad \hat p_{\bullet j} = \frac{n_{\bullet j}}{n}$$

## Test nezávislosti dvou kvalitativních znaků

Test ověřuje, zda varianty znaku $A$ a varianty znaku $B$ jsou na sobě nezávislé, tedy zda simultánní
pravděpodobnost je součinem marginálních pravděpodobností.

**Postup testu:**

1. $H_0: p_{ij} = p_{i\bullet}\,p_{\bullet j}$ pro všechna $i = 1,\dots,r$, $j = 1,\dots,s$ (znaky jsou na sobě
   nezávislé) proti $H_1$: znaky jsou závislé.
2. Testové kritérium

   $$\chi^2 = \sum_{i=1}^{r}\sum_{j=1}^{s} \frac{(n_{ij} - n\hat p_{ij})^2}{n\hat p_{ij}}, \qquad \hat p_{ij} = \hat p_{i\bullet}\,\hat p_{\bullet j}$$

   má asymptoticky Pearsonovo ($\chi^2$) rozdělení o $(r-1)(s-1)$ stupních volnosti. Hodnota $n\hat p_{ij} = \dfrac{n_{i\bullet}n_{\bullet j}}{n}$ je **očekávaná četnost** políčka $(i,j)$ — četnost, kterou bychom čekali, kdyby $H_0$ platila.
3. Kritický obor: $W = \{\chi^2 : \chi^2 \ge \chi^2_{1-\alpha}((r-1)(s-1))\}$.
4. Padne-li testové kritérium do $W$, zamítáme na hladině $\alpha$ nulovou hypotézu o nezávislosti a přijímáme
   $H_1$; jinak nemáme důvod $H_0$ zamítnout.

V R počítá test i očekávané četnosti funkce `chisq.test()`.

> [!example] Příklad: nákup potravin na internetu a vzdělání
> Testujte hypotézu, zda se vzájemně ovlivňuje zkušenost s nákupem potravin na internetu a vzdělání respondenta
> (n = 385 respondentů).
>
> Základní soubor: respondenti; výběrový soubor: respondenti, kteří odpověděli; měřený znak A: vzdělání, měřený
> znak B: způsob nákupu.
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

```r
tab1 <- matrix(c(4, 13, 12,
                 31, 62, 71,
                 44, 58, 66,
                 3,  9, 12),
               nrow = 4, byrow = TRUE,
               dimnames = list(
                 vzdelani = c("SS bez maturity", "SS s maturitou nebo VOS", "VS", "ZS"),
                 nakup    = c("ano", "ne, ale planuji", "ne, neplanuji")))
chisq.test(tab1)
chisq.test(tab1)$expected
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

Všechny očekávané četnosti jsou nad 5, aproximace je v pořádku. Testové kritérium $\chi^2 = 5{,}49$ s $6$ stupni
volnosti dává p-hodnotu $0{,}483 > 0{,}05$: $H_0$ nezamítáme, závislost mezi zkušeností s nákupem potravin na
internetu a vzděláním respondenta se neprokázala.

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
chisq.test(tab2)
chisq.test(tab2)$expected
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
p-hodnotu $0{,}032 < 0{,}05$: $H_0$ zamítáme — na rozdíl od předchozího příkladu tady vzdělání a zveřejňování
citlivých údajů na Facebooku na sobě **závisí**.

Srovnání pozorovaných a očekávaných četností ukazuje, proč jeden příklad $H_0$ nezamítá a druhý ano — ve druhém
se pozorované sloupce (zejména u ZŠ) systematicky odchylují od očekávaných, v prvním kolísají jen náhodně kolem nich:

![[mask-kt-observed-expected.png|Grupované sloupce pozorovaných a očekávaných četností pro oba příklady: u nákupu potravin se pozorované a očekávané četnosti v každé kategorii téměř shodují, u zveřejňování údajů se u ZŠ výrazně liší]]

Totéž je vidět na rozdělení testového kritéria: u prvního příkladu leží $\chi^2$ hluboko pod kritickou hodnotou,
u druhého uvnitř kritického oboru $W$:

![[mask-kt-chi2-kriticky-obor.png|Hustota χ² rozdělení s vyznačeným kritickým oborem a pozorovanou hodnotou testového kritéria pro nákup potravin (mimo kritický obor) a zveřejňování údajů (uvnitř kritického oboru)]]

## Cramérův koeficient kontingence

Test nezávislosti pouze rozhodne, zda jsou znaky závislé, nebo ne. Sílu závislosti měří **Cramérův koeficient
kontingence**:

$$V = \sqrt{\frac{\chi^2}{n(m-1)}}, \qquad m = \min(r, s)$$

kde $\chi^2$ je hodnota testového kritéria z testu nezávislosti. $V = 0$ odpovídá úplné nezávislosti znaků,
$V = 1$ jejich úplné závislosti.

```r
V1 <- sqrt(as.numeric(chisq.test(tab1)$statistic) / (sum(tab1) * (min(dim(tab1)) - 1)))
V2 <- sqrt(as.numeric(chisq.test(tab2)$statistic) / (sum(tab2) * (min(dim(tab2)) - 1)))
V1
V2
```

```text
[1] 0.08441958
[1] 0.1762822
```

![[mask-kt-cramerovo-v.png|Cramérův koeficient kontingence V pro nákup potravin (0,084) a zveřejňování údajů (0,176) na škále od 0 (úplná nezávislost) do 1 (úplná závislost)]]

U nákupu potravin je $V = 0{,}084$ zanedbatelné — ostatně $H_0$ jsme ani nezamítli. U zveřejňování údajů je $V = 0{,}176$: $H_0$
jsme zamítli, ale samotná závislost je stále slabá.

## Čtyřpolní tabulka

**Čtyřpolní tabulka** je speciální případ kontingenční tabulky, kdy oba znaky $A$ i $B$ mají jen dvě varianty
($r = s = 2$):

| $A \backslash B$ | $B_1$ | $B_2$ | $n_{i\bullet}$ |
|---|---|---|---|
| $A_1$ | $n_{11}$ | $n_{12}$ | $n_{1\bullet}$ |
| $A_2$ | $n_{21}$ | $n_{22}$ | $n_{2\bullet}$ |
| $n_{\bullet j}$ | $n_{\bullet 1}$ | $n_{\bullet 2}$ | $n$ |

Pro $n > 40$ se místo obecného vzorce používá zjednodušená varianta testového kritéria:

$$\chi^2 = n\,\frac{(n_{11}n_{22} - n_{12}n_{21})^2}{n_{1\bullet}n_{2\bullet}n_{\bullet 1}n_{\bullet 2}}$$

s kritickým oborem $W_\alpha = \{\chi^2 : \chi^2 \ge \chi^2_{1-\alpha}(1)\}$ — formálně jde o stejný test
nezávislosti jako výše, jen dosazený do zjednodušeného tvaru pro $(r-1)(s-1) = 1$ stupeň volnosti. V R dává tuto hodnotu `chisq.test(tab, correct = FALSE)`. Bez `correct = FALSE` R u tabulky 2 × 2 použije Yatesovu korekci na kontinuitu a testové kritérium vyjde menší.

## McNemarův test

Čtyřpolní tabulka z předchozí sekce porovnává dva **různé** znaky na stejném souboru. **McNemarův test** řeší
jinou situaci: na prvcích základního souboru se měří **jeden** alternativní znak, a to **dvakrát** — před a po
nějakém zásahu. Cílem je zjistit, zda zásah změnil pravděpodobnostní rozdělení variant tohoto znaku. Jde tedy o
**párová data** (stejné prvky měřené opakovaně), ne o dva nezávisle naměřené znaky.

Kontingenční tabulka před/po má tvar:

| před \ po | + | − | $n_{i\bullet}$ |
|---|---|---|---|
| + | $n_{11}$ | $n_{12}$ | $n_{1\bullet}$ |
| − | $n_{21}$ | $n_{22}$ | $n_{2\bullet}$ |
| $n_{\bullet j}$ | $n_{\bullet 1}$ | $n_{\bullet 2}$ | $n$ |

Pole $n_{11}$ a $n_{22}$ jsou **shodná** (prvek zůstal ve stejné variantě), pole $n_{12}$ a $n_{21}$ jsou
**diskordantní** (prvek mezi měřeními variantu změnil) — jen ta rozhodují o výsledku testu:

![[mask-kt-mcnemar-tabulka.png|2×2 tabulka McNemarova testu s počty 24, 68, 28, 50; diskordantní pole b = n12 a c = n21 jsou zvýrazněna červeně, shodná pole n11 a n22 fialově]]

**Postup testu:**

1. $H_0: p_{12} = p_{21}$ — pravděpodobnost přechodu z varianty (+) do (−) je stejná jako pravděpodobnost
   přechodu z (−) do (+); zásah tedy nemá na rozdělení variant žádný vliv.
2. Testové kritérium

   $$\chi^2 = \frac{(n_{12} - n_{21})^2}{n_{12} + n_{21}}$$

   má asymptoticky Pearsonovo rozdělení o $1$ stupni volnosti.
3. Kritický obor: $W = \{\chi^2 : \chi^2 \ge \chi^2_{1-\alpha}(1)\}$.
4. Padne-li testové kritérium do $W$, zamítáme $H_0$ a přijímáme $H_1$: zásah rozdělení variant změnil.

V R počítá tento test funkce `mcnemar.test()`. Vzorec výše **neobsahuje korekci na kontinuitu** — aby R vrátilo
přesně tuto hodnotu, musí se volat s `correct = FALSE` (viz Časté chyby níže).

> [!example] Příklad: informační kampaň a zveřejňování na Facebooku
> U 170 studentů bylo zjišťováno, zda zveřejňují své údaje na Facebooku. Poté proběhla informační kampaň o
> rizicích zveřejňování a zjišťování se opakovalo. Posuďte, zda měla kampaň vliv na změnu chování studentů.
>
> Základní soubor: všichni studenti; výběrový soubor: vybraní studenti; měřený znak: zveřejňování (ano / ne).
>
> | před \ po | nezveřejňuje | zveřejňuje | $n_{i\bullet}$ |
> |---|---|---|---|
> | nezveřejňuje | 24 | 68 | 92 |
> | zveřejňuje | 28 | 50 | 78 |
> | $n_{\bullet j}$ | 52 | 118 | 170 |
>
> $H_0: p_{12} = p_{21}$ — informační kampaň nemá na chování vliv.

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

P-hodnota $0{,}00004456 < 0{,}05$: $H_0$ zamítáme, přijímáme $H_1$ — informační kampaň měla vliv na změnu
chování studentů ve zveřejňování údajů na Facebooku.

## Časté chyby

> [!warning] Test nezávislosti na párovaných datech
> Tabulka před/po vypadá jako obyčejná kontingenční tabulka, ale `chisq.test()` na ní předpokládá dva nezávislé
> výběry a ignoruje, že jde o tytéž studenty měřené dvakrát. Na datech z předchozího příkladu to vede k úplně
> jinému (a chybnému) závěru.

```r
chisq.test(tab3)
```

```text
	Pearson's Chi-squared test with Yates' continuity correction

data:  tab3
X-squared = 1.4793, df = 1, p-value = 0.2239
```

P-hodnota $0{,}224 > 0{,}05$ by vedla k nezamítnutí $H_0$ — opačný závěr než správný McNemarův test. Na
párovaná data (stejné prvky měřené dvakrát) vždy patří `mcnemar.test()`, nikdy `chisq.test()`.

> [!warning] Výchozí korekce na kontinuitu v `mcnemar.test()`
> Bez argumentu `correct` R ve výchozím nastavení použije Yatesovu korekci na kontinuitu, která dá jinou
> p-hodnotu než nekorigovaný vzorec uvedený výše.

```r
mcnemar.test(tab3)
```

```text
	McNemar's Chi-squared test with continuity correction

data:  tab3
McNemar's chi-squared = 15.844, df = 1, p-value = 6.879e-05
```

Oproti nekorigované hodnotě $p = 0{,}00004456$ vyjde $p = 0{,}00006879$ — v tomto příkladu obě vedou ke
stejnému rozhodnutí, ale u hodnot blíž hranici $\alpha$ by korekce mohla rozhodnutí změnit. Aby R reprodukovalo
nekorigovaný vzorec, je třeba vždy volat `mcnemar.test(x, correct = FALSE)`.

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
