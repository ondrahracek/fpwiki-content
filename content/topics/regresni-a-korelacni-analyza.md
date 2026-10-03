---
title: "Regresní a korelační analýza"
course: mask
type: topic
tags: [mask, statistika, regrese, korelace, r]
sources: ["raw/mask/04 regresní analýza.pdf", "raw/mask/04 regresní analýza - návod R.pdf"]
created: 2026-10-02
updated: 2026-10-02
---

# Regresní a korelační analýza

> [!tldr] V kostce
> - **Regresní analýza** zkoumá jednostrannou závislost vysvětlované proměnné $y$ na vysvětlujících proměnných $x$ (příčina → následek); **korelační analýza** měří intenzitu (těsnost) vzájemné závislosti.
> - Parametry regresní funkce se odhadují **metodou nejmenších čtverců** — minimalizací součtu čtverců reziduí $\sum(y_i-\hat y_i)^2$.
> - Kvalitu fitu měří **index determinace** $R^2$; obecnou těsnost závislosti **index korelace** $I=\sqrt{R^2}$, který je pro regresní přímku roven **koeficientu korelace** $r_{xy}$.
> - Když přímka nestačí, volí se **parabolická, polynomická, hyperbolická nebo logaritmická** regrese (stále lineární v parametrech, odhad metodou nejmenších čtverců) nebo **exponenciální** regrese (nelineární v parametrech, odhad přes `nls2`).
> - **Vícenásobná regrese** rozšiřuje model o více regresorů; vyžaduje výběr proměnných (ENTER/stepwise), ověření šesti předpokladů modelu a kontrolu multikolinearity přes VIF.
> - V R: `lm()`, `nls2()`, `summary()`, `confint()`, `predict()`, `step()`, `car::vif()`, `lmtest::dwtest()`, `whitestrap::white_test()`, `shapiro.test()`.

## Základní pojmy

[[mask|Metody aplikované statistiky]] pracuje se dvěma znaky $x$ a $y$ zjištěnými na stejných jednotkách. **Regresní analýza** se zabývá jednostrannými závislostmi, kdy proti sobě stojí vysvětlující (nezávisle) proměnná $x$ v úloze příčiny a vysvětlovaná (závisle) proměnná $y$ v úloze následku. **Korelační analýza** se zabývá vzájemnými, většinou lineárními závislostmi; důraz je kladen na intenzitu vztahu. Oba přístupy se v praxi prolínají — nejdřív se zvolí a odhadne regresní funkce, pak se její kvalita vyjádří korelační charakteristikou.

Hlavním úkolem obou analýz je přispět k poznání vztahů mezi znaky — podat matematický popis systematických okolností, které závislost provázejí, a nalézt funkci, která nejlépe vystihuje její charakter (**regresní funkce**).

Druh regresní analýzy určuje struktura datového souboru:

- **dvourozměrný datový soubor** (jedna $x$, jedna $y$) → **regresní analýza dvou proměnných**,
- **vícerozměrný datový soubor** (více $x_1,\dots,x_p$) → **vícenásobná regresní analýza**.

Volba konkrétní regresní funkce by měla vycházet jak z **ekonomické teorie** (ta napovídá, zda závislost roste, nebo klesá, zda je přímková, nebo zakřivená), tak z **grafické a matematicko-statistické analýzy** dat — oba přístupy je vhodné kombinovat.

## Metoda nejmenších čtverců

Rozlišují se **teoretická regresní funkce** $\eta = f(x;\beta_0,\beta_1,\dots,\beta_p)$ — neznámá, populační, daná neznámými parametry $\beta_i$ — a **empirická regresní funkce** $\hat y = f(x; b_0,b_1,\dots,b_p)$, jejíž odhadnuté parametry $b_i$ jsou odhadem $\beta_i$ vypočteným z konkrétních dat. Odchylky skutečných hodnot od empirické funkce, $e_i=y_i-\hat y_i$, se nazývají **rezidua**.

Nejpoužívanější metodou odhadu parametrů je **metoda nejmenších čtverců (OLS)**: hledají se takové parametry, pro které je součet čtverců reziduí minimální,

$$\sum_{i=1}^n (y_i - \hat y_i)^2 \to \min.$$

Odhad probíhá ve čtyřech krocích: (1) posoudit dostupné informace o charakteru závislosti, (2) navrhnout jeden nebo víc typů regresních funkcí, (3) odhadnout jejich parametry metodou nejmenších čtverců, (4) porovnat vhodnost odhadnutých funkcí a při neuspokojivém výsledku zvolit jiný typ.

![[mask-ra-primka-rezidua.png|Vlevo týdenní výdaje domácnosti podle počtu členů s regresní přímkou ŷ = 108,7 + 368,0·x a R² = 0,9995; vpravo rezidua ve zvětšeném měřítku od −24,7 do 17,3 Kč jako červené úsečky od nulové přímky]]

Obrázek ukazuje přesně to, co metoda minimalizuje: délky červených úseček jsou rezidua $e_i$, metoda nejmenších čtverců volí přímku tak, aby součet jejich čtverců byl nejmenší možný.

## Regresní přímka

Nejjednodušší regresní funkcí je **regresní přímka**:

$$\eta = \beta_0 + \beta_1 x, \qquad \hat y = b_0 + b_1 x.$$

Koeficient $b_1$ udává změnu průměru $y$ při jednotkové změně $x$; jeho znaménko určuje, zda je závislost přímá, nebo nepřímá.

### V R

Vstupní data se nahrají buď ze souboru (`d <- read.table("data.txt")`, případně `d <- read.table(file.choose())`), nebo zapíší přímo jako vektory. Na šesti domácnostech sledujeme počet členů domácnosti a jejich týdenní výdaje:

```r
pocet_clenu <- c(1, 2, 3, 4, 5, 6)
tydenni_vydaje <- c(490, 820, 1230, 1570, 1950, 2320)
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

Odhadnutý model je $\hat y = 108{,}7 + 368{,}0\,x$. Sloupec `Pr(>|t|)` je p-hodnota t-testu $H_0:\beta_i=0$ proti $H_1:\beta_i\neq0$ pro každý parametr — obě p-hodnoty jsou hluboko pod 0,05, oba parametry jsou tedy statisticky významné. `Multiple R-squared` je index determinace $R^2=0{,}9995$: model vysvětluje 99,95 % rozptylu výdajů.

Pro doplňkový přehled slouží přímé přístupové funkce:

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

`coef()` vrací odhadnuté parametry $b_0,b_1$, `fitted()` predikce $\hat y_i$ pro pozorované $x_i$, `residuals()` rezidua $e_i=y_i-\hat y_i$ — stejná čísla, která na obrázku výše tvoří délky červených úseček.

Intervaly spolehlivosti pro parametry a pro predikci v nových bodech $x$ (zde 7 a 8 členů domácnosti):

```r
confint(model, level = 0.95)
nove <- data.frame(pocet_clenu = c(7, 8))
predict(model, newdata = nove, interval = "confidence", level = 0.95)
predict(model, newdata = nove, interval = "prediction", level = 0.95)
```

```text
                2.5 %   97.5 %
(Intercept)  63.64981 153.6835
pocet_clenu 356.44074 379.5593
       fit     lwr      upr
1 2684.667 2639.65 2729.684
2 3052.667 2997.03 3108.303
       fit      lwr      upr
1 2684.667 2618.600 2750.733
2 3052.667 2978.953 3126.381
```

`interval = "confidence"` dává interval spolehlivosti pro **střední hodnotu** $y$ při daném $x$, `interval = "prediction"` širší interval pro **jednotlivé budoucí pozorování** — ten musí zahrnout i rozptyl kolem regresní přímky, proto je vždy širší.

### Diagnostika modelu

Platnost závěrů z regresní přímky stojí na předpokladech o reziduích: **absenci autokorelace**, **stálosti rozptylu (homoskedasticitě)** a **normalitě**. V R se ověřují takto:

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

Durbinův–Watsonův test má $H_0$: v modelu není problém s autokorelací, proti $H_1$: v modelu problém s autokorelací je. Statistika DW se pohybuje mezi 0 a 4, hodnota blízko 2 znamená žádnou autokorelaci. Zde p-hodnota 0,96 je výrazně nad 0,05, $H_0$ se nezamítá.

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

Shapiro–Wilkův test má $H_0$: rezidua pocházejí z normálního rozdělení. P-hodnota 0,73 opět nevede k zamítnutí — všechny tři předpoklady model splňuje.

![[mask-ra-diagnostika-rezidui.png|Vlevo: rezidua regresní přímky proti predikovaným hodnotám, rovnoměrně rozptýlená kolem nuly. Vpravo: Q-Q graf reziduí proti normálnímu rozdělení]]

Grafická kontrola normality doplňuje Shapiro–Wilkův test: body v levém panelu by měly být rovnoměrně rozptýlené po obou stranách vodorovné osy (bez trychtýře či oblouku), body v Q-Q grafu by měly ležet kolem přímky. U malého počtu pozorování se dává přednost testu; u velkého datového souboru se předpoklad normality reziduí stává méně kritickým díky centrální limitní větě.

> [!example] Příklad: Regresní přímka
> V souboru s údaji o hodnotě produkce (v milionech Kč, proměnná $y$) a výši investic (ve stovkách tisíc Kč, proměnná $x$) za rok 2015 u dvanácti vybraných soukromých firem s více než 30 zaměstnanci byla metodou nejmenších čtverců odhadnuta regresní přímka modelující závislost hodnoty produkce na výši investic.
>
> Výsledek: $\hat y = 32{,}74 + 2{,}15\,x$.
>
> Koeficient $b_1=2{,}15$ říká, že se zvýšením investic o 100 000 Kč vzroste produkce v průměru o $2{,}15\cdot 1\,000\,000=2\,150\,000$ Kč.
>
> Dosazením libovolné hodnoty investic do empirické regresní funkce dostaneme predikci produkce, například pro třináctou firmu s investicemi $x=34$: $\hat y_{13} = b_0 + b_1\cdot 34 \doteq 105{,}81$ milionu Kč (se zaokrouhlenými koeficienty $32{,}74 + 2{,}15\cdot 34 \doteq 105{,}8$).

## Nelineární a vyšší řády regresních funkcí

Když přímka závislost nevystihuje, nabízí se další **lineární funkce** — tedy funkce lineární ve svých parametrech, zapsatelné ve tvaru $\eta=\beta_0+\beta_1 f_1(x)+\dots+\beta_p f_p(x)$ se známými funkcemi $f_i$ a neznámými parametry $\beta_i$. I tyto parametry se odhadují metodou nejmenších čtverců, stejně jako u přímky:

$$
\begin{aligned}
\text{parabolická regrese: }\quad &\hat y = b_0 + b_1 x + b_2 x^2\\
\text{polynomická regrese $p$-tého stupně: }\quad &\hat y = b_0 + b_1 x + b_2 x^2 + \dots + b_p x^p\\
\text{hyperbolická regrese: }\quad &\hat y = b_0 + b_1\frac1x\\
\text{logaritmická regrese: }\quad &\hat y = b_0 + b_1\ln x
\end{aligned}
$$

Naproti tomu **nelineární funkce** nelze do tvaru $\eta=\beta_0+\beta_1 f_1(x)+\dots$ převést — je nelineární i ve svých parametrech. Jejich parametry nelze získat přímo metodou nejmenších čtverců, ale vhodnou transformací nebo iterativně. Základní příklad je **exponenciální regrese**:

$$\hat y = b_0 \cdot b_1^{\,x}.$$

![[mask-ra-nelinearni-krivky.png|Vlevo: parabolická a exponenciální regresní funkce proložené daty ročního zisku firmy. Vpravo: hyperbolická regresní funkce proložená daty týdenních výdajů domácnosti]]

### V R — parabolická regrese

Na ročních ziscích firmy (šest let) se parabolická regrese odhadne přidáním kvadratického členu `I(x^2)`:

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

Odhadnutá parabola $\hat y = 164{,}6 - 76{,}6\,x + 32{,}1\,x^2$ vysvětluje 99,8 % rozptylu zisku — podstatně víc, než by vysvětlila přímka proložená stejně rostoucími daty.

### V R — exponenciální regrese

Nelineární funkce se v R odhadují funkcí `nls2()` ze stejnojmenného balíčku. Bez zadaných počátečních hodnot R upozorní, že parametry nastavil na 1, a odhad dopočítá iteračně:

```r
library(nls2)
model_exp <- nls2(zisk ~ b1 * exp(b2 * rok))
summary(model_exp)
```

```text
Formula: zisk ~ b1 * exp(b2 * rok)

Parameters:
   Estimate Std. Error t value Pr(>|t|)    
b1 65.35423    3.57542   18.28 5.27e-05 ***
b2  0.43161    0.01013   42.63 1.81e-06 ***
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Residual standard error: 11.89 on 4 degrees of freedom
```

Stejnou křivku lze zapsat i v mocninném tvaru $\hat y=b_1\cdot b_2^{x}$:

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
```

Obě varianty popisují stejnou křivku ($b_2^{\text{mocninný}} = e^{\,b_2^{\text{exponenciální}}}$, zde $e^{0{,}4316}\approx 1{,}540$) a mají totožnou reziduální chybu — je to jen otázka parametrizace.

### V R — hyperbolická regrese

Hyperbolická regrese se odhadne jako obyčejná lineární regrese na transformované proměnné `I(1/x)`:

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

Model $\hat y = 2180{,}7 - \dfrac{1920{,}0}{x}$ vysvětluje jen 76,3 % rozptylu — u těchto dat je hyperbola podstatně horší volbou než přímka ($R^2=0{,}9995$). Právě k takovému porovnání slouží index determinace: nízká hodnota signalizuje, že zvolený typ funkce k datům nesedí.

> [!example] Příklad: Parabolická regrese
> Prodejna počítačových her nechala prodavače absolvovat kurz prodejních dovedností. Při dvaceti měřeních sledovala, kolik zákazníků navštíví prodejnu během prodejní doby (proměnná $x$) a jaká je toho dne tržba v tisících Kč (proměnná $y$). Zároveň chtěla zjistit, zda při rostoucím počtu zákazníků stačí stávající počet prodavačů.
>
> Výsledek: $\hat y = -60{,}3 + 4{,}55\,x - 0{,}05\,x^2$.
>
> Záporný koeficient $b_2$ znamená, že tržba s počtem zákazníků neroste neomezeně — funkce má maximum. Derivací a položením rovné nule vychází maximum přibližně při 45 zákaznících: nad tímto počtem zřejmě prodejna další zákazníky obsloužit nestíhá.

> [!example] Příklad: Hyperbolická regrese
> V podniku se podle interního účetnictví sledovala závislost vlastních nákladů na jednotku produkce v Kč (proměnná $y$) na objemu produkce v tisících kusů (proměnná $x$).
>
> Výsledek: $\hat y = -96{,}78 + \dfrac{250\,528{,}88}{x}$.
>
> Záporná hodnota $b_1$ v čitateli ukazuje klesající náklady na jednotku s rostoucím objemem produkce — typický projev úspor z rozsahu, který hyperbola dobře zachycuje.

## Kvalita regresní funkce a korelační analýza

Kvalitu odhadnuté regresní funkce vyjadřuje **index determinace**:

$$R^2 = \frac{s^2_{\hat y}}{s^2_y} = 1 - \frac{s^2_{y-\hat y}}{s^2_y}.$$

Čím blíž je $R^2$ k 1, tím silnější je závislost; v procentech udává, jakou část rozptylu závisle proměnné $y$ se podařilo vysvětlit zvolenou regresní funkcí. Nízký index determinace může signalizovat špatně zvolený typ regresní funkce, ne nutně absenci závislosti.

Obecnou mírou těsnosti závislosti — platnou pro libovolný typ regresní funkce — je **index korelace** $I=\sqrt{R^2}$. Je-li zvolenou funkcí regresní přímka, index korelace je roven (až na znaménko) **koeficientu korelace**:

$$r_{xy} = \frac{s_{xy}}{\sqrt{s^2_x\cdot s^2_y}}.$$

Koeficient korelace nabývá hodnot od $-1$ do $+1$: znaménko určuje typ závislosti (pozitivní, nebo negativní), absolutní hodnota její sílu — čím blíž k 0, tím je závislost slabší.

![[mask-ra-korelace-sila.png|Čtyři rozptylové grafy simulovaných dvojic (x, y) se silou lineární závislosti klesající od r = 0,97 přes r = 0,33 a r = 0,17 po r = -0,75]]

S rostoucí absolutní hodnotou $r$ se body v rozptylovém grafu víc blíží přímce; kolem $r\approx 0$ je mezi $x$ a $y$ patrná jen náhodná rozptýlenost bez lineárního trendu.

### V R

```r
cor(pocet_clenu, tydenni_vydaje)
```

```text
[1] 0.9997441
```

Hodnota 0,9997 odpovídá $\sqrt{R^2}=\sqrt{0{,}9995}$ ze summary regresní přímky výše — přesně tak, jak definice říká: pro přímkovou regresi je koeficient korelace roven indexu korelace.

> [!example] Příklad: Koeficient korelace
> Pro stejná data o hodnotě produkce a výši investic dvanácti firem jako u regresní přímky byl spočten koeficient korelace mezi oběma proměnnými.
>
> Výsledek: $r_{xy} = 0{,}739$ — silná kladná závislost hodnoty produkce na výši investic.

## Vícenásobná regrese a korelace

Pokud na závisle proměnnou $y$ působí víc vysvětlujících proměnných současně, analyzuje se zvlášť vliv každé z nich a výsledná regresní funkce se konstruuje jako součet jednoduchých regresních funkcí:

$$\eta = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \dots + \beta_p x_p, \qquad \hat y = b_0 + b_1 x_1 + \dots + b_p x_p.$$

### Výběr proměnných

- **Metoda ENTER** — vloží do modelu všechny proměnné najednou. Použije se, když jde o index determinace celého modelu, o vliv každé nezávislé proměnné při kontrole vlivu ostatních, nebo o relativní důležitost proměnných. Vyžaduje poměrně vysoký počet pozorování — aspoň 20 na každou proměnnou.
- **Metoda stepwise (postupná regrese)** — hledá „nejlepší" model (co nejmíň proměnných, co nejkvalitnější predikce) na základě F-testu; pořadí vstupu/odebrání proměnných řídí program, ne uživatel. Varianta **forward** proměnné postupně přidává, varianta **backward** naopak začíná plným modelem a proměnné postupně odebírá. Pořadí vkládání ovlivňuje odhad důležitosti proměnných, proto je třeba metodu zvolit uvážlivě. Stepwise vyžaduje ještě víc pozorování — aspoň 40 na proměnnou.

### Postup odhadu

1. ověření předpokladů regresního modelu,
2. samotný odhad parametrů,
3. reziduální analýza výsledného modelu.

Důležitost každého parametru $b_i$ v modelu ověřuje **t-test**: $H_0:\beta_i=0$ (proměnná je v modelu nevýznamná) proti $H_1:\beta_i\neq0$ (proměnná je významná). Při nezamítnutí $H_0$ by proměnná — a s ní spojený regresor — v modelu neměla zůstat.

### Předpoklady modelu

1. Závisle proměnná $y$ musí být aspoň intervalového typu (ne binární, diskrétní s málo hodnotami apod.) — jinak je na místě logistická regrese.
2. Nezávislé proměnné $x_1,\dots,x_p$ jsou rovněž aspoň intervalového typu, mohou být i alternativní.
3. Nezávislé proměnné by mezi sebou neměly být příliš vysoce korelované — **multikolinearita**.
4. V datech nesmí být odlehlé či extrémní hodnoty; regresní analýza je na ně citlivá a mohou vážně narušit kvalitu odhadů.
5. Proměnné musí být ve vzájemně lineárním vztahu — vícenásobná lineární regrese je založená na Pearsonově koeficientu korelace, takže nelineární vztahy mezi proměnnými zůstanou neodhalené.
6. Proměnné mají mít [[nahodne-veliciny-a-rozdeleni|normální rozložení]]; význam tohoto předpokladu ustupuje do pozadí u dostatečně velkého datového souboru díky centrální limitní větě.

Normalita se u menšího počtu pozorování ověřuje stejnými testy jako u jiných znaků (viz [[testovani-hypotez|testování statistických hypotéz]]) — Shapiro–Wilkovým nebo Kolmogorovovým–Smirnovovým testem — nebo graficky grafem reziduí proti predikovaným hodnotám, kde by body měly být rovnoměrně rozptýlené po obou stranách vodorovné osy.

### Multikolinearita

Multikolinearita vzniká, když vysvětlující proměnné silně závisejí jedna na druhé. Je nežádoucí, protože:

- výsledky regrese jsou pak nespolehlivé,
- zvyšuje pravděpodobnost, že se důležitá proměnná jeví jako statisticky nevýznamná a bude z modelu vyřazena,
- směrodatné odchylky odhadnutých parametrů jsou vysoké, testová kritéria t-testů nízká, p-hodnoty vysoké.

Pozná se podle vysokých korelačních koeficientů mezi regresory (nad 0,75), podle toho, že celkový F-test modelu je významný, ale jednotlivé t-testy parametrů ne, nebo softwarově přes **VIF (Variance Inflation Factor)**: hodnoty $1<\text{VIF}<5$ jsou varující, $\text{VIF}>5$ (přísněji $>10$) značí vysokou multikolinearitu.

Řešení: je-li multikolinearita způsobená silnou závislostí dvou proměnných, jednu z nich se z modelu vyřadí; je-li způsobená závislostí víc proměnných najednou, použije se metoda hlavních komponent a pracuje se s novými, nekorelovanými proměnnými.

### Další ukazatele kvality modelu

- **F-test** — testuje hypotézu, že všechny regresní koeficienty jsou rovny nule, proti alternativě, že aspoň jeden v modelu být má (celková významnost modelu).
- **RMSE** (odmocnina z reziduálního rozptylu) — absolutní měřítko vhodnosti funkce (na rozdíl od indexu determinace, který je relativní); nižší hodnota znamená lepší fit.
- **AIC** (Akaikeho informační kritérium) a **BIC** (Bayesovo informační kritérium) — čím nižší hodnoty obou kritérií, tím lepší model; používají se hlavně při stepwise výběru proměnných.

### V R

Pro vícenásobnou regresi je postup v R rozšířením postupu pro regresní přímku — přibývá výběr proměnných a kontrola multikolinearity:

```r
data <- read.table("4_4.txt", header = TRUE)
model_plny <- lm(y ~ x1 + x2 + x3 + x4, data = data)
model_krok <- step(model_plny, direction = "both")
summary(model_krok)

library(car)
vif(model_krok)

library(lmtest)
dwtest(model_krok)

library(whitestrap)
white_test(model_krok)

shapiro.test(residuals(model_krok))
```

`step()` provádí stepwise výběr podle AIC, `vif()` spočítá Variance Inflation Factor pro každý regresor v modelu, zbylé tři volání ověřují stejné tři předpoklady (autokorelace, homoskedasticita, normalita reziduí) jako u regresní přímky výše.

> [!example] Příklad: Vícenásobná regrese
> U souboru nemovitostí prodaných v roce 1981 se sledovala prodejní cena v dolarech v závislosti na stáří nemovitosti, počtu sousedících nemovitostí, velikosti podlahové plochy a pozemku, vzdálenosti k mezistátní silnici, vzdálenosti ke spalovně a počtu pokojů a koupelen. Úkolem bylo odhadnout model, který by dobře popisoval data.
>
> Postup: odhad plného modelu → stepwise analýza podle AIC → ověření předpokladů.
>
> Diagnostika odhaleného modelu ukázala tři problémy: (1) **nelinearita** — mezi některými vysvětlujícími proměnnými a cenou je zjevně jiný než lineární vztah, řešením je zkusit u nich druhou mocninu; (2) **multikolinearita** mezi dvojicí proměnných popisujících vzdálenost (k silnici a ke spalovně) — doporučeno jednu z nich vynechat; (3) **odlehlá pozorování** — vhodné je provést ještě test a případně je vyřadit. Výsledný model obsahoval i nevýznamné proměnné, jako celek však byl statisticky významný s přibližně průměrným indexem determinace; dalšího zlepšení šlo dosáhnout snížením AIC pomocí stepwise regrese.

## Časté chyby

> [!warning] Koeficient korelace jen pro přímku
> Vzorec $r_{xy}=s_{xy}/\sqrt{s_x^2 s_y^2}$ měří lineární závislost. Pro nelineární regresní funkci (parabola, hyperbola, exponenciála) se kvalita fitu posuzuje indexem determinace $R^2$, případně obecným indexem korelace $\sqrt{R^2}$ — ne koeficientem korelace mezi $x$ a $y$.

> [!warning] Významný F-test, nevýznamné t-testy
> Pokud je celkový F-test modelu významný, ale jednotlivé t-testy parametrů ne, nejde nutně o chybně zvolené proměnné — je to typický příznak multikolinearity. Řešením je zkontrolovat VIF, ne mechanicky vyřazovat „nevýznamné" proměnné.

> [!warning] Durbin-Watsonova statistika mimo okolí 2
> DW se pohybuje od 0 do 4; hodnoty blízko 2 znamenají žádnou autokorelaci, blízko 0 pozitivní autokorelaci, blízko 4 negativní autokorelaci. Samotná odchylka od 2 bez pohledu na p-hodnotu testu nic neprokazuje — rozhoduje až test, ne vzdálenost od 2.

> [!warning] Nízký počet pozorování při stepwise výběru
> Metoda ENTER potřebuje aspoň 20 pozorování na proměnnou, stepwise regrese aspoň 40. Při menším vzorku jsou výsledky výběru proměnných nespolehlivé bez ohledu na to, jak hezky vychází AIC.

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
