---
title: "Popisná statistika a datové soubory"
course: mask
type: topic
tags: [mask, statistika, popisna-statistika, histogram, kvantily, r]
sources: [raw/mask/02 datové soubory.pdf, raw/mask/02 datové soubory - návod R.pdf, raw/mask/příklady 01 a 02.docx, raw/mask/data k příkladům/4.txt, raw/mask/data k příkladům/5.txt, raw/mask/data k příkladům/6.txt, raw/mask/data k příkladům/9.txt]
created: 2026-10-02
updated: 2026-10-02
---

# Popisná statistika a datové soubory

> [!tldr] V kostce
> - Rozlišit základní a výběrový soubor, typ statistického znaku (kvantitativní/kvalitativní, diskrétní/spojitý) a požadavek reprezentativity a nezávislého výběru.
> - Spočítat výběrový průměr, rozptyl, směrodatnou odchylku a variační rozpětí; interpretovat je jako bodové odhady charakteristik náhodné veličiny.
> - Určit medián a kvartily a číst empirickou distribuční funkci $F_n(x)$.
> - Roztřídit velký datový soubor do tříd (intervalové rozdělení četností), sestavit tabulku $I_j, Z_j, f_j, p_j$ a nakreslit histogram.
> - Z histogramu odhadnout zákon rozdělení dat; formální test shody patří do testování hypotéz.

## Základní pojmy

[[mask|Metody aplikované statistiky]] pracuje s **datovými soubory** — konkrétními hodnotami, které popisují vlastnost zkoumaných prvků.

- **Základní soubor** — množina prvků, na nichž provádíme šetření (např. všichni výdělečně činní obyvatelé ČR).
- **Statistický znak** — funkce, která vyjadřuje určitou vlastnost prvku (např. velikost platu). Znaky dělíme na:
  - **kvantitativní** (vyjádřitelné číslem) — dále **diskrétní** (spočetně mnoho hodnot) nebo **spojité** (libovolná hodnota v intervalu);
  - **kvalitativní** (vyjádřitelné slovně).
- **Výběrový soubor** — podmnožina prvků základního souboru, na níž znak skutečně zjišťujeme (např. 5 náhodně vybraných obyvatel).
- **Datový soubor** — n-tice naměřených hodnot zkoumaného znaku, např. $(29\,500,\ 38\,000,\ 37\,800,\ 41\,000,\ 31\,200)$.
- Podle počtu sledovaných znaků rozlišujeme **jednorozměrné**, **dvourozměrné** a **vícerozměrné** datové soubory.

![[mask-ilu-zakladni-soubor-vyber.png|Základní soubor s neznámými parametry μ a σ², z něhož náhodný výběr n prvků dává výběrové charakteristiky x̄ a s²; zpětná šipka statistické indukce vede od výběru k odhadům a testům o základním souboru]]

Aby výběrový soubor dobře vypovídal o základním souboru, měl by být **reprezentativní** (podobný základnímu souboru svým složením). Není-li to možné zajistit přímo, volí se prvky do výběru náhodně — **nezávislý výběr**. Bez náhodnosti výběru nelze vlastnosti základního souboru správně vystihnout.

## Empirické charakteristiky

Zpracováním datového souboru získáme **empirické charakteristiky** a odhad **zákona rozdělení** zkoumané náhodné veličiny $X$. Jde o **bodové odhady** charakteristik $X$; ruční výpočet podle vzorců níže je potřeba jen bez dostupného softwaru.

**Míry polohy**

$$\bar{x} = \frac{1}{n}\sum_{i=1}^{n} x_i \qquad \text{(výběrový průměr)}$$

Dalšími mírami polohy jsou **medián** a **modus** (nejčetnější hodnota výběru).

**Míry variability**

$$s^2 = \frac{1}{n-1}\left(\sum_{i=1}^{n} x_i^2 - n\bar{x}^2\right), \qquad s=\sqrt{s^2} \qquad \text{(výběrový rozptyl, směrodatná odchylka)}$$

$$R = x_{\max} - x_{\min} \qquad \text{(variační rozpětí)}$$

**Kvantily**

Kvantil $\tilde{x}_p$ dělí hodnoty datového souboru na dvě části: $100p\,\%$ hodnot je menších nebo rovných $\tilde{x}_p$, zbylých $100(1-p)\,\%$ je větších. Nejdůležitější kvantily:

- **medián** $\tilde{x}_{0{,}5}$ — pro lichý počet prvků uspořádaného souboru prostřední prvek, pro sudý počet průměr dvou prostředních prvků;
- **dolní kvartil** $\tilde{x}_{0{,}25}$ a **horní kvartil** $\tilde{x}_{0{,}75}$.

Datový soubor se do R zadává buď přímo (`x <- c(...)`), nebo načtením ze souboru:

```r
x <- c(4.1, 4.0, 3.8, 3.9, 3.8, 3.8, 3.5, 3.7, 4.0, 4.0)   # přímé zadání hodnot
# x <- read.table("data.txt")[, 1]                       # načtení prvního sloupce ze souboru
```

Řádek s načtením ze souboru je zakomentovaný znakem `#`: soubor musí ležet v pracovním adresáři R. `read.table()` vrací datovou tabulku (`data.frame`), proto `[, 1]` vybere její první sloupec jako vektor.

V R:

```r
x <- c(11.1, 12.7, 10.8, 13.2, 12.7, 13.4, 12.7, 14.4, 14.7, 14.4)
length(x)
mean(x)
var(x)
sd(x)
min(x); max(x); max(x) - min(x)
quantile(x, 0.5, type = 6)
quantile(x, 0.25, type = 6)
quantile(x, 0.75, type = 6)
```

```text
[1] 10
[1] 13.01
[1] 1.747667
[1] 1.321993
[1] 10.8
[1] 14.7
[1] 3.9
  50% 
12.95 
 25% 
12.3 
 75% 
14.4 
```

`quantile(x, p, type = 6)` je potřeba zadat explicitně — výchozí typ v R (`type = 7`) by u některých souborů dal mírně odlišné hodnoty kvantilů než ruční výpočet použitý v této kapitole.

![[mask-ps-kvantily.png|Naměřené doby opravy součástky na číselné ose s krabicí mezi kvartily a vyznačeným mediánem 12,95, dolním kvartilem 12,30 a horním kvartilem 14,40 minuty]]

Seřazení souboru a krabicový graf:

```r
sort(x)                     # vzestupně
sort(x, decreasing = TRUE)  # sestupně
boxplot(x)
```

```text
 [1] 10.8 11.1 12.7 12.7 12.7 13.2 13.4 14.4 14.4 14.7
 [1] 14.7 14.4 14.4 13.4 13.2 12.7 12.7 12.7 11.1 10.8
```

`boxplot()` kreslí krabici mezi hodnotami `fivenum(x)` (zde 12,7 a 14,4), které se od kvartilů typu 6 mohou mírně lišit.

> [!example] Příklad: Empirické charakteristiky
> Na deseti náhodně vybraných mechanicích byla měřena doba opravy vadné součástky (v minutách):
> 11,1  12,7  10,8  13,2  12,7  13,4  12,7  14,4  14,7  14,4.
> Určete empirické charakteristiky a kvantily.

Výstup R kódu výše dává $\bar{x}=13{,}01$, $s^2=1{,}75$, $s=1{,}32$, $R=3{,}9$, medián $\tilde{x}_{0{,}5}=12{,}95$, dolní kvartil $12{,}3$, horní kvartil $14{,}4$.

Odhad střední doby opravy je přibližně 13 minut, odhad směrodatné odchylky přibližně 1,32 minuty. Odchylka je vzhledem k průměru nízká — data kolísají kolem průměru jen málo. Uspořádaný soubor má medián 12,95: polovina oprav trvala méně, polovina více; 25 % oprav bylo kratších než 12,3 minuty a 75 % kratších než 14,4 minuty.

> [!example] Příklad: Doba oprav televizorů
> Při 50 opravách určité závady televizoru byly naměřeny časy (v minutách). Určete empirické charakteristiky.

```r
x6 <- c(44, 40.2, 41.9, 43.4, 42.8, 42.3, 43.2, 45, 41.5, 42.7,
        43.9, 40.1, 43.3, 41.1, 42.5, 42.4, 41.4, 40.8, 42, 44.7,
        41.2, 41.9, 42.4, 44.4, 40.5, 39.7, 41.1, 41, 41.9, 40.8,
        43, 42.8, 42.9, 42.7, 43.3, 42.2, 39.2, 41.5, 41.6, 42.7,
        45, 42.3, 43.6, 43.2, 38.8, 43, 44.2, 43, 40, 44.4)
length(x6)
mean(x6)
sd(x6)
max(x6) - min(x6)
median(x6)
```

```text
[1] 50
[1] 42.27
[1] 1.48052
[1] 6.2
[1] 42.4
```

Průměrná doba opravy je 42,27 minuty se směrodatnou odchylkou 1,48 minuty a mediánem 42,4 minuty; průměr a medián téměř splývají, data jsou kolem středu rozložena souměrně.

## Empirická distribuční funkce

Pro libovolný rozsah datového souboru, diskrétní i spojitou náhodnou veličinu $X$, lze sestrojit **empirickou distribuční funkci** $F_n(x)$. Pro datový soubor $(x_1,\dots,x_n)$ je

$$F_n(x) = \frac{k}{n},$$

kde $k$ je počet prvků datového souboru menších nebo rovných číslu $x$.

V R:

```r
f <- ecdf(x)
knots(f)        # vzestupně seřazené různé hodnoty datového souboru
f(knots(f))      # hodnoty Fn(x) v těchto bodech
f(13)            # Fn v libovolném bodě
plot(f)
```

```text
[1] 10.8 11.1 12.7 13.2 13.4 14.4 14.7
[1] 0.1 0.2 0.5 0.6 0.7 0.9 1.0
[1] 0.5
```

`knots()` vrací jen různé hodnoty (opakující se hodnota 12,7 je ve výpočtu $F_n$ započtena třikrát, v seznamu uzlů je ale jen jednou); `plot(f)` nakreslí schodovitý graf, který v každém uzlu skáče o $k$-násobek $1/n$.

![[mask-ps-ecdf.png|Empirická distribuční funkce jako schodová čára: vlevo doba opravy součástky se sedmi schody po 0,1 až 0,3, vpravo odpad materiálu s podobným tvarem]]

> [!example] Příklad: Empirická distribuční funkce
> Pro předchozí datový soubor (doba opravy součástky) určete empirickou distribuční funkci.

Uspořádaný soubor je $10{,}8;\ 11{,}1;\ 12{,}7;\ 12{,}7;\ 12{,}7;\ 13{,}2;\ 13{,}4;\ 14{,}4;\ 14{,}4;\ 14{,}7$.

| $x$ | 10,8 | 11,1 | 12,7 | 13,2 | 13,4 | 14,4 | 14,7 |
|---|---|---|---|---|---|---|---|
| $k$ | 1 | 2 | 5 | 6 | 7 | 9 | 10 |
| $F_n(x)$ | 0,1 | 0,2 | 0,5 | 0,6 | 0,7 | 0,9 | 1,0 |

Graf (levý panel výše) odpovídá tabulce: funkce je nulová pod 10,8, skáče o $1/n = 0{,}1$ v každé jednoduché hodnotě a o $3/n = 0{,}3$ v bodě 12,7, kde se hodnota opakuje třikrát.

> [!example] Příklad: Odpad materiálu
> Na deseti obráběných kusech byly naměřeny hodnoty odpadu materiálu (v %):
> 4,1  4,0  3,8  3,9  3,8  3,8  3,5  3,7  4,0  4,0.
> Určete empirické charakteristiky a nakreslete empirickou distribuční funkci.

```r
x4 <- c(4.1, 4.0, 3.8, 3.9, 3.8, 3.8, 3.5, 3.7, 4.0, 4.0)
length(x4)
mean(x4)
sd(x4)
max(x4) - min(x4)
median(x4)
f4 <- ecdf(x4)
knots(f4)
f4(knots(f4))
```

```text
[1] 10
[1] 3.86
[1] 0.1776388
[1] 0.6
[1] 3.85
[1] 3.5 3.7 3.8 3.9 4.0 4.1
[1] 0.1 0.2 0.5 0.6 0.9 1.0
```

Průměrný odpad je 3,86 % se směrodatnou odchylkou 0,18 % a mediánem 3,85 %. Pravý panel obrázku výše ukazuje tvar $F_n(x)$: hodnota 3,8 se v souboru opakuje třikrát, proto zde funkce skáče o 0,3 najednou, stejně jako hodnota 4,0.

## Třídění datového souboru do tříd

Je-li rozsah datového souboru velký (řádově přes 30 až 50 pozorování), hodnoty se před dalším zpracováním **roztřídí**: variační rozpětí $R$ se rozdělí na určitý počet **tříd** (intervalů) a zjistí se, kolik hodnot do které třídy padne. Na počet ani šířku tříd neexistuje obecný předpis — počet by neměl být ani příliš malý, ani příliš velký.

Výsledkem je tabulka četností se sloupci:

- $I_j$ — $j$-tý interval (v této kapitole vždy zleva uzavřený a zprava otevřený, $I_j = \langle c_j; c_{j+1})$),
- $Z_j$ — střed (reprezentant) intervalu,
- $f_j$ — četnost, počet hodnot v intervalu,
- $p_j = f_j/n$ — relativní četnost, přičemž $\sum_j f_j = n$ a $\sum_j p_j = 1$.

V R se třídění provádí příkazem `hist()` — buď necháme R zvolit třídy samo (`hist(x)`), nebo zadáme hranice přímo (`hist(x, br = seq(0, 550, by = 50))`). Uložením výsledku do proměnné (`y <- hist(...)`) získáme jednotlivé sloupce tabulky: `y$counts` ($f_j$), `y$breaks` (hranice tříd), `y$mids` ($Z_j$) a `y$density` (relativní četnosti na škále hustoty).

Interval $I_j$ je ve výchozím nastavení `hist()` zleva otevřený a zprava uzavřený, $(c_j; c_{j+1}\rangle$ — opačně, než jak třídy zapisujeme v této kapitole. Parametr `right = FALSE` třídy obrátí na $\langle c_j; c_{j+1})$.

![[mask-ps-histogram-trideni.png|Sloupcový histogram četností doby do poruchy výrobku s 11 třídami po 50 minutách, četnosti klesají z 19 na nulu s ojedinělými výkyvy u 300 a 500 minut]]

> [!example] Příklad: Třídění datového souboru
> Byly provedeny zkoušky životnosti nového výrobku. Datový soubor obsahuje 68 hodnot doby do poruchy (v minutách). Určete odhady charakteristik a zákona rozdělení.

```r
x9 <- c(101, 338, 150, 47, 10, 2, 12, 392, 5, 73,
        367, 54, 114, 213, 71, 341, 313, 112, 343, 151,
        9, 160, 18, 113, 77, 71, 159, 12, 119, 130,
        140, 161, 379, 54, 373, 168, 365, 110, 145, 88,
        74, 46, 246, 259, 19, 119, 48, 3, 163, 179,
        194, 33, 49, 501, 193, 19, 5, 2, 221, 300,
        88, 13, 428, 249, 25, 209, 54, 91)
length(x9)
max(x9) - min(x9)
y9 <- hist(x9, br = seq(0, 550, by = 50), right = FALSE, plot = FALSE)
y9$counts
round(y9$counts / length(x9), 3)
mean(x9); sd(x9)
```

```text
[1] 68
[1] 499
 [1] 19 11 10 10  5  1  5  5  1  0  1
 [1] 0.279 0.162 0.147 0.147 0.074 0.015 0.074 0.074 0.015 0.000 0.015
[1] 145.4412
[1] 126.1283
```

Variační rozpětí je $R = 501 - 2 = 499$ minut; rozdělit je na 11 tříd po 50 minutách je rozumná volba (ani moc málo, ani moc tříd). Výsledná tabulka četností:

| $j$ | $I_j$ | $Z_j$ | $f_j$ | $p_j$ |
|---|---|---|---|---|
| 1 | ⟨0; 50) | 25 | 19 | 0,279 |
| 2 | ⟨50; 100) | 75 | 11 | 0,162 |
| 3 | ⟨100; 150) | 125 | 10 | 0,147 |
| 4 | ⟨150; 200) | 175 | 10 | 0,147 |
| 5 | ⟨200; 250) | 225 | 5 | 0,074 |
| 6 | ⟨250; 300) | 275 | 1 | 0,015 |
| 7 | ⟨300; 350) | 325 | 5 | 0,074 |
| 8 | ⟨350; 400) | 375 | 5 | 0,074 |
| 9 | ⟨400; 450) | 425 | 1 | 0,015 |
| 10 | ⟨450; 500) | 475 | 0 | 0,000 |
| 11 | ⟨500; ∞) | 525 | 1 | 0,015 |

Asi 27,9 % výrobků vydrželo méně než 50 minut, jen asi 1,5 % mezi 250 a 300 minutami. Charakteristiky spočtené ze středů tříd $Z_j$ (vážený průměr a rozptyl se střední hodnotou nahrazenou $Z_j$) vycházejí $\bar{x} \approx 149{,}26$, $s^2 \approx 15\,484{,}5$, $s \approx 124{,}44$ — blízko hodnotám $\bar{x}=145{,}44$, $s=126{,}13$ spočteným přímo z nerozdělených dat; malý rozdíl vzniká tím, že třídění nahrazuje skutečné hodnoty středy tříd.

Tvar histogramu — vysoká četnost u krátkých dob, rychlý pokles — odpovídá **exponenciálnímu rozdělení**, které se pro dobu do poruchy používá nejčastěji. Jeho hustota je $f(x) = \lambda e^{-\lambda x}$ pro $x \ge 0$, s parametrem $\lambda$ odhadnutým jako $\lambda = 1/\bar{x}$ (v R je `rate` parametrem `dexp()`):

```r
rate9 <- 1 / mean(x9)
rate9
```

```text
[1] 0.006875632
```

![[mask-ps-hustota-fit.png|Histogram doby do poruchy na škále hustoty s proloženou klesající exponenciální křivkou s rychlostí 0,0069]]

Proložená křivka dobře sleduje tvar sloupců. Zda data odpovídají exponenciálnímu rozdělení formálně, posuzuje test dobré shody popsaný v [[testovani-hypotez|Testování statistických hypotéz]].

> [!example] Příklad: Doba života výrobku
> Sledováním doby života výrobku bylo naměřeno 50 hodnot (v minutách). Určete empirické charakteristiky, roztřiďte datový soubor a nakreslete histogram četností.

```r
x5 <- c(63, 156, 184, 786, 822, 278, 15, 561, 229, 8,
        4, 35, 73, 203, 178, 323, 275, 176, 427, 196,
        415, 140, 17, 293, 991, 100, 189, 176, 672, 134,
        529, 310, 22, 69, 130, 272, 117, 169, 466, 286,
        46, 236, 387, 92, 177, 188, 124, 385, 174, 23)
length(x5)
mean(x5); sd(x5); median(x5)
max(x5) - min(x5)
y5 <- hist(x5, br = seq(0, 1050, by = 150), right = FALSE, plot = FALSE)
y5$mids
y5$counts
round(y5$counts / length(x5), 3)
```

```text
[1] 50
[1] 246.42
[1] 220.0209
[1] 181
[1] 987
[1]   75 225 375 525 675 825 975
[1] 18 19  6  3  1  2  1
[1] 0.36 0.38 0.12 0.06 0.02 0.04 0.02
```

Variační rozpětí 987 minut rozdělené do 7 tříd po 150 minutách dává podobný tvar jako u předchozího příkladu: 74 % výrobků vydrželo méně než 300 minut, ojedinělé hodnoty sahají až k 991 minutám. Průměr 246,4 minuty leží výrazně nad mediánem 181 minut — rozdělení je zešikmené k vyšším hodnotám stejně jako u doby do poruchy výše.

## Časté chyby

- **Výchozí typ kvantilu v R.** `quantile()` bez argumentu `type` používá jiný výpočetní vzorec (`type = 7`) než ruční postup v této kapitole — u některých souborů se hodnoty liší. Pro shodu s ručním výpočtem zadávejte `quantile(x, p, type = 6)`.
- **Výchozí ohraničení tříd v `hist()`.** Bez `right = FALSE` jsou třídy zprava uzavřené, $(c_j; c_{j+1}\rangle$ — opačně než konvence $\langle c_j; c_{j+1})$ použitá v tabulkách výše. Hodnota ležící přesně na hranici pak spadne do jiné třídy a četnosti $f_j$ vyjdou jinak.
- **Rozptyl vs. směrodatná odchylka.** $s^2$ se udává v jednotkách znaku na druhou, $s$ ve stejných jednotkách jako data — pro interpretaci (např. „kolísání kolem průměru") patří vždy $s$, ne $s^2$.
- **Příliš mnoho nebo příliš málo tříd.** Málo tříd skryje tvar rozdělení, moc tříd rozmělní četnosti na jednotky a histogram je nečitelný; volí se kompromis, ne pevné pravidlo.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]]
- [[testovani-hypotez|Testování statistických hypotéz]]
- [[regresni-a-korelacni-analyza|Regresní a korelační analýza]]
- [[kontingencni-tabulky|Kontingenční tabulky]]
- [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]]
- [[mask-r-tahak|Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.
