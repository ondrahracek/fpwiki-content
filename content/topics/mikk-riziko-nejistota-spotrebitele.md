---
title: "Riziko, nejistota a pojištění"
course: mikk
type: topic
tags: [mikk, mikroekonomie, riziko, nejistota, pojisteni, vnm]
sources: [raw/mikk/mikro-FINAL-2-1.pdf, raw/mikk/Prednaska 1. a 2. blok.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Riziko, nejistota a pojištění

> [!tldr] TL;DR
> Spotřebitelé čelí často **rizikovým** rozhodnutím (známé pravděpodobnosti) i **nejistotě** (neznámé). Užitek z náhodné výplaty modelujeme přes **očekávaný užitek** (von Neumann-Morgenstern). **Risk-averse** spotřebitel je ochoten platit za pojištění (i nadprůměrně), **risk-neutral** je indiferentní mezi loterií a jistotou se stejnou střední hodnotou, **risk-loving** preferuje sázku. Klíčové pojmy: *fair premium*, *maximum premium*, *jistotní ekvivalent*, *riziková prémie*.

Tato strana spadá do kurzu [[mikk|Mikroekonomie 2 (mikK)]] a navazuje na [[mikk-utility-preference|teorii užitku a preferencí]]. Aplikace na strategickou nejistotu (rozhodování pod akcí protihráče) viz [[mikk-vezno-dilema-teorie-her|Vězňovo dilema a teorie her]]. Konkrétní zkouškové úlohy jsou shrnuty v [[mikk-vzorove-zkousky|přehledu vzorových zkoušek]] a vzorce v [[mikk-vzorce-prehled|kompletním přehledu vzorců]].

---

## 1. Riziko vs. nejistota — Knightova distinkce

Klasické rozlišení od Franka Knighta (1921, *Risk, Uncertainty, and Profit*) odděluje dvě kategorie neúplné informace o budoucnosti:

- **Riziko** — známe **množinu možných výsledků** i **pravděpodobnosti**, s nimiž nastanou. Příklady:
  - Hod kostkou: 6 výstupů, každý s pravděpodobností $1/6$.
  - Pojistná matematika: tabulky úmrtnosti, požárů, pojistných událostí.
  - Loterijní výhry s definovaným pravidlem výplaty.
- **Nejistota** — známe pouze možné výstupy (nebo ani ty), pravděpodobnosti jsou **neznámé**. Příklady:
  - Úspěch nového start-upu na trhu, který ještě neexistuje.
  - Geopolitické šoky, válka, regulační zásah.
  - Reakce konkurence v oligopolu, kde nemá historickou stopu.

> [!note] Kde se v kurzu pohybujeme
> V [[mikk|Mikroekonomii 2]] pracujeme primárně s **rizikem** — pravděpodobnosti považujeme za dané. Nejistotu řeší až teorie her (kde protihráč generuje strategickou nejistotu) a teorie firmy v dynamickém prostředí.

V praxi není hranice ostrá: subjekt si často **subjektivně přiřadí** pravděpodobnosti i k nejistým událostem (Bayesovský přístup). Pak se nejistota redukuje na riziko s vlastním pravděpodobnostním pohledem.

---

## 2. Loterie jako popis rizikové situace

**Loterie** je formální zápis rizikové alternativy. Zapisujeme ji jako množinu dvojic:

$$
L = \{(x_1, p_1), (x_2, p_2), \ldots, (x_n, p_n)\}
$$

kde:

- $x_i$ je **výplata** (výsledné bohatství, příjem, zisk) v $i$-tém scénáři,
- $p_i$ je **pravděpodobnost**, že tento scénář nastane,
- platí $\sum_{i=1}^n p_i = 1$ a $p_i \geq 0$.

Příklad loterie: vsadíme na hod mincí, hlava → 100 Kč, orel → 0 Kč.

$$
L = \{(100, 0{,}5), (0, 0{,}5)\}
$$

Loterie může být i **degenerovaná** — jeden výstup s pravděpodobností 1. Pak jde o jistotu, nikoli o riziko.

### 2.1 Očekávaná hodnota loterie

**Očekávaná hodnota** (střední hodnota výplaty) loterie:

$$
E(L) = \sum_{i=1}^n p_i \cdot x_i
$$

Pro mincový příklad: $E(L) = 0{,}5 \cdot 100 + 0{,}5 \cdot 0 = 50$ Kč.

> [!warning] Pozor na záměnu
> Očekávaná hodnota popisuje **průměrnou výplatu** v korunách (penězích, statcích). Sama o sobě **neříká nic** o tom, jestli loterii spotřebitel akceptuje. Tu informaci nese až **užitek z loterie** (následující sekce).

---

## 3. Očekávaný užitek — von Neumann-Morgenstern

Centrální nástroj kurzu pro modelování rozhodnutí pod rizikem je **očekávaný užitek (Expected Utility, EU)** podle von Neumanna a Morgensterna (1944):

$$
EU(L) = \sum_{i=1}^n p_i \cdot u(x_i)
$$

kde $u(\cdot)$ je užitková funkce definovaná nad **jistými výplatami** (nad bohatstvím, příjmem). Užitek z loterie je **vážený průměr užitků z jednotlivých výplat**, kde vahami jsou pravděpodobnosti.

> [!tip] Klíčová dichotomie
> **Pozor:** $EU(L) = E[u(L)] \neq u[E(L)]$.
>
> - $E[u(L)]$ — *spočítáme užitek z každé výplaty, pak zprůměrujeme.*
> - $u[E(L)]$ — *spočítáme průměrnou výplatu, pak její užitek.*
>
> Tyto dvě veličiny jsou **obecně různé** a jejich vzájemný vztah definuje typ přístupu spotřebitele k riziku.

### 3.1 Axiomy vNM

Aby preference nad loteriemi byly reprezentovatelné očekávaným užitkem, musí splňovat čtyři axiomy:

1. **Úplnost** — pro každé dvě loterie umí spotřebitel říct, kterou preferuje (nebo je indiferentní).
2. **Tranzitivita** — z $L_1 \succ L_2$ a $L_2 \succ L_3$ plyne $L_1 \succ L_3$.
3. **Spojitost** — pokud $L_1 \succ L_2 \succ L_3$, existuje pravděpodobnost $p$ taková, že smíchaná loterie $pL_1 + (1-p)L_3$ je indiferentní s $L_2$.
4. **Nezávislost** — pokud $L_1 \succ L_2$, pak pro libovolnou třetí $L_3$ a $p \in (0,1)$ platí $pL_1 + (1-p)L_3 \succ pL_2 + (1-p)L_3$.

Splnění těchto axiomů zaručuje existenci $u(\cdot)$ tak, že porovnání loterií se redukuje na porovnání jejich očekávaných užitků.

---

## 4. Tři typy přístupu k riziku

![[mikk-utility-postoj-k-riziku.jpeg|Tři postoje k riziku — averze (konkávní U), sklon (konvexní U) a neutralita (lineární U) s certainty equivalent CE]]

Tvar užitkové funkce $u(W)$ nad bohatstvím rozhoduje o postoji k riziku. Rozhodující je **konkavita / linearita / konvexita**.

```graph
title: "Tři postoje k riziku — averze, neutrál, sklon (užitek z bohatství)"
alt: "Tři typické tvary užitkové funkce z bohatství u(W). Konkávní √W (averze k riziku), lineární W (neutralita) a konvexní W² (sklon k riziku). Pozor — jde o užitek z bohatství, nikoli z fyzických statků."
xAxis: { label: "W (bohatství)", domain: [0, 100] }
yAxis: { label: "u(W) — užitek z bohatství", domain: [0, 12] }
params: []
curves:
  - { fn: "sqrt(x)", label: "Averzní: u = √W", color: "fp-purple" }
  - { fn: "x/10", label: "Neutrální: u = W/10", color: "paper-700" }
  - { fn: "(x*x)/1000", label: "Sklon: u = W²/1000", color: "fp-red" }
markers: []
```

### 4.1 Risk-averse (averze k riziku)

- Užitková funkce $u$ je **konkávní** ($u'' < 0$).
- Z **Jensenovy nerovnosti** plyne $u[E(L)] > E[u(L)]$.
- Slovně: užitek jistého průměrného výsledku převyšuje očekávaný užitek loterie se stejnou střední hodnotou.
- Spotřebitel **preferuje jistotu** před stejně bohatou loterií.
- Typické funkce: $u(W) = \sqrt{W}$, $u(W) = \ln W$, $u(W) = 1 - e^{-aW}$.

### 4.2 Risk-neutral (neutralita k riziku)

- $u$ je **lineární** ($u'' = 0$).
- $u[E(L)] = E[u(L)]$.
- Spotřebitel je **indiferentní** mezi loterií a jistotou se stejnou střední hodnotou.
- Typická funkce: $u(W) = aW + b$ (běžně se klade $u(W) = W$).
- Reálné aplikace: velké firmy s diverzifikovaným portfoliem, kde jednotlivé riziko je marginální.

### 4.3 Risk-loving (vyhledávání rizika)

- $u$ je **konvexní** ($u'' > 0$).
- $u[E(L)] < E[u(L)]$.
- Spotřebitel **preferuje loterii** před jistotou se stejnou střední hodnotou.
- Typické funkce: $u(W) = W^2$, $u(W) = e^{aW}$.
- Reálné aplikace: kasinoví hráči, sázkaři, část mladých investorů.

> [!note] Reálná situace je hybridní
> Empiricky (Kahneman & Tversky, *prospect theory*) jsou lidé v doméně **zisků** spíše risk-averse, v doméně **ztrát** často risk-loving (snaží se "dohnat" prohru sázkou). Čistá vNM teorie tuto asymetrii nezachycuje, slouží jako idealizovaný benchmark.

---

## 5. Geometrie averze k riziku

Pro názornost uvažujme dvouvýstupovou loterii $L = \{(W_1, p), (W_2, 1-p)\}$ s konkávní $u$:

1. Na grafu vyneseme $u(W)$ — konkávní křivka (např. $\sqrt{W}$).
2. Body $A = (W_1, u(W_1))$ a $B = (W_2, u(W_2))$ leží na křivce.
3. **Sečna AB** spojuje tyto body. Pro konkávní funkci leží sečna **pod** křivkou.
4. Bod sečny v horizontále $x = E(W) = pW_1 + (1-p)W_2$ má vertikální souřadnici **právě** $E[u(L)]$.
5. Bod **na křivce** ve stejné horizontále má hodnotu $u[E(W)]$.
6. Z konkavity: $u[E(W)] > E[u(L)]$ — užitek jistoty převyšuje očekávaný užitek loterie.

> [!example] Vizualizace
> Představte si tětivu napjatou mezi dvěma body na konkávním kopci. Tětiva (= možnosti loterie) sedí pod hřebenem (= jisté výplaty). Spotřebitel preferuje stát na hřebeni.

```graph
title: "Konkávní užitek z bohatství u(W) = √W a Jensenova nerovnost"
alt: "Konkávní užitková funkce z bohatství u = √W. Tětiva mezi body W-Ll a Ww leží pod křivkou. Markery ukazují E(W) = Ww - Pp·Ll, jistotní ekvivalent CE a body W-Ll, Ww. Vertikální vzdálenost mezi křivkou a tětivou v bodě E(W) je riziková prémie. Pozor — užitek je z bohatství, ne ze statků."
xAxis: { label: "W (bohatství)", domain: [0, 250] }
yAxis: { label: "u(W) = √W", domain: [0, 16] }
params:
  - { name: Ww, label: "Bohatství W", min: 80, max: 200, default: 100, step: 5 }
  - { name: Ll, label: "Ztráta L", min: 10, max: 75, default: 75, step: 5 }
  - { name: Pp, label: "Pravděpodobnost ztráty", min: 0.05, max: 0.5, default: 0.1, step: 0.05 }
curves:
  - { fn: "sqrt(x)", label: "u(W) = √W", color: "fp-purple" }
  - { fn: "sqrt(Ww - Ll) + (sqrt(Ww) - sqrt(Ww - Ll)) * (x - (Ww - Ll)) / Ll", label: "Tětiva mezi (W-L) a W", color: "fp-red" }
markers:
  - { x: "Ww - Ll", label: "W - L" }
  - { x: "Ww - Pp*Ll", label: "E(W)" }
  - { x: "pow((1-Pp)*sqrt(Ww) + Pp*sqrt(Ww - Ll), 2)", label: "CE" }
  - { x: "Ww", label: "W" }
```

Pro **konvexní** $u$ je situace zrcadlová: sečna leží **nad** křivkou, $E[u(L)] > u[E(W)]$.
Pro **lineární** $u$ sečna **splývá** s grafem: $E[u(L)] = u[E(W)]$.

---

## 6. Jistotní ekvivalent (Certainty Equivalent, CE)

**Jistotní ekvivalent** je jistá částka, která spotřebiteli přináší **stejný užitek** jako účast v rizikové loterii:

$$
u(CE) = E[u(L)]
$$

Z této rovnice se $CE$ řeší jako $CE = u^{-1}(E[u(L)])$.

| typ spotřebitele | vztah CE a E(L) | interpretace                                |
|------------------|-----------------|---------------------------------------------|
| risk-averse      | $CE < E(L)$     | Akceptuje jistou částku **menší** než průměr loterie. |
| risk-neutral     | $CE = E(L)$     | Akceptuje jistou částku rovnou průměru.    |
| risk-loving      | $CE > E(L)$     | Vyžaduje jistou částku **vyšší** než průměr (jinak preferuje sázku). |

### 6.1 Riziková prémie

**Riziková prémie** $RP$ vyjadřuje, **kolik je spotřebitel ochoten obětovat** z očekávané výplaty, aby se zbavil rizika:

$$
RP = E(L) - CE
$$

- Pro risk-averse: $RP > 0$ — připravený platit za odstranění rizika.
- Pro risk-neutral: $RP = 0$.
- Pro risk-loving: $RP < 0$ — sám by si **připlatil**, aby riskoval.

> [!tip] Ekonomický smysl rizikové prémie
> $RP$ je horní hranice toho, kolik spotřebitel zaplatí pojišťovně **navíc** k očekávané ztrátě, než ekonomicky přestane mít smysl pojistit se. Při fair premium ($\pi_F = E(\text{ztráta})$) má spotřebitel kladný "spotřebitelský přebytek" rovný $RP$.

---

## 7. Pojištění — fair vs. unfair premium

Aplikujeme aparát na pojistnou situaci. Spotřebitel má bohatství $W$ a hrozí mu ztráta $L$ s pravděpodobností $p$ (např. úraz, požár, krádež).

### 7.1 Bez pojištění

Loterie:

$$
\{(W, 1-p), (W - L, p)\}
$$

Očekávané bohatství:

$$
E(W) = (1-p) \cdot W + p \cdot (W - L) = W - pL
$$

Očekávaný užitek:

$$
EU = (1-p) \cdot u(W) + p \cdot u(W - L)
$$

### 7.2 Spravedlivá pojistka (fair premium)

> [!quote] Definice ze zkouškové (Předtermín, varianta C)
> *"Spravedlivá pojistka — je náklad na takové pojištění, kdy očekávaná hodnota bohatství člověka s riziky nekrytými je stejná, jako by byla v případě stejných rizik pojištěním krytých. V takovém případě je výše pojistného shodná s očekávanou ztrátou, resp. jistý příjem je roven očekávanému příjmu."*

Fair premium $\pi_F$ pokrývá právě **očekávanou ztrátu**:

$$
\pi_F = p \cdot L
$$

Pojišťovna na takové pojistce v průměru nic nevydělá ani neztratí (pomineme administrativu). Při plném pojištění má spotřebitel po zaplacení pojistného jistý příjem $W - \pi_F = W - pL$, což se přesně rovná $E(W)$ z nepojištěné loterie.

### 7.3 Maximální pojistka (maximum premium)

> [!quote] Definice ze zkouškové (Předtermín, varianta C)
> *"Maximální pojistka — je taková výše pojistky, která vede k tomu, že užitek spojený s jistotou (dosaženou pojištěním) je shodný s očekávaným užitkem spojeným s riskantní alternativou (bez pojištění)."*

Maximum premium $\pi_{\max}$ vyrovnává **užitky** (nikoli peněžní hodnoty):

$$
u(W - \pi_{\max}) = (1-p) \cdot u(W) + p \cdot u(W - L)
$$

Po vyřešení:

$$
\pi_{\max} = W - u^{-1}\bigl[(1-p) \cdot u(W) + p \cdot u(W - L)\bigr]
$$

### 7.4 Vztah $\pi_F$ a $\pi_{\max}$

| typ spotřebitele | vztah                | důsledek                                         |
|------------------|----------------------|--------------------------------------------------|
| risk-averse      | $\pi_F < \pi_{\max}$ | **Vždy přijme fair premium** (a unfair až do $\pi_{\max}$). |
| risk-neutral     | $\pi_F = \pi_{\max}$ | Indiferentní vůči fair premium, neplatí nadprůměr. |
| risk-loving      | $\pi_F > \pi_{\max}$ | Fair premium je pro něj **drahé**, nepojistí se ani férově. |

```graph
title: "Fair vs maximum pojistné jako funkce pravděpodobnosti"
alt: "Spravedlivé pojistné π_F = p·L (přímka) a maximální pojistné π_max = W - [(1-p)·√W + p·√(W-L)]² (konvexní křivka) jako funkce pravděpodobnosti ztráty p. Vzdálenost mezi křivkami v daném bodě je riziková prémie risk-averzního spotřebitele s u(W)=√W. Pozor — užitek je z bohatství."
xAxis: { label: "p — pravděpodobnost ztráty", domain: [0, 1] }
yAxis: { label: "Pojistné", domain: [0, 80] }
params:
  - { name: Ww, label: "Bohatství W", min: 80, max: 200, default: 100, step: 5 }
  - { name: Ll, label: "Ztráta L", min: 10, max: 75, default: 75, step: 5 }
curves:
  - { fn: "x*Ll", label: "Fair π_F = p·L", color: "fp-purple" }
  - { fn: "Ww - pow((1-x)*sqrt(Ww) + x*sqrt(Ww - Ll), 2)", label: "Max π_max", color: "fp-red" }
markers:
  - { x: "0.1", label: "p=0.1 (z příkladu)" }
```

> [!note] Proč pojišťovny existují
> Fakticky pojišťovny účtují **víc** než fair premium (musí pokrýt režii, kapitálovou rezervu, zisk). Existují, protože většina populace je risk-averse a má $\pi_{\max} > \pi_F + \text{režie}$. Riziková prémie je důvod, proč je pojištění životaschopným byznysem.

---

## 8. Numerický příklad — kompletně dořešený

Zadání ve stylu zkouškové úlohy:

> Spotřebitel má užitkovou funkci $u(W) = \sqrt{W}$, počáteční bohatství $W = 100$. Hrozí mu ztráta $L = 75$ s pravděpodobností $p = 0{,}1$. Spočítejte:
>
> 1. Očekávané bohatství.
> 2. Očekávaný užitek.
> 3. Jistotní ekvivalent.
> 4. Rizikovou prémii.
> 5. Maximální pojistku.
> 6. Spravedlivou pojistku a posuďte, zda se spotřebitel pojistí.

### Krok 1 — Očekávané bohatství

$$
E(W) = 0{,}9 \cdot 100 + 0{,}1 \cdot (100 - 75) = 0{,}9 \cdot 100 + 0{,}1 \cdot 25 = 90 + 2{,}5 = 92{,}5
$$

### Krok 2 — Očekávaný užitek

$$
EU = 0{,}9 \cdot \sqrt{100} + 0{,}1 \cdot \sqrt{25} = 0{,}9 \cdot 10 + 0{,}1 \cdot 5 = 9 + 0{,}5 = 9{,}5
$$

### Krok 3 — Jistotní ekvivalent

$$
\sqrt{CE} = 9{,}5 \quad\Rightarrow\quad CE = 9{,}5^2 = 90{,}25
$$

### Krok 4 — Riziková prémie

$$
RP = E(W) - CE = 92{,}5 - 90{,}25 = 2{,}25
$$

Spotřebitel je ochoten obětovat až **2,25** Kč z očekávané výplaty výměnou za jistotu.

### Krok 5 — Maximální pojistka

Hledáme $\pi_{\max}$ tak, aby $u(W - \pi_{\max}) = EU = 9{,}5$:

$$
\sqrt{100 - \pi_{\max}} = 9{,}5 \quad\Rightarrow\quad 100 - \pi_{\max} = 90{,}25 \quad\Rightarrow\quad \pi_{\max} = 9{,}75
$$

### Krok 6 — Spravedlivá pojistka a rozhodnutí

$$
\pi_F = p \cdot L = 0{,}1 \cdot 75 = 7{,}5
$$

Srovnání: $\pi_F = 7{,}5 < \pi_{\max} = 9{,}75$.

> [!tip] Závěr příkladu
> Spravedlivá pojistka stojí 7,5, ale spotřebitel by za pojistku zaplatil až 9,75. **Pojistí se.** Jeho spotřebitelský přebytek z fair pojištění je $9{,}75 - 7{,}5 = 2{,}25$ — což je přesně **riziková prémie**.

### Kontrolní výpočet

Po pojištění (zaplaceno $\pi_F = 7{,}5$) má spotřebitel jisté bohatství $100 - 7{,}5 = 92{,}5$ a užitek $\sqrt{92{,}5} \approx 9{,}617$. Bez pojištění byl jeho očekávaný užitek $9{,}5$. Pojištěním vzrostl o $\approx 0{,}117$ jednotky užitku — proto se pojistí.

---

## 9. Co určuje míru averze k riziku

Averze k riziku není binární — měří se **velikostí** zakřivení užitkové funkce. Standardní míry:

### 9.1 Arrow-Pratt absolutní averze

$$
r_A(W) = -\frac{u''(W)}{u'(W)}
$$

- Vysoké $r_A$ → silná averze.
- $r_A = 0$ → risk-neutral.
- $r_A < 0$ → risk-loving.

### 9.2 Arrow-Pratt relativní averze

$$
r_R(W) = -\frac{W \cdot u''(W)}{u'(W)} = W \cdot r_A(W)
$$

Užitečná, protože je **bezrozměrná** a reaguje na změny škály bohatství.

### 9.3 Příklady pro běžné funkce

| užitková funkce      | $r_A$         | $r_R$    | typ                                        |
|----------------------|---------------|----------|--------------------------------------------|
| $u(W) = W$           | $0$           | $0$      | risk-neutral                               |
| $u(W) = \ln W$       | $1/W$         | $1$      | konstantní relativní averze (CRRA, $\gamma = 1$) |
| $u(W) = \sqrt{W}$    | $1/(2W)$      | $1/2$    | CRRA s $\gamma = 1/2$                      |
| $u(W) = -e^{-aW}$    | $a$           | $aW$     | konstantní absolutní averze (CARA)         |
| $u(W) = W^2$         | $-1/W$        | $-1$     | risk-loving                                |

```graph
title: "CARA — užitek z bohatství u(W) = 1 - exp(-aa·W)"
alt: "Exponenciální CARA užitek z bohatství. Posuvník aa odpovídá Arrow-Prattovu koeficientu absolutní averze — vyšší aa znamená silnější averzi (silněji konkávní křivka), aa blízké nule odpovídá risk-neutralitě. Užitek je z bohatství, nikoli ze spotřeby statků."
xAxis: { label: "W (bohatství)", domain: [0, 200] }
yAxis: { label: "u(W)", domain: [0, 1] }
params:
  - { name: aa, label: "Koeficient absolutní averze aa", min: 0.005, max: 0.05, default: 0.02, step: 0.001 }
curves:
  - { fn: "1 - exp(-aa*x)", label: "u(W) = 1 - exp(-aa·W)", color: "fp-purple" }
markers: []
```

### 9.4 Empirické zjištění

- Lidé jsou **silněji risk-averse u velkých částek** vůči svému bohatství (ztráta auta zatřese rozpočtem).
- U **drobných** sázek (kávomat, výherní automat za 20 Kč) jsou prakticky **risk-neutral** nebo dokonce risk-loving.
- $r_R$ se v populaci pohybuje kolem hodnot $1$–$3$ (typicky $\gamma = 2$ pro modelování v makru, viz [[is-lm|IS-LM model]]).

---

## 10. Vazba na kapitálové a intertemporální rozhodování

Jeden z předtermínových úloh (Předtermín I, *Capital vs. labour decision*) propojuje riziko s **intertemporální volbou** — rozhodnutím mezi spotřebou dnes a spotřebou zítra.

- Dnešní spotřeba $C_0$ je jistá.
- Budoucí spotřeba $C_1$ je riziková (úroková sazba kolísá, inflace, příjem se může snížit).
- Spotřebitel řeší $\max u(C_0) + \beta \cdot E[u(C_1)]$, kde $\beta$ je diskontní faktor.

Risk-averse spotřebitel:

- Drží **rezervní úspory** (precautionary saving) — zvyšuje $C_1$ na úkor $C_0$.
- Vyžaduje **rizikovou prémii v úroku** — odměnu za držbu rizikových aktiv.
- Je ochoten platit za **anuitu** (jistý budoucí příjem) — pojistka proti dlouhověkosti.

Stejný aparát (vNM užitek, jistotní ekvivalent) se zde používá s tím, že $W$ je nahrazeno $C_t$.

---

## 11. Aplikace v reálné ekonomii

### 11.1 Pojistný trh

- **Životní, úrazové, majetkové pojištění** — fair premium je tabulkovým výpočtem (úmrtnostní tabulky, statistika škod). Komerční pojistka je o **margin** vyšší.
- **Adverzní výběr** — pojistku si kupují přednostně lidé s vysokým rizikem, což pojišťovnu nutí premium dále zvyšovat.
- **Morální hazard** — pojištěný nemá motivaci riziku zabraňovat ("auto je pojištěné, neuzamknu ho").

### 11.2 Diverzifikace portfolia

- Riziko portfolia $\sigma_P^2 = \sum w_i^2 \sigma_i^2 + 2 \sum_{i<j} w_i w_j \sigma_{ij}$.
- Při korelaci $< 1$ klesá $\sigma_P$ pod prostý vážený průměr — **diverzifikace eliminuje idiosynkratické riziko**.
- Risk-averse investor drží diverzifikované portfolio i za cenu nižšího očekávaného výnosu.

### 11.3 Loterie a kasina

- Komerční loterie mají $E(L) <$ cena losu (pojišťovna obráceně) — fair premium pro hráče by znamenala los zdarma.
- Existují, protože malá kohorta je **risk-loving** v doméně malých sázek a/nebo nadhodnocuje malé pravděpodobnosti (overweighting tail probabilities, Kahneman-Tversky).

### 11.4 Rozhodování "co je v krabičce"

Klasické zadání (Monty Hall, Allaisův paradox) — spotřebitel se rozhoduje mezi **jistou výplatou** a **rizikovou loterií**. Reálné rozhodnutí často porušuje vNM axiomy (zejména nezávislost), což motivovalo vznik *prospect theory*.

---

## 12. Návaznost na teorii her

Ve hře dvou hráčů není nejistota statistická, ale **strategická** — výsledek závisí na akci protihráče, jehož motivace neznám.

- *Smíšená strategie* hráče B se chová formálně jako loterie pro hráče A.
- *Očekávaná výplata* z mixu $\sigma_B$ je analogie $E[u]$.
- *Maximin / minimax* je strategie risk-averse hráče (zaručuje nejhorší případ).

Detailně viz [[mikk-vezno-dilema-teorie-her|Vězňovo dilema a teorie her]].

---

## 13. Shrnutí pro zkoušku

> [!example] Předtermín, varianta C — typická úloha
> *"Definujte riziko, spravedlivou pojistku, maximální pojistku. Proč se lidé chtějí pojistit proti nejistým situacím, jestliže je pojistka spravedlivá? Zakreslete průběhy do grafu."*
>
> **Šablona odpovědi:**
>
> 1. Definovat *riziko* (známé pravděpodobnosti, viz sekce 1) jako "bad" — statek s negativní preferencí pro risk-averse subjekt.
> 2. Definovat *fair premium* $\pi_F = pL$ — pojistné rovné očekávané ztrátě.
> 3. Definovat *maximum premium* $\pi_{\max}$ z rovnice $u(W - \pi_{\max}) = EU$.
> 4. Vysvětlit, že pro risk-averse platí $EU \leq u(EW)$ (Jensen), tedy jistý příjem $W - \pi_F$ má **vyšší užitek** než nepojištěná loterie se stejnou střední hodnotou.
> 5. Zakreslit konkávní $u(W)$, dvě bohatství $W_1 = W - L$ a $W_2 = W$, sečnu mezi nimi, body $E(W)$, $CE$, $u(EW)$, $EU$.

> [!example] Předtermín I — kapitál vs. práce
> *Spotřebitel volí mezi "jistým" pracovním příjmem a "rizikovým" kapitálovým výnosem.* Postup: rozepsat obě alternativy jako loterie (práce má často degenerovanou loterii), spočítat $EU$ obou, porovnat s jistotním ekvivalentem. Risk-averse subjekt typicky volí práci, pokud nedostane prémii za riziko v podobě vyššího očekávaného výnosu kapitálu.

### Vzorce na rychlou referenci

| veličina               | vzorec                                              |
|------------------------|-----------------------------------------------------|
| Očekávaná hodnota      | $E(L) = \sum p_i x_i$                               |
| Očekávaný užitek       | $EU(L) = \sum p_i u(x_i)$                           |
| Jistotní ekvivalent    | $u(CE) = EU(L)$                                     |
| Riziková prémie        | $RP = E(L) - CE$                                    |
| Fair premium           | $\pi_F = pL$                                        |
| Max premium            | $u(W - \pi_{\max}) = EU$                            |
| Arrow-Pratt absolutní  | $r_A = -u''/u'$                                     |
| Arrow-Pratt relativní  | $r_R = -W u''/u'$                                   |

> [!tip] Trik na zkoušku
> Pokud zadání obsahuje $u(W) = \sqrt{W}$, počítejte v krocích: nejdřív odmocniny výplat, pak vážený průměr (= $EU$), pak druhá mocnina ($CE$). Rizikovou prémii a maximum premium dopočítáte z $E(W)$ a $u^{-1}(EU)$.

---

## 14. Reference a další zdroje

- Předtermínová zadání: varianta C otázka 2 (riziko, spravedlivá pojistka, maximální pojistka) a varianta I (kapitál vs. práce). Viz [[mikk-vzorove-zkousky]].
- Související wiki:
  - [[mikk|Mikroekonomie 2 (mikK)]] — kurz hub.
  - [[mikk-utility-preference|Užitek a preference]] — výchozí teorie užitku.
  - [[mikk-vezno-dilema-teorie-her|Vězňovo dilema a teorie her]] — strategická nejistota.
  - [[mikk-vzorove-zkousky|Vzorové zkoušky]] — všechny řešené předtermíny.
  - [[mikk-vzorce-prehled|Přehled vzorců]] — kompletní referenční list.
  - [[uzitecnost|Užitečnost (obecná teorie)]] — základní pojem ze sdíleného slovníku.
  - [[definice-rizika|Definice rizika]] — pojetí v kurzu IRMaNK (manažerské řízení rizik).
