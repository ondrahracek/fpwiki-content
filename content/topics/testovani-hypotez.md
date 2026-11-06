---
title: "Testování statistických hypotéz"
course: mask
type: topic
tags: [mask, statistika, testovani-hypotez, t-test, normalita, neparametricke-testy]
sources: [raw/mask/03 testy hypotéz.pdf, raw/mask/03 testování hypotéz - návod R 01.pdf, raw/mask/03 testování hypotéz - návod R 02.pdf, raw/mask/příklady 03.docx, raw/mask/příklady 01 a 02.docx, raw/mask/data k příkladům/7.txt, raw/mask/data k příkladům/9.txt]
created: 2026-10-02
updated: 2026-11-06
---

# Testování statistických hypotéz

> [!tldr] V kostce
> - Statistický test posuzuje konkrétní předpoklad, například shodu průměrů dvou skupin.
> - Rozlišujeme jeden výběr, nezávislé skupiny a párová měření, například před změnou a po ní.
> - P-hodnota pomáhá rozhodnout, zda jsou data v rozporu s testovaným předpokladem.
> - Nezamítnutí předpokladu není jeho důkaz. Také záleží na tom, zda data splňují podmínky zvoleného testu.

Průměr naměřený ve výběru se obvykle liší od předpokládané hodnoty. Statistický test pomáhá rozhodnout, zda lze rozdíl přičíst náhodě, nebo zda svědčí proti původnímu předpokladu. Vychází z [[popisna-statistika|charakteristik výběru]] a ze známých [[nahodne-veliciny-a-rozdeleni|rozdělení pravděpodobnosti]], například normálního, $t$ nebo $F$. Stejně lze posuzovat i tvrzení o tvaru rozdělení.

## Statistická hypotéza a její test

Tvrzení, že určitý typ auta má průměrnou spotřebu 7 l/100 km, je příkladem **statistické hypotézy**. Obecně jde o předpoklad o parametru nebo tvaru rozdělení sledovaného znaku. Měřit celý základní soubor bývá nákladné nebo technicky nemožné. **Testování hypotéz** proto posuzuje takové tvrzení pomocí náhodného výběru. Výsledkem je rozhodnutí s určitou možností chyby, nikoli jistota o celém souboru.

Proti sobě stojí dvě hypotézy:

- **Nulová hypotéza $H_0$** je výchozí tvrzení o parametru nebo rozdělení, které testujeme.
- **Alternativní hypotéza $H_1$** vyjadřuje, jaký rozdíl oproti $H_0$ chceme zjistit.

Pro $H_0: \mu = \mu_0$ může alternativa $H_1$ sledovat jakoukoli odchylku, nebo pouze odchylku jedním směrem:

| Tvar $H_1$ | Zápis | Typ |
|---|---|---|
| nerovnost | $H_1: \mu \neq \mu_0$ | dvoustranná |
| větší | $H_1: \mu > \mu_0$ | jednostranná |
| menší | $H_1: \mu < \mu_0$ | jednostranná |

### Chyba I. a II. druhu

Jiný náhodný výběr by mohl vést k jinému rozhodnutí. Rozlišujeme proto dva druhy chyby:

- **Chyba I. druhu** nastane, když zamítneme $H_0$, přestože platí. Její pravděpodobnost označujeme $\alpha$.
- **Chyba II. druhu** nastane, když nezamítneme $H_0$, přestože platí $H_1$. Její pravděpodobnost označujeme $\beta$.

| Úsudek o $H_0$ | $H_0$ platí | $H_0$ neplatí |
|---|---|---|
| Nezamítá se | správné rozhodnutí, $1-\alpha$ | chyba II. druhu, $\beta$ |
| Zamítá se | chyba I. druhu, $\alpha$ | správné rozhodnutí, $1-\beta$ |

**Hladina významnosti** $\alpha$ stanovuje předem zvolenou pravděpodobnost chyby I. druhu, obvykle 5 %. Při této hladině chceme současně co nejmenší pravděpodobnost chyby II. druhu. Oba požadavky je třeba posuzovat společně.

![[mask-th-chyba-i-ii.png|Dvě normální hustoty testového kritéria za platnosti H0 a H1 se svislou kritickou hodnotou a vyšrafovanými plochami alfa a beta]]

V obrázku posunutí kritické hodnoty $c$ doleva zmenší $\beta$, ale zvětší $\alpha$. Posunutí opačným směrem má opačný účinek. Když zvolíme hladinu $\alpha$, odvodíme hranici $c$ z rozdělení testového kritéria za předpokladu, že platí $H_0$.

### Testové kritérium a kritický obor

Naměřené hodnoty převedeme na jediné číslo, **testové kritérium** $T$. Abychom mohli posoudit, zda je jeho hodnota neobvyklá, potřebujeme znát jeho rozdělení za platnosti $H_0$.

**Kritický obor** $W$ obsahuje hodnoty, které už považujeme za dostatečně neobvyklé a svědčící pro $H_1$. Hranice tohoto oboru se volí tak, aby

$$P(T \in W \mid H_0) = \alpha,$$

tedy aby kritérium spadlo do $W$ i při platné $H_0$ s pravděpodobností rovnou zvolené hladině významnosti.

### Postup testování hypotézy

![[mask-ilu-postup-testovani.png|Čtyři kroky testu: formulace H0 a H1, testové kritérium T, hladina významnosti α a kritický obor W, závěr testu; T ∈ W znamená zamítnutí H0, T ∉ W znamená, že H0 nezamítáme; totéž rozhodnutí dává p-hodnota porovnaná s α]]

1. Zapište hypotézy $H_0$ a $H_1$ a předem zvolte hladinu významnosti.
2. Zvolte test vhodný pro daná data, posuďte jeho předpoklady a spočítejte testové kritérium.
3. Pro zvolenou hladinu významnosti určete kritický obor $W$.
4. Porovnejte výsledek s kritickým oborem a vyslovte závěr:
   - pokud $T \in W$, výsledek svědčí pro $H_1$ na hladině významnosti $100\alpha\,\%$ a zamítáme $H_0$;
   - pokud $T \notin W$, nemáme pro $H_1$ dostatek důkazů na hladině významnosti $100\alpha\,\%$ a $H_0$ nezamítáme.

Stejné rozhodnutí lze získat pomocí **p-hodnoty**, kterou R vypisuje přímo. Za předpokladu platnosti $H_0$ vyjadřuje pravděpodobnost výsledku alespoň tak krajního, jako je pozorovaný výsledek. Menší p-hodnota tedy znamená silnější důkaz proti $H_0$. Platí $p \le \alpha \Rightarrow$ zamítáme $H_0$; $p > \alpha \Rightarrow$ $H_0$ nezamítáme. Porovnání p-hodnoty s hladinou významnosti odpovídá porovnání kritéria s kritickým oborem.

## Jednovýběrový t-test

Jednovýběrový t-test porovnává střední hodnotu $\mu$ se zadaným číslem. Předpokládá normální rozdělení $X \sim N(\mu, \sigma^2)$. Z výběru o rozsahu $n$ spočítáme průměr $\bar{x}$ a rozptyl $s^2$. Rozdíl mezi zadanou hodnotou $\mu_0$ a neznámou střední hodnotou $\mu$ posoudíme kritériem

$$T = \frac{\bar{x} - \mu_0}{s}\sqrt{n} \sim t_{n-1}$$

které má za platnosti nulové hypotézy Studentovo rozdělení o $n-1$ stupních volnosti.

| $H_0$ | $H_1$ | Kritický obor $W$ |
|---|---|---|
| $\mu \le \mu_0$ | $\mu > \mu_0$ | $t \ge t_{1-\alpha}(n-1)$ |
| $\mu = \mu_0$ | $\mu \neq \mu_0$ | $\lvert t \rvert \ge t_{1-\alpha/2}(n-1)$ |
| $\mu \ge \mu_0$ | $\mu < \mu_0$ | $t \le -t_{1-\alpha}(n-1)$ |

Autobusová linka měla průměrnou dobu jízdy 12 minut. Po úpravě trasy byly změřeny časy devíti jízd. Pomocí `t.test()` posoudíme, zda se průměrná doba změnila kterýmkoli směrem:

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

Ve výstupu je `t` hodnota testového kritéria, `df` počet stupňů volnosti, `p-value` p-hodnota a `mean of x` výběrový průměr. Protože $p = 0{,}02843 < 0{,}05$, zamítáme nulovou hypotézu. Průměrná doba jízdy se od původních 12 minut statisticky významně liší.

> [!example] Příklad: Kontrola objemu lahví
> Pivovar plní lahve, deklarovaný objem je $\mu_0 = 0{,}5$ l. Náhodný výběr $n = 20$ lahví dal $\bar{x} = 0{,}492$ l, $s = 0{,}015$ l. Na hladině významnosti 5 % ověřte podezření, že pivovar lahve nedoplňuje.
>
> $H_0: \mu \ge 0{,}5$ l (objem je v pořádku nebo větší), $H_1: \mu < 0{,}5$ l (lahve jsou nedoplněné).
>
> $$t = \frac{0{,}492 - 0{,}5}{0{,}015}\sqrt{20} = -2{,}385, \qquad W = \{t \le -t_{0,95}(19)\} = \{t \le -1{,}729\}$$
>
> Protože $t \in W$, zamítáme $H_0$. Na hladině významnosti 5 % výsledek svědčí pro plnění lahví pod deklarovaný objem.

Máme jen průměr, směrodatnou odchylku a počet lahví. Funkce `t.test()` však potřebuje jednotlivá měření. Kritérium proto spočítáme přímo ze vzorce a kritickou hodnotu získáme pomocí `qt()`:

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

V dalších příkladech známe jednotlivá měření a můžeme použít přímo `t.test()`.

**Životnost baterií.** Výrobce udává průměrnou životnost 10 hodin. Na 11 bateriích byly naměřeny následující doby v hodinách. Dvoustranný test posoudí, zda se průměr liší od údaje výrobce:

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

Protože $p = 0{,}006548 < 0{,}05$, zamítáme nulovou hypotézu. Průměrná životnost se od deklarovaných 10 hodin statisticky významně liší. Výběrový průměr ukazuje na kratší životnost.

**Odpad materiálu.** U deseti obráběných kusů známe odpad materiálu v procentech. Posoudíme, zda se průměrný odpad liší od 4 %. Shapiro-Wilkův test současně prověří odchylky od normality, kterou t-test předpokládá:

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

Výsledek $p = 0{,}0343 < 0{,}05$ vede k zamítnutí nulové hypotézy: průměrný odpad se od 4 % statisticky významně liší. Výběrový průměr je 3,86 %. Shapiro-Wilkův test vrací $p = 0{,}4634 > 0{,}05$, takže odchylku od normality neprokázal.

## Párový t-test

Při měření před změnou a po ní patří obě hodnoty ke stejnému objektu. Taková měření jsou párová a nelze s nimi zacházet jako se dvěma nezávislými výběry.

U každé dvojice $(X_i, Y_i)$ nejprve spočítáme rozdíl $D_i = X_i - Y_i$. Párový t-test předpokládá normální rozdělení těchto rozdílů, $D \sim N(\mu_D, \sigma_D^2)$. Z $n$ dvojic získáme průměr rozdílů $\bar{d}$ a jejich rozptyl $s_d^2$. Test pak porovnává zadané číslo $\mu_0$, obvykle 0, se střední hodnotou rozdílů $\mu_D$. Používá kritérium

$$T = \frac{\bar{d} - \mu_0}{s_d}\sqrt{n} \sim t_{n-1}.$$

| $H_0$ | $H_1$ | Kritický obor $W$ |
|---|---|---|
| $\mu_D \le \mu_0$ | $\mu_D > \mu_0$ | $t \ge t_{1-\alpha}(n-1)$ |
| $\mu_D = \mu_0$ | $\mu_D \neq \mu_0$ | $\lvert t \rvert \ge t_{1-\alpha/2}(n-1)$ |
| $\mu_D \ge \mu_0$ | $\mu_D < \mu_0$ | $t \le -t_{1-\alpha}(n-1)$ |

> [!example] Příklad: Snížení spotřeby paliva aditivem
> U $n = 10$ vozů byla změřena spotřeba před přidáním aditiva ($X_i$) a po něm ($Y_i$). Rozdíl $D_i = X_i - Y_i$ představuje úsporu paliva. Průměrná úspora vyšla $\bar{d} = 0{,}4$ l/100 km a směrodatná odchylka rozdílů $s_d = 0{,}35$ l/100 km. Posuďte, zda aditivum průměrnou spotřebu statisticky významně snižuje.
>
> $H_0: \mu_D \le 0$ (aditivum nemá vliv nebo spotřebu zvyšuje), $H_1: \mu_D > 0$ (aditivum spotřebu snižuje).
>
> $$t = \frac{0{,}4 - 0}{0{,}35}\sqrt{10} = 3{,}614, \qquad W = \{t \ge t_{0,95}(9)\} = \{t \ge 1{,}833\}$$
>
> Protože $t \in W$, zamítáme $H_0$. Výsledek svědčí pro snížení průměrné spotřeby paliva po přidání aditiva.

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

> [!warning] U párového t-testu záleží na rozdělení rozdílů
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
> Párový t-test nezamítá $H_0$ ($p = 0{,}2635$), takže rozdíl mezi odhadci neprokázal. Shapiro-Wilkův test rozdílů však dává $p = 0{,}03203 < 0{,}05$ a normalitu zamítá. Předpoklad párového t-testu tedy není podpořen a jeho závěr nelze bez dalšího převzít. Nejdříve je třeba posoudit rozdělení rozdílů. Neparametrickou alternativu nabízí párový Wilcoxonův test uvedený níže.

## Testy o dvou základních souborech

U dvou dodavatelů můžeme porovnat průměrnou pevnost součástek i to, jak moc pevnost kolísá. Každý dodavatel dodá vlastní výběr dílů; nejde o dvojí měření týchž součástek, takže výběry jsou nezávislé. Průměry porovnává t-test, kolísání F-test rozptylů. Oba následující postupy předpokládají normální rozdělení hodnot v každé skupině.

Označme základní soubory $Z_1, Z_2$. Předpokládáme normální rozdělení $X \sim N(\mu_1, \sigma_1^2)$ v $Z_1$ a $X \sim N(\mu_2, \sigma_2^2)$ v $Z_2$. Z nezávislých výběrů spočítáme $\bar{x}_1, s_1^2$ a $\bar{x}_2, s_2^2$. t-test porovnává střední hodnoty $\mu_1, \mu_2$, F-test rozptyly $\sigma_1^2, \sigma_2^2$.

### F-test o rozptylech

F-test porovnává, jak silně hodnoty v obou souborech kolísají. Vychází z poměru výběrových rozptylů:

$$F = \frac{s_1^2}{s_2^2} \sim F_{n_1-1,\,n_2-1}$$

Za předpokladu shodných rozptylů má tento poměr Fisherovo-Snedecorovo rozdělení o $n_1-1$ a $n_2-1$ stupních volnosti.

| $H_0$ | $H_1$ | Kritický obor $W$ |
|---|---|---|
| $\sigma_1 \le \sigma_2$ | $\sigma_1 > \sigma_2$ | $F \ge F_{1-\alpha}(n_1-1, n_2-1)$ |
| $\sigma_1 = \sigma_2$ | $\sigma_1 \neq \sigma_2$ | $F \le F_{\alpha/2}(n_1-1, n_2-1)$ nebo $F \ge F_{1-\alpha/2}(n_1-1, n_2-1)$ |
| $\sigma_1 \ge \sigma_2$ | $\sigma_1 < \sigma_2$ | $F \le F_{\alpha}(n_1-1, n_2-1)$ |

### Dvouvýběrový t-test o středních hodnotách

Chceme zjistit, zda se liší průměrná pevnost součástek od obou dodavatelů. Jestliže můžeme předpokládat stejně velké kolísání v obou skupinách, použijeme variantu $T_1$ se společným odhadem rozptylu. Bez tohoto předpokladu použijeme variantu pro rozdílné rozptyly; v R ji počítá Welchův test.

Ve vzorcích označují $\bar{x}_1$ a $\bar{x}_2$ průměry pevností, $s_1^2$ a $s_2^2$ výběrové rozptyly a $n_1$ a $n_2$ počty zkoušených dílů. Varianta se společným rozptylem má kritérium

$$T_1 = \frac{\bar{x}_1 - \bar{x}_2}{\sqrt{(n_1-1)s_1^2 + (n_2-1)s_2^2}}\sqrt{\frac{n_1+n_2-2}{\frac1{n_1}+\frac1{n_2}}}, \qquad t_p^* = t_p(n_1+n_2-2)$$

Předpoklad alespoň přibližně shodných rozptylů $\sigma_1^2, \sigma_2^2$ je pro tuto variantu podstatný. Při rozdílných rozptylech se používá kritérium

$$T_2 = \frac{\bar{x}_1-\bar{x}_2}{\sqrt{s_1^2/n_1 + s_2^2/n_2}}, \qquad t_p^* = \frac{\dfrac{s_1^2}{n_1}t_p(n_1-1) + \dfrac{s_2^2}{n_2}t_p(n_2-1)}{\dfrac{s_1^2}{n_1}+\dfrac{s_2^2}{n_2}}.$$

| $H_0$ | $H_1$ | Kritický obor $W$ |
|---|---|---|
| $\mu_1 \le \mu_2$ | $\mu_1 > \mu_2$ | $t \ge t_p^*$ |
| $\mu_1 = \mu_2$ | $\mu_1 \neq \mu_2$ | $\lvert t \rvert \ge t_p^*$ |
| $\mu_1 \ge \mu_2$ | $\mu_1 < \mu_2$ | $t \le -t_p^*$ |

R při `var.equal = FALSE` používá Welchovu variantu. Ta má stejné kritérium $T_2$, ale kritickou hodnotu určuje pomocí jiného přiblížení stupňů volnosti než uvedený ruční vzorec.

V následujících příkladech nejprve F-testem posoudíme shodu rozptylů. Podle výsledku pak zvolíme variantu $T_1$ nebo $T_2$ pro porovnání středních hodnot.

![[mask-th-f-kriticky-obor.png|Hustota F-rozdělení o 9 a 11 stupních volnosti s vyšrafovaným dvoustranným kritickým oborem a vyznačenou pozorovanou hodnotou F]]

> [!example] Příklad: Porovnání dvou dodavatelů součástek
> U plastových dílů porovnáváme pevnost. Dodavatel A má $n_1 = 10$, $\bar{x}_1 = 82$ MPa a $s_1^2 = 25$. Dodavatel B má $n_2 = 12$, $\bar{x}_2 = 75$ MPa a $s_2^2 = 16$. Předpokládáme normální rozdělení v obou souborech.
>
> **Krok 1 — F-test rozptylů.** $H_0: \sigma_1^2 = \sigma_2^2$, $H_1: \sigma_1^2 \neq \sigma_2^2$.
>
> $$F = \frac{25}{16} = 1{,}5625, \qquad W = \{F \le F_{0,025}(9,11) \;\text{nebo}\; F \ge F_{0,975}(9,11)\} = \{F \le 0{,}256 \;\text{nebo}\; F \ge 3{,}588\}$$
>
> Protože $F \notin W$, hypotézu shodných rozptylů nezamítáme. Pro navazující t-test použijeme $T_1$.
>
> **Krok 2 — dvouvýběrový t-test středních hodnot.** $H_0: \mu_1 = \mu_2$, $H_1: \mu_1 \neq \mu_2$.
>
> $$s_p^2 = \frac{9\cdot 25 + 11\cdot 16}{20} = 20{,}05, \qquad t = \frac{82-75}{\sqrt{20{,}05}}\sqrt{\frac{120}{22}} \approx 3{,}651, \qquad W = \{\lvert t\rvert \ge t_{0,975}(20)\} = \{\lvert t\rvert \ge 2{,}086\}$$
>
> Protože $t \in W$, zamítáme $H_0$. Průměrná pevnost součástek od obou dodavatelů se statisticky významně liší.

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

V R rozptyly porovná `var.test()` a střední hodnoty `t.test()`. Obě varianty, $T_1$ a $T_2$, se liší tím, zda pracují se společným rozptylem. Nastavení `var.equal = TRUE` ve funkci `t.test()` předpokládá shodné rozptyly. Nastavení `FALSE` tento předpoklad nevyžaduje.

**Kabely A/B.** U dvou výrobců bylo změřeno po 12 kabelech. Hodnoty pevnosti v tahu jsou v MPa. Nejprve porovnáme rozptyly, poté průměrné pevnosti:

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

F-test shodu rozptylů nezamítá ($p = 0{,}7776$), proto zde použijeme `var.equal = TRUE`. t-test vrací $p = 0{,}06932$. Na hladině 5 % tedy $H_0$ nezamítáme: rozdíl průměrných pevností se neprokázal. P-hodnota přitom leží poměrně blízko zvolené hranice.

**Výšky chlapců a dívek v páté třídě.** Stejným postupem porovnáme rozptyly a průměry naměřených výšek:

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

F-test shodu rozptylů nezamítá ($p = 0{,}6977$). Následující t-test s `var.equal = TRUE` vrací $p = 0{,}4883$. Na hladině 5 % se rozdíl průměrných výšek chlapců a dívek neprokázal.

## Testy dobré shody a normalita

Histogram může připomínat normální nebo exponenciální rozdělení. Test dobré shody posuzuje, zda se pozorované odchylky od zvoleného rozdělení ještě dají vysvětlit náhodou.

### Kolmogorovův-Smirnovův test

Kolmogorovův-Smirnovův test porovnává podíly skutečně naměřených hodnot s pravděpodobnostmi podle zvoleného spojitého rozdělení. Měří největší rozdíl mezi empirickou distribuční funkcí $F_n(x)$ a teoretickou distribuční funkcí $F(x)$:

- $H_0$: odchylky mezi $F_n(x)$ a $F(x)$ lze přičíst náhodě při výběru z daného rozdělení.
- $H_1$: data nemají dané rozdělení.
- Testové kritérium: $D = \sup_x \lvert F_n(x) - F(x) \rvert$.
- Kritický obor: $W_\alpha = \{d : d > D_\alpha(n)\}$; na hladině 5 % se pro $n>30$ kritická hodnota aproximuje zlomkem $1{,}36/\sqrt{n}$.

U tohoto testu musí být parametry rozdělení známé předem. Pokud je odhadneme ze stejných dat, která testujeme, běžná p-hodnota z `ks.test()` už pro rozhodnutí nestačí.

Funkci `ks.test()` předáme naměřené hodnoty a označení teoretické funkce `F(x)`, například `"pnorm"` nebo `"pexp"`, spolu s jejími parametry:

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

R sice vypíše $p = 0{,}8847$, ale průměr i směrodatnou odchylku jsme právě spočítali z `x3`. Z tohoto výsledku proto nelze rozhodnout o normalitě. Pro její posouzení použijeme Shapiro-Wilkův test uvedený níže.

### Shapiro-Wilkův test

Shapiro-Wilkův test je určen přímo pro posouzení normality. Seřazené naměřené hodnoty porovnává s hodnotami očekávanými u normálního rozdělení. Využívá přitom jejich korelaci, tedy míru vzájemné souvislosti. Zachycuje mimo jiné nesouměrnost rozdělení i odlišnou špičatost.

- $H_0$: data mají normální rozdělení.
- $H_1$: data nemají normální rozdělení.
- Testové kritérium $W \in \langle 0,1 \rangle$ nabývá hodnot blízkých 1 při dobré shodě s normálním rozdělením.

V praxi se výsledek čte z p-hodnoty, takže není třeba hledat tabulkovou kritickou hodnotu pro $W$. Rozhodujeme takto: $p \ge \alpha \Rightarrow$ $H_0$ nezamítáme, tedy odchylku od normality jsme neprokázali; $p < \alpha \Rightarrow$ $H_0$ zamítáme a předpoklad normality je zpochybněn.

```r
x2 <- c(9.5, 10.5, 8.9, 9.2, 10.0, 8.5, 9.2, 8.8, 10.0, 9.5, 9.2)
shapiro.test(x2)
```
```text
	Shapiro-Wilk normality test

data:  x2
W = 0.96022, p-value = 0.7744
```

U životnosti baterií se normalita nezamítá ($p = 0{,}7744$). Tento výsledek tedy použití t-testu z hlediska normality nezpochybňuje.

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
> Výběrový průměr (145,44 min) a směrodatná odchylka (126,13 min) jsou podobně velké. Medián (113,5 min) leží výrazně níže než průměr, protože delší doby posouvají průměr vzhůru. Shapiro-Wilkův test normalitu zamítá ($p < 0{,}0001$). Exponenciální rozdělení zde může být vhodným kandidátem podle tvaru histogramu. Hodnota $p = 0{,}8421$ z `ks.test()` ale jeho vhodnost nepotvrzuje: parametr `rate` jsme odhadli ze stejných dat. Běžnou p-hodnotu tohoto testu proto nemůžeme použít k rozhodnutí o shodě.

![[mask-th-exponencialni-shoda.png|Histogram doby do poruchy s překrytou hustotou exponenciálního rozdělení s parametrem 1 lomeno výběrovým průměrem]]

## Neparametrické testy

Pokud data neodpovídají předpokladu normality, lze podle typu výběru použít neparametrickou alternativu. Wilcoxonovy testy pracují s pořadím hodnot a normalitu nevyžadují. Polohu rozdělení zde popisujeme pomocí **mediánu** ($x_{0,5}$), nikoli střední hodnoty.

### Wilcoxonovy testy

| $H_0$ | $H_1$ | Příkaz v R |
|---|---|---|
| $x_{0,5} \le c$ | $x_{0,5} > c$ | `wilcox.test(x, alternative = "greater", mu = c)` |
| $x_{0,5} = c$ | $x_{0,5} \neq c$ | `wilcox.test(x, alternative = "two.sided", mu = c)` |
| $x_{0,5} \ge c$ | $x_{0,5} < c$ | `wilcox.test(x, alternative = "less", mu = c)` |

**Jednovýběrový Wilcoxonův test** porovnává polohu jednoho souboru se zadanou konstantou $c$. Je neparametrickou alternativou jednovýběrového t-testu. Předpokládá přibližně souměrné rozdělení hodnot kolem jejich mediánu.

**Párový Wilcoxonův test** pracuje s rozdíly uvnitř dvojic a nahrazuje párový t-test. Porovnává medián rozdílů uvnitř dvojic se zadaným $c$. Tyto rozdíly mají mít přibližně souměrné rozdělení. V R se zadává obdobně jako v tabulce a přidává se `paired = TRUE`.

**Dvouvýběrový Wilcoxonův test** porovnává polohu dvou nezávislých souborů a nahrazuje dvouvýběrový t-test. Pokud mají obě rozdělení stejný tvar a liší se jen posunutím, můžeme výsledek chápat jako porovnání mediánů. Při běžném porovnání nezadáváme argument `mu`. Pro výšky chlapců a dívek použijeme:

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

Protože $p = 0{,}315 > 0{,}05$, nulovou hypotézu nezamítáme. Rozdíl v poloze výšek chlapců a dívek se neprokázal, stejně jako předtím rozdíl průměrů u dvouvýběrového t-testu.

> [!example] Příklad: Realitní odhadci — neparametrická alternativa
> U cenových odhadů Shapiro-Wilkův test zamítl normalitu rozdílů ($p = 0{,}03203$). Možnou alternativou je párový Wilcoxonův test, pokud je rozdělení rozdílů přibližně souměrné. Pro stejné dvojice odhadů vychází:
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
> Protože $p = 0{,}1484 > 0{,}05$, nulovou hypotézu nezamítáme. Posun mezi odhady se neprokázal. Rozdíl neprokázal ani předchozí párový t-test, jehož předpoklad normality však byl zpochybněn. Wilcoxonův test normalitu nevyžaduje, ale jeho závěr zde platí za předpokladu přibližné souměrnosti rozdílů.

### Kruskalův-Wallisův test

Kruskalův-Wallisův test porovnává více nezávislých skupin. Rozšiřuje dvouvýběrový Wilcoxonův test a je neparametrickou obdobou analýzy rozptylu jednoduchého třídění. Nulová hypotéza $H_0$ říká, že všechny výběry pocházejí ze stejného rozdělení.

Například u výrobků z různých strojů zaznamenáme do jednoho sloupce rozměr výrobku a do druhého stroj, z něhož pochází. Každý výrobek se objeví jen jednou. Chceme zjistit, zda se rozměry mezi stroji liší.

Data pro tento test lze uložit do tabulky: v jednom sloupci jsou naměřené hodnoty, ve druhém skupina, ke které každé měření patří. Tomu odpovídá zápis `kruskal.test(y ~ faktor, data = soubor)`. Název `y` zastupuje číselný sloupec, `faktor` sloupec se skupinami a `soubor` celou tabulku. Při použití se tyto názvy nahradí názvy vlastních dat.

### Mediánový test

Mediánový test také porovnává více nezávislých skupin bez předpokladu normality. Je alternativou k analýze rozptylu jednoduchého třídění. Hypotéza $H_0$ předpokládá, že všechny výběry pocházejí ze stejného rozdělení. V R je test součástí balíčku `agricolae`.

I zde můžeme porovnávat rozměry výrobků z různých strojů: `y` obsahuje rozměry a `faktor` označení stroje u každého výrobku.

Po načtení balíčku příkazem `library(agricolae)` se používá zápis `Median.test(y, faktor)`. Do `y` patří naměřené hodnoty a do `faktor` označení skupin ve stejném pořadí.

### Friedmanův test

Friedmanův test porovnává podmínky u párovaných pozorování. Pozorování jsou uspořádána do bloků a pro každou kombinaci bloku a podmínky máme jedno měření. Jde o neparametrickou obdobu analýzy rozptylu dvojného třídění s jedním pozorováním v každé podtřídě. Hypotéza $H_0$ říká, že distribuční funkce veličin $X_{i1}, \dots, X_{ik}$ jsou totožné.

Představme si, že stejní lidé vyzkouší různé pracovní postupy a u každého změříme čas. Časy téhož člověka tvoří jeden blok, protože jeho rychlost ovlivňuje všechna jeho měření. V tabulce by každý řádek obsahoval čas, použitý postup a označení člověka.

V tabulce potřebujeme naměřenou hodnotu, označení podmínky a označení bloku, ke kterému měření patří. Zápis `friedman.test(y ~ A | B, data = soubor)` používá `A` pro porovnávané podmínky a `B` pro bloky párovaných pozorování. Pokud máme tyto údaje v samostatných vektorech, použijeme `friedman.test(y, A, B)` bez argumentu `data`.

## Přehled testů

![[mask-ilu-volba-testu.png|Rozhodovací strom pro volbu testu: jeden výběr, párová měření, dva nezávislé výběry nebo více výběrů; podle normality dat t-test, F-test nebo Wilcoxonův, Kruskalův-Wallisův či Friedmanův test s příkazy v R]]

| Situace | Test | R funkce |
|---|---|---|
| Jedna střední hodnota vs. zadané číslo, normální data | jednovýběrový t-test | `t.test(x, mu = ..., alternative = ...)` |
| Rozdíl dvou závislých měření, diference normální | párový t-test | `t.test(x, y, paired = TRUE)` |
| Shoda rozptylů dvou nezávislých normálních výběrů | F-test | `var.test(x, y)` |
| Shoda středních hodnot dvou nezávislých normálních výběrů | dvouvýběrový t-test | `t.test(x, y, var.equal = TRUE/FALSE)` |
| Shoda s rozdělením o předem známých parametrech | Kolmogorovův-Smirnovův test | `ks.test(x, "pnorm", mu, sigma)`, `ks.test(x, "pexp", 1/delta)` |
| Normalita dat | Shapiro-Wilkův test | `shapiro.test(x)` |
| Medián jednoho výběru vs. konstanta, přibližně souměrná data | jednovýběrový Wilcoxonův test | `wilcox.test(x, mu = c, alternative = ...)` |
| Medián rozdílů ve dvojicích, přibližně souměrné rozdíly | párový Wilcoxonův test | `wilcox.test(x, y, paired = TRUE, mu = c)` |
| Poloha dvou nezávislých výběrů; mediány při stejném tvaru rozdělení | dvouvýběrový Wilcoxonův test | `wilcox.test(x, y)` |
| Více než dva nezávislé výběry, data nejsou normální | Kruskalův-Wallisův test | `kruskal.test(y ~ faktor, data)` |
| Více než dva nezávislé výběry, data nejsou normální (alternativa) | mediánový test | `Median.test(y, faktor)` z balíčku `agricolae` |
| Více než dva závislé výběry (dvojné třídění, jedno pozorování na podtřídu) | Friedmanův test | `friedman.test(y ~ A \| B, data)` |

## Časté chyby

- **Nezamítnutí $H_0$ nedokazuje platnost $H_0$.** U kabelů A/B vyšlo $p = 0{,}06932$. Na hladině 5 % se $H_0$ nezamítá, ale p-hodnota leží blízko hranice. Závěr zní „rozdíl průměrů se neprokázal“. Rovnost průměrů tím prokázána není.
- **Samotný výstup t-testu nepotvrzuje jeho předpoklady.** U realitních odhadců se párový t-test spočítal bez varování, ale Shapiro-Wilkův test zamítl normalitu rozdílů. Před interpretací je proto třeba posoudit předpoklady zvolené metody. U párového t-testu se normalita týká rozdílů, u dvouvýběrového obou souborů.
- **Nastavení `var.equal` mění variantu t-testu.** Výchozí `var.equal = FALSE` používá Welchovu variantu bez předpokladu shodných rozptylů. Pokud zvolíme variantu se společným rozptylem, musíme zadat `var.equal = TRUE`. F-test přitom může hypotézu shodných rozptylů nezamítnout, ale nemůže jejich shodu dokázat.
- **Směr alternativy mění kritický obor i závěr.** Volba `alternative = "greater"/"less"/"two.sided"` musí odpovídat hypotéze $H_1$. Výchozí `"two.sided"` posuzuje odchylku oběma směry a nehodí se automaticky pro každou otázku.
- **U Shapiro-Wilkova testu čteme rozhodnutí z p-hodnoty.** Samotné $W$ bez dalšího porovnání nestačí; R poskytuje p-hodnotu přímo.

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

Dokumentace R: [Kolmogorovův-Smirnovův test](https://www.stat.ethz.ch/R-manual/R-devel/library/stats/html/ks.test.html), [Wilcoxonovy testy](https://stat.ethz.ch/R-manual/R-devel/library/stats/html/wilcox.test.html).
