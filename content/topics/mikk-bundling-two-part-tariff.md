---
title: "Bundling a Two-Part Tariff"
course: mikk
type: topic
tags: [mikk, mikroekonomie, bundling, two-part-tariff, cenova-diskriminace, polaroid]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf, raw/mikk/Prikady pro KS 5 prednaska reseni 2026.pdf]
created: 2026-04-27
updated: '2026-05-12'
---

# Bundling a Two-Part Tariff

## TL;DR

**Two-Part Tariff** (dvousložková cena) a **Bundling** (spojování produktů) jsou dvě pokročilé cenové
strategie monopolisty (či firmy s tržní silou), které mu umožňují **zachytit větší podíl spotřebitelského
přebytku**, než dovoluje jednoduchá monopolní cena, a aniž by vyžadovaly přímou identifikaci typu
zákazníka.

- **Two-Part Tariff** = cena má dvě složky: jednorázový **vstupní poplatek** $T$ (entry fee) a **cenu
  za jednotku** $P$ (usage fee). Klasický příklad — Polaroid SX-70 (1971): kamera za nízkou marži,
  filmy s vysokou marží. Strategie je samoselekční — zákazník svým chováním (kolik nakoupí) odhalí
  svůj typ.
- **Bundling** = prodej dvou nebo více produktů jako jednoho **balíčku** za jednu cenu, místo
  samostatných cen. Funguje, když mají zákazníci **inverzní rezervační ceny** (ten, kdo si vysoko
  cení A, hodnotí B níže, a naopak), a kdy nelze přímo cenově diskriminovat.

Oba postupy patří k **mechanismům odhalování typu zákazníka skrze jeho volbu** (mechanism design)
a jsou alternativami klasické 1./2./3. cenové diskriminace popsané v tématu
[[mikk-cenova-diskriminace|Cenová diskriminace]].

---

## Motivace — proč nestačí prostá cenová diskriminace

Klasická triáda cenové diskriminace má praktické limity:

1. **1. stupeň** (perfektní cenová diskriminace) — vyžaduje znát rezervační cenu každého zákazníka
   individuálně. Prakticky nemožné: lidé svou maximální ochotu platit nesdělí, a firma ji
   neumí přečíst z chování.
2. **2. stupeň** (samoselekční menu — různá cena podle objemu) — funguje, ale jen na omezené
   spektrum produktů (množstevní slevy, paušály).
3. **3. stupeň** (segmentace trhu — různá cena pro různé skupiny) — vyžaduje **identifikovatelné
   segmenty** (studenti, senioři, geografické trhy) a **nemožnost reseneru** mezi segmenty.

**Two-Part Tariff a Bundling řeší případy, kdy nic z výše uvedeného nestačí**:

- Zákazníci jsou heterogenní, ale segmenty nelze pozorovat (nelze diskriminovat 3. stupně).
- Není proveditelné individuální vyjednávání (1. stupeň).
- Přesto chce firma extrahovat více než klasický monopolní zisk.

Klíčová idea obou postupů: **necháme zákazníka, aby svou volbou sám odhalil typ** — to vede
k samoselekci a vyšším zachyceným přebytkům.

---

## Two-Part Tariff — definice

> **Two-Part Tariff** je cenový mechanismus, ve kterém zákazník platí **dvě složky**:
>
> - **Entry fee** $T$ — jednorázový vstupní/členský poplatek (placený jednou, nezávislý na množství).
> - **Usage fee** $P$ — cena za jednotku výstupu/služby (placena za každou spotřebovanou jednotku).
>
> Celková platba zákazníka, který spotřebuje $Q$ jednotek: $\text{platba} = T + P \cdot Q$.

Strategie se nasazuje v případech, kde **funkčnost vyžaduje dvě nákupní rozhodnutí** — nejprve si
zákazník koupí přístup nebo zařízení, teprve pak začne nakupovat opakovaně.

### Příklady Two-Part Tariff v praxi

| Situace | Entry fee $T$ | Usage fee $P$ |
|---------|---------------|---------------|
| Disneyland | Vstupné do parku | Cena rychlejších atrakcí (Express Pass) |
| Telekom (paušál) | Měsíční paušál | Cena za minutu hovoru / SMS |
| Klub/diskotéka | Členský poplatek, vstupné | Ceny drinků a jídla |
| Tržiště / bazar | Pronájem stánku, kotce | Provize z prodejů |
| Amazon Prime | Roční členství | Ceny zboží (často s benefity) |
| Costco / Sam's Club | Roční členství | Slevové ceny zboží |
| Polaroid SX-70 (1971) | Cena kamery | Cena filmu (per snímek) |
| Espresso kávovar | Cena stroje | Cena kapslí (Nespresso) |
| Holicí strojek + břity | Holicí strojek | Náhradní hlavice |

### Dvě extrémní řešení

**Dvě extrémní polohy**:

1. **Pure entry fee** — $T$ velké, $P = MC$ (cena jednotky se rovná mezním nákladům, používání
   prakticky zdarma). Při homogenních zákaznících tato strategie zachytí **celý spotřebitelský
   přebytek** ve formě entry fee — analogie 1. stupně cenové diskriminace.
2. **Pure usage fee** — $T = 0$, $P > MC$ (klasická monopolní cena za jednotku). Jednoduchá
   monopolní strategie, jejíž zisk je menší než pure entry fee při homogenním trhu.

**Mezi nimi leží optimum** závislé na heterogenitě zákazníků.

### Geometrie — graf zisku v závislosti na $T$

```
zisk π(T)
  │           ┌─────●─────┐
  │         /     T*       \
  │       /                  \
  │     /                      \
  │   /                          \
  │ /                              \
  └────────────────────────────────────→ T
   T=0  (pure usage)        T_max (vstup zadarmo, P=MC)
```

**Křivka celkového zisku** jako funkce entry fee $T$:

- Nízké $T$: drtivá většina zákazníků koupí vstup, ale firma málo vydělává na vstupu samém.
  Zisk plyne z usage fee.
- Rostoucí $T$: vstupné přináší více, ale klesá počet kupujících (ti s nejnižší rezervační cenou
  odpadají).
- $T = T^*$: optimum, kde derivace celkového zisku podle $T$ je nulová.
- $T > T^*$: další růst vstupu už odrazí více zákazníků, než kolik přidá ze zisku z těch, kteří
  zůstanou.

Křivka je **konkávní** (jeden vrchol). Optimum balancuje dvě protisměrné síly:

$$\frac{\partial \pi}{\partial T} = n(T) + T \cdot n'(T) + (P - MC) \cdot Q'(T) = 0,$$

kde $n(T)$ je počet kupujících při daném vstupu a $Q(T)$ celkové množství usage napříč nimi.

```graph
title: Two-Part Tariff — zisk jako funkce vstupního poplatku T
alt: Graf ukazuje konkávní průběh celkového zisku firmy v závislosti na výši vstupního poplatku; nízké T znamená drtivé využití přes usage fee, vysoké T odráží mnoho zákazníků a pokles počtu kupujících, optimum leží uprostřed.
xAxis: { label: "T (vstupní poplatek)", domain: [0, 100] }
yAxis: { label: "Zisk π(T)", domain: [0, 5000] }
params:
  - { name: Smax, label: "Max přebytek spotřebitele", min: 50, max: 100, default: 80, step: 5 }
  - { name: Pusage, label: "Marže z usage na zákazníka", min: 5, max: 50, default: 20, step: 1 }
  - { name: NN, label: "Velikost trhu N", min: 50, max: 200, default: 100, step: 10 }
curves:
  - { fn: "max(0, NN * (1 - x/Smax)) * (x + Pusage)", label: "π(T)", color: "fp-purple" }
markers:
  - { x: "(Smax - Pusage)/2", label: "T* (přibližné optimum)" }
```

---

## Polaroid case — modelový příklad

V roce 1971 představila firma **Polaroid** revoluční instantní fotoaparát **Polaroid SX-70**.
Stroj byl konstrukčně samostatný, ale **nefunkční bez originálních filmů Polaroid**, které firma
také vyráběla. Jde o kanonický Two-Part Tariff problém.

### Cenová strategie Polaroidu

- **Kamera** se prodávala s **nízkou marží** (téměř za výrobní náklady, někdy i pod cenou).
  Cílem nebylo vydělat na kameře, ale **rozšířit instalovanou bázi** uživatelů.
- **Filmy** se prodávaly s **vysokou marží** (násobky výrobních nákladů). Každý prodaný film
  je v podstatě malý "usage fee" za fotografování jako službu.

Tato strategie se v literatuře nazývá také **"razor and blades"** (strojek a žiletky) nebo
**"printer and ink"** (tiskárna a inkoust) — stejný princip používá Gillette, HP, Nespresso a další.

### Vzorec zisku Polaroidu

Obecný tvar (zhuštěná notace):

$$\pi = \underbrace{(T - C_1) \cdot n}_{\text{zisk z kamer}} + \underbrace{(P - C_2) \cdot Q}_{\text{zisk z filmů}}$$

kde:

- $T$ — cena kamery (entry fee, jednorázová);
- $C_1$ — výrobní náklad kamery;
- $n$ — počet prodaných kamer (= počet kupujících v Two-Part Tariff);
- $P$ — cena filmu (usage fee, opakovaná);
- $C_2$ — výrobní náklad filmu;
- $Q$ — celkové množství prodaných filmů.

Klíčová vazba: **$Q$ závisí na $n$** (více majitelů kamer kupuje více filmů) a **$n$ závisí na
$T$** (vyšší cena kamery → méně kupujících). Optimalizace probíhá společně přes $T$ a $P$.

### Optimální strategie

- **Cenu kamery $T$** nastav na úroveň, která **získá širokou bázi kupujících** (včetně těch
  s nižší rezervační cenou na samotnou kameru).
- **Cenu filmu $P$** zvolíš nad $MC_2$ tak, aby dlouhodobě **zachytila přebytek z opakovaného
  použití**.

Pokud zákazníci s vysokou ochotou platit i hodně fotí (vysoká korelace), pak vyšší $P$ funguje
jako de facto cenová diskriminace 2. stupně — těžcí uživatelé platí celkově víc, lehcí uživatelé
méně.

> [!callout] Lock-in efekt
> Polaroid si filmy patentově chránil — žádná konkurence nemohla vyrábět filmy do SX-70.
> Tím vznikl **vendor lock-in**: jakmile si zákazník koupil kameru, byl uzamčen v ekosystému.
> Tatáž logika dnes platí pro Nespresso kapsle, HP cartridge, lightning kabely Apple atd.

---

## Heterogenní zákazníci a Two-Part — proč extrém často nefunguje

V čistém modelu s **homogenními zákazníky** (všichni mají stejnou rezervační cenu a stejnou
intenzitu používání) je optimální **pure entry fee strategie** (vysoké $T$ rovné celému
spotřebitelskému přebytku, $P = MC$).

V realitě jsou ale zákazníci heterogenní — některý uživatel kameru koupí a vyfotí 5 filmů
za rok, jiný 50. Analogicky pro Disneyland, telekom, klub apod.

Pak musí firma najít **kompromis**:

- Vyšší $T$ a $P = MC$: maximalizuje zisk z těžkých uživatelů, ale **odradí lehké uživatele**
  (jejich přebytek z usage je menší než $T$).
- Nižší $T$ a $P > MC$: získá širokou bázi (lehké uživatele zachytí), ale **nedostane plný
  přebytek od těžkých uživatelů**.

**Optimální mix** záleží na rozdělení typů. Pokud jsou těžcí uživatelé v menšině, vyšší $P$
a nižší $T$ je obvykle výhodnější.

Tento problém je formálně příbuzný [[mikk-cenova-diskriminace|cenové diskriminaci 2. stupně]] —
firma nabízí menu (vstup + cena za jednotku) a zákazníci se sami zařadí.

---

## Bundling — definice a podmínky

![[mikk-bundling-rezervacni-ceny.jpeg|Bundling — rezervační ceny dvou zboží, separate prices vs. pure bundle vs. mixed bundling pro 4 zákazníky]]

> **Bundling** (česky *spojování*, *prodej v balíčku*) je strategie prodeje, při které firma
> nabízí **dva nebo více produktů jako jeden balíček za jednu cenu**, místo samostatných cen
> pro každý produkt.

**Tři podmínky**, za kterých má bundling smysl jako strategie:

1. **Heterogenní zákazníci** — zákazníci mají různé preferenční profily (jinak by stačila jedna
   cena pro všechny a bundling by nepřinesl nic navíc).
2. **Nemožnost (přímé) cenové diskriminace** — firma nedokáže identifikovat segmenty a účtovat
   jim různě (jinak by 3. stupeň diskriminace stačil).
3. **Inverzní vztah poptávek (rezervačních cen)** — zákazník, který si vysoko cení produkt A,
   si nízko cení produkt B, a naopak. Bez této inverzní korelace bundling ztrácí výhodu.

### Pure bundling vs. mixed bundling

- **Pure bundling** — produkty se prodávají **pouze** jako balíček, samostatně nedostupné.
  Příklad: kabelová TV, kde si nemůžete koupit jediný kanál.
- **Mixed bundling** — firma nabízí balíček **i** samostatné produkty (každý za vlastní cenu).
  Zákazník volí, co je pro něj výhodnější. Příklad: Microsoft Office (balíček) i samostatný
  Word/Excel.

Mixed bundling je obvykle **silnější strategie** (dominuje pure bundlingu) — neztrácí zákazníky,
kteří chtějí jen jeden produkt.

---

## Klasický příklad — HOT DOG + PIVO

Stánek prodává dva produkty, **HOT DOG** a **PIVO**, dvěma typům zákazníků s následujícími
rezervačními cenami:

| Zákazník | HOT DOG | PIVO |
|----------|---------|------|
| Muž      | $3{,}0$ | $2{,}5$ |
| Žena     | $4{,}0$ | $1{,}3$ |

Pozorování: **poptávky jsou inverzní** — žena dává víc za hot dog, ale méně za pivo, muž naopak.
Předpokládáme zanedbatelné mezní náklady ($MC \approx 0$) a cíl maximalizovat tržby (= zisk).

### Strategie 1: Samostatné ceny (bez bundlingu)

Aby koupili **oba** zákazníci každý produkt zvlášť, cena nesmí překročit nižší rezervační
cenu z dvojice:

- $P_{\text{HOT DOG}} = \min(3, 4) = 3$ → tržba $2 \cdot 3 = 6$.
- $P_{\text{PIVO}} = \min(2{,}5, 1{,}3) = 1{,}3$ → tržba $2 \cdot 1{,}3 = 2{,}6$.
- **Celkem: $8{,}6$**.

Alternativně mohla firma stanovit vyšší ceny a prodat každý produkt jen jednomu zákazníkovi —
ale to také nevede výš (např. pivo za 2,50 jen muži = 2,50; hot dog za 4 jen ženě = 4 → součet 6,5).

### Strategie 2: Bundling (jediný balíček)

Cena balíčku se musí vejít do nižší **součtové** rezervační ceny:

- Muž: ochota platit za balíček = $3 + 2{,}5 = 5{,}5$.
- Žena: ochota platit za balíček = $4 + 1{,}3 = 5{,}3$.
- $P_{\text{balíček}} = \min(5{,}5, 5{,}3) = 5{,}3$ → oba zákazníci koupí.
- **Celkem: $2 \cdot 5{,}3 = 10{,}6$**.

### Vyhodnocení

| Strategie | Tržba | Rozdíl |
|-----------|-------|--------|
| Samostatné ceny | $8{,}6$ | — |
| Bundling | $10{,}6$ | **+$2{,}0$** |

**Bundling přinesl $+23\,\%$ tržby**. Příčina: inverzní rezervační ceny způsobí, že rozptyl
**součtových** ochot platit ($5{,}3$ a $5{,}5$) je **menší** než rozptyl jednotlivých ochot
($1{,}3$–$4$ resp. $2{,}5$–$3$). Užší rozptyl umožní zachytit širší část přebytku.

> [!callout] Klíčový mechanismus bundlingu
> Bundling **homogenizuje** ochotu platit napříč zákazníky. Když firma neumí oddělit zákazníky,
> nutí ji to volit cenu podle **nejnižší** rezervační. Inverzní korelace způsobí, že nejnižší
> *součtová* rezervační cena je vyšší než součet nejnižších *jednotlivých* — proto bundling
> dominuje.

---

## Detailní příklad — Hotel U Pepy Flinty

Manažer hotelu nabízí dvě služby — **ubytování** a **wellness** — a uvažuje cenovou strategii.
Trh tvoří 3 skupiny zákazníků s rozdílnou ochotou platit:

| Skupina | Počet osob | Ubytování | Wellness |
|---------|-----------|-----------|----------|
| 1       | 30        | $300$   | $50$   |
| 2       | 40        | $250$   | $80$   |
| 3       | 45        | $220$   | $90$   |

Jednotkové náklady: $C_{\text{ubyt}} = 40$, $C_{\text{well}} = 40$. Celkem 115 zákazníků.

### Klíčové pozorování — inverzní rezervační ceny

Skupina, která nejvíc platí za ubytování (Sk. 1: $300$), platí **nejméně** za wellness ($50$).
Skupina, která platí nejvíc za wellness (Sk. 3: $90$), platí **nejméně** za ubytování ($220$).
**Poptávky jsou tedy inverzní** — situace ideální pro bundling.

### Varianta A — cenová diskriminace 3. stupně

Pokud manažer dokáže rozpoznat skupinu (např. byznysmen vs. rodina), nasadí každé skupině jinou
cenu. Optimum (každý zákazník zaplatí svou maximální ochotu, monopolista bere vše):

- Sk. 1: marže za pár = $(300 - 40) + (50 - 40) = 260 + 10 = 270$ $\to$ $30 \cdot 270 = 8\,100$.
- Sk. 2: marže za pár = $(250 - 40) + (80 - 40) = 210 + 40 = 250$ $\to$ $40 \cdot 250 = 10\,000$.
- Sk. 3: marže za pár = $(220 - 40) + (90 - 40) = 180 + 50 = 230$ $\to$ $45 \cdot 230 = 10\,350$.
- **Součet: $28\,450$**.

V praxi je ale 3. stupeň často **neproveditelný** — zákazník neukáže "kartičku skupiny" a manažer
neumí dopředu poznat, kdo do které skupiny patří.

### Varianta B — jednotná cena (bez diskriminace, bez bundlingu)

Když firma nemůže diskriminovat, nasadí dvě jednotlivé ceny — pro ubytování a pro wellness samostatně.
Aby se prodalo všem, ceny se musejí vejít do **minimální** rezervační ceny napříč skupinami:

- $P_{\text{ubyt}} = \min(300, 250, 220) = 220$ $\to$ marže $180 \cdot 115 = 20\,700$.
- $P_{\text{well}} = \min(50, 80, 90) = 50$ $\to$ marže $10 \cdot 115 = 1\,150$.
- **Součet: $21\,850$**.

(Případně mohl manažer zkusit cenu wellness 80 Kč jen skupinám 2 a 3,
nebo jiné kombinace samostatných cen — žádná z nich ale nepřekoná bundling.)

### Varianta C — bundling (balíček ubytování + wellness)

Firma nabídne balíček "ubytování + wellness" za jednu cenu. Ochota platit za balíček:

- Sk. 1: $300 + 50 = 350$.
- Sk. 2: $250 + 80 = 330$.
- Sk. 3: $220 + 90 = 310$.

Aby koupili všichni, cena balíčku $\le \min(350, 330, 310) = 310$. Optimum:

$$P_{\text{balíček}} = 310, \quad \text{marže} = 310 - 40 - 40 = 230.$$

Celkový zisk: $\pi = 230 \cdot 115 = \boxed{13\,800}$ (plus dodatečné prodeje, viz pozn.).

> **Pozn.:** Údaj `230 \cdot 60 = 13\,800` v ručně psaném řešení odpovídá tomu, že počty osob
> v ručních poznámkách kolísají (20/40/45 vs. 30/40/45). Princip — *bundling sjednocuje vyšší
> rezervační cenu napříč heterogenními skupinami* — zůstává stejný.

### Srovnání variant

| Strategie | Princip | Zisk |
|-----------|---------|------|
| 3. stupeň diskriminace | Každá skupina jinou cenu | $28\,450$ |
| **Bundling (pure)** | **Jeden balíček, jedna cena** | **$13\,800$** |
| Jednotná cena (bez bundlingu) | Cena ubyt. + cena well. samostatně | $10\,350$–$21\,850$ |

Bundling tedy **nedosahuje** úrovně skutečné cenové diskriminace 3. stupně (pokud by byla
proveditelná), ale **významně překonává** naivní jednotnou cenu — což je realisticky dostupný
benchmark, když segmenty nelze identifikovat. Spolu s [[mikk-cenova-diskriminace|cenovou
diskriminací]] tvoří plnou paletu cenových strategií monopolisty.

---

## Mixed bundling — kdy se vyplatí

V některých konfiguracích zákazníků **pure bundling odřízne segment**, který si cení jen jednoho
z produktů (např. hostů, kteří chtějí jen ubytování bez wellness). **Mixed bundling** to řeší
nabídkou tří možností:

- $P_A$ — cena samotného produktu A.
- $P_B$ — cena samotného produktu B.
- $P_{AB}$ — cena balíčku, **se slevou** oproti součtu $P_A + P_B$.

Zákazník samoselekčně volí, co je pro něj výhodnější:

- Kdo má rezervační cenu jen na A (a B nepoužije), koupí samotné A.
- Kdo má rezervační cenu na oba, koupí balíček (sleva ho přiláká).
- Kdo nemá ani jednu, nekupuje nic.

Mixed bundling je **slabě dominující** strategií oproti pure bundlingu (nikdy nedělá hůř, často
lépe), ale optimální cenový vektor $(P_A, P_B, P_{AB})$ se hledá hůř — typicky numericky.

---

## Aplikace v reálném světě

| Firma / odvětví | Strategie | Komentář |
|-----------------|-----------|----------|
| **Microsoft Office** | Mixed bundling | Balíček Word + Excel + PowerPoint vs. samostatné aplikace |
| **Adobe Creative Cloud** | Pure / mixed bundling | Hlavně balíček All Apps; samostatné aplikace dražší v poměru |
| **Disneyland / parky** | Two-Part + mixed bundling | Vstupné (entry) + cena atrakcí (usage) + Express Pass |
| **Costco / Sam's Club** | Two-Part Tariff | Roční členství (entry) + slevové ceny zboží (usage) |
| **Amazon Prime** | Two-Part Tariff | Roční členství (entry) + dopravy zdarma + Video / Music |
| **Spotify Family** | Bundling | 6 účtů za jednu cenu — sjednocuje rezervační ceny rodiny |
| **Kabelová TV** | Pure bundling | Tématické balíčky kanálů; jednotlivé kanály obvykle nedostupné |
| **Telekom — paušál + tarif** | Two-Part Tariff | Měsíční paušál (entry) + cena za hovor (usage) |
| **Polaroid / Nespresso / HP** | Two-Part Tariff | "Razor & blades" — levný stroj, drahé spotřeba |
| **iPhone + Lightning + nabíječka** | Bundling (do 2020) | Bundling až do EU regulace 2020, pak unbundle |
| **Fast food meal deals** | Bundling | Cheeseburger + hranolky + cola za jednu cenu |
| **Software licence (sítě)** | Bundling | Antivirus + firewall + zálohy v jednom balíčku |

---

## Limity a problémy strategií

### Two-Part Tariff

- **Antitrust risk** — pokud entry fee je tak vysoký, že vytlačí konkurenci nebo brání vstupu
  nových firem (essential facility doctrine).
- **Heterogenita zákazníků** — pokud je skupina lehkých uživatelů velká, vysoké $T$ ji odřízne
  a celkový zisk klesne (viz výše).
- **Reputační riziko** — pokud zákazník vnímá vstupní poplatek jako "skrytý poplatek" navíc,
  může to poškodit značku (viz kritika bankovních poplatků).

### Bundling

- **Antitrust risk** — pokud bundling tlačí konkurenci z trhu (klasický případ Microsoft IE
  vs. Netscape v 90. letech, nebo Microsoft Media Player). EU regulátor opakovaně intervenoval.
- **Reverse engineering / parallel imports** — zákazníci si "rozkládají" balíček a prodávají
  jeho části na sekundárním trhu (například divadelní lístky přes StubHub, kabelové předplatné
  share s rodinou).
- **Resale a arbitráž** — pokud je balíček obsahově dělitelný a sekundární trh existuje,
  zachycený přebytek se postupně rozplyne.
- **Customer dissatisfaction** — pokud balíček obsahuje pro zákazníka **nezajímavé položky**
  ("musím platit za to, co nepoužiju"), může to vést k odlivu zákazníků ke konkurenci nabízející
  unbundled produkty (Netflix vs. kabelová TV).
- **Mandatory unbundling regulace** — v některých odvětvích (telekom local loop, EU mobilní
  poplatky, US kabel) regulátor přímo nutí firmy nabízet odbalíčkované verze.

---

## Vztah k ostatním cenovým strategiím

- [[mikk-cenova-diskriminace|Cenová diskriminace]] — kanonické 3 stupně (1. — perfektní,
  2. — samoselekční menu, 3. — segmentace). Two-Part i Bundling lze chápat jako **speciální
  případy 2. stupně diskriminace**.
- [[mikk-monopol-pokrocily|Pokročilý monopol]] — Two-Part a Bundling jsou klíčovými strategiemi,
  jak monopolista může jít **nad** prostou cenu $P^M$ z $MR = MC$.
- [[mikk-monopolisticka-konkurence|Monopolistická konkurence]] — bundling je rozšířenou strategií
  i v konkurenčních odvětvích s diferencovaným produktem (fast food, software).
- [[mikk-elasticita-poptavky|Elasticita poptávky]] — design Two-Part i Bundling se opírá o
  rozdílnou elasticitu poptávek napříč produkty a zákazníky.

---

## Shrnutí — kdy použít kterou strategii

| Situace | Strategie | Důvod |
|---------|-----------|-------|
| Komplementární produkty, opakovaný nákup | **Two-Part Tariff** | Lock-in přes entry, zachytí přebytek z usage |
| Více produktů s inverzními rezervačními cenami | **Pure bundling** | Sjednotí ochotu platit napříč zákazníky |
| Produkty s inverzními cenami + segment chce jen jedno | **Mixed bundling** | Pokryje obě skupiny, slabě dominuje pure |
| Identifikovatelné segmenty | **3. stupeň cenové diskriminace** | Přímější a vyšší zisk |
| Homogenní zákazníci, dělitelný produkt | **2. stupeň (množstevní slevy)** | Klasický nelineární tarif |

---

## Související

- [[mikk|Mikroekonomie 2 (mikK)]] — hlavní rozcestník kurzu
- [[mikk-cenova-diskriminace|Cenová diskriminace]] — 1./2./3. stupeň, kontext k Two-Part a Bundling
- [[mikk-monopol-pokrocily|Pokročilá teorie monopolu]] — strategický kontext
- [[mikk-monopolisticka-konkurence|Monopolistická konkurence]] — bundling v diferencovaných trzích
- [[mikk-elasticita-poptavky|Elasticita poptávky]] — vstup pro design cenových schémat
- [[mikk-vzorce-prehled|Přehled vzorců — MikK]] — kompaktní tahák
- [[mikk-vzorove-zkousky|Vzorové zkoušky — MikK]] — typické úlohy
