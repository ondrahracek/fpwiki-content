---
title: "Náhodné veličiny a rozdělení pravděpodobnosti"
course: mask
type: topic
tags: [mask, statistika, nahodna-velicina, normalni-rozdeleni, distribucni-funkce, r]
sources: ["raw/mask/01 náhodné veličiny.pdf", "raw/mask/01 náhodné veličiny - návod R.pdf", "raw/mask/příklady 01 a 02.docx"]
created: 2026-10-02
updated: 2026-11-06
---

# Náhodné veličiny a rozdělení pravděpodobnosti

> [!tldr] V kostce
> - Životnost výrobku nebo počet bodů při hodu kostkou můžeme popsat jako náhodnou veličinu.
> - Rozdělení pravděpodobnosti říká, jak pravděpodobné jsou jednotlivé výsledky nebo intervaly hodnot.
> - U spojité veličiny počítáme pravděpodobnost pomocí plochy pod křivkou hustoty.
> - Střední hodnota popisuje střed rozdělení, rozptyl jeho rozptýlení a kvantil hranici pro zadanou pravděpodobnost.

## Náhodná veličina

Při hodu kostkou předem neznáme počet bodů, které padnou. Podobně neznáme přesnou délku náhodně vybraného výrobku. Takové číselné výsledky popisujeme pomocí náhodné veličiny.

Množinu všech možných výsledků pokusu označujeme $\Omega$. **Náhodná veličina** $X$ každému výsledku $\omega \in \Omega$ přiřadí reálné číslo $x$ podle předpisu $x = X(\omega)$. Náhodnou veličinu zapisujeme velkým písmenem ($X$, $Y$, $T$), konkrétní naměřenou hodnotu malým písmenem ($x$, $y$, $t$). Pravděpodobnost, že $X$ nabude hodnoty $x$, zapisujeme $P(X = x)$.

Podle možných hodnot rozlišujeme:

- **Diskrétní náhodná veličina** nabývá oddělených hodnot. Výsledky z $\Omega$ tak odpovídají bodům $x_1, x_2, \dots, x_k$ na číselné ose, z nichž každý má nenulovou pravděpodobnost. Příkladem je počet bodů při hodu kostkou nebo počet studentů na cvičení.
- **Spojitá náhodná veličina** může nabýt libovolné hodnoty z intervalu. Pravděpodobnost jedné přesné hodnoty je nulová; smysl má počítat pravděpodobnost pro celý interval. Příkladem je velikost výrobku, doba psaní testu nebo výška dětí v populaci.

## Distribuční funkce

Jednotlivý výsledek pokusu předem neznáme, ale můžeme popsat pravděpodobnosti možných výsledků. Tento popis se nazývá **rozdělení pravděpodobnosti**. Pro diskrétní i spojité veličiny ho lze vyjádřit distribuční funkcí.

![[mask-nv-distribucni-funkce.png|Distribuční funkce diskrétní náhodné veličiny (schodovitý průběh, hod kostkou) vedle distribuční funkce spojité náhodné veličiny (hladká S-křivka, N(0;1))]]

> [!info] Definice
> **Distribuční funkce** náhodné veličiny $X$ je funkce $F(x)$, která pro každé reálné číslo $x$ udává
> $$F(x) = P(X \le x).$$
> Hodnota $F(x)$ tedy zahrnuje všechny výsledky $X$ v intervalu $(-\infty, x\rangle$, včetně jeho pravého krajního bodu.

Značí-li například $X$ výšku mužů v populaci, pak $F(175)$ je pravděpodobnost, že muž měří nejvýše 175 cm.

Distribuční funkce má tyto vlastnosti:

- $0 \le F(x) \le 1$,
- je neklesající: $x_1 \le x_2 \Rightarrow F(x_1) \le F(x_2)$,
- je spojitá zprava: $\lim_{h \to 0^+} F(x+h) = F(x)$,
- $\lim_{x \to -\infty} F(x) = 0$, $\lim_{x \to \infty} F(x) = 1$.

U spojité náhodné veličiny získáme distribuční funkci jako plochu pod křivkou hustoty od levého kraje až po zvolený bod. Obráceně je hustota derivací distribuční funkce:

$$F'(x) = f(x), \qquad F(x) = \int_{-\infty}^{x} f(t)\,dt.$$

Pravděpodobnost, že $X$ leží mezi $x_1$ a $x_2$, odpovídá ploše pod hustotou mezi těmito body. Stačí proto odečíst hodnoty distribuční funkce:

$$P(x_1 < X < x_2) = \int_{x_1}^{x_2} f(t)\,dt = F(x_2) - F(x_1).$$

## Hustota pravděpodobnosti

> [!info] Definice
> Hustota pravděpodobnosti $f(x)$ určuje, jak jsou hodnoty spojité náhodné veličiny $X$ nahuštěny v okolí bodu $x$. Je vždy nezáporná a platí pro ni $\int_{-\infty}^{\infty} f(x)\,dx = 1$.

Například výšky mužů v populaci můžeme rozdělit do stejně širokých intervalů. V intervalech blízko průměru bývá více pozorování než na okrajích. Vyšší hustota zde vyjadřuje právě toto větší soustředění hodnot.

## Charakteristiky spojité náhodné veličiny

**Střední hodnota** popisuje průměrnou úroveň náhodné veličiny:

$$E(X) = \int_{-\infty}^{\infty} x \cdot f(x)\,dx.$$

Pokud opakovaně provedeme sérii pozorování a pokaždé spočítáme průměr, budou tyto výběrové průměry kolísat kolem střední hodnoty.

**Rozptyl** popisuje, jak daleko od střední hodnoty hodnoty leží. Jeho odmocninou je **směrodatná odchylka**:

$$D(X) = \int_{-\infty}^{\infty} [x - E(X)]^2 f(x)\,dx = \int_{-\infty}^{\infty} x^2 f(x)\,dx - [E(X)]^2, \qquad \sigma(X) = \sqrt{D(X)}.$$

Směrodatná odchylka vyjadřuje rozptýlení ve stejných jednotkách jako sledovaná veličina. Odhady střední hodnoty a rozptylu z naměřených dat popisuje [[popisna-statistika|popisná statistika]].

**Kvantil** je hranice, pod kterou leží zvolený podíl hodnot náhodné veličiny $X$. Pro 100p%-ní kvantil $x_p$ a pravděpodobnost $p$ platí

$$F(x_p) = p.$$

V intervalu $(-\infty; x_p)$ leží 100p % hodnot, v intervalu $\langle x_p; \infty)$ leží 100(1-p) % hodnot. Nejdůležitější kvantily jsou medián $x_{0{,}5}$, dolní kvartil $x_{0{,}25}$ a horní kvartil $x_{0{,}75}$.

## Normální rozdělení

Normální rozdělení má souměrnou zvonovitou hustotu. Její polohu určuje střední hodnota a šířku směrodatná odchylka. Spojitá náhodná veličina $X$ s **normálním rozdělením** $N(\mu; \sigma^2)$ má hustotu a distribuční funkci

$$f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}, \qquad F(x) = \frac{1}{\sigma\sqrt{2\pi}} \int_{-\infty}^{x} e^{-\frac{(t-\mu)^2}{2\sigma^2}}\,dt,$$

přičemž $E(X) = \mu$, $D(X) = \sigma^2$.

![[mask-nv-normalni.png|Gaussova křivka hustoty normálního rozdělení s vybarvenými pásmy μ ± σ (68,27 % hodnot), μ ± 2σ (95,45 %) a μ ± 3σ (99,73 %) a odpovídající S-křivka distribuční funkce]]

Křivka hustoty se nazývá **Gaussova křivka**. Je souměrná kolem $\mu$ a právě zde má $f(x)$ nejvyšší hodnotu. Ve vzdálenosti $3\sigma$ od $\mu$ je už křivka velmi blízko ose x. V intervalu $(\mu - 3\sigma; \mu + 3\sigma)$ leží zhruba 99,73 % hodnot.

**Normované normální rozdělení** $N(0; 1)$ získáme z libovolného normálního rozdělení tak, že odečteme střední hodnotu a výsledek vydělíme směrodatnou odchylkou. Tento převod se nazývá standardizace: $Z = (X-\mu)/\sigma$.

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

Hustotu v bodě spočítá `dnorm()`, pravděpodobnost do dané hranice `pnorm()` a hranici pro zadanou pravděpodobnost `qnorm()`:

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

`dnorm(0)` vrací výšku hustoty $N(0;1)$ v bodě 0. Výsledek `pnorm(1.96)` je pravděpodobnost $F(1{,}96)$. Funkce `qnorm(0.975)` postupuje opačně: vrací 97,5%-ní kvantil, tedy hranici, pod kterou leží 97,5 % pravděpodobnosti.

> [!example] Příklad: Návštěvnost zábavního parku
> Denní návštěvnost zábavního parku je náhodná veličina s normálním rozdělením, průměrnou hodnotou 230 a směrodatnou odchylkou 27,5 návštěvníků: $X \sim N(230; 27{,}5^2)$. Přijde-li za den méně než 180 návštěvníků, je park ztrátový. Kolik procent dní je ztrátových?

![[mask-nv-priklad-park.png|Hustota normálního rozdělení N(230; 27,5²) s vybarvenou plochou pod křivkou vlevo od 180, odpovídající pravděpodobnosti 3,45 %]]

```r
pnorm(180, mean = 230, sd = 27.5)
```

```text
[1] 0.03451817
```

Plocha vlevo od hranice odpovídá ztrátovým dnům. Park je tedy ztrátový přibližně ve 3,45 % dní.

> [!example] Příklad: Délka výrobku
> Automat je seřízen tak, aby střední hodnota délky výrobku byla 42 mm, s přesností charakterizovanou směrodatnou odchylkou 1,2 mm: $X \sim N(42; 1{,}2^2)$. Výrobky s délkou 41 až 43 mm jsou zařazeny do 1. jakostní třídy. Jaké je procento výrobků v 1. jakostní třídě?

![[mask-nv-priklad-delka.png|Hustota normálního rozdělení N(42; 1,2²) s vybarvenou plochou mezi 41 a 43 mm, odpovídající pravděpodobnosti 59,53 %]]

```r
pnorm(43, mean = 42, sd = 1.2) - pnorm(41, mean = 42, sd = 1.2)
```

```text
[1] 0.5953432
```

Odečtením obou pravděpodobností zůstane podíl délek mezi stanovenými mezemi. Do 1. jakostní třídy tak spadá přibližně 59,53 % výrobků.

> [!example] Příklad: Obsah ampulky
> Obsah ampulky s lékem (v cm³) má rozdělení $N(10; 0{,}12)$, tedy střední hodnota 10 a rozptyl 0,12 ($\sigma = \sqrt{0{,}12} \approx 0{,}346$). Kolik procent ampulek má obsah menší než 9,8 cm³?

![[mask-nv-priklad-ampulka.png|Hustota normálního rozdělení N(10; 0,12) s vybarvenou plochou vlevo od 9,8 cm³, odpovídající pravděpodobnosti 28,19 %]]

```r
pnorm(9.8, mean = 10, sd = sqrt(0.12))
```

```text
[1] 0.2818514
```

Výsledek vyjadřuje pravděpodobnost pod zadanou hranicí: obsah menší než 9,8 cm³ má přibližně 28,19 % ampulek.

## Další rozdělení dostupná v R

Stejné názvy funkcí používá R i pro další rozdělení. Předpona `d*` označuje hustotu u spojitých veličin a pravděpodobnost jednotlivé hodnoty u diskrétních veličin. Předpona `p*` vrací pravděpodobnost do zadané hranice, `q*` hledá hranici pro zadanou pravděpodobnost. Pravděpodobnost nad hranicí se označuje jako horní chvost a volí se argumentem `lower.tail = FALSE`. Pořadí argumentů se mezi rozděleními liší; tabulka ukazuje konkrétní zápisy.

| Rozdělení | $P(X=k)$ / $f(x)$ | $P(X \le k)$ | horní chvost $P(X>k)$ |
|---|---|---|---|
| Binomické $Bi(n,p)$ | `dbinom(k, n, p)` | `pbinom(k, n, p)` | `pbinom(k, n, p, FALSE)` |
| Poissonovo $Po(\lambda)$ | `dpois(k, lambda)` | `ppois(k, lambda)` | `ppois(k, lambda, FALSE)` |
| Geometrické $G(p)$ | `dgeom(k, p)` | `pgeom(k, p)` | `pgeom(k, p, FALSE)` |
| Hypergeometrické $H(N,M,n)$ | `dhyper(k, M, N-M, n)` | `phyper(k, M, N-M, n)` | `phyper(k, M, N-M, n, FALSE)` |
| Exponenciální $E(\delta)$ | `dexp(k, 1/delta)` | `pexp(k, 1/delta)` | `pexp(k, 1/delta, FALSE)` |

> [!warning] Exponenciální rozdělení: R bere intenzitu, ne střední hodnotu
> R parametrizuje exponenciální rozdělení intenzitou (`rate`). Je-li $\delta$ střední doba do události, do R se dosazuje `1/delta`, ne `delta`.

Pro $X \sim Bi(5; 0{,}95)$ vypočteme pravděpodobnosti jednotlivých hodnot a distribuční funkci:

```r
x <- 0:5
dbinom(x, 5, 0.95)
pbinom(x, 5, 0.95)
```

```text
[1] 0.0000003125 0.0000296875 0.0011281250 0.0214343750 0.2036265625
[6] 0.7737809375
[1] 0.0000003125 0.0000300000 0.0011581250 0.0225925000 0.2262190625
[6] 1.0000000000
```

Pravděpodobnost, že událost s exponenciální dobou čekání a střední hodnotou $\delta = 5$ nastane do 3 jednotek času, spočítáme zvlášť:

```r
delta <- 5
pexp(3, rate = 1 / delta)
```

```text
[1] 0.4511884
```

## Studentovo, Pearsonovo a Fisherovo-Snedecorovo rozdělení

Při výpočtu intervalů spolehlivosti a [[testovani-hypotez|testování hypotéz]] pracujeme s charakteristikami vypočtenými z výběru. Jejich rozdělení umožňuje určit kritické hodnoty testu. Často jde právě o Studentovo, Pearsonovo nebo Fisherovo-Snedecorovo rozdělení. Nejde tedy o další druhy naměřených dat, ale o rozdělení výsledků výpočtu. Pomáhají poznat, zda je výsledek testu ještě obvyklý, nebo už příliš krajní.

**Stupně volnosti** souvisejí s množstvím nezávislé informace ve výběru. Například po výpočtu průměru z $n$ hodnot zbývá pro odhad rozptylu $n-1$ stupňů volnosti. Jejich počet mění tvar rozdělení, a tím i kritické hodnoty. Pro praktický výpočet použijeme funkce R v tabulce níže; vzorce hustot popisují přesný tvar křivek.

**Studentovo rozdělení** používáme například při t-testu průměru, když rozptyl populace neznáme a odhadujeme jej z výběru. S $k$ stupni volnosti má hustotu pravděpodobnosti

$$f(x) = \frac{1}{B\left(\frac12, \frac{k}{2}\right)\sqrt{k}} \left(1 + \frac{x^2}{k}\right)^{-\frac{k+1}{2}}, \qquad x \in \mathbb{R},$$

Ve vzorci je $B$ funkce beta. Rozdělení je souměrné kolem nuly. Počet stupňů volnosti $k$ určuje tvar křivky: s rostoucím $k$ se přibližuje normálnímu rozdělení.

**Pearsonovo (chí-kvadrát) rozdělení** využívá například test nezávislosti v kontingenční tabulce. Velká hodnota jeho kritéria znamená velký nesoulad mezi skutečnými a očekávanými počty. S $k$ stupni volnosti má hustotu:

$$f(x) = \frac{1}{2^{k/2}\Gamma(k/2)} x^{k/2-1} e^{-x/2}, \qquad x > 0,$$

kde $\Gamma$ je funkce gama.

**Fisherovo-Snedecorovo rozdělení** používáme při F-testu pro porovnání dvou rozptylů. Počítá se jejich poměr, proto má rozdělení dva počty stupňů volnosti: jeden pro výběr v čitateli a druhý pro výběr ve jmenovateli. Se stupni volnosti $k_1$ a $k_2$ má hustotu:

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

Také pro tato rozdělení lze v R spočítat hustotu, distribuční funkci a kvantily:

| Rozdělení | hustota | distribuční funkce | kvantil |
|---|---|---|---|
| Studentovo $t(k)$ | `dt(x, df = k)` | `pt(x, df = k)` | `qt(p, df = k)` |
| Pearsonovo $\chi^2(k)$ | `dchisq(x, df = k)` | `pchisq(x, df = k)` | `qchisq(p, df = k)` |
| Fisherovo-Snedecorovo $F(k_1, k_2)$ | `df(x, df1 = k1, df2 = k2)` | `pf(x, df1 = k1, df2 = k2)` | `qf(p, df1 = k1, df2 = k2)` |

Následující výpočet vrací 97,5%-ní kvantil Studentova rozdělení s 9 stupni volnosti a poté 95%-ní kvantily Pearsonova a Fisherova-Snedecorova rozdělení:

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

- **Záměna rozptylu a směrodatné odchylky v R.** V zápisu $N(\mu; \sigma^2)$ je druhým parametrem rozptyl. Funkce `dnorm`/`pnorm`/`qnorm` však očekávají směrodatnou odchylku $\sqrt{\sigma^2}$. Při $\sigma^2 \ne 1$ může záměna výrazně změnit výsledek, jak ukazuje příklad s ampulkou.
- **$P(X=x)$ u spojité veličiny je vždy 0.** Hodnota hustoty $f(x)$ je výška křivky, nikoli pravděpodobnost. Pravděpodobnosti odpovídá až plocha pod křivkou na intervalu.
- **Záměna stupňů volnosti u Fisherova-Snedecorova rozdělení.** $k_1$ patří čitateli a $k_2$ jmenovateli. Na pořadí záleží: `qf(p, df1, df2)` vrací jiný výsledek než `qf(p, df2, df1)`.

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
