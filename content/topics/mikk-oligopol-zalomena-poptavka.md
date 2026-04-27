---
title: "Oligopol — Sweezyho model zalomené poptávky"
course: mikk
type: topic
tags: [mikk, mikroekonomie, oligopol, sweezy, zalomena-poptavka, cenova-tuhost]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf, raw/mikk/mikro-FINAL-2-1.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Oligopol — Sweezyho model zalomené poptávky

## TL;DR

**Sweezyho model** (Paul Sweezy, 1939) vysvětluje, proč jsou ceny v oligopolu **dlouhodobě stabilní** i přes změny v nákladových podmínkách. Klíčová hypotéza: konkurenti reagují **asymetricky** — pokud jedna firma sníží cenu, ostatní ji následují (aby neztratili zákazníky); pokud cenu zvýší, ostatní cenu **nezvedají** (rádi přebírají její zákazníky). Z pohledu firmy to znamená, že **poptávková křivka je v bodě tržní ceny zalomená**: nad bodem zlomu elastická, pod ním méně elastická. Zalomení v $D$ generuje **diskontinuitu (vertikální skok) v $MR$**, a pokud $MC$ leží uvnitř tohoto skoku, optimum se nemění — tj. **ani malé změny mezních nákladů (vstupy, mzdy) nezpůsobí změnu ceny ani výstupu**. Tím Sweezyho model formálně vysvětluje pozorovanou **cenovou tuhost** v oligopolních odvětvích.

![[mikk-zalomena-poptavka.jpeg|Zalomená poptávková křivka se svislou nespojitostí v MR a stabilní zónou MC]]

## 1. Sweezyho hypotéza o asymetrických reakcích konkurentů

Východiskem modelu je úvaha, jak se zachovají ostatní firmy v oligopolu, pokud jedna z nich změní cenu:

- **Snížení ceny pod aktuální tržní úroveň $P^*$**: konkurenti se obávají ztráty zákazníků, a proto **cenu rovněž sníží**. Firma tedy nezíská tolik nových zákazníků, kolik by čekala — ostatní totiž její snížení ceny vyrovnali.
- **Zvýšení ceny nad aktuální tržní úroveň $P^*$**: konkurenti **cenu nezvýší**, protože vidí příležitost přebrat zákazníky odcházející od firmy s vyšší cenou. Firma tak ztratí podstatnou část poptávky.

Z pohledu firmy se to projeví na vlastní (subjektivně vnímané) poptávkové křivce takto:

- Při **snížení** ceny pod $P^*$ → menší než očekávaný nárůst $Q$ (ostatní šli také dolů s cenou) → **málo elastická / strmější** část poptávky.
- Při **zvýšení** ceny nad $P^*$ → výraznější než očekávaný pokles $Q$ (zákazníci utíkají k levnějším konkurentům) → **silně elastická / plošší** část poptávky.

Asymetrie tedy plyne přímo ze strategického chování konkurence: firma očekává, že **nezíská** plný benefit ze snížení ceny, ale **plně utrpí** za zvýšení ceny.

## 2. Geometrie zalomené poptávky

Důsledkem asymetrických reakcí je, že firma místo jedné lineární poptávkové křivky vidí **dvě části** spojené v bodě tržní rovnováhy $(Q^*, P^*)$:

- **Horní segment** (ceny $P > P^*$): plochá, **silně elastická** poptávka. Malé zvýšení ceny vede k velkému poklesu $Q$.
- **Dolní segment** (ceny $P < P^*$): strmá, **málo elastická** poptávka. I výrazné snížení ceny přinese jen malé zvýšení $Q$.

V bodě $(Q^*, P^*)$ se obě části setkávají pod úhlem — odtud anglický název **kinked demand curve** ("zalomená" / "se zlomem"). Poptávka má i nadále **negativní sklon** (cena a množství stále reagují inverzně), ale **strmost se v bodě $P^*$ skokově mění**.

## 3. MR křivka — diskontinuita

Pro každou ze dvou částí poptávky existuje vlastní křivka mezních příjmů:

- **$MR_1$** odpovídá **elastické (horní)** části poptávky: méně strmá, leží nad bodem zlomu.
- **$MR_2$** odpovídá **neelastické (dolní)** části poptávky: výrazně strmější, leží pod bodem zlomu.

Protože sklon levé části poptávky se v bodě zlomu skokově mění z plošší na strmější, **nemůže existovat spojitá $MR$**. Místo toho v bodě $Q = Q^*$ vzniká **vertikální segment** (skok) v $MR$ křivce — křivka mezních příjmů má **diskontinuitu**:

$$
MR =
\begin{cases}
MR_1(Q) & \text{pro } Q < Q^* \\
\text{vertikální skok} & \text{v } Q = Q^* \\
MR_2(Q) & \text{pro } Q > Q^*
\end{cases}
$$

Délka vertikálního skoku závisí na rozdílu sklonů obou částí poptávky — čím větší rozdíl, tím delší skok.

## 4. Cenová tuhost a vliv $MC$

Klíčová implikace modelu: optimum monopolistického / oligopolního výrobce splňuje obvyklou podmínku $MR = MC$. Pokud křivka $MC$ protíná $MR$ uvnitř vertikálního segmentu, optimum zůstává v bodě $(Q^*, P^*)$:

> **Pokud se mezní náklady pohybují ve vertikální části MR, cena ani výstup se nemění.**

Konkrétně: označme horní okraj vertikálního skoku jako $MR_1(Q^*)$ a dolní okraj jako $MR_2(Q^*)$. Pak:

$$
MR_2(Q^*) \le MC \le MR_1(Q^*) \quad\Rightarrow\quad Q = Q^*,\ P = P^*
$$

Tj. **fluktuace mezních nákladů** (např. díky kolísavé ceně vstupů, energií, mezd, surovin) v rámci tohoto pásma **nezpůsobí žádnou změnu** výstupu ani ceny. Teprve když $MC$ vystoupí nad $MR_1(Q^*)$ nebo klesne pod $MR_2(Q^*)$, firma reaguje změnou výstupu (a tedy i ceny).

**Důsledek**: ceny v oligopolu jsou systematicky **stabilnější** než v dokonalé konkurenci, kde $P = MC$ a každá změna $MC$ se ihned promítne do ceny.

## 5. Empirické důkazy cenové tuhosti

Sweezyho model byl motivován reálnými pozorováními cenové tuhosti v meziválečných USA:

- **Mzdové rigidity** v oligopolních průmyslových odvětvích — mzdy se nepřizpůsobovaly vstupní inflaci.
- **Ceny papíru, skla, oceli a hliníku** zůstávaly konstantní po měsíce i roky, navzdory změnám v nákladech.
- **Detroitský automobilový průmysl** (Big Three): ceny se měnily prakticky jen jednou ročně, vždy s uvedením nového ročního modelu.
- **Cigaretový průmysl** ve 30. letech: cena standardní krabičky se neměnila po celé desetiletí.

Tato pozorování přesně odpovídají predikci Sweezyho modelu — cena drží i při proměnlivých $MC$.

## 6. Detailní výpočet (Předtermín B)

Zadání: monopolistický / oligopolní výrobce s nákladovou funkcí

$$
TC = 100 + 30Q
$$

a se zalomenou poptávkou definovanou po částech:

$$
Q_1 = 100 - P \quad\text{(pro } P \le P^*\text{, dolní část)}, \qquad
Q_2 = 160 - 2P \quad\text{(pro } P > P^*\text{, horní část)}
$$

### 6.1 Inverzní poptávky

$$
P_1 = 100 - Q_1 \qquad
P_2 = \tfrac{160 - Q_2}{2} = 80 - 0{,}5 \, Q_2
$$

### 6.2 Bod zlomu

V bodě zlomu obě části poptávky musí dávat stejnou kombinaci $(Q^*, P^*)$. Položíme $P_1 = P_2$ při stejném $Q$:

$$
100 - Q = 80 - 0{,}5 Q \quad\Longrightarrow\quad 20 = 0{,}5 Q \quad\Longrightarrow\quad Q^* = 40
$$

Dosazením zpět: $P^* = 100 - 40 = 60$. Bod zlomu tedy je $(Q^*, P^*) = (40,\ 60)$.

### 6.3 Mezní příjmy z obou částí

Pro lineární poptávky $P = a - bQ$ platí $MR = a - 2bQ$:

- **Horní (elastická) část**, $P_2 = 80 - 0{,}5 Q$:

$$
MR_2 = 80 - Q
$$

- **Dolní (neelastická) část**, $P_1 = 100 - Q$:

$$
MR_1 = 100 - 2Q
$$

### 6.4 Vertikální skok v $MR$ při $Q = 40$

- $MR_2(40) = 80 - 40 = 40$ (horní okraj skoku — z elastické části)
- $MR_1(40) = 100 - 2 \cdot 40 = 20$ (dolní okraj skoku — z neelastické části)

Vertikální segment $MR$ při $Q^* = 40$ tedy leží mezi hodnotami $20$ a $40$:

$$
MR(40) \in [20,\ 40]
$$

### 6.5 Mezní náklady a optimum

Z $TC = 100 + 30Q$ plyne $MC = 30$. Protože

$$
20 \le 30 \le 40,
$$

hodnota $MC$ leží **uvnitř vertikálního skoku** $MR$ — optimum tedy **zůstává v bodě zlomu**:

$$
Q^* = 40, \qquad P^* = 60
$$

### 6.6 Zisk

$$
\pi = P^* \cdot Q^* - TC(Q^*) = 60 \cdot 40 - (100 + 30 \cdot 40) = 2400 - 100 - 1200 = 1100
$$

### 6.7 Pásmo cenové tuhosti

> **Klíčový poznatek**: i kdyby $MC$ libovolně kolísalo v intervalu $[20,\ 40]$ (např. fluktuace ceny vstupů, výkyv mzdových sazeb), **rovnovážná cena $P^* = 60$ ani výstup $Q^* = 40$ se nezmění**. Teprve $MC > 40$ nebo $MC < 20$ posune optimum jinam.

## 7. Kritika modelu

Sweezyho model je elegantní, ale není bez kritiků:

- **Nevysvětluje, kde se zlom nastane.** Model bere $P^*$ jako dané, ale nedokáže říci, **jak se počáteční cena ustavila**. Zlomená poptávka je tedy spíše popisem stability než teorií rovnováhy.
- **Stigler (1947)** v empirické studii nenašel **konzistentní důkazy** o asymetrických reakcích konkurentů. V některých odvětvích konkurence reagovala spíše na zvýšení než na snížení ceny.
- **Některé novější studie** (např. Dominick Salvatore) našly chování přímo **opačné** — konkurence následovala zvýšení a ne snížení.
- Model **statický** — neumí vysvětlit, jak oligopol reaguje na trvalé změny v poptávce nebo nákladech.

## 8. Alternativní vysvětlení cenové tuhosti

Cenová tuhost se v moderní mikroekonomii vysvětluje i jinými mechanismy než Sweezyho asymetrickou reakcí:

- **Menu costs** — fyzické náklady na změnu cen (přepis ceníků, etiket, marketingových materiálů, IT systémů). Drobné změny $MC$ nepokryjí náklady na re-pricing.
- **Implicit collusion** — firmy se nechtějí pouštět do cenové války a mlčky drží cenu. Viz [[mikk-oligopol-cenovy-vudce-kartel|cenový vůdce a kartel]].
- **Nominální rigidita mezd** — kolektivní smlouvy a pracovní kontrakty fixují náklady na práci na delší období.
- **Reputational concerns** — časté změny ceny narušují důvěru zákazníků; "spolehlivá cena" je marketingová hodnota sama o sobě.
- **Opakovaná hra** v teorii her — viz [[mikk-vezno-dilema-teorie-her|vězňovo dilema a opakované hry]] — kooperativní rovnováha drží cenu nahoře.

## 9. Kdy Sweezyho model platí

Předpoklady, za nichž model dává nejlepší predikce:

- Oligopol s **3–5 firmami** (víc firem oslabuje strategickou interakci, méně směřuje k duopolu).
- **Homogenní nebo téměř homogenní produkt** (zákazníci snadno přechází mezi firmami).
- **Stabilní tržní podmínky** — bez technologických zlomů a bez dramatických šoků v nákladech.
- **Vysoká cenová viditelnost** — zákazníci snadno porovnávají ceny a rychle přecházejí k levnějšímu (typické pro maloobchod, telekomunikace, leteckou dopravu).
- **Neexistence dominantní firmy** — pokud má jedna firma rozhodující podíl, lépe pasuje [[mikk-oligopol-cenovy-vudce-kartel|model dominantní firmy / cenového vůdce]].

## 10. Vztah k dalším modelům oligopolu

| Model | Volební proměnná | Reakce konkurentů | Predikce ceny |
|---|---|---|---|
| **Bertrand** | cena | ostrá konkurence — sníží cenu o $\varepsilon$ pod | $P = MC$, nulový zisk |
| **Cournot** | množství | "fixní" — drží své $q_j$ | $P > MC$, pozitivní zisk |
| **Sweezy** | cena | **asymetrické** (následují snížení, neseupozor zvýšení) | $P^*$ dlouhodobě **stabilní** |
| **Stackelberg** | množství, sekvenčně | follower reaguje na leadera | $P$ nižší než Cournot |

Pro detailní srovnání viz [[mikk-srovnani-modelu-oligopolu|srovnání modelů oligopolu]] a [[mikk-oligopol-cournot-stackelberg|Cournot a Stackelberg]] nebo [[mikk-oligopol-bertrand-cenova-konkurence|Bertrandův cenový model]].

## 11. Aplikace v reálném světě

- **Letecká doprava v 80.–90. letech (USA, Evropa)**: typický cyklus — krátké cenové války iniciované jedním přepravcem, následované obdobími stability, kdy ceny drží i při kolísavých cenách paliva.
- **Telekomunikace v ČR**: dlouholetá stabilita cen u trojice T-Mobile / O2 / Vodafone navzdory změnám v technologických nákladech (LTE → 5G). Změna obvykle přichází jen tehdy, když ji vyvolá nový operátor (Bleskmobil, MNVO).
- **Maloobchodní řetězce** (Tesco / Lidl / Penny / Albert): leták se mění týdně, ale **ceny základního koše** zůstávají dlouhodobě v úzkém pásmu — cenová parita je strategická.
- **Pivovarnictví ČR**: ceny lahvového piva v hypermarketech roky stabilní, přestože náklady na ječmen a energie kolísají.
- **Cementárny a ocelárny v EU**: dlouhodobě stabilní ceny, vysvětlované jak Sweezyho mechanismem, tak menu costs.

## Související

- [[mikk|Mikroekonomie 2]]
- [[mikk-oligopol-cournot-stackelberg]]
- [[mikk-oligopol-bertrand-cenova-konkurence]]
- [[mikk-oligopol-cenovy-vudce-kartel]]
- [[mikk-vezno-dilema-teorie-her]]
- [[mikk-srovnani-modelu-oligopolu]]
- [[mikk-vzorce-prehled]]
- [[mikk-vzorove-zkousky]]
