---
title: "Testování statistických hypotéz"
course: mask
type: topic
tags: [mask, statistika, testovani-hypotez, t-test, normalita, neparametricke-testy]
sources: [raw/mask/03 testy hypotéz.pdf, raw/mask/03 testování hypotéz - návod R 01.pdf, raw/mask/03 testování hypotéz - návod R 02.pdf, raw/mask/příklady 03.docx, raw/mask/příklady 01 a 02.docx, raw/mask/data k příkladům/7.txt, raw/mask/data k příkladům/9.txt]
created: 2026-10-02
updated: 2026-10-02
---

# Testování statistických hypotéz

> [!tldr] V kostce
> - Test porovnává tvrzení $H_0$ s alternativou $H_1$ pomocí testového kritéria spočteného z výběru; padne-li kritérium do kritického oboru $W$, $H_0$ zamítáme.
> - Rozhodnutí nese dva typy chyb: chybu I. druhu ($\alpha$, zamítnutí platné $H_0$) a chybu II. druhu ($\beta$, přijetí neplatné $H_0$). Hladina významnosti $\alpha$ se volí předem, obvykle 0,05.
> - Pro střední hodnotu normálního rozdělení slouží jednovýběrový a párový t-test; pro srovnání dvou souborů F-test (rozptyly) a dvouvýběrový t-test (střední hodnoty).
> - Normalitu ověřuje Shapiro-Wilkův test, shodu s libovolným rozdělením Kolmogorov-Smirnovův test; při porušené normalitě nastupují neparametrické testy (Wilcoxonovy, Kruskalův-Wallisův, mediánový, Friedmanův).
> - Rozhodnutí lze číst dvěma rovnocennými způsoby — podle polohy kritéria vůči $W$, nebo podle p-hodnoty vůči $\alpha$.

Testy statistických hypotéz jsou nástroj [[mask|Metod aplikované statistiky]] pro rozhodování o parametrech nebo tvaru rozdělení na základě náhodného výběru, nikoli vyčerpávajícího šetření celého základního souboru. Vycházejí z charakteristik, které lze předem spočítat jako [[popisna-statistika|popisnou statistiku]] výběru, a z rozdělení uvedených u [[nahodne-veliciny-a-rozdeleni|náhodných veličin]] (normální, $t$, $F$).

## Statistická hypotéza a její test

**Statistická hypotéza** je předpoklad o parametru nebo tvaru rozdělení zkoumaného znaku — například že určitý typ auta má průměrnou spotřebu 7 l/100 km. Ověřit ji na celém základním souboru je obvykle neekonomické nebo technicky neproveditelné, a tak se posuzuje na výběru. **Testování hypotéz** je proces ověření správnosti nebo nesprávnosti hypotézy pomocí výsledků získaných náhodným výběrem.

Proti sobě stojí dvě hypotézy:

- **Nulová hypotéza $H_0$** — tvrzení o parametru nebo rozdělení, které chceme ověřit.
- **Alternativní hypotéza $H_1$** — staví se proti $H_0$ a určitým způsobem popírá její tvrzení.

Pro $H_0: \mu = \mu_0$ existují tři varianty $H_1$:

| Tvar $H_1$ | Zápis | Typ |
|---|---|---|
| nerovnost | $H_1: \mu \neq \mu_0$ | dvoustranná |
| větší | $H_1: \mu > \mu_0$ | jednostranná |
| menší | $H_1: \mu < \mu_0$ | jednostranná |

### Chyba I. a II. druhu

Protože je úsudek odvozen z náhodného výběru, může vést ke dvěma typům chybného rozhodnutí:

- **Chyba I. druhu** — zamítnutí $H_0$, ačkoliv ve skutečnosti platí. Pravděpodobnost $\alpha$.
- **Chyba II. druhu** — přijetí $H_0$, ačkoliv platí $H_1$. Pravděpodobnost $\beta$.

| Úsudek o $H_0$ | $H_0$ platí | $H_0$ neplatí |
|---|---|---|
| Nezamítá se | správné rozhodnutí, $1-\alpha$ | chyba II. druhu, $\beta$ |
| Zamítá se | chyba I. druhu, $\alpha$ | správné rozhodnutí, $1-\beta$ |

**Hladina významnosti** $\alpha$ je předem pevně zvolená pravděpodobnost chyby I. druhu (klasicky 5 %). Testovací postup je odvozen tak, aby při dané hladině významnosti zajišťoval minimální pravděpodobnost chyby II. druhu.

![[mask-th-chyba-i-ii.png|Dvě normální hustoty testového kritéria za platnosti H0 a H1 se svislou kritickou hodnotou a vyšrafovanými plochami alfa a beta]]

Obrázek ukazuje, proč jde o kompromis: posunutí kritické hodnoty $c$ doleva zmenší $\beta$, ale zvětší $\alpha$, a naopak. Pro danou hladinu $\alpha$ je $c$ jednoznačně určena rozdělením kritéria za platnosti $H_0$.

### Testové kritérium a kritický obor

**Testové kritérium** $T$ je statistika spočtená z výběru; aby bylo možné test provést, musí být známo jeho rozdělení za platnosti $H_0$.

**Kritický obor** $W$ je množina hodnot svědčících pro $H_1$. Je zkonstruován tak, aby

$$P(T \in W \mid H_0) = \alpha,$$

tedy aby pravděpodobnost, že výběr dá hodnotu kritéria v $W$ i při platné $H_0$, byla rovna zvolené hladině významnosti.

### Postup testování hypotézy

![[mask-ilu-postup-testovani.png|Čtyři kroky testu: formulace H0 a H1, testové kritérium T, hladina významnosti α a kritický obor W, závěr testu; T ∈ W znamená zamítnutí H0, T ∉ W znamená, že H0 nezamítáme; totéž rozhodnutí dává p-hodnota porovnaná s α]]

1. Formulace hypotéz $H_0$ a $H_1$.
2. Volba testového kritéria a výpočet jeho hodnoty.
3. Volba hladiny významnosti a sestrojení příslušného kritického oboru $W$.
4. Formulace závěru:
   - pokud $T \in W$: $H_1$ je testem prokázána na hladině významnosti $100\alpha\,\%$ (zamítáme $H_0$);
   - pokud $T \notin W$: $H_1$ není testem prokázána na hladině významnosti $100\alpha\,\%$ ; $H_0$ nezamítáme.

Rovnocennou alternativou je **p-hodnota**: udává, nakolik jsou data slučitelná s $H_0$. Čím menší p-hodnota, tím více data svědčí proti $H_0$. Rozhodovací pravidlo: $p \le \alpha \Rightarrow$ zamítáme $H_0$; $p > \alpha \Rightarrow$ $H_0$ nezamítáme. Obě cesty — kritický obor i p-hodnota — vedou vždy ke stejnému závěru; R u všech testů vrací p-hodnotu přímo.

## Jednovýběrový t-test

Test o střední hodnotě $\mu$ rozdělení $X \sim N(\mu, \sigma^2)$. Z výběru o rozsahu $n$ se určí charakteristiky $\bar{x}$ a $s^2$; testem se posuzuje vztah mezi zvoleným číslem $\mu_0$ a neznámou hodnotou $\mu$. Testové kritérium

$$T = \frac{\bar{x} - \mu_0}{s}\sqrt{n} \sim t_{n-1}$$

má Studentovo rozdělení o $n-1$ stupních volnosti.

| $H_0$ | $H_1$ | Kritický obor $W$ |
|---|---|---|
| $\mu \le \mu_0$ | $\mu > \mu_0$ | $t \ge t_{1-\alpha}(n-1)$ |
| $\mu = \mu_0$ | $\mu \neq \mu_0$ | $\lvert t \rvert \ge t_{1-\alpha/2}(n-1)$ |
| $\mu \ge \mu_0$ | $\mu < \mu_0$ | $t \le -t_{1-\alpha}(n-1)$ |

V R test provádí `t.test()`. Autobusová linka měla na trase průměrnou dobu jízdy 12 minut; po úpravě trasy se při devíti jízdách naměřily časy v minutách. Ovlivnila úprava trasy dobu jízdy?

```r
x <- c(12.5, 13.5, 11.9, 12.2, 13.0, 14.3, 12.2, 11.8, 14.0)
t.test(x, mu = 12, alternative = "two.sided")
```
```text
	One Sample t-test

data:  x
t = 2.6685, df = 8, p-value = 0.02843
alternative hypothesis: true mean is not equal to 12
95 percent confidence interval:
 12.11169 13.53275
sample estimates:
mean of x 
 12.82222 
```

`t` je testové kritérium, `df` stupně volnosti, `p-value` p-hodnota pro zvolenou alternativu a `mean of x` výběrový průměr. Zde $p = 0{,}02843 < 0{,}05$: úprava trasy průměrnou dobu jízdy (původně 12 minut) statisticky významně změnila.

> [!example] Příklad: Kontrola objemu lahví
> Pivovar plní lahve, deklarovaný objem je $\mu_0 = 0{,}5$ l. Náhodný výběr $n = 20$ lahví dal $\bar{x} = 0{,}492$ l, $s = 0{,}015$ l. Na hladině významnosti 5 % ověřte podezření, že pivovar lahve nedoplňuje.
>
> $H_0: \mu \ge 0{,}5$ l (objem je v pořádku nebo větší), $H_1: \mu < 0{,}5$ l (lahve jsou nedoplněné).
>
> $$t = \frac{0{,}492 - 0{,}5}{0{,}015}\sqrt{20} = -2{,}385, \qquad W = \{t \le -t_{0,95}(19)\} = \{t \le -1{,}729\}$$
>
> Protože $t \in W$, zamítáme $H_0$: na hladině významnosti 5 % se potvrdilo, že pivovar plní lahve pod deklarovaný objem.

Ze souhrnných charakteristik bez surových dat `t.test()` spustit nelze — kritérium a kritická hodnota se dopočítají přímo z definice pomocí `qt()`:

```r
xbar <- 0.492; s <- 0.015; n <- 20; mu0 <- 0.5
t <- (xbar - mu0) / s * sqrt(n)
t_krit <- qt(0.05, df = n - 1)
t
t_krit
```
```text
[1] -2.385139
[1] -1.729133
```

![[mask-th-t-jednostranny.png|Hustota Studentova t-rozdělení s 19 stupni volnosti, levostranný kritický obor t ≤ −1,729 vyšrafován, pozorované t = −2,385 v něm leží]]

Další dva příklady mají k dispozici surová data, takže je lze otestovat přímo `t.test()`:

**Životnost baterií.** Výrobce udává průměrnou životnost 10 hodin, na 11 bateriích byly naměřeny hodnoty v hodinách.

```r
x2 <- c(9.5, 10.5, 8.9, 9.2, 10.0, 8.5, 9.2, 8.8, 10.0, 9.5, 9.2)
t.test(x2, mu = 10, alternative = "two.sided")
```
```text
	One Sample t-test

data:  x2
t = -3.42, df = 10, p-value = 0.006548
alternative hypothesis: true mean is not equal to 10
95 percent confidence interval:
 8.994081 9.787737
sample estimates:
mean of x 
 9.390909 
```

$p = 0{,}006548 < 0{,}05$: skutečná životnost se od deklarovaných 10 hodin statisticky významně liší (baterie vydrží méně).

**Odpad materiálu.** Na deseti obráběných kusech byl naměřen odpad materiálu v procentech; testuje se rozdíl proti 4 % a zároveň normalita dat.

```r
x3 <- c(4.1, 4.0, 3.8, 3.9, 3.8, 3.8, 3.5, 3.7, 4.0, 4.0)
t.test(x3, mu = 4, alternative = "two.sided")
shapiro.test(x3)
```
```text
	One Sample t-test

data:  x3
t = -2.4922, df = 9, p-value = 0.0343
alternative hypothesis: true mean is not equal to 4
95 percent confidence interval:
 3.732925 3.987075
sample estimates:
mean of x 
     3.86 

	Shapiro-Wilk normality test

data:  x3
W = 0.93156, p-value = 0.4634
```

$p = 0{,}0343 < 0{,}05$: průměrný odpad se od 4 % statisticky významně liší (výběrový průměr 3,86 %). Shapiro-Wilkův test dává $p = 0{,}4634 > 0{,}05$, předpoklad normality pro t-test je v pořádku.

## Párový t-test

Používá se, když jsou měření závislá — na stejných objektech se měří dvě hodnoty $(X_i, Y_i)$ a vyhodnocují se jejich diference $D_i = X_i - Y_i$, kde $D \sim N(\mu_D, \sigma_D^2)$. Z $n$ dvojic se určí $\bar{d}$ a $s_d^2$; testuje se vztah mezi zvoleným číslem $\mu_0$ (obvykle 0) a $\mu_D$. Testové kritérium

$$T = \frac{\bar{d} - \mu_0}{s_d}\sqrt{n} \sim t_{n-1}.$$

| $H_0$ | $H_1$ | Kritický obor $W$ |
|---|---|---|
| $\mu_D \le \mu_0$ | $\mu_D > \mu_0$ | $t \ge t_{1-\alpha}(n-1)$ |
| $\mu_D = \mu_0$ | $\mu_D \neq \mu_0$ | $\lvert t \rvert \ge t_{1-\alpha/2}(n-1)$ |
| $\mu_D \ge \mu_0$ | $\mu_D < \mu_0$ | $t \le -t_{1-\alpha}(n-1)$ |

> [!example] Příklad: Snížení spotřeby paliva aditivem
> U $n = 10$ vozů se změřila spotřeba před přidáním aditiva ($X_i$) a po něm ($Y_i$), diference $D_i = X_i - Y_i$ představují úsporu paliva. Z dat vyšla průměrná úspora $\bar{d} = 0{,}4$ l/100 km, $s_d = 0{,}35$ l/100 km. Ověřte, že aditivum spotřebu statisticky významně snižuje.
>
> $H_0: \mu_D \le 0$ (aditivum nemá vliv nebo spotřebu zvyšuje), $H_1: \mu_D > 0$ (aditivum spotřebu snižuje).
>
> $$t = \frac{0{,}4 - 0}{0{,}35}\sqrt{10} = 3{,}614, \qquad W = \{t \ge t_{0,95}(9)\} = \{t \ge 1{,}833\}$$
>
> Protože $t \in W$, zamítáme $H_0$: aditivum prokazatelně snižuje průměrnou spotřebu paliva.

```r
dbar <- 0.4; sd_d <- 0.35; n <- 10
t <- (dbar - 0) / sd_d * sqrt(n)
t_krit <- qt(0.95, df = n - 1)
t
t_krit
```
```text
[1] 3.614032
[1] 1.833113
```

> [!warning] Ověřte normalitu diferencí, ne jen výsledek testu
> Realitní kancelář nechala dva odhadce ocenit osm nemovitostí (tisíce Kč):
>
> ```r
> estA <- c(3282, 2506, 2812, 5453, 3263, 4571, 3121, 2963)
> estB <- c(3271, 2531, 2799, 5471, 3285, 4557, 3139, 2976)
> t.test(estA, estB, paired = TRUE)
> shapiro.test(estA - estB)
> ```
> ```text
> 	Paired t-test
>
> data:  estA and estB
> t = -1.2157, df = 7, p-value = 0.2635
> alternative hypothesis: true mean difference is not equal to 0
> 95 percent confidence interval:
>  -21.351272   6.851272
> sample estimates:
> mean difference 
>           -7.25 
>
> 	Shapiro-Wilk normality test
>
> data:  estA - estB
> W = 0.80456, p-value = 0.03203
> ```
>
> Párový t-test sám nezamítá $H_0$ ($p = 0{,}2635$): odhadci se podle něj neliší. Shapiro-Wilkův test na diferencích ale dává $p = 0{,}03203 < 0{,}05$ — předpoklad normality diferencí je porušen a výsledek t-testu proto není spolehlivý. Správný postup je ověřit normalitu diferencí dříve, než se párový t-test interpretuje, a při jejím porušení použít párový Wilcoxonův test (viz oddíl Neparametrické testy níže).

## Testy o dvou základních souborech

Uvažují se dva nezávislé základní soubory $Z_1, Z_2$ se znakem $X \sim N(\mu_1, \sigma_1^2)$ v $Z_1$ a $X \sim N(\mu_2, \sigma_2^2)$ v $Z_2$. Z výběrů se určí $\bar{x}_1, s_1^2$ a $\bar{x}_2, s_2^2$. Testují se varianty vztahů mezi $\mu_1, \mu_2$, resp. mezi $\sigma_1^2, \sigma_2^2$.

### F-test o rozptylech

Statistika

$$F = \frac{s_1^2}{s_2^2} \sim F_{n_1-1,\,n_2-1}$$

má Fisherovo-Snedecorovo rozdělení o $n_1-1$ a $n_2-1$ stupních volnosti.

| $H_0$ | $H_1$ | Kritický obor $W$ |
|---|---|---|
| $\sigma_1 \le \sigma_2$ | $\sigma_1 > \sigma_2$ | $F \ge F_{1-\alpha}(n_1-1, n_2-1)$ |
| $\sigma_1 = \sigma_2$ | $\sigma_1 \neq \sigma_2$ | $F \le F_{\alpha/2}(n_1-1, n_2-1)$ nebo $F \ge F_{1-\alpha/2}(n_1-1, n_2-1)$ |
| $\sigma_1 \ge \sigma_2$ | $\sigma_1 < \sigma_2$ | $F \le F_{\alpha}(n_1-1, n_2-1)$ |

### Dvouvýběrový t-test o středních hodnotách

Volba statistiky závisí na tom, zda jsou rozptyly považovány za shodné:

$$T_1 = \frac{\bar{x}_1 - \bar{x}_2}{\sqrt{(n_1-1)s_1^2 + (n_2-1)s_2^2}}\sqrt{\frac{n_1+n_2-2}{\frac1{n_1}+\frac1{n_2}}}, \qquad t_p^* = t_p(n_1+n_2-2)$$

se použije, pokud jsou rozptyly $\sigma_1^2, \sigma_2^2$ alespoň přibližně shodné; při rozdílných rozptylech

$$T_2 = \frac{\bar{x}_1-\bar{x}_2}{\sqrt{s_1^2/n_1 + s_2^2/n_2}}, \qquad t_p^* = \frac{\dfrac{s_1^2}{n_1}t_p(n_1-1) + \dfrac{s_2^2}{n_2}t_p(n_2-1)}{\dfrac{s_1^2}{n_1}+\dfrac{s_2^2}{n_2}}.$$

| $H_0$ | $H_1$ | Kritický obor $W$ |
|---|---|---|
| $\mu_1 \le \mu_2$ | $\mu_1 > \mu_2$ | $t \ge t_p^*$ |
| $\mu_1 = \mu_2$ | $\mu_1 \neq \mu_2$ | $\lvert t \rvert \ge t_p^*$ |
| $\mu_1 \ge \mu_2$ | $\mu_1 < \mu_2$ | $t \le -t_p^*$ |

Postup je dvoukrokový: nejprve F-test rozhodne o shodě rozptylů, pak se podle výsledku zvolí $T_1$ nebo $T_2$.

![[mask-th-f-kriticky-obor.png|Hustota F-rozdělení o 9 a 11 stupních volnosti s vyšrafovaným dvoustranným kritickým oborem a vyznačenou pozorovanou hodnotou F]]

> [!example] Příklad: Porovnání dvou dodavatelů součástek
> Pevnost plastových dílů: dodavatel A ($n_1 = 10$, $\bar{x}_1 = 82$ MPa, $s_1^2 = 25$), dodavatel B ($n_2 = 12$, $\bar{x}_2 = 75$ MPa, $s_2^2 = 16$). Předpokládá se normalita obou rozdělení.
>
> **Krok 1 — F-test rozptylů.** $H_0: \sigma_1^2 = \sigma_2^2$, $H_1: \sigma_1^2 \neq \sigma_2^2$.
>
> $$F = \frac{25}{16} = 1{,}5625, \qquad W = \{F \le F_{0,025}(9,11) \;\text{nebo}\; F \ge F_{0,975}(9,11)\} = \{F \le 0{,}256 \;\text{nebo}\; F \ge 3{,}588\}$$
>
> $F \notin W$, rozptyly nezamítáme jako shodné — pro t-test se použije $T_1$.
>
> **Krok 2 — dvouvýběrový t-test středních hodnot.** $H_0: \mu_1 = \mu_2$, $H_1: \mu_1 \neq \mu_2$.
>
> $$s_p^2 = \frac{9\cdot 25 + 11\cdot 16}{20} = 20{,}05, \qquad t = \frac{82-75}{\sqrt{20{,}05}}\sqrt{\frac{120}{22}} \approx 3{,}651, \qquad W = \{\lvert t\rvert \ge t_{0,975}(20)\} = \{\lvert t\rvert \ge 2{,}086\}$$
>
> $t \in W$, zamítáme $H_0$: pevnost součástek od obou dodavatelů se statisticky významně liší.

```r
s1 <- 25; n1 <- 10
s2 <- 16; n2 <- 12
Fstat <- s1 / s2
F_dolni <- qf(0.025, n1 - 1, n2 - 1)
F_horni <- qf(0.975, n1 - 1, n2 - 1)
Fstat
F_dolni
F_horni
```
```text
[1] 1.5625
[1] 0.2556189
[1] 3.587899
```
```r
sp2 <- ((n1 - 1) * s1 + (n2 - 1) * s2) / (n1 + n2 - 2)
t <- (82 - 75) / sqrt(sp2) * sqrt(n1 * n2 / (n1 + n2))
t_krit <- qt(0.975, df = n1 + n2 - 2)
sp2
t
t_krit
```
```text
[1] 20.05
[1] 3.65107
[1] 2.085963
```

![[mask-th-t-dvoustranny.png|Hustota Studentova t-rozdělení s 20 stupni volnosti, kritický obor |t| ≥ 2,086 vyšrafován v obou koncích, pozorované t = 3,651 leží v pravém kritickém oboru]]

V R provede obě kroky `var.test()` a `t.test()`. Parametr `var.equal` nastavuje volbu mezi $T_1$ a $T_2$: `TRUE` znamená předpoklad shodných rozptylů (podle výsledku F-testu), `FALSE` předpoklad rozdílných rozptylů.

**Kabely A/B.** Pevnost v tahu dvou výrobců (MPa, 12 kabelů od každého):

```r
A <- c(313, 299, 315, 312, 310, 308, 314, 313, 305, 310, 309, 314)
B <- c(307, 322, 313, 313, 311, 316, 315, 314, 308, 319, 313, 312)
var.test(A, B)
t.test(A, B, var.equal = TRUE)
```
```text
	F test to compare two variances

data:  A and B
F = 1.1905, num df = 11, denom df = 11, p-value = 0.7776
alternative hypothesis: true ratio of variances is not equal to 1
95 percent confidence interval:
 0.3427173 4.1354275
sample estimates:
ratio of variances 
          1.190497 

	Two Sample t-test

data:  A and B
t = -1.9096, df = 22, p-value = 0.06932
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -7.1273286  0.2939953
sample estimates:
mean of x mean of y 
 310.1667  313.5833 
```

F-test shodu rozptylů nezamítá ($p = 0{,}7776$), proto `var.equal = TRUE`. Výsledný t-test dává $p = 0{,}06932$ — na hladině 5 % se $H_0$ nezamítá, ale hodnota je těsně nad hranicí.

**Výšky chlapců a dívek v páté třídě:**

```r
boys <- c(130, 140, 136, 141, 139, 133, 149, 151, 139, 136, 138, 142, 127, 139, 147)
girls <- c(135, 141, 143, 132, 146, 146, 151, 141, 141, 131, 142, 141)
var.test(boys, girls)
t.test(boys, girls, var.equal = TRUE)
```
```text
	F test to compare two variances

data:  boys and girls
F = 1.2721, num df = 14, denom df = 11, p-value = 0.6977
alternative hypothesis: true ratio of variances is not equal to 1
95 percent confidence interval:
 0.3787299 3.9365720
sample estimates:
ratio of variances 
          1.272082 

	Two Sample t-test

data:  boys and girls
t = -0.70344, df = 25, p-value = 0.4883
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -6.67727  3.27727
sample estimates:
mean of x mean of y 
 139.1333  140.8333 
```

F-test shodu rozptylů nezamítá ($p = 0{,}6977$), t-test s `var.equal = TRUE` dává $p = 0{,}4883$: na hladině 5 % se rozdíl průměrných výšek chlapců a dívek neprokázal.

## Testy dobré shody a normalita

Testy dobré shody ověřují, zda datový soubor pochází ze základního souboru s určitým typem rozdělení (normální, exponenciální apod.).

### Kolmogorovův-Smirnovův test

Univerzální test pro spojitá rozdělení. Porovnává empirickou distribuční funkci $F_n(x)$ s teoretickou distribuční funkcí $F(x)$ testovaného rozdělení.

- $H_0$: odchylky mezi $F_n(x)$ a $F(x)$ jsou náhodné (data mají dané rozdělení).
- $H_1$: data nemají dané rozdělení.
- Testové kritérium: $D = \sup_x \lvert F_n(x) - F(x) \rvert$.
- Kritický obor: $W_\alpha = \{d : d > D_\alpha(n)\}$; pro $n>30$ se kritická hodnota aproximuje zlomkem $1{,}36/\sqrt{n}$.

V R test provádí `ks.test()`, kde se za `F(x)` dosadí příslušná distribuční funkce (`"pnorm"`, `"pexp"`, …) s jejími parametry:

```r
x3 <- c(4.1, 4.0, 3.8, 3.9, 3.8, 3.8, 3.5, 3.7, 4.0, 4.0)
ks.test(x3, "pnorm", mean(x3), sd(x3))
```
```text
	Asymptotic one-sample Kolmogorov-Smirnov test

data:  x3
D = 0.18469, p-value = 0.8847
alternative hypothesis: two-sided
```

$p = 0{,}8847 > 0{,}05$: odpad materiálu je slučitelný s normálním rozdělením se stejným průměrem a směrodatnou odchylkou.

### Shapiro-Wilkův test

Nejpoužívanější a nejsilnější obecný test normality, citlivý na odchylky v šikmosti i špičatosti. Využívá korelaci mezi uspořádanými hodnotami výběru a jejich očekávanými hodnotami v normálním rozdělení.

- $H_0$: data mají normální rozdělení.
- $H_1$: data nemají normální rozdělení.
- Testová statistika $W \in \langle 0,1 \rangle$; hodnoty blízké 1 indikují shodu s normalitou.

Na rozdíl od ostatních testů v této kapitole se Shapiro-Wilkův test v praxi vyhodnocuje pouze přes p-hodnotu (tabulka kritických hodnot pro $W$ se běžně neudává): $p \ge \alpha \Rightarrow$ $H_0$ nezamítáme (normalitu lze předpokládat); $p < \alpha \Rightarrow$ $H_0$ zamítáme (předpoklad normality je porušen).

```r
x2 <- c(9.5, 10.5, 8.9, 9.2, 10.0, 8.5, 9.2, 8.8, 10.0, 9.5, 9.2)
shapiro.test(x2)
```
```text
	Shapiro-Wilk normality test

data:  x2
W = 0.96022, p-value = 0.7744
```

U dat o životnosti baterií se normalita nezamítá ($p = 0{,}7744$), předpoklad t-testu je tedy splněn.

> [!example] Příklad: Doba do poruchy výrobku
> Zkoušky životnosti nového výrobku daly soubor 68 hodnot doby do poruchy (v minutách). Odhadněte charakteristiky a zákon rozdělení.
>
> ```r
> x9 <- c(101, 338, 150, 47, 10, 2, 12, 392, 5, 73, 367, 54, 114, 213, 71, 341, 313, 112, 343, 151,
>         9, 160, 18, 113, 77, 71, 159, 12, 119, 130, 140, 161, 379, 54, 373, 168, 365, 110, 145,
>         88, 74, 46, 246, 259, 19, 119, 48, 3, 163, 179, 194, 33, 49, 501, 193, 19, 5, 2, 221, 300,
>         88, 13, 428, 249, 25, 209, 54, 91)
> mean(x9)
> sd(x9)
> median(x9)
> shapiro.test(x9)
> ks.test(x9, "pexp", rate = 1 / mean(x9))
> ```
> ```text
> [1] 145.4412
> [1] 126.1283
> [1] 113.5
>
> 	Shapiro-Wilk normality test
>
> data:  x9
> W = 0.89872, p-value = 4.389e-05
>
> 	Asymptotic one-sample Kolmogorov-Smirnov test
>
> data:  x9
> D = 0.074727, p-value = 0.8421
> alternative hypothesis: two-sided
> ```
>
> Výběrový průměr (145,44 min) je blízký směrodatné odchylce (126,13 min) a medián (113,5 min) je výrazně nižší než průměr — typický tvar doby do poruchy. Shapiro-Wilkův test normalitu jasně zamítá ($p < 0{,}0001$), zatímco Kolmogorov-Smirnovův test proti exponenciálnímu rozdělení se střední hodnotou $\bar{x}$ shodu nezamítá ($p = 0{,}8421$): data odpovídají spíše exponenciálnímu rozdělení než normálnímu.

![[mask-th-exponencialni-shoda.png|Histogram doby do poruchy s překrytou hustotou exponenciálního rozdělení s parametrem 1 lomeno výběrovým průměrem]]

## Neparametrické testy

Když předpoklad normality neplatí, nahrazují t-testy jejich neparametrické obdoby — Wilcoxonovy testy posuzují **medián** ($x_{0,5}$) místo střední hodnoty a nevyžadují normalitu dat.

### Wilcoxonovy testy

| $H_0$ | $H_1$ | Příkaz v R |
|---|---|---|
| $x_{0,5} \le c$ | $x_{0,5} > c$ | `wilcox.test(x, alternative = "greater", mu = c)` |
| $x_{0,5} = c$ | $x_{0,5} \neq c$ | `wilcox.test(x, alternative = "two.sided", mu = c)` |
| $x_{0,5} \ge c$ | $x_{0,5} < c$ | `wilcox.test(x, alternative = "less", mu = c)` |

*Jednovýběrový Wilcoxonův test* (obdoba t-testu) posuzuje odchylku mediánu od konstanty $c$.

*Jednovýběrový Wilcoxonův test na diferencích* (obdoba párového t-testu) posuzuje odchylku mediánu rozdílu $x_{0,5}-y_{0,5}$ od $c$; v R se volá se stejnými argumenty jako výše a navíc `paired = TRUE`.

*Dvouvýběrový Wilcoxonův test* (obdoba dvouvýběrového t-testu) posuzuje odchylku mediánů dvou nezávislých výběrů; argument `mu` odpadá. Pro výšky chlapců a dívek z příkladu výše:

```r
boys <- c(130, 140, 136, 141, 139, 133, 149, 151, 139, 136, 138, 142, 127, 139, 147)
girls <- c(135, 141, 143, 132, 146, 146, 151, 141, 141, 131, 142, 141)
wilcox.test(boys, girls, alternative = "two.sided")
```
```text
	Wilcoxon rank sum exact test

data:  boys and girls
W = 69, p-value = 0.315
alternative hypothesis: true location shift is not equal to 0
```

$p = 0{,}315 > 0{,}05$: mediány výšek chlapců a dívek se statisticky významně neliší — stejný závěr jako u dvouvýběrového t-testu.

> [!example] Příklad: Realitní odhadci — neparametrická alternativa
> U odhadů cen z párového t-testu výše normalita diferencí neplatí ($p = 0{,}03203$). Správnou volbou je párový Wilcoxonův test:
>
> ```r
> estA <- c(3282, 2506, 2812, 5453, 3263, 4571, 3121, 2963)
> estB <- c(3271, 2531, 2799, 5471, 3285, 4557, 3139, 2976)
> wilcox.test(estA, estB, paired = TRUE)
> ```
> ```text
> 	Wilcoxon signed rank exact test
>
> data:  estA and estB
> V = 7.5, p-value = 0.1484
> alternative hypothesis: true location shift is not equal to 0
> ```
>
> $p = 0{,}1484 > 0{,}05$: medián diferencí se od nuly statisticky významně neliší, odhadci se neliší. Závěr je stejný jako u (nespolehlivého) párového t-testu, ale tady je podložený testem, jehož předpoklady data splňují.

### Kruskalův-Wallisův test

Zobecnění dvouvýběrového Wilcoxonova testu, neparametrická obdoba analýzy rozptylu jednoduchého třídění. $H_0$: všechny výběry pocházejí ze stejného rozdělení.

```r
kruskal.test(kvantitativní_proměnná ~ faktor, data = soubor)
```

### Mediánový test

Má stejný účel jako Kruskalův-Wallisův test (obdoba analýzy rozptylu jednoduchého třídění, $H_0$: všechny výběry pocházejí ze stejného rozdělení) a je součástí balíčku `agricolae`:

```r
library(agricolae)
Median.test(kvantitativní_proměnná, faktor)
```

### Friedmanův test

Neparametrická obdoba analýzy rozptylu dvojného třídění s jedním pozorováním v každé podtřídě. $H_0$: distribuční funkce veličin $X_{i1}, \dots, X_{ik}$ jsou totožné.

```r
friedman.test(kvantitativní_proměnná ~ faktor_A | faktor_B, data = soubor)
# jsou-li proměnné samostatné vektory (bez argumentu data):
friedman.test(kvantitativní_proměnná, faktor_A, faktor_B)
```

## Přehled testů

![[mask-ilu-volba-testu.png|Rozhodovací strom pro volbu testu: jeden výběr, párová měření, dva nezávislé výběry nebo více výběrů; podle normality dat t-test, F-test nebo Wilcoxonův, Kruskalův-Wallisův či Friedmanův test s příkazy v R]]

| Situace | Test | R funkce |
|---|---|---|
| Jedna střední hodnota vs. zadané číslo, normální data | jednovýběrový t-test | `t.test(x, mu = ..., alternative = ...)` |
| Rozdíl dvou závislých měření, diference normální | párový t-test | `t.test(x, y, paired = TRUE)` |
| Shoda rozptylů dvou nezávislých normálních výběrů | F-test | `var.test(x, y)` |
| Shoda středních hodnot dvou nezávislých normálních výběrů | dvouvýběrový t-test | `t.test(x, y, var.equal = TRUE/FALSE)` |
| Shoda dat se zadaným typem rozdělení (normální, exponenciální, …) | Kolmogorovův-Smirnovův test | `ks.test(x, "pnorm", mu, sigma)`, `ks.test(x, "pexp", 1/delta)` |
| Normalita dat | Shapiro-Wilkův test | `shapiro.test(x)` |
| Medián jednoho výběru vs. konstanta, data nejsou normální | jednovýběrový Wilcoxonův test | `wilcox.test(x, mu = c, alternative = ...)` |
| Medián diferencí dvou závislých měření, data nejsou normální | párový Wilcoxonův test | `wilcox.test(x, y, paired = TRUE, mu = c)` |
| Mediány dvou nezávislých výběrů, data nejsou normální | dvouvýběrový Wilcoxonův test | `wilcox.test(x, y)` |
| Více než dva nezávislé výběry, data nejsou normální | Kruskalův-Wallisův test | `kruskal.test(y ~ faktor, data)` |
| Více než dva nezávislé výběry, data nejsou normální (alternativa) | mediánový test | `Median.test(y, faktor)` z balíčku `agricolae` |
| Více než dva závislé výběry (dvojné třídění, jedno pozorování na podtřídu) | Friedmanův test | `friedman.test(y ~ A \| B, data)` |

## Časté chyby

- **Nezamítnutí $H_0$ není důkaz, že $H_0$ platí.** U kabelů A/B vyšlo $p = 0{,}06932$ — na hladině 5 % se $H_0$ nezamítá, ale hodnota je blízko hranice; správná interpretace je „data rovnost průměrů nevyvracejí“, ne „rovnost je prokázána“.
- **Před párovým nebo dvouvýběrovým t-testem ověřte normalitu.** U realitních odhadců vycházel párový t-test bez varování, ale Shapiro-Wilkův test na diferencích normalitu zamítl — správným testem byl párový Wilcoxonův test.
- **`var.equal` v `t.test()` se volí podle F-testu, ne podle výchozí hodnoty.** Výchozí nastavení R je `var.equal = FALSE` (Welchova varianta); pokud F-test potvrdí shodné rozptyly, je třeba explicitně napsat `var.equal = TRUE`, jinak se použije jiná statistika a jiné stupně volnosti.
- **Jednostranná vs. dvoustranná alternativa mění kritický obor i závěr.** Volba `alternative = "greater"/"less"/"two.sided"` musí odpovídat formulaci $H_1$ v zadání, ne být ponechána na výchozí hodnotě `"two.sided"`.
- **Shapiro-Wilkův test se vyhodnocuje jen přes p-hodnotu**, ne porovnáním $W$ s tabulkovou kritickou hodnotou jako u ostatních testů v této kapitole.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]]
- [[popisna-statistika|Popisná statistika a datové soubory]]
- [[regresni-a-korelacni-analyza|Regresní a korelační analýza]]
- [[kontingencni-tabulky|Kontingenční tabulky]]
- [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]]
- [[mask-r-tahak|Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.
