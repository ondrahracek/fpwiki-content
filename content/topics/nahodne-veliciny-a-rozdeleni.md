---
title: "Náhodné veličiny a rozdělení pravděpodobnosti"
course: mask
type: topic
tags: [mask, statistika, nahodna-velicina, normalni-rozdeleni, distribucni-funkce, r]
sources: ["raw/mask/01 náhodné veličiny.pdf", "raw/mask/01 náhodné veličiny - návod R.pdf", "raw/mask/příklady 01 a 02.docx"]
created: 2026-10-02
updated: 2026-10-02
---

# Náhodné veličiny a rozdělení pravděpodobnosti

> [!tldr] V kostce
> - Náhodná veličina je funkce, která výsledkům pokusu přiřazuje reálná čísla; rozlišujeme **diskrétní** (izolované hodnoty s nenulovou pravděpodobností) a **spojité** (hodnoty z intervalu, každý bod má nulovou pravděpodobnost).
> - Každou náhodnou veličinu popisuje **distribuční funkce** $F(x) = P(X \le x)$; u spojité veličiny platí $F'(x) = f(x)$, kde $f(x)$ je hustota pravděpodobnosti.
> - Pravděpodobnost na intervalu se počítá jako $P(x_1 < X < x_2) = F(x_2) - F(x_1)$.
> - **Normální rozdělení** $N(\mu; \sigma^2)$ je nejdůležitější spojité rozdělení; v R ho počítáme funkcemi `dnorm`, `pnorm`, `qnorm` — R jako parametr očekává směrodatnou odchylku $\sigma$, ne rozptyl $\sigma^2$.
> - **Studentovo**, **Pearsonovo (χ²)** a **Fisherovo-Snedecorovo** rozdělení slouží jako nástroj pro pozdější konstrukci intervalů spolehlivosti a testování hypotéz.

## Náhodná veličina

[[mask|Metody aplikované statistiky]] pracuje s veličinami, jejichž hodnota závisí na náhodě. Formálně: uvažujeme základní prostor $\Omega$ přiřazený výsledkům pokusu. **Náhodná veličina** $X$ je funkce, která prvkům $\omega \in \Omega$ přiřazuje reálná čísla $x$, kde $x = X(\omega)$. Náhodné veličiny značíme velkými písmeny ($X$, $Y$, $T$), jejich konkrétní hodnoty odpovídajícími malými písmeny ($x$, $y$, $t$); pravděpodobnost, že $X$ nabyla hodnoty $x$, zapisujeme $P(X = x)$.

Podle typu hodnot, kterých náhodná veličina nabývá, rozlišujeme dva typy:

- **Diskrétní náhodná veličina** — prvky $\Omega$ se zobrazí na osu reálných čísel jako izolované body $x_1, x_2, \dots, x_k$, přičemž každý z nich má nenulovou pravděpodobnost. Příklad: počet bodů při hodu kostkou, počet studentů na cvičení.
- **Spojitá náhodná veličina** — hodnoty tvoří interval na ose reálných čísel, přičemž každý bod intervalu má nulovou pravděpodobnost. Příklad: velikost výrobku, doba psaní testu, výška dětí v populaci.

## Distribuční funkce

Náhodná veličina nabývá při pokusu určité hodnoty, aniž bychom předem věděli, které. Při opakování pokusu se ale projevují zákonitosti, které popisují **zákony rozdělení**. Nejobecnějším z nich je distribuční funkce.

![[mask-nv-distribucni-funkce.png|Distribuční funkce diskrétní náhodné veličiny (schodovitý průběh, hod kostkou) vedle distribuční funkce spojité náhodné veličiny (hladká S-křivka, N(0;1))]]

> [!info] Definice
> Distribuční funkcí náhodné veličiny $X$ nazýváme reálnou funkci $F(x)$ definovanou pro každé reálné číslo $x$ jako
> $$F(x) = P(X \le x).$$
> $F(x)$ tedy vyjadřuje pravděpodobnost, s jakou $X$ nabude hodnoty z intervalu $(-\infty, x\rangle$.

Značí-li například $X$ výšku mužů v populaci, pak $F(175)$ je pravděpodobnost, že muž měří nejvýše 175 cm.

Pro distribuční funkci vždy platí:

- $0 \le F(x) \le 1$,
- je neklesající: $x_1 \le x_2 \Rightarrow F(x_1) \le F(x_2)$,
- je spojitá zprava: $\lim_{h \to 0^+} F(x+h) = F(x)$,
- $\lim_{x \to -\infty} F(x) = 0$, $\lim_{x \to \infty} F(x) = 1$.

U spojité náhodné veličiny je distribuční funkce svázaná s hustotou pravděpodobnosti vztahem

$$F'(x) = f(x), \qquad F(x) = \int_{-\infty}^{x} f(t)\,dt.$$

Pravděpodobnost, že $X$ padne mezi body $x_1$ a $x_2$, se pak počítá jako

$$P(x_1 < X < x_2) = \int_{x_1}^{x_2} f(t)\,dt = F(x_2) - F(x_1).$$

## Hustota pravděpodobnosti

> [!info] Definice
> Hustota pravděpodobnosti $f(x)$ určuje, jak jsou hodnoty spojité náhodné veličiny $X$ nahuštěny v okolí bodu $x$. Je vždy nezáporná a platí pro ni $\int_{-\infty}^{\infty} f(x)\,dx = 1$.

Intuitivně: rozdělíme-li hodnoty náhodné veličiny (např. výšku mužů v populaci) do stejně širokých intervalů, bude v intervalech blízko průměru nahuštěno víc pozorování než v krajních intervalech — hustota tam bude vyšší.

## Charakteristiky spojité náhodné veličiny

**Střední hodnota** je nejdůležitější charakteristika náhodné veličiny:

$$E(X) = \int_{-\infty}^{\infty} x \cdot f(x)\,dx.$$

Je to číslo, kolem něhož kolísají výběrové průměry vypočtené ze sérií pozorovaných hodnot náhodné veličiny.

**Rozptyl** a **směrodatná odchylka**:

$$D(X) = \int_{-\infty}^{\infty} [x - E(X)]^2 f(x)\,dx = \int_{-\infty}^{\infty} x^2 f(x)\,dx - [E(X)]^2, \qquad \sigma(X) = \sqrt{D(X)}.$$

Směrodatná odchylka udává, jak moc jsou hodnoty náhodné veličiny rozptýlené kolem střední hodnoty. (Pro odhad těchto charakteristik z naměřených dat viz empirické protějšky v [[popisna-statistika]].)

**Kvantily** udávají, jak jsou hodnoty náhodné veličiny $X$ rozděleny na ose reálných čísel v určitém pravděpodobnostním poměru. 100p%-ní kvantil $x_p$ je číslo, pro které při zvolené pravděpodobnosti $p$ platí

$$F(x_p) = p.$$

V intervalu $(-\infty; x_p)$ leží 100p % hodnot, v intervalu $\langle x_p; \infty)$ leží 100(1-p) % hodnot. Nejdůležitější kvantily jsou medián $x_{0{,}5}$, dolní kvartil $x_{0{,}25}$ a horní kvartil $x_{0{,}75}$.

## Normální rozdělení

Spojitá náhodná veličina $X$ má **normální rozdělení** $N(\mu; \sigma^2)$, jestliže její hustota pravděpodobnosti a distribuční funkce jsou dány předpisy

$$f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}, \qquad F(x) = \frac{1}{\sigma\sqrt{2\pi}} \int_{-\infty}^{x} e^{-\frac{(t-\mu)^2}{2\sigma^2}}\,dt,$$

přičemž $E(X) = \mu$, $D(X) = \sigma^2$.

![[mask-nv-normalni.png|Gaussova křivka hustoty normálního rozdělení s vybarvenými pásmy μ ± σ (68,27 % hodnot), μ ± 2σ (95,45 %) a μ ± 3σ (99,73 %) a odpovídající S-křivka distribuční funkce]]

Křivka hustoty se nazývá **Gaussova křivka**: je symetrická kolem svislé přímky procházející $\mu$, kde má $f(x)$ globální maximum, a ve vzdálenosti $3\sigma$ od $\mu$ se téměř dotýká osy x — zhruba 99,73 % hodnot leží v intervalu $(\mu - 3\sigma; \mu + 3\sigma)$.

Zvláštní postavení má **normované normální rozdělení** $N(0; 1)$, na které se dá libovolné normální rozdělení převést standardizací $Z = (X-\mu)/\sigma$.

```graph
title: Hustota normálního rozdělení N(μ; σ²)
alt: Hustota normálního rozdělení f(x) = 1/(σ√(2π)) krát exp(−(x−μ)²/(2σ²)) s nastavitelnou střední hodnotou μ a směrodatnou odchylkou σ. Se zvyšujícím se σ se křivka zplošťuje a rozšiřuje, se změnou μ se posouvá po ose x.
xAxis: { label: "x", domain: [-15, 15] }
yAxis: { label: "f(x)", domain: [0, 0.9] }
params:
  - { name: mu, label: "střední hodnota μ", min: -3, max: 3, default: 0, step: 0.5 }
  - { name: s, label: "směrodatná odchylka σ", min: 0.5, max: 3, default: 1, step: 0.25 }
curves:
  - { fn: "(1/(s*sqrt(2*PI)))*exp(-((x-mu)^2)/(2*s^2))", label: "f(x) = N(μ; σ²)", color: "fp-purple" }
markers:
  - { x: "mu", label: "μ" }
```

> [!warning] R očekává směrodatnou odchylku, ne rozptyl
> Zápis $N(\mu; \sigma^2)$ v definici používá **rozptyl**. Funkce `dnorm`, `pnorm` a `qnorm` v R ale jako třetí argument berou **směrodatnou odchylku** $\sigma$. Má-li náhodná veličina rozdělení $N(10; 0{,}12)$, je `sd = sqrt(0.12)`, ne `sd = 0.12`.

V R:

```r
dnorm(0)
pnorm(1.96)
qnorm(0.975)
```

```text
[1] 0.3989423
[1] 0.9750021
[1] 1.959964
```

`dnorm(0)` je hodnota hustoty $N(0;1)$ v bodě 0, `pnorm(1.96)` je $F(1{,}96)$ a `qnorm(0.975)` je 97,5%-ní kvantil — hodnota, pod kterou leží 97,5 % pravděpodobnosti.

> [!example] Příklad: Návštěvnost zábavního parku
> Denní návštěvnost zábavního parku je náhodná veličina s normálním rozdělením, průměrnou hodnotou 230 a směrodatnou odchylkou 27,5 návštěvníků: $X \sim N(230; 27{,}5^2)$. Přijde-li za den méně než 180 návštěvníků, je park ztrátový. Kolik procent dní je ztrátových?

![[mask-nv-priklad-park.png|Hustota normálního rozdělení N(230; 27,5²) s vybarvenou plochou pod křivkou vlevo od 180, odpovídající pravděpodobnosti 3,45 %]]

```r
pnorm(180, mean = 230, sd = 27.5)
```

```text
[1] 0.03451817
```

Park je ztrátový přibližně v 3,45 % dní.

> [!example] Příklad: Délka výrobku
> Automat je seřízen tak, aby střední hodnota délky výrobku byla 42 mm, s přesností charakterizovanou směrodatnou odchylkou 1,2 mm: $X \sim N(42; 1{,}2^2)$. Výrobky s délkou 41 až 43 mm jsou zařazeny do 1. jakostní třídy. Jaké je procento výrobků v 1. jakostní třídě?

![[mask-nv-priklad-delka.png|Hustota normálního rozdělení N(42; 1,2²) s vybarvenou plochou mezi 41 a 43 mm, odpovídající pravděpodobnosti 59,53 %]]

```r
pnorm(43, mean = 42, sd = 1.2) - pnorm(41, mean = 42, sd = 1.2)
```

```text
[1] 0.5953432
```

Do 1. jakostní třídy spadá přibližně 59,53 % výrobků.

> [!example] Příklad: Obsah ampulky
> Obsah ampulky s lékem (v cm³) má rozdělení $N(10; 0{,}12)$, tedy střední hodnota 10 a rozptyl 0,12 ($\sigma = \sqrt{0{,}12} \approx 0{,}346$). Kolik procent ampulek má obsah menší než 9,8 cm³?

![[mask-nv-priklad-ampulka.png|Hustota normálního rozdělení N(10; 0,12) s vybarvenou plochou vlevo od 9,8 cm³, odpovídající pravděpodobnosti 28,19 %]]

```r
pnorm(9.8, mean = 10, sd = sqrt(0.12))
```

```text
[1] 0.2818514
```

Obsah menší než 9,8 cm³ má přibližně 28,19 % ampulek.

## Další rozdělení dostupná v R

Vedle normálního rozdělení R přímo nabízí hustotu, distribuční funkci a kvantilovou funkci i pro další běžná rozdělení. Pojmenování funkcí je jednotné: `d*` je hustota/pravděpodobnostní funkce, `p*` distribuční funkce (s `lower.tail = FALSE`, případně čtvrtým argumentem `TRUE`/`FALSE`, pro horní chvost) a `q*` kvantilová funkce.

| Rozdělení | $P(X=k)$ / $f(x)$ | $P(X \le k)$ | horní chvost $P(X>k)$ |
|---|---|---|---|
| Binomické $Bi(n,p)$ | `dbinom(k, n, p)` | `pbinom(k, n, p)` | `pbinom(k, n, p, FALSE)` |
| Poissonovo $Po(\lambda)$ | `dpois(k, lambda)` | `ppois(k, lambda)` | `ppois(k, lambda, FALSE)` |
| Geometrické $G(p)$ | `dgeom(k, p)` | `pgeom(k, p)` | `pgeom(k, p, FALSE)` |
| Hypergeometrické $H(N,M,n)$ | `dhyper(k, M, N-M, n)` | `phyper(k, M, N-M, n)` | `phyper(k, M, N-M, n, FALSE)` |
| Exponenciální $E(\delta)$ | `dexp(k, 1/delta)` | `pexp(k, 1/delta)` | `pexp(k, 1/delta, FALSE)` |

> [!warning] Exponenciální rozdělení: R bere intenzitu, ne střední hodnotu
> R parametrizuje exponenciální rozdělení intenzitou (`rate`). Je-li $\delta$ střední doba do události, do R se dosazuje `1/delta`, ne `delta`.

V R (pravděpodobnostní a distribuční funkce diskrétní náhodné veličiny $X \sim Bi(5; 0{,}95)$, a pravděpodobnost, že u exponenciálního rozdělení se střední hodnotou $\delta = 5$ nastane událost do 3 jednotek času):

```r
x <- 0:5
round(dbinom(x, 5, 0.95), 4)
round(pbinom(x, 5, 0.95), 4)

delta <- 5
round(pexp(3, rate = 1 / delta), 4)
```

```text
[1] 0.0000 0.0000 0.0011 0.0214 0.2036 0.7738
[1] 0.0000 0.0000 0.0012 0.0226 0.2262 1.0000
[1] 0.4512
```

## Studentovo, Pearsonovo a Fisherovo-Snedecorovo rozdělení

Tato tři rozdělení mají statistiky, které se dále používají při konstrukci intervalů spolehlivosti a testování hypotéz (viz [[testovani-hypotez]]) — na rozdíl od normálního rozdělení se v příkladech této kapitoly samostatně nepočítají, jsou to nástroje pro další kapitoly.

**Studentovo rozdělení** s $k$ stupni volnosti má hustotu pravděpodobnosti

$$f(x) = \frac{1}{B\left(\frac12, \frac{k}{2}\right)\sqrt{k}} \left(1 + \frac{x^2}{k}\right)^{-\frac{k+1}{2}}, \qquad x \in \mathbb{R},$$

kde $B$ je funkce beta. Je symetrické kolem nuly; číslo $k$ určuje tvar křivky — s rostoucím $k$ se rozdělení blíží normálnímu.

**Pearsonovo (chí-kvadrát) rozdělení** s $k$ stupni volnosti:

$$f(x) = \frac{1}{2^{k/2}\Gamma(k/2)} x^{k/2-1} e^{-x/2}, \qquad x > 0,$$

kde $\Gamma$ je funkce gama.

**Fisherovo-Snedecorovo rozdělení** se stupni volnosti $k_1$ a $k_2$:

$$f(x) = \frac{1}{B\left(\frac{k_1}{2}, \frac{k_2}{2}\right)} \left(\frac{k_1}{k_2}\right)^{k_1/2} x^{k_1/2 - 1} \left(1 + \frac{k_1}{k_2}x\right)^{-\frac{k_1+k_2}{2}}, \qquad x > 0.$$

![[mask-nv-specialni-rozdeleni.png|Tři grafy hustot vedle sebe: Studentovo rozdělení pro k=1,2,5,100 konvergující k normálnímu tvaru, Pearsonovo (χ²) rozdělení pro k=1,2,3,5,10 a Fisherovo-Snedecorovo rozdělení pro vybrané dvojice stupňů volnosti]]

```graph
title: Studentovo rozdělení a jeho konvergence k normálnímu rozdělení
alt: Srovnání hustoty standardizovaného normálního rozdělení N(0;1) s hustotou Studentova rozdělení pro k = 1, 2 a 4 stupně volnosti. S rostoucím k se Studentovo rozdělení přibližuje normálnímu — má méně těžké konce a vyšší vrchol.
xAxis: { label: "x", domain: [-6, 6] }
yAxis: { label: "f(x)", domain: [0, 0.42] }
curves:
  - { fn: "exp(-x^2/2)/sqrt(2*PI)", label: "N(0; 1)", color: "ink" }
  - { fn: "(1/PI)*(1+x^2)^(-1)", label: "t, k = 1", color: "fp-red" }
  - { fn: "(1/(2*sqrt(2)))*(1+x^2/2)^(-1.5)", label: "t, k = 2", color: "fp-purple" }
  - { fn: "(3/8)*(1+x^2/4)^(-2.5)", label: "t, k = 4", color: "paper-500" }
```

R funkce pro tato tři rozdělení:

| Rozdělení | hustota | distribuční funkce | kvantil |
|---|---|---|---|
| Studentovo $t(k)$ | `dt(x, df = k)` | `pt(x, df = k)` | `qt(p, df = k)` |
| Pearsonovo $\chi^2(k)$ | `dchisq(x, df = k)` | `pchisq(x, df = k)` | `qchisq(p, df = k)` |
| Fisherovo-Snedecorovo $F(k_1, k_2)$ | `df(x, df1 = k1, df2 = k2)` | `pf(x, df1 = k1, df2 = k2)` | `qf(p, df1 = k1, df2 = k2)` |

V R (97,5%-ní kvantil Studentova rozdělení s 9 stupni volnosti, 95%-ní kvantily Pearsonova a Fisherova-Snedecorova rozdělení):

```r
qt(0.975, df = 9)
qchisq(0.95, df = 9)
qf(0.95, df1 = 3, df2 = 10)
```

```text
[1] 2.262157
[1] 16.91898
[1] 3.708265
```

## Časté chyby

- **Rozptyl vs. směrodatná odchylka v R.** Zápis $N(\mu; \sigma^2)$ používá rozptyl, ale `dnorm`/`pnorm`/`qnorm` očekávají směrodatnou odchylku. Dosazení rozptylu místo $\sqrt{\sigma^2}$ dává jiný — a pro $\sigma^2 \ne 1$ výrazně odlišný — výsledek (viz příklad s ampulkou).
- **$P(X=x)$ u spojité veličiny je vždy 0.** Hustota $f(x)$ sama o sobě pravděpodobnost neudává — pravděpodobnost dává až plocha pod křivkou na intervalu.
- **Záměna stupňů volnosti u Fisherova-Snedecorova rozdělení.** $k_1$ (čitatel) a $k_2$ (jmenovatel) nejsou zaměnitelné — `qf(p, df1, df2)` dá jiný výsledek než `qf(p, df2, df1)`.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[popisna-statistika]]
- [[testovani-hypotez]]
- [[regresni-a-korelacni-analyza]]
- [[kontingencni-tabulky]]
- [[regulacni-diagramy-a-indexy-zpusobilosti]]
- [[mask-r-tahak|Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.
