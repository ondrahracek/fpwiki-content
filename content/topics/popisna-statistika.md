---
title: "Popisná statistika a datové soubory"
course: mask
type: topic
tags: [mask, statistika, popisna-statistika, histogram, kvantily, r]
sources: [raw/mask/02 datové soubory.pdf, raw/mask/02 datové soubory - návod R.pdf, raw/mask/příklady 01 a 02.docx, raw/mask/data k příkladům/4.txt, raw/mask/data k příkladům/5.txt, raw/mask/data k příkladům/6.txt, raw/mask/data k příkladům/9.txt]
created: 2026-10-02
updated: 2026-11-06
---

# Popisná statistika a datové soubory

> [!tldr] V kostce
> - Průměr a medián popisují střed naměřených hodnot.
> - Rozptyl a směrodatná odchylka ukazují, jak moc se hodnoty liší.
> - Kvartily pomáhají popsat rozložení seřazených dat.
> - Histogram ukáže tvar dat a oblasti, v nichž se hodnoty vyskytují nejčastěji.

## Základní pojmy

Chceme-li zjistit, jaké jsou platy obyvatel, obvykle nezjišťujeme plat každého z nich. Vybereme část z nich a jejich platy zapíšeme. V tomto postupu rozlišujeme, koho zkoumáme, jakou vlastnost sledujeme a jaké hodnoty jsme získali:

- **Základní soubor** tvoří všechny prvky, o kterých chceme něco zjistit, například všichni výdělečně činní obyvatelé ČR.
- **Statistický znak** je sledovaná vlastnost, například velikost platu. **Kvantitativní znak** vyjadřujeme číslem. Je buď **diskrétní**, s konečným nebo spočetně mnoha možnými hodnotami, nebo **spojitý**, který může nabýt libovolné hodnoty v intervalu. **Kvalitativní znak** vyjadřujeme slovně.
- **Výběrový soubor** tvoří prvky, u nichž vlastnost skutečně zjišťujeme, například 5 náhodně vybraných obyvatel.
- **Datový soubor** je seznam n naměřených hodnot, například platů $(29\,500,\ 38\,000,\ 37\,800,\ 41\,000,\ 31\,200)$.
- Sledujeme-li u každého prvku jediný znak, jde o **jednorozměrný** datový soubor. Při sledování dvou znaků je soubor **dvourozměrný**, při více znacích **vícerozměrný**.

![[mask-ilu-zakladni-soubor-vyber.png|Základní soubor s neznámými parametry μ a σ², z něhož náhodný výběr n prvků dává výběrové charakteristiky x̄ a s²; zpětná šipka statistické indukce vede od výběru k odhadům a testům o základním souboru]]

Z vybraných prvků chceme usuzovat na celý základní soubor. Výběr proto má být **reprezentativní**, tedy podobný celku svým složením. K tomu slouží náhodný výběr. U **nezávislého výběru** navíc výběr jednoho prvku neovlivňuje výběr dalších. Způsob výběru je třeba posoudit dříve, než začneme vypočtené výsledky zobecňovat.

## Empirické charakteristiky

Naměřené hodnoty shrnujeme pomocí průměru, rozptylu a dalších **empirických charakteristik**. Z dat také odhadujeme **rozdělení** náhodné veličiny $X$. Každá vypočtená charakteristika nahrazuje jedním číslem příslušnou neznámou vlastnost $X$, a proto jde o **bodový odhad**. Následující vzorce ukazují, co software při výpočtu dělá.

**Míry polohy** popisují, kolem jakých hodnot se data soustřeďují. Výběrový průměr získáme součtem hodnot a vydělením jejich počtem:

$$\bar{x} = \frac{1}{n}\sum_{i=1}^{n} x_i \qquad \text{(výběrový průměr)}$$

Dalšími mírami polohy jsou **medián**, tedy prostřední hodnota seřazených dat, a **modus**, tedy nejčetnější hodnota výběru.

**Míry variability** popisují, jak moc se hodnoty liší. Rozptyl vychází z jejich odchylek od průměru. Směrodatná odchylka je jeho odmocnina a má stejné jednotky jako data:

$$s^2 = \frac{1}{n-1}\left(\sum_{i=1}^{n} x_i^2 - n\bar{x}^2\right), \qquad s=\sqrt{s^2} \qquad \text{(výběrový rozptyl, směrodatná odchylka)}$$

Rozdíl největší a nejmenší hodnoty se nazývá variační rozpětí:

$$R = x_{\max} - x_{\min} \qquad \text{(variační rozpětí)}$$

**Kvantily**

Po seřazení dat můžeme hledat hranice pro zvolené podíly hodnot. Taková hranice se nazývá **kvantil** $\tilde{x}_p$: $100p\,\%$ hodnot je menších nebo rovných $\tilde{x}_p$ a zbývajících $100(1-p)\,\%$ je větších. Nejčastěji se používají:

- **medián** $\tilde{x}_{0{,}5}$ — pro lichý počet prvků uspořádaného souboru prostřední prvek, pro sudý počet průměr dvou prostředních prvků;
- **dolní kvartil** $\tilde{x}_{0{,}25}$ a **horní kvartil** $\tilde{x}_{0{,}75}$.

Hodnoty lze do R zapsat přímo pomocí `x <- c(...)` nebo načíst ze souboru. Přímé zadání zde ukazuje odpad materiálu na obráběných kusech:

```r
x <- c(4.1, 4.0, 3.8, 3.9, 3.8, 3.8, 3.5, 3.7, 4.0, 4.0)   # přímé zadání hodnot
# x <- read.table("data.txt")[, 1]                       # načtení prvního sloupce ze souboru
```

Řádek začínající znakem `#` se nespouští. Ukazuje alternativní načtení ze souboru v pracovním adresáři R. Funkce `read.table()` načte tabulku s řádky a sloupci, označovanou jako `data.frame`. Zápis `[, 1]` z ní vybere hodnoty prvního sloupce.

> [!example] Příklad: Empirické charakteristiky
> Na deseti náhodně vybraných mechanicích byla měřena doba opravy vadné součástky (v minutách):
> 11,1  12,7  10,8  13,2  12,7  13,4  12,7  14,4  14,7  14,4.
> Určete empirické charakteristiky a kvantily.

Nejprve zadáme naměřené doby opravy:

```r
x <- c(11.1, 12.7, 10.8, 13.2, 12.7, 13.4, 12.7, 14.4, 14.7, 14.4)
```

Počet pozorování, průměr, rozptyl, směrodatnou odchylku, krajní hodnoty, rozpětí a kvantily získáme přímými voláními příslušných funkcí. U kvantilů zde výslovně používáme způsob interpolace `type = 6`:

```r
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

Výpočet `quantile(x, p, type = 6)` určuje kvantily interpolací mezi seřazenými hodnotami podle jejich pořadí. R nabízí více způsobů interpolace. Jeho výchozí nastavení `type = 7` může dát mírně jiné výsledky; pro uvedené hodnoty je proto třeba zadat způsob výpočtu výslovně.

![[mask-ps-kvantily.png|Naměřené doby opravy součástky na číselné ose s krabicí mezi kvartily a vyznačeným mediánem 12,95, dolním kvartilem 12,30 a horním kvartilem 14,40 minuty]]

Příkaz `sort()` vypíše hodnoty v požadovaném pořadí. Krabicový graf pak zobrazí jejich polohu a rozptýlení:

```r
sort(x)                     # vzestupně
sort(x, decreasing = TRUE)  # sestupně
boxplot(x)
```

```text
 [1] 10.8 11.1 12.7 12.7 12.7 13.2 13.4 14.4 14.4 14.7
 [1] 14.7 14.4 14.4 13.4 13.2 12.7 12.7 12.7 11.1 10.8
```

`boxplot()` určuje okraje krabice pomocí `fivenum(x)`. Zde leží na hodnotách 12,7 a 14,4. Je to jiný způsob výpočtu než kvantily typu 6, takže se okraje krabice mohou od vypočtených kvartilů mírně lišit.

Z předchozího výpočtu dostáváme $\bar{x}=13{,}01$, $s^2=1{,}75$, $s=1{,}32$ a $R=3{,}9$. Medián je $\tilde{x}_{0{,}5}=12{,}95$, dolní kvartil $12{,}3$ a horní kvartil $14{,}4$.

Střední dobu opravy odhadujeme přibližně na 13 minut. Směrodatná odchylka přibližně 1,32 minuty ukazuje poměrně malé kolísání vůči průměru. Medián 12,95 leží uprostřed seřazených dob: polovina oprav trvala méně a polovina více. Dolní kvartil vymezuje nejkratších 25 % oprav hranicí 12,3 minuty, horní kvartil vymezuje 75 % oprav hranicí 14,4 minuty.

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

Průměrná doba opravy je 42,27 minuty, směrodatná odchylka 1,48 minuty a medián 42,4 minuty. Blízkost průměru a mediánu zde odpovídá přibližně souměrnému rozložení hodnot kolem středu.

## Empirická distribuční funkce

Z naměřených hodnot náhodné veličiny $X$ můžeme zjistit, jaký podíl pozorování nepřekročil určitou hranici. Tento podíl vyjadřuje **empirická distribuční funkce** $F_n(x)$. Lze ji sestrojit pro diskrétní i spojité veličiny a pro libovolně velký soubor. Pro hodnoty $(x_1,\dots,x_n)$ platí

$$F_n(x) = \frac{k}{n},$$

kde $k$ je počet prvků datového souboru menších nebo rovných číslu $x$.

Funkce `ecdf()` vytvoří tento popis přímo z dat o době opravy:

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

Příkaz `knots()` vypíše různé naměřené hodnoty. Například hodnota 12,7 se ve výpočtu $F_n$ započítá třikrát, ale v tomto seznamu je jen jednou. Příkaz `plot(f)` vykreslí schodovitý graf. Každý schod odpovídá $k$-násobku $1/n$ podle počtu opakování dané hodnoty.

![[mask-ps-ecdf.png|Empirická distribuční funkce jako schodová čára: vlevo doba opravy součástky se sedmi schody po 0,1 až 0,3, vpravo odpad materiálu s podobným tvarem]]

> [!example] Příklad: Empirická distribuční funkce
> Pro předchozí datový soubor (doba opravy součástky) určete empirickou distribuční funkci.

Uspořádaný soubor je $10{,}8;\ 11{,}1;\ 12{,}7;\ 12{,}7;\ 12{,}7;\ 13{,}2;\ 13{,}4;\ 14{,}4;\ 14{,}4;\ 14{,}7$.

| $x$ | 10,8 | 11,1 | 12,7 | 13,2 | 13,4 | 14,4 | 14,7 |
|---|---|---|---|---|---|---|---|
| $k$ | 1 | 2 | 5 | 6 | 7 | 9 | 10 |
| $F_n(x)$ | 0,1 | 0,2 | 0,5 | 0,6 | 0,7 | 0,9 | 1,0 |

Tabulka vysvětluje schody v levém panelu obrázku. Pod 10,8 je funkce nulová, protože tak krátká oprava nebyla naměřena. U hodnoty, která se vyskytla jednou, vzroste o $1/n = 0{,}1$. V bodě 12,7 se opakují tři pozorování, a proto vzroste o $3/n = 0{,}3$.

> [!example] Příklad: Odpad materiálu
> Na deseti obráběných kusech byly naměřeny hodnoty odpadu materiálu (v %):
> 4,1  4,0  3,8  3,9  3,8  3,8  3,5  3,7  4,0  4,0.
> Určete empirické charakteristiky a nakreslete empirickou distribuční funkci.

```r
x4 <- c(4.1, 4.0, 3.8, 3.9, 3.8, 3.8, 3.5, 3.7, 4.0, 4.0)
```

Charakteristiky odpadu a empirickou distribuční funkci získáme v jednom navazujícím výpočtu:

```r
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

Průměrný odpad je 3,86 %, směrodatná odchylka 0,18 % a medián 3,85 %. Pravý panel obrázku ukazuje odpovídající $F_n(x)$. Hodnota 3,8 se vyskytla třikrát, proto funkce v tomto bodě vzroste o 0,3. Stejný skok nastává u hodnoty 4,0.

## Třídění datového souboru do tříd

U většího souboru, řádově přes 30 až 50 pozorování, se jednotlivé hodnoty hůře prohlížejí. Přehlednější je rozdělit variační rozpětí $R$ na intervaly zvané **třídy** a spočítat hodnoty v každé třídě. Počet a šířka tříd ovlivňují, co z dat uvidíme. Příliš málo tříd skryje podrobnosti, příliš mnoho rozmělní četnosti. Jediný obecně vhodný počet neexistuje.

Výsledkem je tabulka četností se sloupci:

- $I_j$ — $j$-tý interval. Zápis $I_j = \langle c_j; c_{j+1})$ zahrnuje levou hranici, ale pravou už ne. Hodnota na společné hranici proto patří až do následující třídy.
- $Z_j$ — střed (reprezentant) intervalu,
- $f_j$ — četnost, počet hodnot v intervalu,
- $p_j = f_j/n$ — relativní četnost, přičemž $\sum_j f_j = n$ a $\sum_j p_j = 1$.

Funkce `hist()` roztřídí data a nakreslí histogram. V zápisu `hist(x)` zvolí hranice sama. Zápis `hist(x, br = seq(0, 550, by = 50))` je zadává přímo. Výsledek lze uložit pomocí `y <- hist(...)` a dále z něj číst: `y$counts` obsahuje četnosti ($f_j$), `y$breaks` hranice tříd, `y$mids` středy ($Z_j$) a `y$density` relativní četnosti přepočtené na šířku tříd.

U hranic intervalu $I_j$ záleží na nastavení funkce. Výchozí `hist()` používá třídy zprava uzavřené, $(c_j; c_{j+1}\rangle$. Nastavení `right = FALSE` použije třídy zleva uzavřené, $\langle c_j; c_{j+1})$, jako v následující tabulce.

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
```

Rozsah souboru, třídění i charakteristiky získáme v jednom navazujícím výpočtu:

```r
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

Variační rozpětí je $R = 501 - 2 = 499$ minut. Zvolených 11 tříd po 50 minutách umožní sledovat, ve kterých intervalech se poruchy soustřeďují. Z výpočtu vznikne tato tabulka četností:

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

Z tabulky vidíme, že asi 27,9 % výrobků vydrželo méně než 50 minut. Mezi 250 a 300 minutami nastalo jen asi 1,5 % poruch. Pokud máme pouze roztříděná data, můžeme každou hodnotu nahradit středem její třídy $Z_j$. Pro průměr a rozptyl pak použijeme středy $Z_j$ vážené četnostmi. Vyjde $\bar{x} \approx 149{,}26$, $s^2 \approx 15\,484{,}5$ a $s \approx 124{,}44$. Výsledky jsou blízko hodnotám $\bar{x}=145{,}44$ a $s=126{,}13$ z původních dat. Rozdíl vznikl tím, že při třídění zanikla informace o přesné poloze hodnot uvnitř intervalů.

Nejvyšší sloupce histogramu jsou u krátkých dob a směrem k delším dobám četnosti rychle klesají. Tento tvar připomíná **exponenciální rozdělení**, používané pro dobu do poruchy. Má hustotu $f(x) = \lambda e^{-\lambda x}$ pro $x \ge 0$. Parametr $\lambda$ odhadneme převrácenou hodnotou průměru, tedy $\lambda = 1/\bar{x}$. V R se tento parametr funkce `dexp()` jmenuje `rate`:

```r
rate9 <- 1 / mean(x9)
rate9
```

```text
[1] 0.006875632
```

![[mask-ps-hustota-fit.png|Histogram doby do poruchy na škále hustoty s proloženou klesající exponenciální křivkou s rychlostí 0,0069]]

Proložená křivka přibližně sleduje tvar sloupců. Obrázek tak pomáhá zvolit možné rozdělení. Jeho shodu s daty dále posuzuje test dobré shody popsaný v [[testovani-hypotez|testování statistických hypotéz]].

> [!example] Příklad: Doba života výrobku
> Sledováním doby života výrobku bylo naměřeno 50 hodnot (v minutách). Určete empirické charakteristiky, roztřiďte datový soubor a nakreslete histogram četností.

```r
x5 <- c(63, 156, 184, 786, 822, 278, 15, 561, 229, 8,
        4, 35, 73, 203, 178, 323, 275, 176, 427, 196,
        415, 140, 17, 293, 991, 100, 189, 176, 672, 134,
        529, 310, 22, 69, 130, 272, 117, 169, 466, 286,
        46, 236, 387, 92, 177, 188, 124, 385, 174, 23)
```

Charakteristiky původních hodnot spočítáme před tříděním a poté přečteme středy, četnosti a relativní četnosti tříd:

```r
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
[1]  75 225 375 525 675 825 975
[1] 18 19  6  3  1  2  1
[1] 0.36 0.38 0.12 0.06 0.02 0.04 0.02
```

Variační rozpětí 987 minut je zde rozděleno do 7 tříd po 150 minutách. V prvních třídách se opět soustřeďuje většina hodnot: 74 % výrobků vydrželo méně než 300 minut. Ojedinělé doby však sahají až k 991 minutám a posouvají průměr vzhůru. Průměr 246,4 minuty proto leží výrazně nad mediánem 181 minut. Rozdělení je podobně jako v předchozím příkladu zešikmené k vyšším hodnotám.

## Časté chyby

- **Různé způsoby výpočtu kvantilů.** `quantile()` bez argumentu `type` používá interpolaci `type = 7`. Pro výpočet použitý v příkladech slouží `quantile(x, p, type = 6)`. Mírně odlišné výsledky nemusí znamenat chybu v datech, ale jinou volbu interpolace.
- **Ohraničení tříd v `hist()`.** Bez `right = FALSE` jsou třídy zprava uzavřené, $(c_j; c_{j+1}\rangle$. Tabulky používají opačné ohraničení $\langle c_j; c_{j+1})$. Hodnota přesně na hranici se proto může zařadit do jiné třídy a změnit četnosti $f_j$.
- **Záměna rozptylu a směrodatné odchylky.** Rozptyl $s^2$ má jednotky znaku na druhou. Směrodatná odchylka $s$ má stejné jednotky jako data. Pro slovní vyjádření kolísání v původních jednotkách proto používáme $s$, nikoli $s^2$.
- **Nevhodný počet tříd.** Příliš málo tříd skryje tvar rozdělení. Při příliš mnoha třídách obsahuje každý interval jen ojedinělá pozorování a tvar se opět hůře čte. Vhodné třídění hledá kompromis mezi přehledností a podrobností.

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
