---
title: "MikK — Srovnání oligopolních modelů"
course: mikk
type: output
tags: [mikk, oligopol, cournot, stackelberg, bertrand, koluze, srovnani]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# MikK — Srovnání oligopolních modelů

> [!abstract] TL;DR
> Pro lineární poptávku $P = a - bQ$ a $MC = 0$ porovnáváme **4 klasické oligopolní modely**: sdílený monopol (koluze), Cournot, Stackelberg a Bertrand. Každý model má svou rovnováhu (rozložení produkce mezi firmy), tržní cenu, zisky firem a celkový blahobyt. Zlatá tabulka v sekci 2 shrnuje výsledky; sekce 3–5 obsahují detailní odvození a numerický příklad. Sekce 6 srovnává modely z hlediska zisku, spotřebitelského přebytku a stability.

## 1. Společný rámec

### Předpoklady všech 4 modelů

- **Tržní poptávka:** $P = a - bQ$, kde $Q = Q_1 + Q_2$ (jen 2 firmy pro srovnatelnost)
- **Mezní náklady:** $MC_1 = MC_2 = 0$ (nulové; výsledky se zobecňují přidáním $-MC$ ke všem cenám)
- **Homogenní zboží:** firmy nabízejí identický produkt
- **2 firmy:** duopol (zobecnění na $n$ firem v sekci 7)

### Klíčové rozdíly modelů

| Aspekt | Koluze | Cournot | Stackelberg | Bertrand |
|--------|--------|---------|-------------|----------|
| Strategická proměnná | množství (společně) | množství (současně) | množství (sekvenčně) | cena (současně) |
| Pořadí tahů | dohoda | simultánní | lider → follower | simultánní |
| Informace | full | full | full | full |
| Druh hry | kooperativní | nekooperativní | nekooperativní | nekooperativní |
| Typ rovnováhy | Pareto-efektivní pro firmy | Nash | Stackelberg-Nash | Nash |

---

## 2. Zlatá srovnávací tabulka

Pro $P = a - bQ$, $MC = 0$:

| Model | $Q_1$ | $Q_2$ | $Q$ celkem | $P$ | $\pi_1$ | $\pi_2$ | $\sum \pi$ | CS | DWL |
|-------|-------|-------|-----------|-----|---------|---------|-----------|-----|-----|
| Sdílený monopol (koluze) | $\frac{a}{4b}$ | $\frac{a}{4b}$ | $\frac{a}{2b}$ | $\frac{a}{2}$ | $\frac{a^2}{8b}$ | $\frac{a^2}{8b}$ | $\frac{a^2}{4b}$ | $\frac{a^2}{8b}$ | $\frac{a^2}{8b}$ |
| Cournot | $\frac{a}{3b}$ | $\frac{a}{3b}$ | $\frac{2a}{3b}$ | $\frac{a}{3}$ | $\frac{a^2}{9b}$ | $\frac{a^2}{9b}$ | $\frac{2a^2}{9b}$ | $\frac{2a^2}{9b}$ | $\frac{a^2}{18b}$ |
| Stackelberg | $\frac{a}{2b}$ | $\frac{a}{4b}$ | $\frac{3a}{4b}$ | $\frac{a}{4}$ | $\frac{a^2}{8b}$ | $\frac{a^2}{16b}$ | $\frac{3a^2}{16b}$ | $\frac{9a^2}{32b}$ | $\frac{a^2}{32b}$ |
| Bertrand | $\frac{a}{2b}$ | $\frac{a}{2b}$ | $\frac{a}{b}$ | $0$ | $0$ | $0$ | $0$ | $\frac{a^2}{2b}$ | $0$ |

> [!info] Poznámka
> CS (consumer surplus) a DWL (deadweight loss) jsou počítané vůči konkurenčnímu (Bertrandovu) ekvilibriu, kde $Q^C = a/b$, $P^C = 0$, $CS^C = a^2/(2b)$, $DWL^C = 0$.

---

## 3. Detailní odvození každého modelu

### 3.1 Sdílený monopol (koluze)

**Princip:** Firmy se domluví, jakoby byly **jeden monopol**. Společně maximalizují součet zisků.

$$\max_{Q_1, Q_2} \pi = (a - b(Q_1 + Q_2))(Q_1 + Q_2)$$

Substitucí $Q = Q_1 + Q_2$:

$$\pi(Q) = (a - bQ) Q = aQ - bQ^2$$

FOC: $\frac{d\pi}{dQ} = a - 2bQ = 0 \Rightarrow Q^K = \frac{a}{2b}$.

$P^K = a - b \cdot \frac{a}{2b} = \frac{a}{2}$.
$\sum \pi^K = \frac{a}{2} \cdot \frac{a}{2b} = \frac{a^2}{4b}$.

Při dělení 50:50: $Q_1 = Q_2 = \frac{a}{4b}$, $\pi_1 = \pi_2 = \frac{a^2}{8b}$.

**Spotřebitelský přebytek:**
$$CS^K = \frac{1}{2}(a - P^K) Q^K = \frac{1}{2} \cdot \frac{a}{2} \cdot \frac{a}{2b} = \frac{a^2}{8b}$$

**Mrtvá ztráta** vůči konkurenci ($P^C = 0, Q^C = a/b$):
$$DWL^K = \frac{1}{2}(P^K - P^C)(Q^C - Q^K) = \frac{1}{2} \cdot \frac{a}{2} \cdot \left(\frac{a}{b} - \frac{a}{2b}\right) = \frac{a^2}{8b}$$

### 3.2 Cournotův model

**Princip:** Každá firma volí $Q_i$ **simultánně**, předpokládá, že druhá firma drží svou strategii.

Firma 1: $\max_{Q_1} \pi_1 = (a - b(Q_1 + Q_2)) Q_1$.

FOC: $\frac{\partial \pi_1}{\partial Q_1} = a - 2bQ_1 - bQ_2 = 0$.

**Reakční funkce firmy 1:**
$$Q_1 = \frac{a - bQ_2}{2b} = \frac{a}{2b} - \frac{Q_2}{2}$$

Symetricky pro firmu 2:
$$Q_2 = \frac{a}{2b} - \frac{Q_1}{2}$$

**Soustava řešení:** dosadíme druhou rovnici do první:
$$Q_1 = \frac{a}{2b} - \frac{1}{2}\left(\frac{a}{2b} - \frac{Q_1}{2}\right) = \frac{a}{2b} - \frac{a}{4b} + \frac{Q_1}{4}$$

$$Q_1 - \frac{Q_1}{4} = \frac{a}{4b} \Rightarrow \frac{3Q_1}{4} = \frac{a}{4b} \Rightarrow Q_1^C = \frac{a}{3b}$$

Symetricky $Q_2^C = a/(3b)$.

$Q^C = 2a/(3b)$, $P^C = a - b \cdot 2a/(3b) = a/3$.
$\pi_i^C = (a/3) \cdot (a/(3b)) = a^2/(9b)$.

**Spotřebitelský přebytek:**
$$CS^{Cournot} = \frac{1}{2}(a - a/3)(2a/(3b)) = \frac{1}{2} \cdot \frac{2a}{3} \cdot \frac{2a}{3b} = \frac{2a^2}{9b}$$

**Antoine Augustin Cournot (1838):** první matematický model oligopolu.

### 3.3 Stackelbergův model

**Princip:** Lider (firma 1) volí $Q_1$ **jako první**, follower (firma 2) ji vidí a optimálně reaguje.

**Krok 1: Reakční funkce followera.** Firma 2 řeší stejnou úlohu jako v Cournotu:
$$Q_2(Q_1) = \frac{a}{2b} - \frac{Q_1}{2}$$

**Krok 2: Liderova úloha.** Firma 1 ví, jak bude follower reagovat, a maximalizuje:
$$\pi_1 = (a - b(Q_1 + Q_2(Q_1))) Q_1$$
$$= \left(a - b\left(Q_1 + \frac{a}{2b} - \frac{Q_1}{2}\right)\right) Q_1$$
$$= \left(a - bQ_1 - \frac{a}{2} + \frac{bQ_1}{2}\right) Q_1$$
$$= \left(\frac{a}{2} - \frac{bQ_1}{2}\right) Q_1$$
$$= \frac{a Q_1}{2} - \frac{b Q_1^2}{2}$$

FOC: $\frac{d\pi_1}{dQ_1} = \frac{a}{2} - b Q_1 = 0 \Rightarrow Q_1^S = \frac{a}{2b}$.

**Krok 3: Followerova reakce:** $Q_2^S = a/(2b) - 1/2 \cdot a/(2b) = a/(4b)$.

$Q^S = a/(2b) + a/(4b) = 3a/(4b)$, $P^S = a - 3a/4 = a/4$.

**Zisky:**
- $\pi_1^S = (a/4) \cdot (a/(2b)) = a^2/(8b)$
- $\pi_2^S = (a/4) \cdot (a/(4b)) = a^2/(16b)$

**Spotřebitelský přebytek:**
$$CS^S = \frac{1}{2}(a - a/4)(3a/(4b)) = \frac{1}{2} \cdot \frac{3a}{4} \cdot \frac{3a}{4b} = \frac{9a^2}{32b}$$

**Heinrich von Stackelberg (1934):** model dominantní firmy.

> [!tip] First-mover advantage
> Lider má **2× větší zisk** než v Cournotu ($a^2/8b$ vs. $a^2/9b$), přestože jeho produkce je vyšší. To je hodnota informace, že může jít první.

### 3.4 Bertrandův model

**Princip:** Firmy si **současně** volí cenu (ne množství). Spotřebitelé kupují u levnější firmy. Při shodě cen půlí trh.

**Argumentace:** Předpokládejme $P_1 > P_2 > MC$. Pak firma 2 má motivaci $P_2$ snížit pod $P_1$ a získat **celý trh** (zisk roste). Stejně firma 1. Tento podsekávací proces končí, až **obě ceny dosáhnou $MC$** — pod $MC$ by firma utrpěla ztrátu.

**Bertrandova rovnováha:**
$$P_1^B = P_2^B = MC = 0$$
$$Q_1^B = Q_2^B = \frac{a}{2b} \quad \text{(půlí konkurenční tržní množství)}$$
$$\pi_1^B = \pi_2^B = 0$$

**Spotřebitelský přebytek** = celý přebytek konkurenčního trhu:
$$CS^B = \frac{1}{2} \cdot a \cdot \frac{a}{b} = \frac{a^2}{2b}$$

$DWL^B = 0$ (efektivní alokace).

**Joseph Bertrand (1883):** kritika Cournota — argumentoval, že firmy si volí ceny, ne množství.

### Bertrandův paradox

Pouhé **2 firmy** stačí pro konkurenční výsledek. V realitě paradox neplatí, protože:

1. **Diferenciace produktu** — firmy nemají identické zboží (Coca-Cola vs. Pepsi), takže poptávka je k ceně méně citlivá.
2. **Kapacitní omezení (Edgeworth)** — firma nemůže zpracovat celý trh, takže vyšší cena druhé firmy zůstává relevantní.
3. **Opakované hry** — možnost koluze jako Nash v opakované hře (folk theorem).
4. **Vyhledávací náklady** — spotřebitelé nezjistí všechny ceny okamžitě.

---

## 4. Numerický příklad pro $a = 30$, $b = 1$, $MC = 0$

Tržní poptávka: $P = 30 - Q$. Konkurenční ekvilibrium: $P^C = 0, Q^C = 30, CS^C = 450$.

### 4.1 Sdílený monopol

$Q^K = 30/2 = 15$, $P^K = 15$.
$Q_1 = Q_2 = 7{,}5$.
$\pi_1 = \pi_2 = 7{,}5 \cdot 15 = 112{,}5$, $\sum \pi = 225$.
$CS^K = 0{,}5 \cdot 15 \cdot 15 = 112{,}5$.
$DWL^K = 0{,}5 \cdot 15 \cdot 15 = 112{,}5$.

### 4.2 Cournot

$Q_1 = Q_2 = 30/3 = 10$, $Q = 20$, $P = 10$.
$\pi_1 = \pi_2 = 10 \cdot 10 = 100$, $\sum \pi = 200$.
$CS^{Cournot} = 0{,}5 \cdot 20 \cdot 20 = 200$.
$DWL^{Cournot} = 0{,}5 \cdot 10 \cdot 10 = 50$.

### 4.3 Stackelberg

$Q_1 = 30/2 = 15$, $Q_2 = 30/4 = 7{,}5$, $Q = 22{,}5$, $P = 7{,}5$.
$\pi_1 = 7{,}5 \cdot 15 = 112{,}5$, $\pi_2 = 7{,}5 \cdot 7{,}5 = 56{,}25$.
$\sum \pi = 168{,}75$.
$CS^S = 0{,}5 \cdot 22{,}5 \cdot 22{,}5 = 253{,}125$.
$DWL^S = 0{,}5 \cdot 7{,}5 \cdot 7{,}5 = 28{,}125$.

### 4.4 Bertrand

$Q_1 = Q_2 = 15$, $Q = 30$, $P = 0$.
$\pi_1 = \pi_2 = 0$.
$CS^B = 0{,}5 \cdot 30 \cdot 30 = 450$.
$DWL^B = 0$.

### 4.5 Souhrnná tabulka

| Model | $Q_1$ | $Q_2$ | $Q$ | $P$ | $\pi_1$ | $\pi_2$ | $\sum\pi$ | $CS$ | $DWL$ | $TS$ |
|-------|-------|-------|-----|-----|---------|---------|-----------|------|-------|------|
| Koluze | 7,5 | 7,5 | 15 | 15 | 112,5 | 112,5 | 225 | 112,5 | 112,5 | 337,5 |
| Cournot | 10 | 10 | 20 | 10 | 100 | 100 | 200 | 200 | 50 | 400 |
| Stackelberg | 15 | 7,5 | 22,5 | 7,5 | 112,5 | 56,25 | 168,75 | 253,1 | 28,1 | 421,9 |
| Bertrand | 15 | 15 | 30 | 0 | 0 | 0 | 0 | 450 | 0 | 450 |

$TS$ = total surplus = $CS + \sum \pi$. Bertrand maximalizuje $TS$ (efektivní alokace).

---

## 5. Geometrické srovnání v rovině $(Q_1, Q_2)$

Pro $a = 30, b = 1, MC = 0$:

### Reakční funkce

- **Firma 1 (Cournot):** $Q_1 = 15 - Q_2/2$
- **Firma 2 (Cournot):** $Q_2 = 15 - Q_1/2$

Obě jsou klesající přímky. Průsečík = Cournotova rovnováha v $(10, 10)$.

### Křivka koluze

Body, kde $Q_1 + Q_2 = a/(2b) = 15$. Šikmá přímka v rovině $(Q_1, Q_2)$.

### Pareto-frontier pro firmy

Body, kde nelze zvýšit $\pi_1$ bez snížení $\pi_2$. Tato frontier obsahuje koluzi (různá dělení mezi $(Q_1, Q_2)$, kde $Q_1 + Q_2 = 15$).

### Polohy 4 rovnováh

- **Koluze:** $(7{,}5, 7{,}5)$ — leží **na** křivce koluze.
- **Cournot:** $(10, 10)$ — průsečík reakčních funkcí.
- **Stackelberg (lider 1):** $(15, 7{,}5)$ — leží **na** reakční funkci 2, vlevo od (5).
- **Bertrand:** $(15, 15)$ — pravý horní roh, leží **mimo** reakční funkce.

### Iso-zisk křivky

Pro firmu 1: $\pi_1 = (a - b(Q_1 + Q_2)) Q_1 = $ konst. $\Rightarrow$ křivka v $(Q_1, Q_2)$ rovině.

Tyto křivky jsou **konkávní** směrem dolů (vyšší zisk = nižší křivka). Nejvyšší zisk = nejníže.

### Vizualizace polohy

```
Q_2
30 |                                               
   |                                               
15 |  ●Bertrand                                    
   |  RF1                                         
10 |─ ─●Cournot                                    
 7,5|  ●Koluze    ●Stackelberg                    
   |              RF2                              
 0 |____________________________________Q_1
   0       7,5    10        15            30
```

**Pořadí podle vzdálenosti od počátku** (= celkové množství $Q$):
- Koluze: nejblíže (15)
- Cournot (20)
- Stackelberg (22,5)
- Bertrand: nejdál (30)

---

## 6. Diskuse — komparativní statika

### 6.1 Pořadí výhodnosti pro firmy

$$\sum \pi^K (225) > \sum \pi^{Cournot} (200) > \sum \pi^S (168{,}75) > \sum \pi^B (0)$$

**Závěr:** Koluze je pro firmy **nejvýhodnější**, ale je nestabilní — každá firma má motivaci zvýšit svůj $Q_i$ (podvádět). Bertrand je pro firmy **nejhorší** — destruktivní cenová válka.

### 6.2 Pořadí výhodnosti pro spotřebitele

$$CS^B (450) > CS^S (253) > CS^{Cournot} (200) > CS^K (112{,}5)$$

**Závěr:** Bertrand maximalizuje $CS$ — firmy si konkurují cenou. Koluze je pro spotřebitele nejhorší.

### 6.3 Pořadí podle celkového blahobytu (total surplus)

$$TS^B (450) > TS^S (421{,}9) > TS^{Cournot} (400) > TS^K (337{,}5)$$

**Závěr:** Bertrand je **Pareto-efektivní** (žádná DWL). Stackelberg má vyšší $TS$ než Cournot díky vyšší celkové produkci.

### 6.4 Stabilita (Nashova rovnováha?)

| Model | Nash? | Stabilní? |
|-------|-------|-----------|
| Koluze | **Ne** | Nestabilní (motivace podvádět) |
| Cournot | **Ano** | Stabilní (jednoduchá Nash) |
| Stackelberg | **Ano** | Stabilní (subgame-perfect Nash) |
| Bertrand | **Ano** | Stabilní (Nash, obě firmy maximalizují daným cenou druhé firmy) |

**Koluze a vězňovo dilema:** Když obě firmy hrají koluzi $(Q_i = 7{,}5)$, každá by si polepšila zvýšením na $11{,}25$ (best response na $Q_2 = 7{,}5$ z reakční funkce $Q_1 = 15 - 7{,}5/2 = 11{,}25$). Ale když to udělají obě, skončí v Cournotově ekvilibriu $(10, 10)$. Klasické vězňovo dilema. Viz [[mikk-vezno-dilema-teorie-her|Vězňovo dilema]].

### 6.5 Stackelberg vs. Cournot — first-mover advantage

| | Cournot | Stackelberg lider | Stackelberg follower |
|---|---------|------------------|---------------------|
| $Q$ | 10 | 15 | 7,5 |
| $\pi$ | 100 | 112,5 | 56,25 |

- **Lider** má 12,5 % vyšší zisk než v Cournotu (využívá přepuje first-mover).
- **Follower** má 43,75 % nižší zisk než v Cournotu — je v horší pozici, ale **nemůže nic udělat**.

> [!info] Když má follower výhodu?
> Pokud strategické proměnné jsou **strategickými komplementy** (= reakční funkce **rostou**), pak je výhodný **second-mover advantage** — nezávazná pozice. Pro Cournot/Stackelberg jsou množství strategickými substituty (reakční funkce klesají), takže first-mover advantage. Pro Bertrand s diferenciovanými cenami jsou ceny komplementy → second-mover advantage.

---

## 7. Kdy který model platí v realitě

### 7.1 Cournot — simultánní volba kapacity

**Vhodné pro:**
- Zemědělství (rozhodnutí o osévané ploše dlouho před sklizní)
- Surovinový průmysl (kapacity dolů, ropných polí)
- Výroba s dlouhým časovým posunem mezi rozhodnutím a uvedením na trh

**Příklad:** Saudská Arábie a Rusko v rozhodování o objemu těžby ropy mimo OPEC+. Cena se ustaví podle součtu rozhodnutí.

### 7.2 Stackelberg — jasný lider

**Vhodné pro:**
- Trh s dominantní firmou, která rozhoduje první
- Sequential entry (jeden vstoupí dřív)

**Příklady:**
- **Microsoft v 90. letech 20. století** vůči ostatním softwarovým firmám
- **Boeing** vs. **Airbus** (Boeing historicky lider, Airbus follower do 2000)
- **Apple** vs. ostatní výrobci smartphone (Apple udává tempo s iPhone, ostatní reagují)

### 7.3 Bertrand — cenová konkurence s flexibilní kapacitou

**Vhodné pro:**
- E-commerce (porovnávače cen okamžitě podsekávají)
- Letenky (yield management — firma okamžitě reaguje na cenu konkurence)
- Elektřina, plyn, telekomunikace v deregulovaném prostředí
- Komodity (homogenní zboží, snadná substituce)

**Příklady:**
- Zboží na **Heureka.cz** — desítky e-shopů s identickým zbožím; ceny se sjednocují téměř na úroveň MC.
- Letenky **Praha-Londýn** — Ryanair, Wizz Air, ČSA, KLM se podsekávají v reálném čase.

### 7.4 Koluze — explicitní nebo tichá dohoda

**Vhodné pro:**
- Stabilní oligopol s malým počtem firem
- Snadno detekovatelné podvádění (transparentní ceny, malé množství zákazníků)
- Vysoká diskontní sazba (firmy si cení budoucích zisků)

**Příklady:**
- **OPEC** — kartel zemí těžících ropu, dohoda o produkci
- **ČR telekom 2018** — pokuta za tichou koluzi mezi O2, T-Mobile, Vodafone (vysoké ceny vůči EU)
- **Vitamínový kartel 90. let** — Hoffmann-La Roche, BASF, Aventis; pokuta EU $855 mil.
- **LIBOR scandal** — manipulace bankovní úrokové sazby skupinou bank

### 7.5 Faktory ovlivňující model

| Faktor | Posun směrem k... |
|--------|-------------------|
| Vyšší počet firem | Cournot → konkurence (Bertrand) |
| Diferenciace produktu | Bertrand → vyšší marže |
| Kapacitní omezení | Bertrand → Cournot |
| Opakovaná interakce | Cournot → koluze |
| Diskontní sazba ↓ | Stabilnější koluze |
| Asymetrie informací | Méně koluze, více konkurence |

---

## 8. Zobecnění na $n$ firem

Pro **Cournot s $n$ identickými firmami** s lineární poptávkou $P = a - bQ$ a $MC = c$:

$$Q_i^C = \frac{a - c}{(n+1) b}, \quad Q^C = \frac{n(a-c)}{(n+1)b}, \quad P^C = \frac{a + nc}{n+1}$$

$$\pi_i^C = \frac{(a-c)^2}{(n+1)^2 b}$$

**Limity:**
- $n = 1$: monopol, $Q^C = (a-c)/(2b)$, $P^C = (a+c)/2$.
- $n = 2$: standardní duopol Cournot.
- $n \to \infty$: $P^C \to c$ (= MC), $Q^C \to (a-c)/b$, $\pi_i^C \to 0$ → konvergence k dokonalé konkurenci.

**Lerner index:** $L = (P - MC)/P = 1/(n \cdot E_D)$ — tržní moc klesá lineárně s počtem firem (pro fixní elasticitu).

Viz [[mikk-monopolisticka-konkurence|Monopolistická konkurence]] pro chování při velkém $n$.

---

## 9. Příklad srovnání s nenulovým MC

Pro $P = 100 - Q$, $MC = 20$ pro obě firmy:

### Koluze
$\max (P - MC) Q = (80 - Q) Q$. FOC: $80 - 2Q = 0 \Rightarrow Q^K = 40$, $P^K = 60$.
Při dělení: $Q_1 = Q_2 = 20$, $\pi_i = (60 - 20) \cdot 20 = 800$, $\sum = 1\,600$.

### Cournot
Reakční funkce: $Q_1 = (80 - Q_2)/2$. Symetricky $Q_1 = Q_2 = 80/3 \approx 26{,}67$.
$Q = 53{,}33$, $P = 46{,}67$.
$\pi_i = (46{,}67 - 20) \cdot 26{,}67 \approx 711{,}1$, $\sum \approx 1\,422$.

### Stackelberg
$Q_1 = 80/2 = 40$, $Q_2 = 80/4 = 20$. $Q = 60$, $P = 40$.
$\pi_1 = (40-20) \cdot 40 = 800$, $\pi_2 = (40-20) \cdot 20 = 400$, $\sum = 1\,200$.

### Bertrand
$P_1 = P_2 = MC = 20$. $Q = 80$, dělení: $Q_1 = Q_2 = 40$.
$\pi_1 = \pi_2 = 0$.

### Souhrnná tabulka pro $MC = 20$

| Model | $Q$ | $P$ | $\sum \pi$ | $CS$ | $TS$ |
|-------|-----|-----|------------|------|------|
| Koluze | 40 | 60 | 1600 | 800 | 2400 |
| Cournot | 53,33 | 46,67 | 1422 | 1422 | 2844 |
| Stackelberg | 60 | 40 | 1200 | 1800 | 3000 |
| Bertrand | 80 | 20 | 0 | 3200 | 3200 |

Pořadí stejné jako v sekci 4 — princip **invariantní vůči $MC$** (po normalizaci $a' = a - MC$).

---

## 10. Praktické otázky pro zkoušku

### Q1: Pro $P = 60 - 2Q$ a $MC = 0$ najdi všechny 4 rovnováhy.

**Řešení:** $a = 60, b = 2$.
- Koluze: $Q^K = 60/4 = 15$, $P^K = 30$, $\sum \pi = 60 \cdot 15/2 = 450$.
- Cournot: $Q_i^C = 60/(3 \cdot 2) = 10$, $Q = 20$, $P = 20$, $\pi_i = 200$, $\sum = 400$.
- Stackelberg: $Q_1 = 60/4 = 15$, $Q_2 = 60/8 = 7{,}5$, $Q = 22{,}5$, $P = 15$, $\pi_1 = 225$, $\pi_2 = 112{,}5$.
- Bertrand: $P = 0$, $\pi = 0$.

### Q2: Vysvětlete, proč je koluze nestabilní.

**Odpověď:** Když obě firmy drží $Q_i^K = a/(4b)$, každá by si zvýšila zisk porušením dohody:
- Reakční funkce: $Q_1^* = a/(2b) - Q_2/2 = a/(2b) - a/(8b) = 3a/(8b) > a/(4b)$
- Zisk při porušení: $\pi_1^{cheat} = (a - b(3a/(8b) + a/(4b))) \cdot 3a/(8b) = (a - 5a/8) \cdot 3a/(8b) = (3a/8)(3a/(8b)) = 9a^2/(64b)$
- Srovnání: $9a^2/(64b)$ vs. koluzi $a^2/(8b) = 8a^2/(64b)$ → porušení dohody přinese **víc**.

Pokud ale **obě** firmy poruší, skončí v Cournotu s $\pi_i = a^2/(9b) < 9a^2/(64b)$. **Vězňovo dilema.**

### Q3: Stackelberg s asymetrickými $MC$.

Pro $P = 100 - Q$, $MC_1 = 10$ (lider), $MC_2 = 20$ (follower).

**Followerova reakční funkce:** $Q_2 = (80 - Q_1)/2 = 40 - Q_1/2$.

**Liderova úloha:**
$$\pi_1 = (100 - Q_1 - Q_2) Q_1 - 10 Q_1 = (100 - Q_1 - (40 - Q_1/2)) Q_1 - 10 Q_1$$
$$= (60 - Q_1/2) Q_1 - 10 Q_1 = 60 Q_1 - 0{,}5 Q_1^2 - 10 Q_1 = 50 Q_1 - 0{,}5 Q_1^2$$

FOC: $50 - Q_1 = 0 \Rightarrow Q_1 = 50$.
$Q_2 = 40 - 25 = 15$, $Q = 65$, $P = 35$.
$\pi_1 = (35 - 10) \cdot 50 = 1\,250$.
$\pi_2 = (35 - 20) \cdot 15 = 225$.

**Pozorování:** Firma 1 s nižším $MC$ má **mnohem větší podíl** ($Q_1 = 50$ vs. $Q_2 = 15$) i zisk.

---

## Související stránky

- [[mikk|Mikroekonomie 2 (MikK)]] — kurzová stránka
- [[mikk-vzorce-prehled|MikK — Kompletní přehled vzorců]] — sheet vzorců, sekce 10–14 pro oligopol
- [[mikk-vzorove-zkousky|MikK — Vzorové zkoušky]] — řešené úlohy se 4 modely

### Topic stránky

- [[mikk-oligopol-cournot-stackelberg|Cournotův a Stackelbergův oligopol]] — primární topic
- [[mikk-oligopol-bertrand-cenova-konkurence|Bertrandův oligopol]] — cenová konkurence
- [[mikk-oligopol-cenovy-vudce-kartel|Cenový vůdce a kartel]] — koluze
- [[mikk-vezno-dilema-teorie-her|Vězňovo dilema a teorie her]] — stabilita koluze
- [[mikk-oligopol-zalomena-poptavka|Zalomená poptávka]] — Sweezyho model (alternativa)
- [[mikk-monopolisticka-konkurence|Monopolistická konkurence]] — limita pro $n \to \infty$

---

> [!tip] Klíčová pointa
> **Pořadí 4 modelů** podle 4 různých kritérií:
> - **Zisk firem:** koluze > Cournot > Stackelberg > Bertrand
> - **Spotřebitelský přebytek:** Bertrand > Stackelberg > Cournot > koluze
> - **Celkový blahobyt:** Bertrand > Stackelberg > Cournot > koluze
> - **Tržní cena:** koluze > Cournot > Stackelberg > Bertrand
>
> Bertrand je **eficient** (= dokonalá konkurence se 2 firmami), ale realisticky vzácný kvůli diferenciaci a kapacitním omezením. Většina trhů osciluje mezi Cournotem a koluzí, regulátoři brání koluzi (antitrust).
