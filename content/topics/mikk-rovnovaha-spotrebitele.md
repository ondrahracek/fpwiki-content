---
title: "Optimalizace spotřebitele — tři metody"
course: mikk
type: topic
tags: [mikk, mikroekonomie, optimalizace, lagrange, mrs, rozpoctove-omezeni]
sources: [raw/mikk/Prednaska 1. a 2. blok.pdf, raw/mikk/mik2K reseni prikladu 1 blok.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Optimalizace spotřebitele — tři metody

> [!abstract] TL;DR
> **Optimum spotřebitele** je takový spotřební koš $(X^*, Y^*)$, kde se sklon nejvyšší dosažitelné indiferenční křivky (tj. $-MRS_C$) přesně rovná sklonu rozpočtové přímky ($-P_X/P_Y$), a který současně leží **na** rozpočtové přímce (utratí celý důchod). Algebraicky:
> $$MRS_C = \dfrac{MU_X}{MU_Y} = \dfrac{P_X}{P_Y}, \qquad P_X X + P_Y Y = I.$$
> Soustavu lze řešit **třemi způsoby**: (I) substitucí přes podmínku $MRS = P_X/P_Y$, (II) dosazením rozpočtové podmínky do funkce užitku a hledáním volného maxima, (III) **Lagrangeovou metodou** s multiplikátorem $\lambda$ (jehož hodnota navíc poskytne ekonomickou interpretaci jako *stínovou cenu důchodu*). Pokud spotřebitel dosáhne **bodu nasycení** ($MU_X = MU_Y = 0$), další jednotky důchodu už užitek nezvyšují.

Tato stránka navazuje na [[mikk|Mikroekonomie 2 (MikK)]], využívá pojmy z [[mikk-utility-preference|funkce užitku, MU a indiferenční křivky]] a poskytuje vstup do navazujících témat [[mikk-marshall-hicks-poptavka|Marshallovy a Hicksovy poptávky]] a [[mikk-substitucni-duchodovy-efekt|substitučního a důchodového efektu]]. Matematickou stránku Lagrangeovy metody obecně rozebírá [[lagrangeova-metoda|Lagrangeova metoda (ImeK)]]; pro úvod do problému viz [[optimalizace-spotrebitele|Optimalizace spotřebitele (ImeK primer)]].

---

## 1. Rozpočtové omezení

Spotřebitel disponuje peněžním důchodem $I$ (anglicky *income*). Jednotková cena zboží $X$ je $P_X$, jednotková cena zboží $Y$ je $P_Y$. **Linie příjmu** (rozpočtová přímka, *budget line*) je množina kombinací $(X, Y)$, které spotřebitel může pořídit, pokud utratí přesně celý důchod:

$$P_X \cdot X + P_Y \cdot Y = I.$$

### 1.1 Geometrie rozpočtové přímky

Rozpočtová přímka je úsečka v prvním kvadrantu mezi dvěma průsečíky s osami:

- **Průsečík s osou $X$:** položíme $Y = 0$, dostáváme $X = I/P_X$. To je maximální množství $X$, kdyby spotřebitel utratil všechen důchod jen za zboží $X$.
- **Průsečík s osou $Y$:** položíme $X = 0$, dostáváme $Y = I/P_Y$. Analogicky to je krajní bod nákupu pouze zboží $Y$.

Sklon přímky získáme vyjádřením $Y$ jako funkce $X$:

$$Y = \dfrac{I}{P_Y} - \dfrac{P_X}{P_Y}\, X.$$

Sklon (směrnice) je tedy

$$\dfrac{dY}{dX} = -\dfrac{P_X}{P_Y}.$$

Záporné znaménko vyjadřuje, že nákup další jednotky $X$ vyžaduje vzdát se určitého počtu jednotek $Y$ — **ekonomicky jde o relativní cenu** (kolik $Y$ je nutné obětovat za jednu $X$).

### 1.2 Soubor tržních příležitostí

**Soubor tržních příležitostí** (*market opportunity set*) je trojúhelník vymezený rozpočtovou přímkou a souřadnicovými osami:

$$\{ (X, Y) \in \mathbb{R}^2_{\ge 0} : P_X X + P_Y Y \le I \}.$$

Body uvnitř trojúhelníka (ostrá nerovnost) představují koše, které jsou *dostupné, ale nevyčerpávají důchod*. V optimu při monotónních preferencích spotřebitel vždy zvolí bod **na** přímce — neutracený důchod by znamenal nevyužitou příležitost zvýšit užitek.

### 1.3 Posuny rozpočtové přímky

Rozpočtová přímka se posouvá v reakci na změnu jejích tří parametrů:

| Změna             | Geometrický efekt                                                                 |
|-------------------|-----------------------------------------------------------------------------------|
| ↑ $I$ (důchod)    | **Paralelní posun** přímky doprava nahoru (sklon zůstává $-P_X/P_Y$).             |
| ↓ $I$             | Paralelní posun doleva dolů.                                                     |
| ↑ $P_X$           | **Rotace kolem bodu** $(0,\, I/P_Y)$ na ose $Y$ směrem dovnitř (přímka se zploští, $|sklon|$ roste). |
| ↓ $P_X$           | Rotace kolem $(0,\, I/P_Y)$ směrem ven.                                          |
| ↑ $P_Y$           | Rotace kolem bodu $(I/P_X, 0)$ na ose $X$ dovnitř.                               |
| ↓ $P_Y$           | Rotace kolem $(I/P_X, 0)$ ven (přímka se napřímí, $|sklon|$ klesá).              |

```graph
title: Rozpočtová přímka — posuny při změně Mm a Pp
alt: Rozpočtová přímka v rovině X-Y. Posuvník důchodu Mm paralelně posouvá přímku, posuvník ceny Pp ji rotuje kolem průsečíku s osou Y.
xAxis: { label: "X (videokazety)", domain: [0, 30] }
yAxis: { label: "Y (koncerty)", domain: [0, 16] }
params:
  - { name: Mm, label: "Důchod I (Kč)", min: 2000, max: 9000, default: 4400, step: 100 }
  - { name: Pp, label: "Cena Px (Kč)", min: 100, max: 500, default: 200, step: 10 }
curves:
  - { fn: "Mm/600 - (Pp/600)*x", label: "Rozpočtová přímka", color: "fp-purple" }
markers:
  - { x: "Mm/Pp", label: "I/Px" }
  - { x: "0", label: "I/Py" }
```

> [!tip] Mnemotechnická pomůcka
> Při změně ceny zboží **se nemění** ten průsečík, který se daného zboží **netýká** (protože v něm je nakupované množství onoho zboží nulové). Přímka kolem něj rotuje.

### 1.4 Nelineární rozpočtové omezení

Pokud trh nabízí **množstevní slevy** nebo **kupony**, rozpočtová přímka přestane být přímkou a stane se *zlomenou křivkou*. Existují dva typické případy:

- **Kupon na 2 lístky za cenu 1:** první lístek za $P$, druhý zdarma — efektivní cena druhé jednotky je 0, takže přímka je v intervalu $X \in [1, 2]$ vodorovná a poté pokračuje s normálním sklonem.
- **Množstevní rabat** od určitého počtu kusů: po překročení prahu se sklon změní (přímka se zlomí směrem ven).

Tyto situace mohou vést ke **dvěma vnitřním optimům** současně nebo k volbě v bodě zlomu.

---

## 2. Vnitřní vs. rohové řešení

Optimální koš se může nacházet ve **vnitřku** trojúhelníka tržních příležitostí (na rozpočtové přímce, ale ne v krajním bodě), nebo v jednom z **rohů** přímky (spotřeba pouze jednoho zboží).

### 2.1 Vnitřní řešení

Je-li $X^* > 0$ a $Y^* > 0$, soustavu pro optimum tvoří dvě rovnice:

$$\boxed{\;MRS_C = \dfrac{MU_X}{MU_Y} = \dfrac{P_X}{P_Y}\quad \text{a} \quad P_X X + P_Y Y = I.\;}$$

První rovnice je **podmínka tečnosti** (sklon indiferenční křivky se rovná sklonu rozpočtové přímky); druhá je rozpočtové omezení.

### 2.2 Rohové řešení

Pokud nejsou splněny obě podmínky současně, optimum leží v rohu. Algebraická definice dvou možných situací:

**Spotřeba pouze $X$** (roh na ose $X$, $Y^* = 0$): ekonomicky to znamená, že pro daného spotřebitele je **každá** jednotka $X$ atraktivnější než výměna za $Y$, i v krajním bodě. Formálně:

$$Y^* = 0, \qquad X^* = \dfrac{I}{P_X}, \qquad MRS_C \ge \dfrac{P_X}{P_Y}.$$

**Spotřeba pouze $Y$** (roh na ose $Y$, $X^* = 0$):

$$X^* = 0, \qquad Y^* = \dfrac{I}{P_Y}, \qquad MRS_C \le \dfrac{P_X}{P_Y}.$$

> [!warning] Kdy očekávat rohové řešení
> Rohové řešení vzniká nejčastěji u **dokonalých substitutů** (lineární $U$, např. $U = aX + bY$), kdy podíl mezních užitků je konstantní a nesplňuje rovnost s poměrem cen. Vnitřní řešení vyžaduje **konvexní** indiferenční křivky (klesající $MRS_C$).

### 2.3 Intuice rohových řešení

Rohové řešení můžeme číst dvojím způsobem:

- **Geometricky:** rozpočtová přímka a indiferenční křivka se v žádném vnitřním bodě nesetkají s tečným kontaktem — nejvyšší dosažitelná indiferenční křivka protíná rozpočtovou přímku právě v jednom z jejích krajních bodů.
- **Ekonomicky:** spotřebitel by chtěl pokračovat v substituci ve prospěch jednoho zboží i za cenu nákupu nulového množství druhého. Mezní užitek z poslední koruny je pro favorizované zboží vyšší než pro to druhé i v krajním bodě.

V takovém případě **klasickou Lagrangeovu metodu nelze použít přímo** — je potřeba řešit Karush-Kuhn-Tuckerovy podmínky (KKT), které explicitně zacházejí s nezápornostními omezeními $X \ge 0$, $Y \ge 0$. V kurzu MikK se však s rohovým řešením setkáváme jen kvalitativně; všechny počítané příklady vedou na vnitřní řešení.

---

## 3. Tři metody řešení optimalizační úlohy

Pro vnitřní optimum existují tři ekvivalentní postupy. Liší se technikou, ale dávají identické řešení; volba metody závisí na tvaru funkce užitku, počtu proměnných a tom, zda potřebujeme i hodnotu $\lambda$ (stínovou cenu).

| Metoda | Jádro postupu | Výhoda | Nevýhoda |
|--------|---------------|--------|----------|
| I — substituce přes MRS | z rovnice $MRS = P_X/P_Y$ vyjádřit $Y(X)$ a dosadit do rozpočtu | nejrychlejší u 2 proměnných | nedává $\lambda$ |
| II — substituce z rozpočtu do $U$ | z rozpočtu vyjádřit $X(Y)$ a dosadit do $U$, pak hledat volné maximum | mechanicky bezpečná, ověří 2. derivací | u nelineárního rozpočtu se rozsype |
| III — Lagrange | postavit funkci $\mathcal{L}$, řešit soustavu tří rovnic | škáluje na více proměnných i podmínek, dává $\lambda$ | algebraicky náročnější |

V této stránce ukážeme **všechny tři metody na témže příkladu** (Petr-kultura), aby byly výsledky přímo srovnatelné.

---

## 4. Společné zadání: příklad Petr-kultura

Spotřebitel Petr utrácí ročně $I = 4\,400\,\text{Kč}$ za kulturu. Nakupuje:

- $X$ — videokazety s akčními filmy, jednotková cena $P_X = 200\,\text{Kč}$,
- $Y$ — vstupenky na koncerty Pražského jara, $P_Y = 600\,\text{Kč}$.

Funkce užitku:

$$U(X, Y) = 10X + 24Y - 0{,}5 X^2 - 0{,}5 Y^2.$$

**Mezní užitky** (parciální derivace):

$$MU_X = \dfrac{\partial U}{\partial X} = 10 - X, \qquad MU_Y = \dfrac{\partial U}{\partial Y} = 24 - Y.$$

**Mezní míra substituce ve spotřebě:**

$$MRS_C = \dfrac{MU_X}{MU_Y} = \dfrac{10 - X}{24 - Y}.$$

**Rozpočtová přímka:**

$$200 X + 600 Y = 4\,400, \quad \text{ekvivalentně} \quad X + 3 Y = 22.$$

Krajní body přímky: $(22, 0)$ a $(0, 22/3) \approx (0, 7{,}33)$.

---

## 5. Metoda I — substituce přes MRS

> [!info] Kdy použít
> Standardní volba pro lineární rozpočet a hladkou (diferencovatelnou) funkci užitku se dvěma proměnnými. Když vám stačí znát $X^*$ a $Y^*$ a nepotřebujete stínovou cenu.

**Krok 1: dosadit poměr cen do podmínky tečnosti.**

$$\dfrac{10 - X}{24 - Y} = \dfrac{P_X}{P_Y} = \dfrac{200}{600} = \dfrac{1}{3}.$$

**Krok 2: vyjádřit $Y$ jako funkci $X$.**

Roznásobíme křížově:

$$3 \cdot (10 - X) = 1 \cdot (24 - Y),$$
$$30 - 3X = 24 - Y,$$
$$Y = 3X - 6. \quad (*)$$

Tato rovnice je **expanzní cesta** pro daný poměr cen — geometricky je to přímka v rovině $(X, Y)$, která prochází body, kde se sklon indiferenční křivky vyrovnává s daným $-1/3$.

**Krok 3: dosadit do rozpočtu.**

$$4\,400 = 200 X + 600 \cdot (3X - 6),$$
$$4\,400 = 200 X + 1\,800 X - 3\,600,$$
$$8\,000 = 2\,000 X,$$
$$\boxed{\,X^* = 4.\,}$$

**Krok 4: dopočítat $Y$** z rovnice (*):

$$Y^* = 3 \cdot 4 - 6 = 6.$$

**Optimum: $(X^*, Y^*) = (4, 6)$.** Užitek v optimu:

$$U^* = 10 \cdot 4 + 24 \cdot 6 - 0{,}5 \cdot 16 - 0{,}5 \cdot 36 = 40 + 144 - 8 - 18 = 158.$$

---

## 6. Metoda II — substituce z rozpočtu do funkce užitku

> [!info] Kdy použít
> Pokud chcete *mechanicky bezpečný* postup s explicitní kontrolou druhé derivace. Funguje skvěle u dvou proměnných a lineárního rozpočtu; u tří a více proměnných se substituce stane nepřehlednou.

**Krok 1: z rozpočtu vyjádřit jednu proměnnou.**

Z $X + 3Y = 22$ máme:

$$X = 22 - 3Y. \quad (\dagger)$$

**Krok 2: dosadit do funkce užitku** a hledat volné maximum přes $Y$.

$$U(Y) = 10 \cdot (22 - 3Y) + 24 Y - 0{,}5 \cdot (22 - 3Y)^2 - 0{,}5 Y^2.$$

Roznásobíme po krocích:

- $10 \cdot (22 - 3Y) = 220 - 30 Y$
- $-0{,}5 \cdot (22 - 3Y)^2 = -0{,}5 \cdot (484 - 132 Y + 9 Y^2) = -242 + 66 Y - 4{,}5 Y^2$

Sečteme:

$$U(Y) = 220 - 30 Y + 24 Y - 242 + 66 Y - 4{,}5 Y^2 - 0{,}5 Y^2.$$

Slučíme členy:

- konstanta: $220 - 242 = -22$
- lineární $Y$: $-30 + 24 + 66 = 60$
- kvadratický $Y^2$: $-4{,}5 - 0{,}5 = -5$

$$\boxed{\,U(Y) = -22 + 60 Y - 5 Y^2.\,}$$

**Krok 3: první derivace = 0** (nutná podmínka extrému):

$$\dfrac{dU}{dY} = 60 - 10 Y = 0 \quad\Rightarrow\quad Y^* = 6.$$

**Krok 4: druhá derivace** (postačující podmínka pro maximum):

$$\dfrac{d^2 U}{dY^2} = -10 < 0,$$

tedy nalezený stacionární bod je **lokální (a vzhledem k tvaru paraboly i globální) maximum**.

**Krok 5: dopočítat $X$** z $(\dagger)$:

$$X^* = 22 - 3 \cdot 6 = 22 - 18 = 4.$$

Stejné optimum: $(4, 6)$, $U^* = 158$. ✓

---

## 7. Metoda III — Lagrangeova metoda

> [!info] Kdy použít
> Standardní postup ve vyšší ekonomii: škáluje na **libovolný počet proměnných i omezení**, nedělá žádné předpoklady o tom, kterou proměnnou je výhodné vyjádřit, a navíc poskytne hodnotu **multiplikátoru $\lambda$**, kterou lze ekonomicky interpretovat jako *stínovou cenu* uvolnění omezení.

### 7.1 Lagrangián

Maximalizujeme $U(X, Y)$ za podmínky $g(X, Y) = I - P_X X - P_Y Y = 0$. Lagrangián:

$$\mathcal{L}(X, Y, \lambda) = U(X, Y) + \lambda \cdot \big(I - P_X X - P_Y Y\big).$$

Pro náš příklad:

$$\mathcal{L} = 10 X + 24 Y - 0{,}5 X^2 - 0{,}5 Y^2 + \lambda \cdot (4\,400 - 200 X - 600 Y).$$

### 7.2 Podmínky stacionarity

Tři parciální derivace musí být nulové:

$$\dfrac{\partial \mathcal{L}}{\partial X} = 10 - X - 200 \lambda = 0, \quad (1)$$

$$\dfrac{\partial \mathcal{L}}{\partial Y} = 24 - Y - 600 \lambda = 0, \quad (2)$$

$$\dfrac{\partial \mathcal{L}}{\partial \lambda} = 4\,400 - 200 X - 600 Y = 0. \quad (3)$$

Rovnice (3) je samotné rozpočtové omezení.

### 7.3 Řešení soustavy

Z (1): $\lambda = (10 - X)/200$. Z (2): $\lambda = (24 - Y)/600$. Položíme rovno:

$$\dfrac{10 - X}{200} = \dfrac{24 - Y}{600}.$$

Přenásobíme 600:

$$3 (10 - X) = 24 - Y \;\Rightarrow\; Y = 3X - 6.$$

To je ta samá rovnice $(*)$ jako v Metodě I — Lagrange ji odvozuje strojově místo intuice "položíme $MRS = P_X/P_Y$".

Dosadíme do (3):

$$4\,400 = 200 X + 600 (3 X - 6) = 2\,000 X - 3\,600 \;\Rightarrow\; X^* = 4, \quad Y^* = 6.$$

Hodnota multiplikátoru:

$$\lambda^* = \dfrac{10 - 4}{200} = \dfrac{6}{200} = 0{,}03.$$

### 7.4 Interpretace $\lambda$ — stínová cena důchodu

Multiplikátor $\lambda$ má v ekonomii konkrétní význam: **udává, o kolik vzroste maximální dosažitelný užitek $U^*$, pokud se důchod zvýší o jednu jednotku.** Formálně (obálková věta, *envelope theorem*):

$$\lambda = \dfrac{\partial U^*(I)}{\partial I}.$$

Anglicky se tomu říká *shadow price of income*. V našem příkladu $\lambda = 0{,}03$ znamená, že **každá další koruna ročního kulturního rozpočtu Petra zvýší jeho užitek z kultury o 0{,}03 jednotky užitku** (v okolí současného optima).

```graph
title: Nepřímý užitek V(I) a stínová cena λ
alt: Konkávní křivka nepřímého užitku V jako funkce důchodu I. Sklon křivky v daném bodě odpovídá Lagrangeově multiplikátoru λ. V bodě nasycení I=16400 sklon klesá k nule.
xAxis: { label: "Důchod I (Kč)", domain: [0, 18000] }
yAxis: { label: "V(I) — užitek", domain: [0, 360] }
params: []
curves:
  - { fn: "10*((x+3600)/2000) + 24*(3*(x+3600)/2000 - 6) - 0.5*pow((x+3600)/2000,2) - 0.5*pow(3*(x+3600)/2000 - 6, 2)", label: "V(I)", color: "fp-purple" }
markers:
  - { x: "4400", label: "I = 4400" }
  - { x: "16400", label: "Bod nasycení I̅" }
```

### 7.4b Ekvivalentní podoba interpretace přes mezní užitky

Z rovnic (1) a (2) můžeme vyjádřit:

$$\lambda = \dfrac{MU_X}{P_X} = \dfrac{MU_Y}{P_Y}.$$

To je tzv. **zákon vyrovnaných mezních užitků** (anglicky *equimarginal principle* nebo *Gossenův druhý zákon*): v optimu se **mezní užitek z koruny utracené za zboží $X$** rovná **meznímu užitku z koruny utracené za zboží $Y$**. Pokud by tomu tak nebylo, spotřebitel by mohl získat vyšší užitek tím, že přesune korunu z méně produktivní položky do produktivnější — a optimum by tedy ještě nebylo dosaženo. Společná hodnota tohoto poměru je právě $\lambda$.

### 7.5 Číselný test stínové ceny

Ověříme, že interpretace skutečně platí. Předpokládejme, že důchod stoupne o jednu korunu, $I' = 4\,401$. Nový rozpočet:

$$200 X' + 600 Y' = 4\,401.$$

Z podmínky tečnosti se nezmění tvar $Y' = 3 X' - 6$. Dosadíme:

$$4\,401 = 200 X' + 600 (3 X' - 6) = 2\,000 X' - 3\,600 \;\Rightarrow\; X' = \dfrac{8\,001}{2\,000} = 4{,}0005.$$

> [!note] Drobná oprava aritmetiky
> Přímý výpočet dává $X' = 4{,}0005$ a $Y' = 3 \cdot 4{,}0005 - 6 = 6{,}0015$. (Hodnota $X' \approx 4{,}0015$ z ručního přepisu se mírně liší zaokrouhlením.) Užitek:
> $$U' = 10 \cdot 4{,}0005 + 24 \cdot 6{,}0015 - 0{,}5 \cdot 4{,}0005^2 - 0{,}5 \cdot 6{,}0015^2 \approx 158{,}03.$$
> Změna užitku $\Delta U = U' - U^* \approx 158{,}03 - 158{,}00 = 0{,}03$, což je **přesně $\lambda$**. ✓

Tento numerický test potvrzuje obálkovou větu: $\Delta U \approx \lambda \cdot \Delta I$.

---

## 8. Bod nasycení

> [!important] Definice
> **Bod nasycení** (*satiation point*, někdy také *bliss point*) je koš $(\bar X, \bar Y)$, ve kterém **všechny mezní užitky jsou nulové**:
> $$MU_X(\bar X, \bar Y) = 0, \qquad MU_Y(\bar X, \bar Y) = 0.$$
> Spotřebitel v něm dosahuje **globálního maxima funkce užitku** *bez ohledu na rozpočet* — jakákoli další jednotka libovolného zboží by mu už užitek nezvyšovala (a u striktně konkávních $U$ by jej dokonce snižovala).

### 8.1 Bod nasycení pro Petrův užitek

Pro $U = 10X + 24Y - 0{,}5 X^2 - 0{,}5 Y^2$:

$$MU_X = 10 - X = 0 \;\Rightarrow\; \bar X = 10,$$
$$MU_Y = 24 - Y = 0 \;\Rightarrow\; \bar Y = 24.$$

Globální maximum užitku:

$$\bar U = 10 \cdot 10 + 24 \cdot 24 - 0{,}5 \cdot 100 - 0{,}5 \cdot 576 = 100 + 576 - 50 - 288 = 338.$$

### 8.2 Důchod potřebný k dosažení bodu nasycení

Při daných cenách je nákladový "ceník" bodu nasycení:

$$\bar I = P_X \cdot \bar X + P_Y \cdot \bar Y = 200 \cdot 10 + 600 \cdot 24 = 2\,000 + 14\,400 = 16\,400\,\text{Kč}.$$

> [!warning] Klíčový poznatek
> Pokud Petrův skutečný důchod $I = 4\,400 < \bar I = 16\,400$, je **rozpočtové omezení aktivní** a optimum leží na rozpočtové přímce ($X^*=4$, $Y^*=6$). Pokud by však Petrův důchod přesáhl $16\,400\,\text{Kč}$, **další navyšování důchodu už užitek nezvyšuje** — utratil by jen $16\,400$ a zbytek by zůstal nevyužit (resp. by spotřeboval i víc, ale s klesajícím užitkem).

V Petrově příběhu to znamená: **Petr nemá zájem o víc než 10 videokazet a 24 koncertů Pražského jara za rok**. Po překročení tohoto stropu mu každá další videokazeta působí dokonce *negativní* mezní užitek — viz $MU_X(11, \cdot) = 10 - 11 = -1$.

### 8.3 Realistická interpretace v Petrově příběhu

Bod nasycení nepředstavuje hypotetickou kuriozitu — odráží konečnou kapacitu spotřebitele. Petr má omezený volný čas (24 koncertů Pražského jara je v praxi blízko maximu, který festival ročně nabízí) i omezenou trpělivost s opakovaným sledováním akčních filmů. Funkce užitku $U = 10X + 24Y - 0{,}5 X^2 - 0{,}5 Y^2$ přirozeně modeluje **klesající mezní užitek** ($\partial^2 U / \partial X^2 = -1 < 0$), který v určitém bodě dosáhne nuly a poté přejde do záporu (přesycení).

Pro reálné rozhodování je třeba si pamatovat, že **bod nasycení často není dosažen** — typický spotřebitel je **rozpočtem omezen** dlouho před tím, než by ho mohl dosáhnout. Studium bodu nasycení má tedy spíše **diagnostický význam**: ujišťuje nás, že naše funkce užitku má rozumný globální tvar, a slouží jako horní mez pro analýzu důchodové elasticity.

### 8.4 Stínová cena ve vztahu k bodu nasycení

V bodě nasycení je $\lambda = MU_X / P_X = 0/P_X = 0$ — důchod přestává mít hodnotu, protože ho nelze "investovat" do dalšího užitku. Stínová cena důchodu je nulová.

---

## 9. Kompletní příklad Petr-kultura — všechny otázky

Pro úplnost projděme všechny podotázky zadání.

### (a) Mezní míra substituce

$$MRS_C = \dfrac{10 - X}{24 - Y}.$$

V optimu (vnitřním) musí $MRS_C$ odpovídat poměru cen.

### (b) Linie rozpočtu

$$200 X + 600 Y = 4\,400 \;\Leftrightarrow\; X + 3 Y = 22.$$

Průsečíky: $(22, 0)$ a $(0, 22/3)$.

### (c) Optimum

$$X^* = 4, \quad Y^* = 6, \quad U^* = 158.$$

V optimu $MRS_C = (10-4)/(24-6) = 6/18 = 1/3 = P_X/P_Y$ ✓.

### (d) Bod nasycení

$$\bar X = 10, \quad \bar Y = 24, \quad \bar U = 338, \quad \bar I = 16\,400\,\text{Kč}.$$

### (e) Zvýšení ceny videokazet na $P_X = 300$

Nový poměr cen: $P_X / P_Y = 300/600 = 1/2$. Nová podmínka tečnosti:

$$\dfrac{10 - X}{24 - Y} = \dfrac{1}{2} \;\Rightarrow\; 2(10 - X) = 24 - Y \;\Rightarrow\; Y = 2X + 4.$$

Dosadíme do nového rozpočtu $300 X + 600 Y = 4\,400$:

$$300 X + 600 (2X + 4) = 4\,400 \;\Rightarrow\; 1\,500 X = 4\,400 - 2\,400 = 2\,000 \;\Rightarrow\; X^*_e \approx 1{,}33.$$

Pak $Y^*_e = 2 \cdot 1{,}33 + 4 \approx 6{,}67$.

**Geometrie:** rozpočtová přímka rotuje **kolem bodu** $(0, 22/3) \approx (0, 7{,}33)$ na ose $Y$ (cena $Y$ se nezměnila, takže krajní bod na ose $Y$ je beze změny) směrem **dovnitř**. Spotřebitel si dovolí méně videokazet, na koncertech naopak nepatrně přidá (efekty jsou kombinací substituce a důchodu — viz [[mikk-substitucni-duchodovy-efekt|substituční a důchodový efekt]]).

V optimu nový $MRS_C = 1/2$.

### (f) Snížení ceny lístku na koncert na $P_Y = 300$

Nový poměr cen: $P_X / P_Y = 200/300 = 2/3$. Podmínka tečnosti:

$$\dfrac{10 - X}{24 - Y} = \dfrac{2}{3} \;\Rightarrow\; 3(10 - X) = 2(24 - Y) \;\Rightarrow\; 2 Y = 2 X + 18 \;\Rightarrow\; Y = X + 9.$$

Dosadíme do rozpočtu $200 X + 300 Y = 4\,400$:

$$200 X + 300 (X + 9) = 4\,400 \;\Rightarrow\; 500 X = 4\,400 - 2\,700 = 1\,700 \;\Rightarrow\; X^*_f = 3{,}4.$$

$Y^*_f = 3{,}4 + 9 = 12{,}4$.

**Geometrie:** přímka rotuje **kolem bodu** $(22, 0)$ na ose $X$ (cena $X$ se nezměnila) směrem **ven**. Levnější koncerty způsobí, že Petr jich navštíví výrazně více ($Y$ vzroste z 6 na 12{,}4), zatímco $X$ klesne mírně z 4 na 3{,}4 — typický substituční efekt ve prospěch zlevněného zboží.

V novém optimu $MRS_C = 2/3$.

### (g) Zvýšení důchodu na $I' = 6\,000\,\text{Kč}$

Ceny zůstávají $P_X = 200$, $P_Y = 600$, takže poměr cen i podmínka tečnosti se nemění. Pořád platí $Y = 3X - 6$. Dosadíme do nového rozpočtu:

$$200 X + 600 (3X - 6) = 6\,000 \;\Rightarrow\; 2\,000 X = 9\,600 \;\Rightarrow\; X^*_g = 4{,}8.$$

$Y^*_g = 3 \cdot 4{,}8 - 6 = 8{,}4$.

**Geometrie:** rozpočtová přímka se **paralelně posouvá** doprava nahoru (sklon $-1/3$ se nemění, oba krajní průsečíky se vzdalují od počátku). Optimum se posouvá podél **expanzní cesty** $Y = 3X - 6$. Protože $MRS_C$ se v optimu nemění (zůstává $1/3$), mluvíme o tzv. *důchodové spotřební křivce* (ICC) — viz [[mikk-substitucni-duchodovy-efekt|substituční a důchodový efekt]] a [[mikk-utility-preference|funkce užitku]].

Užitek v novém optimu:

$$U^*_g = 10 \cdot 4{,}8 + 24 \cdot 8{,}4 - 0{,}5 \cdot 4{,}8^2 - 0{,}5 \cdot 8{,}4^2 = 48 + 201{,}6 - 11{,}52 - 35{,}28 = 202{,}8.$$

> [!tip] Sanity check stínovou cenou
> $\Delta I = 6\,000 - 4\,400 = 1\,600$. Lineární odhad pomocí $\lambda = 0{,}03$: $\Delta U \approx 0{,}03 \cdot 1\,600 = 48$. Skutečné $\Delta U = 202{,}8 - 158 = 44{,}8$. Odhad je nadhodnocen — protože při velké změně už $\lambda$ není konstantní (klesá, jak se blížíme bodu nasycení). Pro infinitezimální změnu je odhad přesný; pro $\Delta I = 1\,600$ vidíme **nelinearitu** funkce nepřímého užitku.

---

## 10. Geometrie optima — tečnost křivek

![[mikk-optimum-spotrebitele.jpeg|Optimum spotřebitele — tečnost indiferenční křivky a rozpočtové přímky, podmínka MRS = P_x/P_y]]

V bodě optima se sklon **indiferenční křivky** rovná sklonu **rozpočtové přímky**:

- Sklon indiferenční křivky procházející $(X^*, Y^*)$: $-MRS_C = -(10 - X^*)/(24 - Y^*)$.
- Sklon rozpočtové přímky: $-P_X / P_Y$.

Podmínka tečnosti:

$$-MRS_C = -\dfrac{P_X}{P_Y} \;\Leftrightarrow\; MRS_C = \dfrac{P_X}{P_Y}.$$

Indiferenční křivka leží **uvnitř** souboru tržních příležitostí (pod rozpočtovou přímkou) všude kromě bodu doteku — kdyby protínala přímku, znamenalo by to, že existuje jiný dostupný koš na vyšší indiferenční křivce, takže původní bod by nebyl optimum.

**Algoritmický pohled:** posouvejme indiferenční křivku od počátku nahoru, dokud se právě dotýká rozpočtové přímky. Bod doteku = optimum.

```graph
title: Tečnost IC a rozpočtové přímky pro U = 10X + 24Y - 0.5X² - 0.5Y²
alt: Indiferenční křivka kvadratického užitku U(X,Y)=158 a rozpočtová přímka X+3Y=22. Posuvník U0 mění úroveň užitku, posuvník Pp mění sklon rozpočtové přímky a posouvá bod tečnosti.
xAxis: { label: "X", domain: [0, 12] }
yAxis: { label: "Y", domain: [0, 12] }
params:
  - { name: U0, label: "Úroveň užitku U0", min: 100, max: 200, default: 158, step: 1 }
  - { name: Pp, label: "Cena Px", min: 100, max: 500, default: 200, step: 10 }
curves:
  - { fn: "24 - sqrt(576 - 2*U0 + 20*x - x*x)", label: "Indiferenční křivka U=U0", color: "fp-red" }
  - { fn: "(4400 - Pp*x)/600", label: "Rozpočtová přímka", color: "fp-purple" }
markers:
  - { x: "4", label: "X* = 4" }
```

---

## 10b. Algebraická symetrie tří metod

Stojí za to si všimnout, že všechny tři metody se v jádru opírají o **stejné dvě podmínky**:

1. **Podmínka tečnosti** $MRS_C = P_X / P_Y$ (nebo ekvivalentně $MU_X / P_X = MU_Y / P_Y$).
2. **Rozpočtová podmínka** $P_X X + P_Y Y = I$.

Liší se pouze pořadím a způsobem, jakým tyto podmínky uplatňují:

- **Metoda I** přímo manipuluje obě podmínky symbolicky.
- **Metoda II** dosadí rozpočet *před* derivováním a tečnost dostane "zdarma" z volné optimalizace.
- **Metoda III** dosadí rozpočet *po* derivování (formálně přes $\partial \mathcal{L} / \partial \lambda$) a podmínku tečnosti odvodí z rovnosti dvou výrazů pro $\lambda$.

Z hlediska matematické teorie jsou si tyto postupy ekvivalentní; volba mezi nimi je čistě otázka přehlednosti a rozšiřitelnosti na složitější úlohy.

---

## 11. Kdy která metoda?

Praktický rozhodovací rámec:

- **Metoda I (substituce přes MRS):** výchozí volba pro **2 zboží + lineární rozpočet + hladkou $U$**. Nejrychlejší ručně.
- **Metoda II (substituce do $U$):** vhodná, když chcete explicitně ověřit **2. derivaci** a máte 2 proměnné. Pro 3+ proměnné se algebraický balast rychle zvyšuje.
- **Metoda III (Lagrange):** standard pro **3 a více proměnných**, pro **více omezení současně** (např. další omezení času, kalorií atd.), a vždy, když potřebujete **stínovou cenu $\lambda$**. V akademickém kontextu (mikroekonomie 2 a vyšší) se používá jako defaultní formalizace.

> [!summary] Praktické pravidlo
> Na zkoušku z MikK doporučujeme zvládnout **všechny tři** — Metoda I jako rychlý sanity check, Metoda III jako standardní postup s plnou ekonomickou interpretací. Metoda II je užitečná při kontrole, zda nám 2. derivace skutečně dává maximum (a ne minimum nebo sedlo).

---

## 11b. Časté chyby a jak se jim vyhnout

> [!danger] Pozor na obvyklé chyby ve zkouškových příkladech
>
> 1. **Záměna $MRS$ a poměru cen.** $MRS_C = MU_X / MU_Y$ (užitky), nikoli $P_Y / P_X$. Poměr cen se používá *na pravé straně* podmínky tečnosti. Pokud máte v poměru $MU_Y$ v čitateli, máte převrácenou rovnici.
> 2. **Záměna číselníků $P_X / P_Y$.** Správně: poměr cen vyjadřuje, kolik $Y$ je nutné obětovat za jednu $X$, takže $P_X / P_Y$, ne $P_Y / P_X$.
> 3. **Zapomenutí ověřit 2. derivaci u Metody II.** První derivace = 0 dává jen stacionární bod; bez ověření $d^2 U / dY^2 < 0$ nemáme jistotu, že jde o maximum.
> 4. **Špatné dosazení v Lagrangiánu.** Znaménko u členu $\lambda(I - P_X X - P_Y Y)$ je **kladné**, protože omezení píšeme ve tvaru $g = I - P_X X - P_Y Y = 0$. Pokud byste psali $\lambda(P_X X + P_Y Y - I)$, znaménka v derivacích se otočí (a $\lambda$ vyjde záporné).
> 5. **Zaokrouhlování v testu stínové ceny.** Pokud chcete numericky ověřit $\Delta U \approx \lambda$, je třeba spočítat $X'$ a $Y'$ na dostatek desetinných míst — na celá čísla zaokrouhlený výsledek dá jen přibližnou shodu.
> 6. **Předpoklad vnitřního řešení bez ověření.** U lineárních funkcí užitku ($U = aX + bY$) nikdy nedostanete vnitřní řešení (kromě degenerovaného případu $a/b = P_X/P_Y$). Vždy začněte úvahou, zda funkce užitku je striktně konkávní.

---

## 12. Vazba na duální úlohu — minimalizace výdajů

Maximalizace užitku za daného důchodu má svou *duální* podobu: **minimalizace výdajů za daného užitku**. Tento vztah shrnuje následující tabulka:

| Primární úloha (Marshall) | Duální úloha (Hicks) |
|---------------------------|----------------------|
| $\max U(X, Y)$ za $P_X X + P_Y Y \le I$ | $\min E = P_X X + P_Y Y$ za $U(X, Y) \ge U_0$ |
| Řešení: **Marshallova poptávka** $X^M(I, P_X, P_Y)$ | Řešení: **Hicksova poptávka** $X^H(U_0, P_X, P_Y)$ |
| Hodnota: **nepřímá funkce užitku** $V(I, P_X, P_Y)$ | Hodnota: **výdajová funkce** $E(U_0, P_X, P_Y)$ |

Obě úlohy dávají v optimu **tentýž bod** $(X^*, Y^*)$ — liší se jen tím, kterou veličinu fixujeme a kterou minimalizujeme/maximalizujeme. Stínová cena $\lambda$ z Lagrangiánu primární úlohy se v duálu mění v *mezní výdaj na jednotku užitku* (převrácená hodnota).

Detailní rozbor duality, odvození obou typů poptávek a Slutskyho rovnice patří do navazujícího tématu [[mikk-marshall-hicks-poptavka|Marshallovy a Hicksovy poptávky]].

---

## 13. Souhrn

> [!success] Co si odnést
> 1. **Optimum vnitřní:** $MRS_C = P_X/P_Y$ a $P_X X + P_Y Y = I$.
> 2. **Tři ekvivalentní metody řešení:** substituce přes MRS (rychlá), substituce do U (mechanická), Lagrange (univerzální + stínová cena).
> 3. **Lagrangeův multiplikátor $\lambda$** = stínová cena důchodu = mezní užitek z koruny navíc.
> 4. **Bod nasycení** $(\bar X, \bar Y)$: $MU_X = MU_Y = 0$. Důchod nad $\bar I = P_X \bar X + P_Y \bar Y$ už užitek nezvyšuje.
> 5. **Posuny rozpočtové přímky:** změna $I$ → paralelní posun; změna ceny → rotace kolem nedotčeného krajního bodu.
> 6. **Petrův příklad:** $X^*=4$, $Y^*=6$, $U^*=158$, $\lambda=0{,}03$, bod nasycení $(10, 24)$.

---

## Související stránky

- [[mikk|Mikroekonomie 2 (MikK)]] — mateřský kurz a rozcestník témat.
- [[mikk-utility-preference]] — funkce užitku, indiferenční křivky, mezní užitek a původ $MRS_C$.
- [[mikk-marshall-hicks-poptavka]] — duální úloha, odvození poptávkových funkcí a Slutskyho rozklad.
- [[mikk-substitucni-duchodovy-efekt]] — analýza změn cen a důchodu, PCC a ICC křivky, Hicksův vs. Slutského rozklad.
- [[lagrangeova-metoda|Lagrangeova metoda (ImeK)]] — matematická báze metody, vícerozměrné optimum s omezením.
- [[optimalizace-spotrebitele|Optimalizace spotřebitele (ImeK primer)]] — stručný matematický úvod do problému z pohledu předmětu Matematická ekonomie.
- [[mikk-elasticita-poptavky]] — citlivost optimálních množství na ceny a důchod.
- [[mikk-vzorce-prehled|Přehled vzorců MikK]] — kompaktní formulář pro zkoušku.
