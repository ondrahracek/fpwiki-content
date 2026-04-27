---
title: "MikK — Monopol pokročile, cenová diskriminace, oligopol"
course: mikk
type: summary
tags: [mikk, mikroekonomie, prednaska, monopol, oligopol, cenova-diskriminace]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# MikK — Monopol pokročile, cenová diskriminace, oligopol

> [!abstract] TL;DR
> Pokročilá část kurzu [[mikk|Mikroekonomie 2]] věnovaná tržním strukturám s nedokonalou konkurencí: **monopol** (stanovení ceny, Lerner, mrtvá ztráta, regulace, monopol s více závody), **monopson** (mzdová diskriminace), **cenová diskriminace** všech tří stupňů (1. dokonalá, 2. blokové ceny, 3. tržní segmentace, peak pricing, two-part tariff, bundling) a **oligopol** (Cournot, Stackelberg, Bertrand, vězňovo dilema, Sweezyho zalomená poptávka, dominantní firma, kartel). Závěrečná **srovnávací tabulka modelů oligopolu** je klíčový studijní materiál ke zkoušce.

## Hlavní obsah

### Stanovení ceny v monopolu

> [!info] Inverse-elasticity rule
> $$\dfrac{P - MC}{P} = -\dfrac{1}{E_D}$$
> ekvivalentně $P = \dfrac{MC}{1 + 1/E_D}$.

- **Lernerův index** $L = (P - MC)/P \in [0, 1]$ měří monopolní sílu; pro dokonalou konkurenci $L = 0$.
- **Markup pricing:** $P = MC \cdot \dfrac{1}{1 + 1/E_D}$ — typická forma s elastickou poptávkou ($\lvert E_D \rvert > 1$).
- **Případ Astra-Merck Prilosec:** Cena $3{,}50/dávka při MC $0{,}30–$0{,}40, příklad reálné monopolní ceny v farmaceutice.

#### Monopol s více závody

Firma s několika výrobními závody alokuje produkci tak, aby **MC bylo stejné ve všech závodech**:

$$MC_1(Q_1) = MC_2(Q_2) = \dots = MC_n(Q_n) = MR(Q),$$

kde $Q = \sum Q_i$.

### Monopolní síla a regulace

- **Mrtvá ztráta (DWL):** trojúhelníková plocha mezi poptávkou a MC mezi $Q^M$ a $Q^{PC}$.
- **Společenské náklady monopolu:** DWL + náklady honu za rentou (rent-seeking).
- **[[mikk-prirozeny-monopol-regulace|Přirozený monopol]]** — situace, kdy LAC klesá v relevantním rozsahu (rostoucí výnosy z rozsahu); regulace cenovým stropem $P^* = AC$ (zero-profit) nebo $P^* = MC$ (efficient, ale ztráta).

### [[mikk-monopson-mzdova-diskriminace|Monopson]]

Jediný kupující na trhu výrobního faktoru (typicky práce):

$$ME_L = \dfrac{d(w \cdot L)}{dL} = w + L \cdot \dfrac{dw}{dL}$$

- $ME_L > w$ (mezní výdaj na práci převyšuje mzdu).
- Optimum: $MRP_L = ME_L$ → najímá $L^M < L^{PC}$ za $w^M < w^{PC}$.

### [[mikk-cenova-diskriminace|Cenová diskriminace]]

| Stupeň | Mechanismus | Příklady |
|---|---|---|
| **1. (dokonalá)** | každá jednotka prodána za maximální ochotu zaplatit | aukce, ojedinělé služby, lékař |
| **2. (block pricing)** | cena podle kvantity (kvantitativní slevy) | tarifní rozpětí elektřiny, letenky podle množství |
| **3. (segmentace)** | různé ceny různým skupinám | studentské slevy, kupony, geografická segmentace |

#### Peak-load pricing

Při kapacitních omezeních (špička × mimo špičku) firma nastaví různé ceny pro různá období:

$$P_{\text{špička}} > P_{\text{mimo špičku}},$$

kde špičková cena reflektuje i kapacitní náklady.

#### Two-Part Tariff

$T(Q) = F + p \cdot Q$ — fixní poplatek $F$ + lineární $p$ za jednotku.

Pro homogenní spotřebitele optimální nastavení: $p = MC$, $F = $ celý spotřebitelský přebytek.

#### Bundling

Spojené prodeje (zboží A + B v balíčku za jednu cenu); ziskové při **negativně korelovaných** rezervačních cenách.

### Modely oligopolu

#### [[mikk-oligopol-cournot-stackelberg|Cournotův model]]

Firmy soutěží **kvantitou současně**.

Pro lineární poptávku $P = a - b(Q_1 + Q_2)$ a konstantní $MC = c$ je rovnováha:

$$Q_i^* = \dfrac{a - c}{3b}, \quad P^* = \dfrac{a + 2c}{3}, \quad \pi_i^* = \dfrac{(a-c)^2}{9b}$$

#### Stackelbergův model

Firmy soutěží **kvantitou sekvenčně** (lídr → následovník):

$$Q_L^* = \dfrac{a-c}{2b}, \quad Q_F^* = \dfrac{a-c}{4b}, \quad \pi_L > \pi_F$$

(first-mover advantage).

#### [[mikk-oligopol-bertrand-cenova-konkurence|Bertrandův model]]

Firmy soutěží **cenou současně** s homogenním produktem:

- Rovnováha: $P_1 = P_2 = MC$ (Bertrandův paradox — i s pouhými dvěma firmami klesne cena na úroveň dokonalé konkurence).

#### [[mikk-vezno-dilema-teorie-her|Vězňovo dilema]]

Dvě firmy se rozhodují mezi „kooperovat" a „defektovat". Dominantní strategie obou je defekce → **Nash equilibrium** je horší než kooperativní výsledek.

#### [[mikk-oligopol-zalomena-poptavka|Sweezyho zalomená poptávka]]

Předpoklad asymetrické reakce konkurentů:

- Pokud zvýším cenu, konkurenti **nezvýší** → moje poptávka je **elastická** nahoře.
- Pokud snížím cenu, konkurenti **také sníží** → moje poptávka je **neelastická** dole.
- Výsledek: zalomená poptávka, **diskontinuita v MR** → cena rigidní v širokém pásmu MC.

#### [[mikk-oligopol-cenovy-vudce-kartel|Dominantní firma a kartel]]

- **Dominantní firma:** chová se jako monopolista vůči zbytkové poptávce $Q_D - Q_F$ (tzv. fringe).
- **Barometrická firma:** lídr signalizuje cenu, ostatní následují.
- **Kartel:** explicitní dohoda. Příklady: **OPEC** (úspěšný díky neelastické poptávce), **CIPEC** (méně úspěšný).

> [!warning] Stabilita kartelu
> Vysoká pokušení k podvádění (defekci): individuální zisk z odchylky převyšuje sankce, zejména když je obtížné monitorovat členy.

### Srovnávací tabulka

> [!tip] Zlatá tabulka — porovnání modelů oligopolu
>
> | Model | Strategická proměnná | Pořadí rozhodnutí | Výsledek $P$ | Výsledek $Q$ |
> |---|---|---|---|---|
> | Dokonalá konkurence | — | — | $P = MC$ | nejvyšší |
> | Bertrand | cena | současně | $P = MC$ | jako PC |
> | Cournot | kvantita | současně | $P > MC$ | nižší než PC |
> | Stackelberg | kvantita | sekvenčně | $P > MC$ | mezi Cournot a kartelem |
> | Kartel/monopol | kvantita (sjednocená) | — | $P^M$ | nejnižší |

## Související stránky

- [[mikk-monopol-pokrocily|Monopol — pokročilá analýza]]
- [[mikk-monopson-mzdova-diskriminace|Monopson a mzdová diskriminace]]
- [[mikk-cenova-diskriminace|Cenová diskriminace]]
- [[mikk-bundling-two-part-tariff|Bundling a two-part tariff]]
- [[mikk-oligopol-cournot-stackelberg|Oligopol Cournot a Stackelberg]]
- [[mikk-oligopol-bertrand-cenova-konkurence|Bertrandův oligopol]]
- [[mikk-vezno-dilema-teorie-her|Vězňovo dilema a teorie her]]
- [[mikk-oligopol-zalomena-poptavka|Zalomená poptávka (Sweezy)]]
- [[mikk-oligopol-cenovy-vudce-kartel|Cenový vůdce a kartel]]
- [[mikk-srovnani-modelu-oligopolu|Srovnání modelů oligopolu]]
- [[mikk-prirozeny-monopol-regulace|Přirozený monopol a regulace]]
- [[mikk|Mikroekonomie 2]] — kurzová stránka.
