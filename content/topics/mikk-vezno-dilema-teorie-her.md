---
title: "Vězňovo dilema, Nashova rovnováha a teorie her"
course: mikk
type: topic
tags: [mikk, mikroekonomie, teorie-her, nash, vezno-dilema, koluze, oligopol]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf, raw/mikk/mikro-FINAL-2-1.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Vězňovo dilema, Nashova rovnováha a teorie her

## TL;DR

**Teorie her** je matematická disciplína studující strategickou interakci mezi racionálními hráči, kteří si uvědomují, že jejich výplata závisí nejen na jejich vlastní volbě, ale i na volbě protihráčů. V mikroekonomii je nepostradatelná pro analýzu **oligopolu**, **koluze**, **aukcí**, **vyjednávání** a obecně všech tržních situací s malým počtem aktérů.

**Nashova rovnováha** je centrální koncept: profil strategií, ze kterého žádný hráč nemá motivaci se jednostranně odchýlit. Je to strategická "stabilita" — pokud znám volbu ostatních, moje volba je nejlepší možná.

**Vězňovo dilema** je nejslavnější hra v ekonomii. Demonstruje, že **individuálně racionální chování může vést ke kolektivně suboptimálnímu výsledku**. Dva hráči hrající sami za sebe skončí v rovnováze (přiznat, přiznat), přestože by oba lépe vyšli při (nepřiznat, nepřiznat). Tento paradox vysvětluje, proč je **koluze v oligopolu nestabilní** — každá firma má motiv tajně podříznout cenu konkurenta.

**Iterované hraní** s dostatečně dlouhým horizontem situaci mění. Strategie typu **tit-for-tat** (oko za oko) umožňuje udržet kooperativní rovnováhu, protože hrozba odvety odrazuje od podrazu. **Folkův teorém** říká, že v opakovaných hrách s nízkou diskontní sazbou existuje kontinuum rovnovah včetně koluzní.

> [!info] Souvislost s [[mikk|Mikroekonomií 2]]
> Teorie her je teoretický rámec pro modely [[mikk-oligopol-cournot-stackelberg|Cournot a Stackelberg]] (množstevní hry), [[mikk-oligopol-bertrand-cenova-konkurence|Bertrand]] (cenová hra) i [[mikk-oligopol-cenovy-vudce-kartel|kartel]] (koluzní řešení). Každý oligopolní model je jen specifická hra s konkrétními pravidly.

---

## Nashova rovnováha — formální definice

**John Forbes Nash Jr.** (1928–2015) — americký matematik, doktorská práce z roku 1950 (28 stran), Nobelova cena za ekonomii 1994 spolu s Reinhardem Seltenem a Johnem Harsanyim. Jeho příběh popularizoval film *A Beautiful Mind* (2001, hlavní role Russell Crowe).

### Formální zápis

Mějme hru s $n$ hráči, kde hráč $i$ má strategickou množinu $S_i$ a výplatní funkci $u_i: S_1 \times S_2 \times \ldots \times S_n \to \mathbb{R}$.

Profil strategií $(s_1^*, s_2^*, \ldots, s_n^*)$ je **Nashova rovnováha**, jestliže pro každého hráče $i$ a pro každou jeho alternativní strategii $s_i \in S_i$ platí:

$$u_i(s_i^*, s_{-i}^*) \ge u_i(s_i, s_{-i}^*)$$

Kde $s_{-i}^*$ je profil rovnovážných strategií všech hráčů kromě $i$.

### Slovní interpretace

> [!definition] Nashova rovnováha
> Profil strategií, ve kterém **žádný hráč nemůže zlepšit svoji výplatu jednostranným odchýlením** za předpokladu, že ostatní hráči zůstávají u svých rovnovážných strategií.

Klíčové slovo je **jednostranný**. Nashova rovnováha negarantuje, že kolektivní odchylka by nebyla výhodnější — to je přesně podstata vězňova dilematu (viz níže).

### Nashův teorém o existenci

> [!theorem] Nashův existenční teorem (1950)
> Každá konečná hra (konečný počet hráčů, konečné strategické množiny) má alespoň jednu Nashovu rovnováhu — případně **smíšenou** (v pravděpodobnostech nad čistými strategiemi).

---

## Hra a její komponenty

Formální popis hry vyžaduje tři složky:

1. **Hráči** $N = \{1, 2, \ldots, n\}$ — kdo hraje? Mohou to být firmy, jednotlivci, státy, biologické druhy.
2. **Strategie** $S_i$ — co může hráč udělat? Diskrétní (přiznat/nepřiznat) nebo spojité (kvantitum produkce $Q_i \ge 0$).
3. **Výplaty** $u_i: S_1 \times \ldots \times S_n \to \mathbb{R}$ — jaký výsledek získá hráč v daném profilu strategií?

V některých hrách se přidává:

- **Pořadí tahů** (sekvenční vs. simultánní)
- **Informační struktura** (kdo co ví v okamžiku rozhodnutí)
- **Časový horizont** (jednorázová vs. opakovaná hra)

---

## Klasifikace her

### Kooperativní vs. nekooperativní

- **Kooperativní hra**: hráči mohou uzavírat **závazné dohody** (binding agreements), často vynucované třetí stranou (smlouvy, soudy).
- **Nekooperativní hra**: každý hráč hraje sám za sebe, žádné závazné dohody. Většina mikroekonomických aplikací (oligopol, aukce) spadá sem.

### Simultánní vs. sekvenční

- **Simultánní (statická) hra**: všichni hráči volí současně, neznají volbu ostatních. Reprezentace **strategickou (normální) formou** — výplatní matice. Příklad: Cournot, Bertrand, vězňovo dilema.
- **Sekvenční (dynamická) hra**: hráči se rozhodují postupně, pozdější hráči vidí volby dřívějších. Reprezentace **rozšířenou (extenzivní) formou** — strom hry. Příklad: Stackelberg, šachy.

### Úplná vs. neúplná informace

- **Úplná informace**: všichni hráči znají strukturu hry (hráče, strategie, výplaty).
- **Neúplná informace**: někteří hráči neznají typy ostatních. Bayesovské hry — výplaty závisí na neznámých "typech".

### Konečné vs. nekonečné opakování

- **Jednorázová hra (one-shot)**: hraje se jen jednou. Klíčový případ: vězňovo dilema → defekce.
- **Konečně opakovaná**: hraje se $T$-krát. *Backward induction* dává v základních hrách stejný výsledek jako jednorázová.
- **Nekonečně opakovaná** (nebo s neznámým koncem): otevírá prostor pro **kooperaci** přes hrozbu trestu.

---

## Vězňovo dilema — scénář

![[mikk-vezno-dilema-matice.jpeg|Vězňovo dilema — 2×2 payoff matice s dominantní strategií 'zradit' a Nashovou rovnováhou (zradit, zradit)]]

> [!example] Klasický scénář (Tucker, 1950)
> Dva podezřelí (A a B) jsou zatčeni za zločin, na který nemá policie přesvědčivé důkazy. Drží je v **oddělených celách** — nemohou spolu komunikovat. Každému zvlášť policie nabídne stejnou dohodu:
>
> - Pokud přiznáš a tvůj komplic ne, jsi propuštěn s podmínkou (-1 rok), on dostane 10 let.
> - Pokud nepřiznáš a komplic přizná, dostaneš 10 let, on jde s podmínkou (-1).
> - Pokud oba přiznáte, dostanete shodně po 5 letech.
> - Pokud nepřizná ani jeden z vás, dostanete oba po 2 letech (jen za drobnější přečin).

### Výplatní matice

Výplaty zapisujeme jako záporné hodnoty (počet let vězení se znaménkem mínus, protože vyšší = horší):

|              | **B přizná** | **B nepřizná** |
|--------------|:------------:|:--------------:|
| **A přizná** | (-5, -5)     | (-1, -10)      |
| **A nepřizná** | (-10, -1)  | (-2, -2)       |

První číslo = výplata hráče A, druhé = výplata hráče B.

---

## Analýza vězňova dilematu

### Pohled hráče A

Hráč A neví, co volí B. Uvažuje obě varianty:

- **Pokud B přizná**: A dostane buď −5 (přizná) nebo −10 (nepřizná). **Lepší je přiznat** (−5 > −10).
- **Pokud B nepřizná**: A dostane buď −1 (přizná) nebo −2 (nepřizná). **Lepší je přiznat** (−1 > −2).

> [!important] Dominantní strategie
> Strategie "**přiznat**" je pro A **lepší ve všech scénářích**. Říkáme, že je **striktně dominantní** — nezáleží na tom, co dělá B, A je vždy lépe, když přizná.

```graph
title: Vyplatní struktura VD jako funkce odměny za kooperaci
alt: Výplaty hráče A ve čtyřech profilech vězňova dilematu (oba kooperují, A kooperuje a B zradí, A zradí a B kooperuje, oba zradí) jako funkce odměny R za kooperaci; struktura zůstává VD, dokud R leží mezi T a P.
xAxis: { label: "R (odměna za kooperaci)", domain: [-15, 5] }
yAxis: { label: "výplata hráče A", domain: [-15, 5] }
params:
  - { name: T, label: "T - zrada proti kooperátorovi", min: -5, max: 0, default: -1, step: 0.5 }
  - { name: PP, label: "P - oba zradí (punishment)", min: -10, max: 0, default: -5, step: 0.5 }
  - { name: S, label: "S - oklamaný kooperátor (sucker)", min: -15, max: -5, default: -10, step: 0.5 }
curves:
  - { fn: "x + 0*T", label: "u_A(CC) = R", color: "fp-purple" }
  - { fn: "T + 0*x", label: "u_A(DC) = T", color: "fp-red" }
  - { fn: "PP + 0*x", label: "u_A(DD) = P", color: "paper-700" }
  - { fn: "S + 0*x", label: "u_A(CD) = S", color: "ink" }
markers:
  - { x: "PP", label: "kde R = P (struktura prestava byt VD)" }
  - { x: "T", label: "kde R = T (zadna strategie nedominuje)" }
```

Symetricky pro hráče B: jeho dominantní strategie je také "přiznat".

### Nashova rovnováha

Profil **(přiznat, přiznat)** s výplatou **(−5, −5)** je jediná Nashova rovnováha. Žádný hráč nemůže jednostranně přejít k "nepřiznat" a zlepšit si situaci (přechod by jeho výplatu zhoršil z −5 na −10).

### Paradox

Profil **(nepřiznat, nepřiznat)** dává **(−2, −2)**, což je pro oba hráče **lepší** než rovnováha (−5, −5). Tento profil je **Pareto-efektivní**, ale **není rovnovážný** — oba hráči mají individuální motiv přejít k "přiznat".

> [!warning] Klíčový vhled vězňova dilematu
> **Individuální racionalita ≠ kolektivní racionalita.** Každý hráč jedná optimálně z hlediska své vlastní výplaty, ale výsledek je pro oba horší, než kdyby spolupracovali.

To je hlavní důvod, proč ekonomie potřebuje regulaci, smlouvy, instituce a opakované interakce — všechny tyto mechanismy se snaží **transformovat dilema** tak, aby kooperativní výsledek byl rovnovážný.

---

## Vězňovo dilema v oligopolu

Stejnou logiku lze aplikovat na **dvě firmy v oligopolu**, které se rozhodují mezi vysokou (koluzní) a nízkou (konkurenční) cenou.

### Výplatní matice (zisky v mil. Kč)

|                    | **F2 koluze** | **F2 konkurence** |
|--------------------|:-------------:|:-----------------:|
| **F1 koluze**      | (50, 50)      | (20, 60)          |
| **F1 konkurence**  | (60, 20)      | (30, 30)          |

### Interpretace

- **Oba kolují** (drží vysokou cenu): trh sdílen, každá firma má 50.
- **F1 koluze, F2 konkuruje**: F2 podřezává cenu, "uloví" zákazníky → F2 má 60, F1 jen 20.
- **F1 konkuruje, F2 koluze**: zrcadlově.
- **Oba konkurují**: cenová válka stlačí ceny, oba mají jen 30.

### Analýza

Pro F1:

- **F2 koluze** → F1 volí konkurence (60 > 50).
- **F2 konkurence** → F1 volí konkurence (30 > 20).

**Konkurence je dominantní strategie.** Symetricky pro F2.

> [!important] Nashova rovnováha v oligopolu
> **(konkurence, konkurence)** s výplatou **(30, 30)**. **Koluze** je sice Pareto-lepší (50, 50), ale **není rovnovážná** — každá firma má motiv tajně cenu snížit.

### Důsledky pro chování oligopolistů

1. **Koluze** (kartel) je atraktivní z hlediska společných zisků.
2. **Není stabilní** v jednorázové interakci — silný motiv k podrazu.
3. **Vyžaduje vynucování** (kartelové dohody, monitorovací mechanismy).
4. **V mnoha jurisdikcích nelegální** (ÚOHS v ČR, EU competition law, FTC v USA).
5. **Tichá koluze** (parallel pricing bez explicitní dohody) je obtížně postižitelná, ale taky nestabilní.

Detailněji v [[mikk-oligopol-cenovy-vudce-kartel|Cenový vůdce a kartel]].

---

## Iterované vězňovo dilema

Pokud se hra opakuje **mnohokrát** (ideálně nekonečně, nebo s neznámým koncem), motivační struktura se mění. **Hrozba budoucího potrestání** může učinit kooperaci stabilní.

### Tit-for-tat strategie

Anatol Rapoport zaslal tuto strategii do Axelrodova počítačového turnaje (1980). Pravidla:

1. **První kolo**: kooperuj.
2. **Další kola**: hraj přesně to, co protihráč hrál v minulém kole.

> [!success] Vlastnosti tit-for-tat (Axelrod 1981, *Evolution of Cooperation*)
> - **Mírná** (nice): nikdy nezačne defektovat jako první.
> - **Jasná** (clear): protihráč snadno dekóduje strategii.
> - **Odpouštějící** (forgiving): po jednom kole defekce se vrací ke kooperaci.
> - **Neprovokující** (non-provocable): ale když ji někdo zkusí podrazit, hned to vrátí.
>
> V Axelrodově turnaji vyhrála jak první, tak druhý ročník — i přes přítomnost mnohem komplexnějších strategií.

### Folkův teorém (Folk theorem)

> [!theorem] Folkův teorém (informálně)
> V nekonečně opakované hře s **dostatečně vysokou diskontní sazbou** $\delta$ (tj. dostatečně malou netrpělivostí) **lze jako Nashovu rovnováhu podpořit jakoukoli individuálně racionální výplatu** — včetně koluzní (50, 50).

Diskontní faktor $\delta$ vyjadřuje, jak moc hráči záleží na budoucích výplatách. Pokud je $\delta$ vysoké:

- Krátkodobý zisk z podrazu (60 místo 50) **nepřeváží** nad ztrátou všech budoucích koluzních zisků (každé další kolo jen 30 místo 50).
- Existuje **kritická hodnota** $\delta^*$, nad kterou je koluze udržitelná.

```graph
title: Kritický diskontní faktor pro tit-for-tat
alt: Lineární funkce gain z kooperace v opakované hře jako funkce diskontního faktoru delta; kde funkce protíná osu (delta-star) je kritický práh, nad kterým folkův teorém umožňuje koluzi.
xAxis: { label: "diskontní faktor", domain: [0, 1] }
yAxis: { label: "scaled gain z kooperace", domain: [-100, 100] }
params:
  - { name: R, label: "R (zisk při koluzi)", min: 0, max: 100, default: 50, step: 5 }
  - { name: T, label: "T (zisk z podrazu)", min: 0, max: 100, default: 60, step: 5 }
  - { name: PP, label: "P (Nash punishment)", min: 0, max: 100, default: 30, step: 5 }
curves:
  - { fn: "R - T + x*(T - PP)", label: "scaled gain (R-T) + delta*(T-P)", color: "fp-purple" }
  - { fn: "0 + 0*x", label: "nulová úroveň", color: "paper-500" }
markers:
  - { x: "(T - R)/(T - PP)", label: "delta* (kritický práh)" }
```

### Praktická implikace

Reálné firmy v oligopolu **interagují opakovaně, dlouhodobě, na malém trhu**. Folkův teorém pomáhá vysvětlit, proč v praxi vidíme **stabilní koluzní ceny** (telekomy, banky, paliva) i bez formálních kartelů — stačí **trust** a **threat of retaliation**.

---

## Sekvenční hry — extenzivní forma

Sekvenční hra se kreslí jako **rozhodovací strom**:

- **Uzly** = body rozhodnutí (kdo hraje).
- **Hrany** = volby strategií.
- **Listy** = koncové stavy s výplatami pro všechny hráče.

### Backward induction

Algoritmus řešení sekvenční hry:

1. Najdi **listy** stromu.
2. V posledním rozhodovacím uzlu vyber pro daného hráče **optimální tah** podle jeho výplatní funkce.
3. Tento výběr "zvedne" výplatu listu nahoru do předchozího uzlu.
4. Postupuj směrem ke kořeni, vždy řeš nejnižší ještě nevyřešený uzel.

### Subgame perfect equilibrium (SPE)

> [!definition] Dokonalá rovnováha v subgame
> Profil strategií, který tvoří **Nashovu rovnováhu v každém podsekvenčním podgame** (subgame). SPE je **silnější koncept** než Nash — vylučuje rovnováhy s **neuvěřitelnými hrozbami** (incredible threats).

Selten zavedl SPE 1965 a obdržel za něj Nobelovu cenu 1994 (společně s Nashem).

---

## Stackelbergova hra jako sekvenční

Klasická aplikace v oligopolu — viz [[mikk-oligopol-cournot-stackelberg|Cournot a Stackelberg]].

- **Lider (F1)** volí $Q_1$ jako první.
- **Follower (F2)** pozoruje $Q_1$ a volí $Q_2$ jako optimální reakci.
- Lider při volbě $Q_1$ **anticipuje** followerovo chování (zná followerovu reakční křivku).
- **SPE řešení** $\Rightarrow$ lider má vyšší zisk než ve Cournotu.

Stackelberg je jen specifický případ obecnější třídy **commitment games** — situací, kde **schopnost se předem zavázat** vytváří strategickou výhodu (first-mover advantage).

---

## Hra typu "nukleární útok" (MAD)

Studená válka jako gigantická aplikace teorie her. **Mutually Assured Destruction (MAD)** — vzájemně zaručené zničení.

### Scénář

Dvě supervelmoci (USA, SSSR) mají jaderný arzenál. Každá volí: **zaútočit / nezaútočit**.

|                  | **B nezaútočí**           | **B zaútočí**             |
|------------------|:-------------------------:|:-------------------------:|
| **A nezaútočí**  | (status quo, status quo)  | (smrt A, vítězství B)     |
| **A zaútočí**    | (vítězství A, smrt B)     | (smrt obou, smrt obou)    |

### Analýza

Na první pohled vypadá hra jako vězňovo dilema — dominantní strategie zaútočit. **Klíčový rozdíl** je ale ve **second-strike capability**: pokud druhá strana má jisté schopnosti odpovědět **i po prvním úderu** (ponorky, mobilní rakety, bunkry), pak:

- **(A zaútočí, B zaútočí)** → **smrt obou** (mnohem horší než status quo).
- Druhá strana může vždy odpovědět → útok nevede k vítězství, vede ke vzájemné záhubě.

V tomto případě se **(nezaútočit, nezaútočit)** stává Nashovou rovnováhou: kdokoliv by zaútočil, jistě zemře.

> [!quote] Thomas Schelling (Nobelova cena 2005)
> *Strategický paradox jaderných zbraní spočívá v tom, že čím jsou ničivější, tím méně pravděpodobné je, že budou použity.*

Tento princip nazývá **deterrence** (odstrašování) a je založen na **kredibilitě hrozby**. Druhá strana **musí věřit**, že odveta proběhne — proto investice do automatizovaných systémů a "dead hand" strategií.

---

## Smíšené strategie

V některých hrách **neexistuje rovnováha v čistých strategiích**. Klasický příklad:

### Matching pennies

Dva hráči současně ukáží minci. Pokud obě stejné (HH nebo TT), bere A. Pokud různé, bere B.

|        | **B: H**  | **B: T**  |
|--------|:---------:|:---------:|
| **A: H** | (1, -1) | (-1, 1)   |
| **A: T** | (-1, 1) | (1, -1)   |

V žádném profilu nemá jeden hráč klid: kterýkoliv zvolí, druhý se chce přizpůsobit. **Žádná čistá rovnováha.**

### Smíšená rovnováha

Hráč hraje strategie **s pravděpodobnostmi**. V matching pennies je rovnováhou: **(0,5; 0,5)** pro oba — každý hráč je naprosto nepředvídatelný a druhý je k tomu lhostejný (jeho očekávaná výplata je stejná pro obě čisté strategie).

> [!important] Princip indiference
> V smíšené rovnováze musí být **každá hraná čistá strategie stejně dobrá**. Jinak by se hráč soustředil jen na lepší — což by ale narušilo rovnováhu druhého hráče.

### Nashův teorém znovu

Každá konečná hra má alespoň jednu rovnováhu, byť možná smíšenou. Tato univerzálnost je důvod, proč je Nashův koncept tak vlivný.

---

## Aplikace v reálném světě

Teorie her přesahuje hluboko za oligopol. Široký přehled aplikací:

### Strategická obchodní politika

- Cla, dovozní kvóty, exportní subvence — hra mezi vládami.
- Brander–Spencer model: vláda subvencuje domácí firmu, aby získala větší díl z mezinárodního zisku.

### Aukce

- **První cena uzavřená obálka**: optimální nabídka < ocenění (shading).
- **Druhá cena (Vickrey)**: dominantní strategie = nabídnout přesně ocenění.
- **Anglická aukce** (rostoucí): podobná Vickrey.
- **Holandská aukce** (klesající): podobná první ceně.

Aukce eBay (proxy bidding) v zásadě simulují Vickrey aukci.

### Sport

- **Penalty kop**: smíšené strategie (vlevo/vpravo). Empiricky: brankář i střelec randomizují, ale ne 50/50 — závisí na noze střelce.
- **Tenis (servis)**: similar.

### Politika

- **Hotelling–Downsův model**: kandidáti konvergují k mediánovému voliči.
- **Negativní kampaň** jako vězňovo dilema.

### Biologie a evoluce

- **Evolutionary stable strategy (ESS)** — Maynard Smith.
- **Hawk–Dove game** — modelování agrese mezi zvířaty.
- Replikátorová dynamika: úspěšné strategie se reprodukují více.

---

## Klasické hry — taxonomie

### Chicken (Hra na kuře)

Dvě auta jedou proti sobě. Kdo uhne první, je "kuře". Kdo neuhne, vyhraje (pokud druhý uhne) nebo zemře (pokud neuhne ani druhý).

|                | **B uhne**  | **B neuhne** |
|----------------|:-----------:|:------------:|
| **A uhne**     | (0, 0)      | (-1, 1)      |
| **A neuhne**   | (1, -1)     | (-10, -10)   |

**Dvě čisté Nashovy rovnováhy** + jedna smíšená. Aplikace: jaderné konfrontace, vyjednávání.

### Battle of Sexes (Boj pohlaví)

Manželé chtějí být spolu, ale mají různé preference (opera vs. fotbal). Dvě čisté rovnováhy (oba opera, oba fotbal) — **koordinační problém**.

### Stag Hunt (Lov jelena)

Dvojice loví. Jelen vyžaduje spolupráci, zajíc jde sám. Pokud druhý "podrazí" a jde na zajíce, první nedostane nic. **Trade-off mezi rizikem a kooperací**. Dvě rovnováhy: (jelen, jelen) Pareto-lepší ale rizikovější; (zajíc, zajíc) bezpečnější.

### Centipede game

Sekvenční hra s rostoucími odměnami. Backward induction předpovídá okamžité ukončení v prvním tahu, ale **lidé experimentálně hrají déle** — důkaz proti striktní racionalitě. "Rationality unraveling" paradox.

---

## Cooperative game theory

Pokud připustíme **závazné dohody**, vstupujeme do kooperativní teorie her:

### Shapley value

**Lloyd Shapley** (Nobelova cena 2012). Spravedlivé rozdělení zisku z koalice mezi $n$ hráčů. Vzorec:

$$\phi_i(v) = \sum_{S \subseteq N \setminus \{i\}} \frac{|S|! \, (n - |S| - 1)!}{n!} \, [v(S \cup \{i\}) - v(S)]$$

Kde $v(S)$ je hodnota koalice $S$. Shapley value = průměrný marginální příspěvek hráče.

### Core (jádro)

Množina rozdělení zisku, které **žádná podkoalice nemá motiv opustit**. Pokud existuje, koalice je stabilní. Jádro může být prázdné — pak žádné stabilní rozdělení.

### Nash bargaining solution

**Nash 1950**: pro vyjednávání dvou hráčů s pohrozkovými body $(d_1, d_2)$ je řešením maximalizace součinu nadvýplaty:

$$\max_{(u_1, u_2)} (u_1 - d_1)(u_2 - d_2)$$

Splňuje 4 axiomy: Pareto efektivita, symetrie, invariance vůči lineárním transformacím, nezávislost na irelevantních alternativách.

---

## Behavioral game theory

Klasická teorie her předpokládá **dokonalou racionalitu**. Empirické výzkumy ukazují systematické odchylky:

### Ultimátní hra

Hráč A dostane 100 Kč a navrhne rozdělení (X pro mě, 100-X pro B). B akceptuje nebo odmítne. Při odmítnutí oba dostanou 0.

- **Racionální predikce**: A nabídne 99 pro sebe, 1 pro B; B akceptuje (1 > 0).
- **Empiricky**: A nabízí kolem 40–50; B odmítá nabídky pod ~25–30.
- **Vysvětlení**: averze k nefér, sociální normy, emoce.

```graph
title: Akceptace v ultimátní hře — racionální vs. empirická
alt: Pravděpodobnost akceptace nabídky x (jako podíl celku) v ultimátní hře — racionální B přijme jakoukoli kladnou nabídku (skok v x=0), ale empiricky pozorovaní hráči odmítají nabídky pod cca 25-30 procent (sigmoid).
xAxis: { label: "nabídka x (podíl pro B)", domain: [0, 0.6] }
yAxis: { label: "P(akceptuje)", domain: [-0.05, 1.1] }
params:
  - { name: kfair, label: "ostrost fairness prahu", min: 5, max: 30, default: 15, step: 1 }
  - { name: xfair, label: "fairness práh (typicky 0.25-0.40)", min: 0.1, max: 0.5, default: 0.3, step: 0.01 }
curves:
  - { fn: "1/(1 + exp(-50*x))", label: "racionální akceptace (skok v x=0)", color: "fp-red" }
  - { fn: "1/(1 + exp(-kfair*(x - xfair)))", label: "empirická akceptace (sigmoid)", color: "fp-purple" }
markers:
  - { x: "0", label: "racionální práh = 0" }
  - { x: "xfair", label: "empirický fairness práh" }
```

### Důležité odchylky

- **Bounded rationality** (Herbert Simon, Nobelova cena 1978): omezené kognitivní kapacity.
- **Loss aversion** (Kahneman–Tversky): ztráty bolí víc, než zisky těší.
- **Fairness preferences** (Fehr–Schmidt, Bolton–Ockenfels).
- **Trust games**: hráči investují do druhých více, než racionalita předpovídá.

Souvisí s [[mikk-behavioristicke-modely-firmy|behavioristickými modely firmy]] — odchylky od profit maximization v reálných firmách.

---

## Vztah k oligopolním modelům

Každý oligopolní model je specifický druh hry:

| Model                                                   | Typ hry                | Strategie    | Pořadí       |
|---------------------------------------------------------|------------------------|--------------|--------------|
| [[mikk-oligopol-cournot-stackelberg\|Cournot]]          | Simultánní             | Množství $Q$ | Současně     |
| [[mikk-oligopol-cournot-stackelberg\|Stackelberg]]      | Sekvenční              | Množství $Q$ | Lider první  |
| [[mikk-oligopol-bertrand-cenova-konkurence\|Bertrand]]  | Simultánní             | Cena $P$     | Současně     |
| [[mikk-oligopol-cenovy-vudce-kartel\|Kartel]]           | Kooperativní           | Joint $Q^*$  | Smluvní      |
| [[mikk-oligopol-zalomena-poptavka\|Zalomená poptávka]]  | Quasi-dynamic          | Cena         | Asymetrická  |

Detailní srovnání viz [[mikk-srovnani-modelu-oligopolu|Srovnání modelů oligopolu]].

> [!info] Klíčové vhledy z teorie her pro oligopol
> 1. **Cournot a Bertrand jsou Nashovy rovnováhy** v simultánních hrách.
> 2. **Stackelberg je SPE** v sekvenční hře.
> 3. **Kartel je Pareto lepší, ale není Nashovou rovnováhou** — vězňovo dilema.
> 4. **V opakované interakci je kartel udržitelný** přes folkův teorém + tit-for-tat.

---

## Rizikové aspekty a nejistota

V reálných hrách hráči často mají **neúplnou informaci** o výplatách protihráče. To otevírá:

- **Bayesovské hry** (Harsanyi 1967–68, Nobelova cena 1994): hráči mají typy s pravděpodobnostními rozděleními.
- **Signaling games**: jeden hráč zná svůj typ a může ho **signalizovat** (drahým signálem).
- **Screening games**: druhý hráč navrhuje **menu kontraktů**, aby si typ "vybral sám".

Souvisí s [[mikk-riziko-nejistota-spotrebitele|rizikem a nejistotou spotřebitele]] — hráči neznají všechny výplaty.

---

## Praktická poučení a heuristiky

> [!tip] Heuristiky pro řešení her
> 1. **Hledej dominantní strategie** — vyřaď je rovnou.
> 2. **Iterativní eliminace dominovaných strategií** — opakuj, než zůstane "core".
> 3. **Hledej Nashovu rovnováhu metodou nejlepších odpovědí** — pro každou volbu protihráče zaškrtni svoji nejlepší.
> 4. **U sekvenčních: backward induction**.
> 5. **U opakovaných: zvaž folk theorem** a cooperation-supporting strategies.
> 6. **U nesymetrických: hledej Pareto-frontier** a multiple equilibria.

### Časté chyby studentů

- Záměna dominantní strategie a Nashovy rovnováhy. (Každá DS je Nash, ale ne naopak.)
- Předpoklad, že Nash je vždy Pareto-efektivní. **Není** (vězňovo dilema).
- Ignorování smíšených rovnováh.
- U sekvenčních her: aplikace simultánního řešení místo backward induction.

---

## Souvislosti a další studium

- [[mikk|Mikroekonomie 2]] — kurz a obecný přehled.
- [[mikk-oligopol-cournot-stackelberg]] — množstevní hry.
- [[mikk-oligopol-bertrand-cenova-konkurence]] — cenová hra.
- [[mikk-oligopol-cenovy-vudce-kartel]] — koluzní řešení.
- [[mikk-oligopol-zalomena-poptavka]] — dynamický pohled.
- [[mikk-monopolisticka-konkurence]] — diferenciace produktu.
- [[mikk-riziko-nejistota-spotrebitele]] — neúplná informace.
- [[mikk-srovnani-modelu-oligopolu]] — souhrnná tabulka.
- [[mikk-behavioristicke-modely-firmy]] — sociální hry, fairness.
- [[mikk-vzorce-prehled]] — přehled vzorců.
- [[mikk-vzorove-zkousky]] — vzorové úlohy.

---

## Klíčové zdroje

- Axelrod, R. (1984). *The Evolution of Cooperation*.
- Nash, J. (1950). "Equilibrium points in n-person games". *PNAS*.
- Schelling, T. (1960). *The Strategy of Conflict*.
