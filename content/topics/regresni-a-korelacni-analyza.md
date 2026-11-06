---
title: "Regresní a korelační analýza"
course: mask
type: topic
tags: [mask, statistika, regrese, korelace, r]
sources: ["raw/mask/04 regresní analýza.pdf", "raw/mask/04 regresní analýza - návod R.pdf", "raw/mask/04 regresní analýza přednáška.pdf", "raw/mask/04 05 příklady.docx", "raw/mask/příklady regrese.zip", "raw/mask/test VZOR.docx"]
created: 2026-10-02
updated: 2026-11-06
---

# Regresní a korelační analýza

> [!tldr] V kostce
> - Regrese popisuje vztah mezi číselnými údaji, například mezi počtem členů domácnosti a jejími výdaji.
> - Začít můžeme přímkou. Zakřivený vztah může lépe popsat jiný tvar funkce.
> - Korelace měří sílu lineárního vztahu. Sama neprokazuje příčinu.
> - Vícenásobná regrese pracuje s několika vlivy současně, například se stářím a velikostí nemovitosti.

## Základní pojmy

Počet členů domácnosti a její týdenní výdaje jsou dva znaky $x$ a $y$, které měříme u stejných domácností. **Regresní analýza** jim přiřazuje různé role: vysvětlující (nezávislá) proměnná $x$ slouží k odhadu vysvětlované (závislé) proměnné $y$. Z takového odhadu samotného neplyne příčinná souvislost.

**Korelační analýza** měří, jak silně spolu znaky souvisejí, zejména zda sledují společný lineární trend. Oba postupy se doplňují: regresní funkce popíše průběh vztahu a korelační charakteristiky pomohou posoudit jeho sílu. Téma patří k [[mask|metodám aplikované statistiky]].

**Regresní funkce** zachycuje společný průběh pozorovaných hodnot. Nemusí procházet každým bodem: jednotlivé domácnosti mohou mít jiné výdaje, než jaké funkce odhaduje podle počtu jejich členů.

Druh regresní analýzy určuje struktura datového souboru:

- **dvourozměrný datový soubor** (jedna $x$, jedna $y$) → **regresní analýza dvou proměnných**,
- **vícerozměrný datový soubor** (více $x_1,\dots,x_p$) → **vícenásobná regresní analýza**.

Při volbě funkce vycházíme ze znalosti zkoumaného jevu i z dat. Například **ekonomická teorie** může napovědět, zda s rostoucím objemem produkce očekáváme růst, nebo pokles jednotkových nákladů. Bodový graf ukáže, zda se vztah podobá přímce, nebo křivce. Vhodnost zvolené funkce pak posoudíme statisticky.

## Metoda nejmenších čtverců

Skutečný průměrný vztah v celém základním souboru neznáme. Popisuje ho **teoretická regresní funkce** $\eta = f(x;\beta_0,\beta_1,\dots,\beta_p)$ s neznámými parametry $\beta_i$. Z naměřených dat získáme **empirickou regresní funkci** $\hat y = f(x; b_0,b_1,\dots,b_p)$. Její parametry $b_i$ jsou odhady neznámých $\beta_i$. Rozdíly mezi skutečnými a odhadnutými hodnotami, $e_i=y_i-\hat y_i$, nazýváme **rezidua**.

**Metoda nejmenších čtverců (OLS)** vybírá parametry tak, aby se odhadnuté hodnoty co nejméně odchylovaly od naměřených. Každou odchylku umocní na druhou a tyto čtverce sečte. Hledá nejmenší možný součet:

$$
\sum_{i=1}^n (y_i - \hat y_i)^2 \to \min.
$$

Při odhadu postupujeme ve čtyřech krocích: (1) posoudíme, co o vztahu víme, (2) navrhneme vhodné typy funkcí, (3) odhadneme jejich parametry metodou nejmenších čtverců, (4) porovnáme, jak dobře vystihují data. Pokud se žádná nehodí, zkusíme jiný tvar.

![[mask-ra-primka-rezidua.png|Vlevo týdenní výdaje domácnosti podle počtu členů s regresní přímkou ŷ = 108,7 + 368,0·x a R² = 0,9995; vpravo rezidua ve zvětšeném měřítku od −24,7 do 17,3 Kč jako červené úsečky od nulové přímky]]

Červené úsečky na obrázku ukazují rezidua $e_i$: o kolik se výdaje jednotlivých domácností liší od odhadu přímky. Metoda nejmenších čtverců hledá přímku s nejmenším součtem čtverců těchto odchylek.

## Regresní přímka

Nejjednodušší regresní funkcí je **regresní přímka**:

$$
\eta = \beta_0 + \beta_1 x, \qquad \hat y = b_0 + b_1 x.
$$

Koeficient $b_1$ udává, o kolik se podle modelu změní průměrná hodnota $y$, když se $x$ zvýší o jednotku. Kladné znaménko znamená rostoucí vztah, záporné klesající.

### V R

U šesti domácností známe počet členů a týdenní výdaje. Do R zapíšeme oba seznamy hodnot jako vektory; hodnoty na stejné pozici patří téže domácnosti. Funkce `lm()` odhadne přímku. V jejím zápisu stojí vlevo od vlnovky výdaje, které odhadujeme, a vpravo počet členů, podle kterého je vysvětlujeme:

```r
pocet_clenu <- c(1, 2, 3, 4, 5, 6)
tydenni_vydaje <- c(490, 820, 1230, 1570, 1950, 2320)
```

Samotný odhad a jeho souhrn pak tvoří dva příkazy:

```r
model <- lm(tydenni_vydaje ~ pocet_clenu)
summary(model)
```

```text
Call:
lm(formula = tydenni_vydaje ~ pocet_clenu)

Residuals:
      1       2       3       4       5       6 
 13.333 -24.667  17.333 -10.667   1.333   3.333 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  108.667     16.214   6.702  0.00258 ** 
pocet_clenu  368.000      4.163  88.391 9.82e-08 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 17.42 on 4 degrees of freedom
Multiple R-squared:  0.9995,	Adjusted R-squared:  0.9994 
F-statistic:  7813 on 1 and 4 DF,  p-value: 9.821e-08
```

Odhadnutý model je $\hat y = 108{,}7 + 368{,}0\,x$. Sloupec `Pr(>|t|)` obsahuje p-hodnotu t-testu $H_0:\beta_i=0$ proti $H_1:\beta_i\neq0$ pro každý parametr. Obě p-hodnoty jsou hluboko pod 0,05, takže nulovou hodnotu obou parametrů zamítáme. Pod názvem `Multiple R-squared` najdeme index determinace $R^2=0{,}9995$: přímka vysvětluje 99,95 % rozptylu výdajů.

V příkladu jsme data zapsali přímo. Pokud je máme v souboru, můžeme je také načíst pomocí `d <- read.table("data.txt")`, případně soubor vybrat příkazem `d <- read.table(file.choose())`.

Parametry přímky, odhadnuté výdaje a odchylky od skutečných výdajů můžeme získat i jednotlivě:

```r
coef(model)
fitted(model)
residuals(model)
```

```text
(Intercept) pocet_clenu 
   108.6667    368.0000 
        1         2         3         4         5         6 
 476.6667  844.6667 1212.6667 1580.6667 1948.6667 2316.6667 
         1          2          3          4          5          6 
 13.333333 -24.666667  17.333333 -10.666667   1.333333   3.333333 
```

Funkce `coef()` vrací odhadnuté parametry $b_0,b_1$. Funkce `fitted()` vypíše odhady $\hat y_i$ pro naměřené $x_i$ a `residuals()` jejich odchylky od skutečnosti, tedy rezidua $e_i=y_i-\hat y_i$. Ta odpovídají červeným úsečkám na obrázku.

Odhady jsou zatížené nejistotou. Funkce `confint()` vypočítá intervaly spolehlivosti parametrů přímky. Funkcí `predict()` pak odhadneme výdaje pro nové hodnoty $x$, zde pro 7 a 8 členů domácnosti, a vyjádříme nejistotu těchto odhadů:

```r
confint(model, level = 0.95)
```

```text
                2.5 %   97.5 %
(Intercept)  63.64981 153.6835
pocet_clenu 356.44074 379.5593
```

Pro nové domácnosti zadáme počet členů a přímo zavoláme `predict()`. První výpis je interval pro průměr, druhý pro jednotlivou domácnost:

```r
nove <- data.frame(pocet_clenu = c(7, 8))
predict(model, newdata = nove, interval = "confidence", level = 0.95)
predict(model, newdata = nove, interval = "prediction", level = 0.95)
```

```text
       fit     lwr      upr
1 2684.667 2639.65 2729.684
2 3052.667 2997.03 3108.303
       fit      lwr      upr
1 2684.667 2618.600 2750.733
2 3052.667 2978.953 3126.381
```

Volba `interval = "confidence"` dává interval spolehlivosti pro **střední hodnotu** $y$ při daném $x$, tedy pro průměrné výdaje domácností stejné velikosti. Volba `interval = "prediction"` dává interval pro **jednotlivé budoucí pozorování**. Ten je širší, protože výdaje konkrétní domácnosti se mohou od průměru lišit.

### Diagnostika modelu

Po odhadu přímky kontrolujeme rezidua. Neměla by na sebe v pořadí pozorování navazovat (**autokorelace**) ani mít různě velký rozptyl v různých částech grafu. Stálý rozptyl nazýváme **homoskedasticita**. Pro běžné testy a intervaly v malém výběru posuzujeme také **normalitu** chyb pomocí reziduí. K jednotlivým předpokladům slouží následující testy:

```r
library(lmtest)
dwtest(model)
```

```text
	Durbin-Watson test

data:  model
DW = 3.4121, p-value = 0.9555
alternative hypothesis: true autocorrelation is greater than 0
```

Durbinův–Watsonův test ověřuje $H_0$: autokorelace prvního řádu je nulová. Jde o vztah mezi chybami sousedních pozorování. Výchozí `dwtest()` hledá **kladnou** autokorelaci, jak uvádí výstup. Statistika DW nabývá hodnot mezi 0 a 4; hodnota blízko 2 odpovídá nulové autokorelaci. P-hodnota 0,96 zde nevede k zamítnutí $H_0$ proti kladné autokorelaci. Chceme-li testovat i zápornou autokorelaci, zadáme `alternative = "two.sided"`.

```r
library(whitestrap)
white_test(model)
```

```text
White's test results

Null hypothesis: Homoskedasticity of the residuals
Alternative hypothesis: Heteroskedasticity of the residuals
Test Statistic: 3.14
P-value: 0.207817
```

Whiteův test má $H_0$: rozptyl reziduí je stálý (homoskedasticita), proti $H_1$: rozptyl není stálý (heteroskedasticita). P-hodnota 0,21 je nad 0,05, $H_0$ se nezamítá.

```r
shapiro.test(residuals(model))
```

```text
	Shapiro-Wilk normality test

data:  residuals(model)
W = 0.94818, p-value = 0.7255
```

Shapiro–Wilkův test ověřuje $H_0$: rezidua pocházejí z normálního rozdělení. P-hodnota 0,73 nevede k zamítnutí $H_0$. Testy tedy v tomto příkladu porušení uvedených předpokladů neprokázaly. Výsledek doplníme grafy reziduí:

![[mask-ra-diagnostika-rezidui.png|Vlevo: rezidua regresní přímky proti predikovaným hodnotám, rovnoměrně rozptýlená kolem nuly. Vpravo: Q-Q graf reziduí proti normálnímu rozdělení]]

V levém grafu hledáme body rozptýlené po obou stranách vodorovné osy. Oblouk by upozorňoval na nevhodný tvar funkce, trychtýř na nestálý rozptyl. Pravý Q-Q graf pomáhá posoudit normalitu: body by měly ležet kolem přímky. U malého výběru nemusí test odchylku odhalit; ani větší počet pozorování však kontrolu reziduí nenahrazuje.

### Příklad: Produkce a investice dvanácti firem

U dvanácti soukromých firem s více než 30 zaměstnanci sledujeme za rok 2015 hodnotu produkce `y1` v milionech Kč a investice `x1` ve stovkách tisíc Kč. Odhadneme přímku, určíme kvalitu modelu a předpovíme produkci pro investice $x_1=34$.

```r
firmy <- data.frame(
  x1 = c(32.6, 33.6, 37, 32.6, 35.8, 34.8, 32.2, 32.4, 34, 33.4, 35, 38.2),
  y1 = c(105.6, 96.8, 108.2, 100, 109.8, 107.8, 106.2, 104.8, 106, 105.8, 106.2, 120.2)
)
```

Přímku odhadneme a celý výsledek přečteme ze standardního souhrnu modelu:

```r
model_firmy <- lm(y1 ~ x1, data = firmy)
summary(model_firmy)
```

```text
Call:
lm(formula = y1 ~ x1, data = firmy)

Residuals:
    Min      1Q  Median      3Q     Max 
-8.1457 -2.0149  0.2351  2.5256  5.3690 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)   
(Intercept)  32.7404    21.2866   1.538  0.15505   
x1            2.1490     0.6197   3.468  0.00604 **
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 3.953 on 10 degrees of freedom
Multiple R-squared:  0.546,	Adjusted R-squared:  0.5006 
F-statistic: 12.02 on 1 and 10 DF,  p-value: 0.006044
```

Pearsonův a Spearmanův koeficient odpovídají dvěma samostatným otázkám o lineárním a pořadovém vztahu:

```r
cor(firmy$x1, firmy$y1)
cor(firmy$x1, firmy$y1, method = "spearman")
```

```text
[1] 0.7388977
[1] 0.7298246
```

Predikce pro investice $x_1=34$ je jediným přímým voláním:

```r
predict(model_firmy, newdata = data.frame(x1 = 34))
```

```text
       1 
105.8053 
```

Odhad je $\hat y_1=32{,}7404+2{,}1490x_1$. Zvýšení investic o 100 000 Kč je v modelu spojeno s růstem průměrné produkce přibližně o 2,149 milionu Kč. Pro investice 3,4 milionu Kč vychází produkce **105,8053 milionu Kč**. Model vysvětluje přibližně **54,60 %** rozptylu produkce. Kladný Pearsonův koeficient $r=0{,}7389$ měří lineární vztah; Spearmanův koeficient počítá korelaci pořadí obou veličin.

## Nelineární a vyšší řády regresních funkcí

Růst zisku se může zrychlovat, zatímco jednotkové náklady mohou s objemem výroby klesat stále pomaleji. Takové vztahy přímka nemusí vystihnout. Pomoci může parabola, hyperbola nebo logaritmická funkce. Přestože tvoří křivky, jsou **lineární v parametrech**: mají tvar $\eta=\beta_0+\beta_1 f_1(x)+\dots+\beta_p f_p(x)$. Známé funkce $f_i$ se násobí neznámými koeficienty $\beta_i$, které pak sčítáme. Parametry proto odhadneme stejnou metodou nejmenších čtverců jako u přímky:

$$
\begin{aligned}
\text{parabolická regrese: }\quad &\hat y = b_0 + b_1 x + b_2 x^2\\
\text{polynomická regrese $p$-tého stupně: }\quad &\hat y = b_0 + b_1 x + b_2 x^2 + \dots + b_p x^p\\
\text{hyperbolická regrese: }\quad &\hat y = b_0 + b_1\frac1x\\
\text{logaritmická regrese: }\quad &\hat y = b_0 + b_1\ln x
\end{aligned}
$$

U některých funkcí vstupují neznámé parametry do výpočtu složitěji, například jako základ mocniny. Jde o funkce **nelineární v parametrech**, které nelze zapsat ve tvaru $\eta=\beta_0+\beta_1 f_1(x)+\dots$. Jejich odhad obvykle vzniká postupným zpřesňováním parametrů nelineární metodou nejmenších čtverců. U některých tvarů pomůže také vhodná transformace. Příkladem je **exponenciální regrese**:

$$
\hat y = b_0 \cdot b_1^{\,x}.
$$

![[mask-ra-nelinearni-krivky.png|Vlevo: parabolická a exponenciální regresní funkce proložené daty ročního zisku firmy. Vpravo: hyperbolická regresní funkce proložená daty týdenních výdajů domácnosti]]

### V R — parabolická regrese

Zisk firmy za šest let roste stále rychleji. Zkusíme ho proto popsat parabolou. Ve funkci `lm()` k roku přidáme jeho druhou mocninu; zápis `I(x^2)` zajistí, že R mocninu opravdu vypočítá:

```r
rok <- c(1, 2, 3, 4, 5, 6)
zisk <- c(112, 149, 238, 354, 580, 867)
model_parabola <- lm(zisk ~ rok + I(rok^2))
summary(model_parabola)
```

```text
Call:
lm(formula = zisk ~ rok + I(rok^2))

Residuals:
      1       2       3       4       5       6 
 -8.071   9.243  14.343 -17.771  -4.100   6.357 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)   
(Intercept)  164.600     27.892   5.901  0.00972 **
rok          -76.636     18.248  -4.200  0.02464 * 
I(rok^2)      32.107      2.552  12.582  0.00108 **
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 15.59 on 3 degrees of freedom
Multiple R-squared:  0.9983,	Adjusted R-squared:  0.9971 
F-statistic: 868.7 on 2 and 3 DF,  p-value: 7.156e-05
```

Odhadnutá parabola $\hat y = 164{,}6 - 76{,}6\,x + 32{,}1\,x^2$ vysvětluje 99,8 % rozptylu zisku. Zachycuje zrychlující se růst, který by přímka s neměnným sklonem vystihovala hůře.

### V R — exponenciální regrese

Stejné zisky nyní popíšeme exponenciální křivkou. K odhadu použijeme funkci `nls2()` ze stejnojmenného balíčku. Ta postupně mění parametry, dokud nenajde dostatečně dobré řešení. Pokud nezadáme počáteční hodnoty, začne od 1 a vypíše o tom upozornění:

```r
library(nls2)
model_exp <- nls2(zisk ~ b1 * exp(b2 * rok))
summary(model_exp)
```

```text
Formula: zisk ~ b1 * exp(b2 * rok)

Parameters:
   Estimate Std. Error t value Pr(>|t|)    
b1 65.35423    3.57541   18.28 5.27e-05 ***
b2  0.43161    0.01013   42.63 1.81e-06 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 11.89 on 4 degrees of freedom

Number of iterations to convergence: 13 
Achieved convergence tolerance: 2.137e-06
```

Pro kladný základ $b_2>0$ lze stejnou křivku zapsat i v alternativním exponenciálním tvaru $\hat y=b_1\cdot b_2^{x}$:

```r
model_pow <- nls2(zisk ~ b1 * (b2^rok))
summary(model_pow)
```

```text
Formula: zisk ~ b1 * (b2^rok)

Parameters:
   Estimate Std. Error t value Pr(>|t|)    
b1 65.35424    3.57542   18.28 5.27e-05 ***
b2  1.53973    0.01559   98.76 6.30e-08 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 11.89 on 4 degrees of freedom

Number of iterations to convergence: 9 
Achieved convergence tolerance: 3.438e-08
```

Oba zápisy dávají stejnou křivku. Koeficient u $x$ v prvním zápisu převedeme na základ mocniny pomocí exponenciály: zde $e^{0{,}4316}\approx 1{,}540$. Proto vychází i stejná reziduální chyba. Mění se způsob zápisu parametrů, nikoli odhadnuté zisky.

### V R — hyperbolická regrese

U hyperboly místo původní vysvětlující proměnné použijeme její převrácenou hodnotu. V R ji zapíšeme jako `I(1/x)` a model odhadneme funkcí `lm()`. Pro srovnání s přímkou použijeme stejné výdaje domácností:

```r
model_hyperbola <- lm(tydenni_vydaje ~ I(1 / pocet_clenu))
summary(model_hyperbola)
```

```text
Call:
lm(formula = tydenni_vydaje ~ I(1/pocet_clenu))

Residuals:
     1      2      3      4      5      6 
 229.3 -400.7 -310.7 -130.7  153.3  459.3 

Coefficients:
                 Estimate Std. Error t value Pr(>|t|)   
(Intercept)        2180.7      266.5   8.182  0.00122 **
I(1/pocet_clenu)  -1920.0      534.6  -3.592  0.02293 * 
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 374.6 on 4 degrees of freedom
Multiple R-squared:  0.7633,	Adjusted R-squared:  0.7041 
F-statistic:  12.9 on 1 and 4 DF,  p-value: 0.02293
```

Model $\hat y = 2180{,}7 - \dfrac{1920{,}0}{x}$ vysvětluje 76,3 % rozptylu výdajů. Přímka se stejnými daty měla $R^2=0{,}9995$, takže jejich průběh vystihuje podstatně lépe. Vyzkoušet složitější tvar tedy samo o sobě ke zlepšení nevede.

### Příklad: Tržby a počet zákazníků

Prodejna počítačových her po kurzu prodejních dovedností provedla dvacet měření. `x2` je počet návštěvníků za den, `y2` tržba v tisících Kč. Odhadneme parabolu a bod, od něhož modelované tržby klesají.

```r
prodejna <- data.frame(
  x2 = c(20, 21, 26, 27, 28, 29, 30, 31, 32, 34, 35, 37, 38, 39, 42, 44, 48, 49, 51, 54),
  y2 = c(15, 18, 20, 21, 24, 28, 30, 32, 35, 38, 39, 41, 42, 45, 48, 45, 46, 43, 40, 39)
)
```

```r
model_prodejna <- lm(y2 ~ x2 + I(x2^2), data = prodejna)
summary(model_prodejna)
```

```text
Call:
lm(formula = y2 ~ x2 + I(x2^2), data = prodejna)

Residuals:
    Min      1Q  Median      3Q     Max 
-5.3620 -1.9165  0.6517  1.3144  4.6691 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept) -60.328179   9.921746  -6.080 1.22e-05 ***
x2            4.546464   0.557549   8.154 2.81e-07 ***
I(x2^2)      -0.049471   0.007457  -6.634 4.23e-06 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 3.125 on 17 degrees of freedom
Multiple R-squared:  0.9175,	Adjusted R-squared:  0.9078 
F-statistic: 94.58 on 2 and 17 DF,  p-value: 6.137e-10
```

Pro zadané počty zákazníků vypočteme predikce přímo:

```r
predict(model_prodejna, newdata = data.frame(x2 = c(70, 50, 62)))
```

```text
       1        2        3 
15.51655 43.31760 31.38618 
```

Model má tvar

$$
\hat y_2=-60{,}3282+4{,}5465x_2-0{,}049471x_2^2.
$$

Model vysvětluje přibližně **91,75 %** rozptylu tržeb. Parabola je obrácená dolů, protože koeficient u druhé mocniny je záporný. Vrchol paraboly určí vztah $-b_1/(2b_2)$; vychází při **45,95 zákazníka**, tedy přibližně při 46 zákaznících. Při vyšší návštěvnosti už modelované tržby klesají. To může být podnětem k posouzení obslužné kapacity prodejny.

Odhady pro 70 a 62 zákazníků však leží mimo naměřený rozsah 20 až 54. Jde o **extrapolaci**: předpovídáme v oblasti, pro kterou nemáme pozorování. Kořeny rovnice $\hat y_2=0$ leží přibližně v bodech 16,08 a 75,82 zákazníka a mají pouze matematický význam. Kdyby model předpovídal záporné tržby, nešlo by o ekonomicky smysluplný výsledek.

### Příklad: Jednotkové náklady a objem produkce

Podnik sleduje vlastní náklady na jednotku produkce `y3` v Kč v závislosti na objemu produkce `x3` v tisících kusů. Odhadneme hyperbolu, náklady při objemu 2 000 tisíc kusů a objem, od něhož modelované náklady klesnou pod 50 Kč.

```r
naklady <- data.frame(
  x3 = c(60, 71, 92, 144, 192, 306, 437, 481, 747, 989, 1383),
  y3 = c(5157, 2620, 1986, 1582, 1100, 954, 729, 456, 200, 196, 110)
)
```

```r
model_naklady <- lm(y3 ~ I(1 / x3), data = naklady)
summary(model_naklady)
```

```text
Call:
lm(formula = y3 ~ I(1/x3), data = naklady)

Residuals:
    Min      1Q  Median      3Q     Max 
-811.80  -84.54   25.63  135.76 1078.29 

Coefficients:
             Estimate Std. Error t value Pr(>|t|)    
(Intercept)    -96.78     229.42  -0.422    0.683    
I(1/x3)     250528.88   28899.56   8.669 1.16e-05 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 513.1 on 9 degrees of freedom
Multiple R-squared:  0.893,	Adjusted R-squared:  0.8812 
F-statistic: 75.15 on 1 and 9 DF,  p-value: 1.159e-05
```

```r
predict(model_naklady, newdata = data.frame(x3 = 2000))
```

```text
      1 
28.4892 
```

Odhadnutá funkce je

$$
\hat y_3=-96{,}78+\frac{250\,528{,}88}{x_3}.
$$

**Kladný** koeficient u $1/x_3$ znamená, že pro $x_3>0$ náklady s objemem výroby klesají. Potvrzuje to záporná derivace $-250\,528{,}88/x_3^2<0$. Model vysvětluje přibližně **89,30 %** rozptylu nákladů. Při objemu 2 000 tisíc kusů odhaduje **28,49 Kč na kus**. Po dosazení $\hat y_3=50$ a vyřešení rovnice vychází hranice **1 706,89 tisíce kusů**; nad ní model předpovídá náklady pod 50 Kč.

Nejvyšší naměřený objem je ale 1 383 tisíc kusů. Oba výsledky jsou tedy extrapolace a pro plánování by potřebovaly další ověření. Pro libovolně velkou výrobu se tato hyperbola nehodí: kvůli zápornému absolutnímu členu by nakonec dávala záporné náklady.

## Kvalita regresní funkce a korelační analýza

Kvalitu funkce posuzujeme podle toho, kolik z rozdílů mezi naměřenými hodnotami dokáže zachytit. **Index determinace** porovnává rozptyl hodnot vysvětlený modelem s celkovým rozptylem:

$$
R^2 = \frac{s^2_{\hat y}}{s^2_y} = 1 - \frac{s^2_{y-\hat y}}{s^2_y}.
$$

Čím blíže je $R^2$ k 1, tím větší část rozptylu vysvětlované proměnné $y$ model zachycuje. Výsledek můžeme vyjádřit v procentech. Nízká hodnota může znamenat, že jsme zvolili nevhodný tvar funkce; mezi znaky přesto může existovat vztah, který by jiná křivka vystihla lépe.

Z indexu determinace vypočítáme **index korelace** $I=\sqrt{R^2}$. Můžeme ho použít pro přímku i pro další typy regresních funkcí. U regresní přímky odpovídá absolutní hodnotě **koeficientu korelace**:

$$
r_{xy} = \frac{s_{xy}}{\sqrt{s^2_x\cdot s^2_y}}.
$$

Koeficient korelace nabývá hodnot od $-1$ do $+1$. Kladné znaménko znamená, že s růstem jednoho znaku zpravidla roste i druhý, záporné označuje opačný směr. Čím blíže je koeficient k 0, tím slabší je lineární vztah.

![[mask-ra-korelace-data.png|Šest domácností s Pearsonovým r 0,9997, dvanáct firem s investicemi a produkcí s r 0,7389 a jedenáct dvojic objemu produkce a jednotkových nákladů s r −0,6680. Každý panel uvádí vlastní jednotky os]]

U domácností leží body téměř na přímce; u investic a produkce je kolem rostoucího trendu větší rozptyl. U objemu produkce a jednotkových nákladů je vztah klesající a zakřivený. Pearsonovo $r=-0{,}6680$ měří jeho **lineární** složku, zatímco vhodnost odhadnuté hyperboly vyjadřuje její $R^2=0{,}8930$. Samotné $r$ blízké nule by vylučovalo silný lineární trend, nikoli obecně závislost.

### V R

```r
cor(pocet_clenu, tydenni_vydaje)
cor(firmy$x1, firmy$y1)
cor(naklady$x3, naklady$y3)
```

```text
[1] 0.9997441
[1] 0.7388977
[1] -0.6679865
```

U domácností vychází korelace 0,9997. To odpovídá $\sqrt{R^2}=\sqrt{0{,}9995}$ z výpisu regresní přímky. Přímka má kladný sklon, takže se koeficient korelace a index korelace rovnají. U přímky obecně platí $I=|r|$.

### Příklad: Produktivita zaměstnanců a délka praxe

U dvanácti zaměstnanců měříme délku praxe `praxe` v letech a produktivitu v kusech za hodinu. Sestavíme přímkový a logaritmický model a porovnáme jejich kvalitu. Logaritmus se týká vysvětlující proměnné, produktivita zůstává v původních jednotkách.

```r
zamestnanci <- data.frame(
  praxe = c(2, 8, 15, 4, 11, 3, 19, 7, 13, 5, 17, 9),
  produktivita = c(18, 30, 35, 24, 31, 20, 38, 27, 34, 23, 36, 29)
)
```

Oba modely odhadneme stejným příkazem `lm()` a jejich parametry i $R^2$ přečteme ze souhrnů:

```r
model_praxe_primka <- lm(produktivita ~ praxe, data = zamestnanci)
model_praxe_log <- lm(produktivita ~ log(praxe), data = zamestnanci)
summary(model_praxe_primka)
summary(model_praxe_log)
```

```text

Call:
lm(formula = produktivita ~ praxe, data = zamestnanci)

Residuals:
    Min      1Q  Median      3Q     Max 
-2.4547 -1.2909  0.2422  1.0253  2.8345 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) 18.21782    0.93256   19.54 2.70e-09 ***
praxe        1.11846    0.08594   13.01 1.36e-07 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 1.605 on 10 degrees of freedom
Multiple R-squared:  0.9443,	Adjusted R-squared:  0.9387 
F-statistic: 169.4 on 1 and 10 DF,  p-value: 1.357e-07


Call:
lm(formula = produktivita ~ log(praxe), data = zamestnanci)

Residuals:
    Min      1Q  Median      3Q     Max 
-1.9216 -0.9347  0.2106  0.9291  1.2595 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  10.5516     1.0006   10.54 9.75e-07 ***
log(praxe)    8.9286     0.4653   19.19 3.21e-09 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 1.105 on 10 degrees of freedom
Multiple R-squared:  0.9736,	Adjusted R-squared:  0.9709 
F-statistic: 368.3 on 1 and 10 DF,  p-value: 3.214e-09
```

Odhadnuté modely jsou

$$
\begin{aligned}
\hat y_{\text{přímka}}&=18{,}2178+1{,}1185x,\\
\hat y_{\text{log}}&=10{,}5516+8{,}9286\ln x.
\end{aligned}
$$

Přímka vysvětluje přibližně **94,43 %**, logaritmická funkce **97,36 %** rozptylu produktivity. Těchto dvanáct pozorování tedy lépe vystihuje logaritmický model: produktivita v něm s praxí roste, ale přírůstky se zmenšují. Přímka naproti tomu přidává přibližně 1,12 kusu za hodinu za každý další rok praxe. Vyšší $R^2$ vypovídá o shodě s naměřenými daty. Předpoklady modelu musíme posoudit zvlášť a předpovědi mimo rozsah 2 až 19 let praxe zůstávají extrapolací.

![[mask-ra-praxe-modely.png|Dvanáct zaměstnanců: produktivita v kusech za hodinu podle délky praxe v letech; přímka s R² 0,9443 a logaritmický model s R² 0,9736]]

## Vícenásobná regrese a korelace

Cenu nemovitosti může současně vysvětlovat její stáří, velikost i poloha. **Vícenásobná regrese** tyto informace spojuje do jednoho modelu pro vysvětlovanou proměnnou $y$. Každý koeficient pak popisuje vztah při stejných hodnotách ostatních zahrnutých proměnných:

$$
\eta = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \dots + \beta_p x_p, \qquad \hat y = b_0 + b_1 x_1 + \dots + b_p x_p.
$$

### Výběr proměnných

**Metoda ENTER** zahrne všechny zvolené proměnné najednou. Umožní posoudit model jako celek i vztah každé proměnné k výsledku při zohlednění ostatních. Orientačně se doporučuje aspoň 20 pozorování na každou proměnnou.

**Postupná regrese (stepwise)** proměnné přidává nebo odebírá a porovnává vzniklé modely. Snaží se zachovat dobrou předpověď při menším počtu proměnných. Klasické postupy se řídí F-testy, funkce `step()` v R používá kritérium AIC, vysvětlené níže. O jednotlivých krocích rozhoduje program podle zvoleného pravidla.

Při postupu **forward** proměnné přidává, při postupu **backward** začíná všemi a odebírá je. Pořadí kroků může ovlivnit, jak se důležitost proměnných projeví. Pro tento postup se doporučuje aspoň 40 pozorování na proměnnou.

### Postup odhadu

1. Posoudíme, zda jsou proměnné a zvolený tvar funkce pro regresi vhodné.
2. Odhadneme parametry modelu.
3. Pomocí reziduí zkontrolujeme, jak model vystihuje data a zda splňuje předpoklady.

U každého parametru $b_i$ posuzujeme **t-testem**, zda se jeho hodnota prokazatelně liší od nuly: $H_0:\beta_i=0$ proti $H_1:\beta_i\neq0$. Pokud $H_0$ nezamítneme, nenulový vztah při zahrnutí ostatních proměnných se neprokázal. Proměnnou přesto automaticky nevyřazujeme. Záleží i na jejím významu pro zkoumaný jev, účelu modelu a vzájemných vztazích vysvětlujících proměnných.

### Předpoklady modelu

1. Vysvětlovaná proměnná $y$ je číselná, alespoň intervalového typu: rozdíly mezi jejími hodnotami mají smysl, jako u ceny nebo výdajů. Pro výsledek ano/ne se používá logistická regrese; také číselné proměnné s málo možnými hodnotami vyžadují zvláštní posouzení.
2. Vysvětlující proměnné $x_1,\dots,x_p$ mohou být číselné, alespoň intervalového typu, nebo alternativní, tedy se dvěma variantami.
3. Vysvětlující proměnné nemají být navzájem příliš silně korelované. Jinak se jejich vztahy k výsledku obtížně oddělují; jde o **multikolinearitu**.
4. Prověříme odlehlá pozorování a hodnoty, které mají na odhad velký vliv. Samotná odlehlost není důvodem k vyřazení.
5. Zvolený tvar funkce má vystihovat průměrný průběh vysvětlované proměnné. Model lineární v parametrech může používat i druhou mocninu nebo logaritmus vysvětlující proměnné.
6. Pro běžné testy a intervaly v malém výběru předpokládáme [[nahodne-veliciny-a-rozdeleni|normální rozdělení]] náhodných chyb. Posuzujeme je pomocí reziduí. Každá vysvětlující proměnná sama normální rozdělení mít nemusí.

Normalitu reziduí posuzujeme Q-Q grafem a testy normality, například Shapiro–Wilkovým či Kolmogorovovým–Smirnovovým testem; jejich princip vysvětluje [[testovani-hypotez|testování statistických hypotéz]]. Graf reziduí proti odhadnutým hodnotám nám naproti tomu pomáhá hledat nevhodný tvar funkce a nestálý rozptyl.

### Multikolinearita

Některé vysvětlující proměnné mohou nést podobnou informaci. Například u nemovitostí spolu mohou silně souviset dvě vzdálenosti. Model pak obtížně určuje, jak velká část vztahu k ceně připadá na každou z nich. Tato **multikolinearita** má několik projevů:

- odhady jednotlivých parametrů jsou nejisté,
- i věcně důležitá proměnná se může jevit jako statisticky nevýznamná,
- směrodatné chyby odhadů rostou, hodnoty t-testů klesají a p-hodnoty rostou.

Na problém upozorňují vysoké korelace mezi vysvětlujícími proměnnými (nad 0,75). Dalším příznakem je významný F-test celého modelu při nevýznamných t-testech jednotlivých parametrů. Podrobněji ho posoudíme pomocí **VIF**, ukazatele zvětšení rozptylu odhadu: hodnoty $1<\text{VIF}<5$ jsou varující, $\text{VIF}>5$ (přísněji $>10$) značí vysokou multikolinearitu.

Pokud problém tvoří silná závislost dvou proměnných, můžeme jednu vyřadit a model znovu odhadnout. Při závislosti více proměnných současně lze použít metodu hlavních komponent. Ta z původních proměnných vytvoří nové, navzájem nekorelované proměnné.

### Další ukazatele kvality modelu

- **F-test** posuzuje model jako celek. Nulová hypotéza říká, že všechny koeficienty u vysvětlujících proměnných jsou nulové ($H_0:\beta_1=\dots=\beta_p=0$, bez absolutního členu). Alternativa říká, že alespoň jeden je nenulový.
- **RMSE**, odmocnina z reziduálního rozptylu, vyjadřuje velikost odchylek od modelu v jednotkách vysvětlované proměnné. Nižší hodnota znamená menší odchylky. Index determinace naproti tomu vyjadřuje relativní podíl vysvětleného rozptylu.
- **AIC** (Akaikeho informační kritérium) a **BIC** (Bayesovo informační kritérium) pomáhají porovnávat modely. U obou dáváme přednost nižší hodnotě. Používají se například při postupném výběru proměnných.

### Příklad: Ceny nemovitostí

U 321 nemovitostí známe prodejní cenu v dolarech v roce 1981. Zkusíme ji vysvětlit stářím v letech, vzdáleností k mezistátní silnici, počtem pokojů, podlahovou plochou, velikostí pozemku, počtem koupelen a vzdáleností ke spalovně. Nejprve do modelu zahrneme všechny tyto údaje.

V R má cena název `price`. Ostatní sloupce se jmenují `age`, `inst`, `rooms`, `area`, `land`, `baths` a `dist`, ve stejném pořadí jako ve výčtu výše. Každý řádek následující tabulky patří jedné nemovitosti. První řádek například popisuje nemovitost starou 48 let se 7 pokoji, prodanou za 60 000 dolarů. Další řádek patří jiné nemovitosti: je stará 83 let, má 6 pokojů a cenu 40 000 dolarů.

Následující rozbalovací část obsahuje kompletní vstupní data: všech 321 pozorování a osm číselných sloupců. Číselné řádky slouží ke spuštění výpočtu v R; výklad pokračuje pod nimi odhadem modelu.

<details>
<summary>Vstupní data pro 321 nemovitostí</summary>

```r
nemovitosti <- read.table(text = "
age inst rooms area land baths dist price
48 305 7 149.4 412.02 1 3263.5 60000
83 305 6 235.08 753.3 2 3355 40000
58 305 6 102.96 450 1 3507.5 34000
11 305 5 102.24 900 1 3629.5 63900
48 610 5 168.12 900 1 3690.5 44000
78 610 6 160.2 855 3 3050 46000
22 610 6 153 979.02 2 3568.5 56000
78 610 6 140.04 348.3 2 3111 38500
42 610 8 147.78 630 2 3202.5 60500
41 610 5 129.87 715.5 2 3355 55000
78 1220 6 129.51 449.1 1 2623 39000
38 1220 5 133.38 721.53 1 3721 41000
18 1220 6 116.1 1128.42 2 3782 50900
32 2135 6 114.66 707.22 1 5124 52000
18 2440 6 132.84 1409.76 1 5246 49000
58 915 7 165.42 832.41 2 3019.5 80000
56 915 6 138.24 944.19 2 3050 50000
70 915 5 221.22 846 2 3050 59000
26 1220 4 67.5 720 1 3233 42000
21 1220 5 189.54 1203.3 2 3568.5 71500
24 1525 4 90 720 1 3568.5 43000
33 1525 6 126.9 933.3 2 3812.5 48000
128 4270 7 211.14 3920.4 2 5978 37500
15 5490 6 109.35 4038.03 1 7320 59000
7 5490 6 191.52 3975.66 2 6771 59000
0 5185 7 206.1 2272.5 3 6618.5 94000
0 5185 7 221.76 4344.21 3 6618.5 95920
0 5185 7 201.6 4042.44 3 6679.5 95000
0 5185 7 221.76 4572.72 3 6710 95900
1 5185 7 201.6 4770 3 6588 91000
0 4880 7 221.76 3731.67 3 6557.5 96900
104 1220 8 231.84 1131.12 2 2867 47000
18 1220 6 123.93 1158.93 2 3111 68500
188 2745 6 186.39 869.85 2 4910.5 36000
12 2440 7 211.68 2420.1 3 4575 90000
178 2745 10 157.5 1126.44 2 5215.5 66900
1 1830 6 168.21 1125 2 1860.5 44000
48 1830 6 134.1 450 1 2013 43500
56 1830 5 168.03 450 1 2074 40000
3 1830 7 113.49 900 2 1830 46000
21 1525 5 93.42 1388.79 1 3050 48000
12 1830 7 162 1172.7 2 3416 61000
28 1525 6 177.48 1808.01 2 3477 55500
23 2135 6 188.01 1524.15 1 3690.5 63000
148 2135 6 131.76 2621.61 2 3812.5 32000
25 2135 6 190.08 1125 2 4270 32000
13 3660 6 176.76 2266.38 2 5581.5 82000
18 5185 5 104.94 4050 1 1586 51000
38 4270 6 347.49 4595.58 2 2440 83000
10 4880 7 202.68 3960 3 4880 100000
8 4880 9 233.82 3960 3 4880 131500
21 5490 4 204.84 3920.4 1 6740.5 37500
68 1830 6 168.75 881.1 2 2043.5 49000
13 1830 6 141.3 791.1 2 3263.5 54000
38 2135 6 182.88 989.37 2 1616.5 56900
22 2440 6 118.62 1849.5 2 1738.5 62000
21 2440 5 97.02 1962 2 1769 48000
56 2135 7 311.4 1027.89 2 1799.5 48000
28 2135 5 143.28 1143 2 2074 53000
54 2135 8 82.35 1260 1 2318 49000
28 2135 5 83.25 412.65 1 3477 31000
14 2135 6 127.89 1900.8 2 2074 56900
78 3050 5 89.1 153.9 1 4758 34000
153 3355 9 341.28 3234.78 4 4941 98000
3 3660 7 228.96 2405.34 3 5398.5 85500
0 3660 7 198.54 4508.46 3 5642.5 122500
189 5185 9 457.02 11917.98 4 4422.5 185000
5 5795 5 122.22 4029.75 2 5093.5 67500
8 5795 7 195.39 3965.76 3 4941 120000
1 6405 7 179.82 3920.49 3 6069.5 79000
1 6405 7 179.82 13290.12 3 6039 77500
26 6710 6 122.04 49005 2 6405 58000
0 6405 9 126.99 3998.79 3 6161 61900
2 6405 7 138.6 4155.66 3 6405 79900
0 6710 7 116.64 4194.81 2 6374.5 62400
1 7320 7 201.6 3920.4 2 7015 89500
0 7015 7 219.24 3920.4 3 7045.5 89500
0 7320 7 214.56 3920.4 3 7076 94900
0 7930 6 167.58 5075.28 2 8265.5 85900
0 7930 7 183.24 4476.33 3 8235 92900
0 7930 7 187.38 3956.22 3 8235 84900
0 7930 7 176.58 4001.85 3 8143.5 85900
0 7930 7 205.74 3959.64 3 8113 85900
0 7625 7 221.76 3920.4 3 8052 97900
0 7625 6 167.58 4077.18 2 8021.5 78400
0 7930 8 246.42 3959.55 2 8235 91400
0 7930 7 201.6 3959.55 3 8265.5 106500
0 7930 7 250.2 3959.55 3 8235 109500
1 4880 7 250.29 3920.4 3 4758 148000
12 5795 6 138.33 4351.68 2 5398.5 75000
1 4880 7 251.64 3920.4 3 4758 90400
1 4880 9 251.46 3959.55 3 4758 125000
158 7015 9 258.48 9408.96 3 10156.5 123000
30 6710 6 122.13 4077.18 1 7808 63000
188 7015 7 293.04 4038.03 2 7716.5 87500
0 9455 7 183.42 4430.07 2 10156.5 73000
0 7930 7 173.16 3998.79 3 8570.5 84900
0 7930 7 213.3 3920.4 3 8326.5 80900
0 7930 7 183.24 4665.24 3 8296 94000
0 9455 7 163.62 4978.89 2 10126 74500
1 10370 7 178.74 4508.46 3 11193.5 82500
3 9760 6 166.95 4586.85 2 10553 86000
1 9150 6 165.24 4155.66 3 10156.5 76900
1 9150 7 165.24 4116.42 2 10156.5 75900
0 9150 7 163.8 4155.66 3 10156.5 75500
0 9150 7 155.52 4312.44 2 10156.5 75000
0 9150 6 188.28 4234.05 3 10156.5 73900
0 10370 7 183.24 4155.66 3 11224 83900
1 10370 7 216 3920.4 3 11315.5 76900
0 9455 7 189.36 6182.01 3 10126 84300
0 9455 7 173.52 14152.68 3 10156.5 75900
0 9455 7 186.03 18386.64 3 10156.5 87900
13 7930 7 122.4 3951.9 2 9180.5 65000
0 7930 7 174.6 3959.64 3 9150 90000
5 7930 7 253.44 3920.4 3 9119.5 104500
14 7625 6 111.15 8624.88 2 8662 63000
5 8235 7 124.92 4194 2 9455 66100
6 8235 7 96.3 4395.06 1 9455 60000
4 8540 7 125.1 4149 2 9455 73000
3 7625 9 231.66 3959.64 3 8601 83000
1 8845 6 110.88 4050 2 9851.5 70500
4 8540 6 238.5 3959.64 3 9760 120000
12 9760 6 178.02 4038.03 2 10888.5 62500
1 8845 6 112.32 4050 2 10004 65500
9 8540 7 154.44 4095 2 9546.5 84900
9 9455 6 102.96 3998.79 1 10858 63400
2 9150 7 220.5 4038.03 3 10522.5 80000
2 7320 7 265.68 3959.64 3 8601 86000
0 7320 7 252 6233.4 3 8662 94376
0 7320 7 189.72 4704.48 3 8540 90500
2 7320 7 198.72 4861.26 3 8662 90500
0 7320 7 140.4 4037.76 3 8723 84900
2 7320 7 202.32 4429.98 3 8631.5 86000
6 7015 7 205.56 3960.09 3 8479 91500
23 6405 7 236.88 5841.36 2 8235 89912
23 6405 7 236.88 5841.36 2 8235 88000
14 5795 6 174.24 3959.64 2 7686 73500
8 6405 8 180.36 3967.2 2 8143.5 85000
13 6405 7 172.8 3983.4 2 7991 87000
5 6100 7 192.24 3960 3 7869 97000
3 7320 7 222.48 4177.98 3 8845 72500
4 7015 7 161.28 4059.54 3 8845 77000
5 7015 7 192.24 10545.84 3 8570.5 85000
4 6100 8 181.44 4041 3 7869 82000
0 6100 6 226.26 3959.64 3 7930 93000
0 6100 7 218.88 3929.67 3 7808 105000
0 6100 7 259.02 3920.4 3 7808 106500
15 7930 5 86.4 4652.1 1 9668.5 44900
11 5490 7 168.12 5121 3 7899.5 73000
11 8540 6 116.64 8546.49 2 10736 46500
13 8540 6 150.12 3920.4 2 10888.5 50000
0 8540 7 184.68 3920.4 3 10797 90000
1 10065 6 99 3489.12 1 11773 49500
28 10370 5 118.8 5762.97 1 12200 57000
9 3965 6 272.7 4312.44 3 4514 120000
3 4575 6 173.16 3841.92 2 5764.5 83500
0 3660 7 339.3 25443.36 3 4727.5 300000
3 3660 7 257.04 2695.95 2 5398.5 64900
58 1830 5 83.7 736.65 1 4087 50900
12 1830 6 125.91 900 2 4148 60500
3 1525 5 120.78 765 2 4117.5 70400
48 2135 6 135 463.77 2 3599 48000
25 3050 7 119.97 1069.47 1 5124 53500
8 7930 6 165.96 8350.47 2 7991 66000
8 7930 6 158.76 7762.41 2 7930 64000
11 4575 7 245.43 4038.03 3 6496.5 65000
10 3965 7 187.2 2250 2 6008.5 72900
2 3965 7 182.7 2260.8 3 5917 26000
0 4270 7 272.7 2902.95 3 6405 117000
0 3965 7 202.68 2780.46 3 6161 97000
2 3965 7 201.42 2312.1 3 6039 95000
0 3965 7 221.76 2785.05 3 6252.5 107900
0 4270 7 221.76 2795.31 3 6374.5 120000
1 4270 7 225.18 3119.94 3 6435.5 120000
0 4270 7 225.9 2872.35 3 6374.5 121000
0 3965 7 181.08 2772 3 6344 107000
0 3965 7 211.68 2819.79 3 6252.5 119900
0 3965 7 224.28 2452.32 3 6191.5 142500
0 3965 7 248.04 2448.45 3 6161 84211
81 305 6 139.86 611.1 1 3599 49000
71 610 5 141.75 313.65 1 3080.5 52000
31 610 6 297.36 1685.79 2 3111 68000
41 610 6 153 675 1 3416 54000
31 610 6 130.86 495 2 3599 70000
81 610 6 126.9 405 1 3111 47000
19 1220 6 143.28 1176.12 1 4026 73900
1 2745 9 171.9 1372.14 3 5551 117500
41 3050 5 66.15 940.86 1 5795 60000
1 4575 6 103.86 3920.4 2 7015 85000
26 2135 5 99.36 1396.08 1 5185 66479
81 915 6 164.7 1254.51 1 2745 70000
41 1220 5 104.94 879.3 1 3202.5 66500
31 1220 7 203.67 901.71 2 3507.5 91000
31 1220 6 133.38 1136.88 1 3629.5 72500
36 1220 4 87.3 999.36 1 3629.5 67000
21 3660 6 151.56 7314.57 2 1769 68000
18 5490 6 97.2 4704.48 2 7350.5 85000
13 1525 6 146.97 1595.52 2 3202.5 106000
24 1525 7 288.72 1568.16 3 3507.5 130000
0 3050 7 203.22 1125 3 5734 119900
1 3050 7 181.44 1136.88 3 5764.5 125000
0 3050 7 179.19 1136.88 3 5764.5 118000
0 3050 7 157.14 1215.36 3 5795 100000
1 3050 7 243 1215.36 3 5795 128000
0 3050 7 207.18 1215.36 3 5734 140000
0 3050 6 192.96 1152.54 3 5612 143500
59 1830 5 168.03 450 1 2074 66500
51 1525 5 102.6 1255.05 1 2165.5 50000
25 1525 5 82.08 1080.45 1 3385.5 65000
20 2135 6 128.25 1759.5 1 4270 86000
131 3660 9 341.82 4504.05 2 5795 120000
0 3355 7 202.68 3139.11 3 5581.5 135000
0 3355 7 202.68 3139.11 3 5581.5 135000
0 3355 7 255.24 3334.14 3 5642.5 160000
0 3355 7 223.74 2772.72 3 5673 168000
0 3355 7 276.66 2264.31 3 5642.5 182095
0 3355 7 276.66 2273.85 3 5642.5 175000
0 3355 7 290.88 2284.2 3 5612 162000
0 3660 7 305.64 2827.08 4 5703.5 189857
0 3660 7 221.76 3332.34 3 5764.5 190508
0 3660 7 292.68 2670.39 3 5795 234552
0 3355 7 273.6 2665.89 3 5795 220000
0 3355 7 274.95 2273.85 3 5764.5 175000
11 4880 7 155.79 1332.9 2 1525 118000
1 4270 9 269.64 4116.42 3 2653.5 155000
0 4270 7 221.76 4155.66 3 2623 144000
0 3965 7 229.32 4155.66 3 2684 216000
0 3965 6 305.82 5693.4 4 3019.5 124500
0 3965 6 178.92 5869.08 3 2470.5 80000
0 4270 7 462.24 4312.44 3 2501 100000
81 1830 6 209.43 3198.42 1 2379 88000
41 2135 6 84.24 744.84 1 1921.5 41000
121 915 7 150.66 4939.74 1 2318 66000
7 2135 5 142.83 536.13 2 2928 74000
1 2135 5 137.79 274.41 2 2196 76900
0 2745 7 231.66 3938.13 3 3751.5 132000
0 2440 7 237.96 3175.56 2 3629.5 130000
39 3050 6 131.04 1639.35 1 4910.5 75000
2 3355 7 221.76 2809.35 3 4880 156500
8 3050 8 216 2630.34 3 4880 140000
81 3355 6 158.4 2940.3 2 5276.5 65000
6 3660 6 281.88 2352.24 3 5429 150000
2 3965 7 241.92 2581.92 2 5795 155000
0 7625 7 239.04 3959.64 3 7472.5 153000
0 7625 7 246.42 3920.4 3 7503 160000
0 7625 7 246.24 3920.4 3 7503 148000
0 7625 8 335.34 3954.15 3 7472.5 142000
1 7320 7 239.04 4077.18 3 7350.5 162000
0 7320 8 295.56 3959.64 3 7320 175500
1 7320 9 285.3 4077.18 3 7289.5 194000
0 7625 6 209.7 3959.55 2 8174 130500
29 5795 6 140.76 4390.83 1 5246 73000
0 5490 6 202.32 4484.61 3 5215.5 140000
29 5795 6 140.94 3959.64 1 5581.5 82000
2 5185 7 246.96 6939.09 3 5032.5 180000
0 5490 7 222.3 5827.05 3 5063 200000
51 7015 6 107.91 4900.5 1 7777.5 52900
17 7015 6 198.36 4077.18 2 7686 110000
0 7320 7 216 4116.42 3 7686 68000
2 7015 7 283.68 4665.15 2 7625 90000
2 7015 7 283.68 4665.15 2 7625 102000
0 7320 7 243.09 4390.83 3 7716.5 119600
2 7930 7 180 3921.21 3 8540 113500
11 8540 7 115.74 3978 2 9424.5 80500
19 7930 6 120.96 7056.72 2 9089 75900
2 7320 6 110.88 4444.56 2 8235 109000
6 7320 7 365.04 6251.85 3 8509.5 160000
8 7625 7 212.76 3959.64 3 8936.5 120000
0 7930 7 213.93 3920.4 3 9028 135900
6 8540 7 243.54 3959.64 3 9699 121000
15 9760 6 178.02 4038.03 2 10888.5 85000
3 8540 7 248.04 3921.57 3 9790.5 133000
0 9455 7 231.84 4430.07 3 10797 143000
2 10065 7 227.52 4116.42 3 11224 130000
0 9760 7 221.76 4194.81 3 11193.5 135000
2 9455 7 262.8 3920.4 3 10675 141000
0 9455 7 229.32 3920.4 3 10675 125000
0 7320 7 232.2 4822.11 3 8875.5 172900
0 7320 7 246.42 4137.57 3 8723 177755
0 7625 7 198.72 4116.42 3 8997.5 125000
0 7015 7 261 3920.4 3 8601 173500
0 7015 7 296.28 3920.4 3 8570.5 169000
0 7320 6 222.48 4743.72 3 8784 167950
0 7320 7 231.21 3920.4 3 8723 145000
0 7015 7 221.76 4273.2 3 8662 159900
0 7015 7 254.34 4193.82 3 8631.5 172267
0 7015 7 221.76 3951.72 3 8631.5 156900
0 7015 7 254.88 3920.4 3 8570.5 169900
7 7015 7 185.04 5880.6 3 8631.5 129900
26 6405 7 236.88 5841.36 2 8235 109900
13 5795 6 227.52 3998.79 3 7472.5 120000
7 6710 6 162 4038.03 3 8570.5 140000
7 7015 6 106.38 3982.23 1 8814.5 83000
0 6405 7 246.42 5381.1 3 8113 175000
7 6100 8 181.44 4041 3 7869 117500
0 6100 7 234.9 3998.79 3 7869 155500
2 6100 7 236.43 3920.4 3 7808 158000
7 5795 6 166.32 4167 2 8082.5 115000
6 7930 7 238.32 4194.81 3 10065 133500
4 7930 7 221.76 3920.4 3 9973.5 128000
5 8845 7 179.82 6115.86 3 11102 105000
16 10065 6 139.41 3998.79 1 11864.5 90000
12 3965 7 300.06 3920.4 3 4575 270000
26 4270 6 137.34 2548.26 1 5368 70000
3 4575 6 107.73 4586.85 2 5703.5 98000
1 3965 7 165.24 3175.56 3 5307 103900
6 3660 7 257.04 2695.95 2 5398.5 101100
1 3965 7 165.24 3160.89 2 5368 107900
15 1830 6 101.97 450 1 4209 62000
1 1525 7 111.78 2077.83 2 4087 96750
36 1830 5 199.44 900 2 4087 79500
0 1525 7 110.34 1176.12 2 3995.5 97900
0 1525 7 171.9 1881.81 2 4026 103900
3 1830 6 155.52 984.42 2 3904 70000
26 3050 6 165.78 2621.7 2 5154.5 175000
65 3050 5 214.56 900 2 5185 80000
25 3050 6 124.92 675 1 5154.5 60000
0 7930 7 282.6 4390.83 3 7625 144500
20 4575 6 116.64 4038.03 2 6496.5 97000
19 4575 5 103.32 3976.38 2 6252.5 95000
0 3965 7 203.49 4091.85 3 5917 204080
", header = TRUE)
```

</details>

Na připravených datech stačí odhadnout model a vypsat jeho standardní souhrn:

```r
model_plny <- lm(price ~ age + inst + rooms + area + land + baths + dist,
                 data = nemovitosti)
summary(model_plny)
```

```text

Call:
lm(formula = price ~ age + inst + rooms + area + land + baths + 
    dist, data = nemovitosti)

Residuals:
   Min     1Q Median     3Q    Max 
-94536 -19379  -1481  16274 126756 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept) -1.088e+04  1.287e+04  -0.845  0.39856    
age         -3.675e+02  6.014e+01  -6.110 2.96e-09 ***
inst        -4.483e+00  1.622e+00  -2.763  0.00607 ** 
rooms        3.845e+03  2.422e+03   1.587  0.11343    
area         3.342e+02  3.748e+01   8.916  < 2e-16 ***
land         1.169e+00  5.207e-01   2.244  0.02552 *  
baths        1.014e+04  3.544e+03   2.860  0.00452 ** 
dist         3.088e+00  1.619e+00   1.907  0.05745 .  
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 29400 on 313 degrees of freedom
Multiple R-squared:  0.5475,	Adjusted R-squared:  0.5373 
F-statistic: 54.09 on 7 and 313 DF,  p-value: < 2.2e-16
```

Koeficient u `age` říká, že další rok stáří je v modelu spojen s cenou nižší přibližně o **367,47 dolaru**, pokud se ostatní zahrnuté údaje nemění. Celý model vysvětluje **54,75 %** rozptylu cen; upravený index determinace vychází **0,5373**.

F-test na hladině 0,05 zamítá hypotézu, že jsou všechny sklony nulové. U jednotlivých proměnných je výsledek různý. Pro `rooms` a `dist` na téže hladině nulový koeficient nezamítáme: při zahrnutí ostatních proměnných se jejich nenulový vztah k ceně neprokázal. U `age`, `inst`, `area`, `land` a `baths` nulovou hypotézu zamítáme. Než začneme proměnné vyřazovat, zkontrolujeme jejich vzájemnou závislost:

```r
cor(nemovitosti$inst, nemovitosti$dist)
library(car)
vif(model_plny)
```

```text
[1] 0.9165934
     age     inst    rooms     area     land    baths     dist 
1.420093 7.396461 1.763687 2.034356 1.269579 2.761292 6.537476 
```

Obě vzdálenosti spolu silně kladně korelují a jejich VIF přesahuje 5. Zkusíme proto model bez vzdálenosti ke spalovně, tedy bez `dist`. Počet pokojů `rooms` zatím ponecháme a jeho p-hodnotu znovu posoudíme v upraveném modelu:

```r
model_bez_dist <- lm(price ~ age + inst + rooms + area + land + baths,
                     data = nemovitosti)
summary(model_bez_dist)
vif(model_bez_dist)
```

```text

Call:
lm(formula = price ~ age + inst + rooms + area + land + baths, 
    data = nemovitosti)

Residuals:
    Min      1Q  Median      3Q     Max 
-101770  -19547    -918   16591  125038 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept) -4792.1730 12516.6764  -0.383  0.70208    
age          -360.9691    60.2965  -5.987 5.85e-09 ***
inst           -1.7304     0.7441  -2.326  0.02068 *  
rooms        3940.0555  2431.5851   1.620  0.10616    
area          324.3653    37.2804   8.701  < 2e-16 ***
land            1.0175     0.5168   1.969  0.04986 *  
baths       10682.8192  3547.6614   3.011  0.00281 ** 
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 29520 on 314 degrees of freedom
Multiple R-squared:  0.5422,	Adjusted R-squared:  0.5335 
F-statistic: 61.98 on 6 and 314 DF,  p-value: < 2.2e-16

     age     inst    rooms     area     land    baths 
1.415532 1.542947 1.762934 1.996060 1.240156 2.743280 
```

Po odebrání `dist` vychází index determinace **0,5422**, takže se podíl vysvětleného rozptylu změnil jen málo. VIF všech vysvětlujících proměnných klesl pod 3. U `rooms` ani teď na hladině 0,05 nulový koeficient nezamítáme; ostatní sklony jsou na této hladině statisticky významné.

Další možností je nechat výběr proměnných na postupu podle AIC. Funkce `step()` porovná modely a vrátí vybraný model. Volba `trace = 0` skryje průběžné výpisy. Porovnáme AIC vybraného modelu s původním modelem:

```r
model_krok <- step(model_plny, direction = "both", trace = 0)
AIC(model_plny, model_krok)
```

```text
           df      AIC
model_plny  9 7526.245
model_krok  9 7526.245
```

Funkce `step()` tentokrát ponechala všechny vysvětlující proměnné a AIC zůstalo **7 526,245**. To není v rozporu s nevýznamnými t-testy některých parametrů na hladině 0,05: AIC porovnává celé modely podle jiného pravidla. Při rozhodování nejprve zvažujeme, které veličiny mají pro vysvětlení ceny smysl. Pak pomocí VIF posoudíme, zda se jejich informace příliš nepřekrývají. Nakonec zkontrolujeme rezidua: zda na sobě nesouvisejí, mají přibližně stálý rozptyl a pro použité testy vhodný tvar rozdělení. Nižší AIC tyto podmínky nezaručuje.

Následující kontrolu provedeme na modelu bez `dist`:

```r
dwtest(model_bez_dist, alternative = "two.sided")
white_test(model_bez_dist)
shapiro.test(residuals(model_bez_dist))
```

```text
	Durbin-Watson test

data:  model_bez_dist
DW = 1.1299, p-value = 2.452e-15
alternative hypothesis: true autocorrelation is not 0

White's test results

Null hypothesis: Homoskedasticity of the residuals
Alternative hypothesis: Heteroskedasticity of the residuals
Test Statistic: 73.66
P-value: 0

	Shapiro-Wilk normality test

data:  residuals(model_bez_dist)
W = 0.96649, p-value = 9.181e-07
```

Whiteův test i Shapiroův–Wilkův test na hladině 0,05 zamítají své nulové hypotézy. Rezidua tedy vykazují nestálý rozptyl a odchylku od normality. Vypsaná nula u Whiteovy p-hodnoty je výsledkem numerického výpočtu; neznamená přesně nulovou pravděpodobnost.

Durbinův–Watsonův test také zamítá nulovou autokorelaci. Používá ale pořadí nemovitostí v tabulce. Abychom z výsledku mohli vyvodit souvislost sousedních chyb, musí mít toto pořadí věcný smysl.

Model proto potřebuje další kontrolu a jeho běžné t-testy a intervaly vykládáme opatrně. Pomoci mohou vhodné transformace proměnných a prověření pozorování s velkým vlivem na odhad. Hodnoty nevyřazujeme jen proto, aby testy vyšly příznivěji.

## Časté chyby

> [!warning] Koeficient korelace jen pro přímku
> Vzorec $r_{xy}=s_{xy}/\sqrt{s_x^2 s_y^2}$ měří lineární vztah. Jak dobře data vystihuje křivka, například parabola, hyperbola nebo exponenciála, posuzujeme indexem determinace $R^2$ nebo indexem korelace $\sqrt{R^2}$. Samotná korelace mezi $x$ a $y$ její vhodnost nevyjadřuje.

> [!warning] Významný F-test, nevýznamné t-testy
> Významný F-test při nevýznamných jednotlivých t-testech může upozorňovat na multikolinearitu. Nejdříve zkontrolujeme VIF a vztahy mezi vysvětlujícími proměnnými. Jejich automatické vyřazování jen podle p-hodnot by mohlo odstranit i věcně důležitou informaci.

> [!warning] Durbin-Watsonova statistika mimo okolí 2
> DW se pohybuje od 0 do 4; hodnoty blízko 2 znamenají žádnou autokorelaci, blízko 0 pozitivní autokorelaci, blízko 4 negativní autokorelaci. Samotná odchylka od 2 bez pohledu na p-hodnotu testu nic neprokazuje — rozhoduje až test, ne vzdálenost od 2.

> [!warning] Nízký počet pozorování při stepwise výběru
> Orientační doporučení pro metodu ENTER je aspoň 20 pozorování na proměnnou, pro stepwise aspoň 40. Tyto počty samy nezaručují spolehlivost modelu; zvláště při malém vzorku může být výběr proměnných nestabilní i při příznivém AIC.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]]
- [[popisna-statistika|Popisná statistika a datové soubory]]
- [[testovani-hypotez|Testování statistických hypotéz]]
- [[kontingencni-tabulky|Kontingenční tabulky]]
- [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]]
- [[mask-r-tahak|Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.
