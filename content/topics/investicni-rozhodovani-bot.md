---
title: "Investiční rozhodování — case study BOT vodní elektrárny"
course: irmank
type: topic
tags: [irmank, npv, irr, bot, citlivostni-analyza, vodni-elektrarna, investicni-rozhodovani]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Investiční rozhodování — case study BOT vodní elektrárny

> [!info] TL;DR
> Case study **Build-Operate-Transfer (BOT) vodní elektrárny za 260 mil USD na 19 let** demonstruje **citlivostní analýzu NPV** a využití **AI metod** (genetické algoritmy, neuronové sítě) pro snížení rizika investičního rozhodování. Klíčový poznatek: **+2 % nákladů** posune návratnost o roky, **+15 % cena** prudce mění NPV (zejména po roce 12). Doporučení: **revize smluv, vlastní financování, remodelování**.
>
> Investiční rozhodnutí je největší rozhodnutí firmy — chybu nelze snadno opravit, kapitál je vázán na desetiletí. Tato stránka ukazuje, jak klasické metriky (NPV, IRR), citlivostní analýza a AI nástroje pracují společně v rámci [[rizeni-rizik|řízení rizik]].

## Kontext: BOT (Build-Operate-Transfer) projekty

**BOT** = forma PPP (public-private partnership), kde:

1. **Build** — soukromý investor postaví infrastrukturu (vlastní kapitál + cizí financování).
2. **Operate** — provozuje 15–30 let a vrátí investici z tržeb od koncových uživatelů (nebo státu).
3. **Transfer** — na konci koncesní lhůty převádí infrastrukturu zdarma na stát/zadavatele.

Typické pro: dálnice, elektrárny, mosty, letiště, vodárny, metro.

**Riziko BOT projektů:**
- Dlouhý časový horizont (15–30 let) → kumulace nejistot.
- Kapitálová náročnost (stovky mil až mld USD) → omezený manévrovací prostor.
- Regulační riziko — změny daňové, environmentální, energetické politiky.
- Měnové riziko — typicky financování v USD/EUR, tržby v lokální měně.
- Politické riziko — emerging markets, znárodnění, kontraktní renegociace.

**BOT** je klasický nástroj projektového financování v rozvíjejících se ekonomikách, kde stát nemá kapitál na vlastní výstavbu, ale potřebuje infrastrukturu.

## Klíčové investiční metriky

### Net Present Value (NPV)

$$NPV = \sum_{t=0}^{T} \frac{CF_t}{(1 + r)^t}$$

- $CF_t$ — cash flow v roce $t$ (záporný v investiční fázi, kladný v provozní).
- $r$ — diskontní sazba (cost of capital, typicky WACC).
- $T$ — horizont projektu.

**Pravidlo:**
- $NPV > 0$ → projekt přijatelný (vytváří hodnotu nad cost of capital).
- $NPV = 0$ → indiferentní (právě pokrývá cost of capital).
- $NPV < 0$ → odmítnutí (ničí hodnotu).

### Internal Rate of Return (IRR)

$$\sum_{t=0}^{T} \frac{CF_t}{(1 + IRR)^t} = 0$$

IRR je diskontní sazba, při které $NPV = 0$.

**Pravidlo:** $IRR > r$ (cost of capital) → projekt přijatelný.

**Úskalí IRR:**
- U nekonvenčních cash flow (více znaménkových změn) může existovat více IRR.
- Reinvestiční předpoklad: IRR předpokládá reinvestici cash flow při samotné IRR sazbě, což je často nereálné.
- Pro vzájemně se vylučující projekty může IRR vést k jiné volbě než NPV → preferujeme NPV.

### Payback period

- **Jednoduchý:** kdy kumulovaný cash flow překročí 0 (kdy se vrátí investice).
- **Diskontovaný:** kdy diskontovaný kumulovaný CF překročí 0 (zohledňuje časovou hodnotu peněz).

Payback je intuitivní, ale neodráží cash flow po bodu zlomu — proto se používá pouze jako doplněk k NPV/IRR.

## Vstupní parametry case study

![[irmank-bot-elektrarna-parametry.jpeg|Vstupní parametry BOT vodní elektrárny — investice, opex, výnosy, daň]]

Z přednáškového slidu 98:

| Parametr | Hodnota |
|---|---|
| **Celková investice** | 260 mil USD |
| **Doba projektu** | 19 let |
| **Diskontní sazba** | 6 % p.a. |
| **Investiční fáze** | rok 1–6 |
| **Roční investice** | 20–70 mil USD (postupně) |
| **Operativní náklady (opex)** | rok 1: 25 mil USD → rok 10+: 15 mil USD |
| **Daňová sazba** | 31 % |
| **Cena energie** | 89.50 USD/MWh |
| **Roční výroba** | 480 GWh/rok |
| **Roční tržby** | 89.50 × 480 000 = ~43 mil USD |

**Struktura cash flow:**
- Roky 1–6: výstavba — záporné CF (CAPEX 20–70 mil USD ročně, postupně podle fáze stavby).
- Roky 7–19: provoz — kladné CF (~43 mil USD tržby − ~15 mil USD opex − daň 31 %).
- Rok 20+: transfer (zdarma na stát) — zbytková hodnota nulová pro investora.

**Kritický poznatek:** investiční fáze je 6 let, ale tržby začínají až po jejím dokončení — kumulovaná investice 260 mil USD musí být splacena za 13 provozních let.

## Citlivostní analýza — variace nákladů (+2 %)

![[irmank-npv-citlivost-naklady-2pct.jpeg|NPV citlivost — vliv +2 % změny provozních nákladů na průběh NPV]]

Z přednáškového slidu 99:

- **Modrá křivka (NPV2):** scénář s +2 % opex (mírně vyšší provozní náklady).
- **Žlutá křivka (NPV1):** základní scénář.
- **Y osa:** NPV od –200 do +50 mil USD.
- **X osa:** roky 1–24 (zahrnuje výstavbu + provoz).

**Pozorování:**
- Křivky začínají blízko sebe v investiční fázi (kde opex hraje malou roli).
- V provozní fázi se postupně rozevírají.
- Drobné +2 % opex způsobí **významný posun bodu obratu** — projekt se vrací cca o 2–3 roky později.

**Poučení:** projekt je velmi citlivý na opex i při malých změnách. Nezbytná je **fixace dlouhodobých smluv s dodavateli** — long-term service agreements, dodávky náhradních dílů za pevné ceny, indexace pouze na CPI nikoli na komoditní ceny.

## Citlivostní analýza — variace ceny (+15 %)

![[irmank-npv-citlivost-cena-15pct.jpeg|NPV citlivost — vliv +15 % změny ceny energie]]

Z přednáškového slidu 100:

- **Modrá křivka (NPV2):** scénář s +15 % cenou energie.
- **Žlutá křivka (NPV1):** základní scénář.
- **Y osa:** NPV od –300 do +400 mil USD.
- **X osa:** roky 1–24.

**Pozorování:**
- **Mnohem dramatičtější změna** než u nákladů — měřítko Y osy je 4× větší.
- Křivky divergují **zejména po roce 12** — kumulativní efekt vyšší ceny se násobí roky provozu.
- V základním scénáři projekt končí kolem +50 mil USD NPV; při +15 % ceně dosahuje +400 mil USD.

**Poučení:** cenové riziko je dominantní — proto je **PPA (Power Purchase Agreement)** s pevnou cenou klíčový. Bez PPA je investor vystaven volatilní spotové ceně elektřiny, kterou ovlivňují ceny plynu, počasí, regulace EU ETS a politické intervence.

## Trade-off: cena vs. náklady

Srovnání dopadů jednotlivých vstupních parametrů:

| Parametr | Posun | Dopad na NPV | Citlivost |
|---|---|---|---|
| Opex | +2 % | Posun návratnosti o 2–3 roky | Vysoká |
| Cena energie | +15 % | Změna NPV o stovky mil USD po roce 12 | Velmi vysoká |
| Diskontní sazba | +1 p.b. | Snížení NPV o ~30 % | Vysoká |
| Výroba (GWh) | –10 % | Snížení tržeb o ~10 % proporcionálně | Střední |

**Pořadí citlivosti** typické pro dlouhodobé energetické projekty: **diskont > cena > výroba > opex**.

Diskontní sazba je často podceňovaná — zvýšení o 1 p.b. (ze 6 % na 7 %) sníží současnou hodnotu cash flow z roku 19 o cca $(1.07/1.06)^{19} \approx 17 \%$. Pokud projekt financujeme z části cizím kapitálem a úroková sazba vzroste, NPV výrazně klesá.

## Použití AI metod

### Genetické algoritmy

Z přednáškového slidu 101:

- **Validace klasického NPV modelu** přes 100 tisíc generací populace.
- GA nezávisle dospívá k podobným výsledkům jako klasické DCF — slouží jako **independent check** pro audit modelu.
- Aproximace průběhu NPV nelineárními křivkami (Gompertzova, exponenciální) — pro hladké simulace senzitivity.
- GA optimalizují strukturu cash flow (např. timing investice, fázování) s ohledem na maximalizaci NPV pod omezeními.

Cross-link: [[geneticke-algoritmy]] (ipmrk) — detail metody.

### Umělé neuronové sítě

Z přednáškových slidů 103–105:

**Vstupní vektor investice** $X = (X_1, X_2, ..., X_M)$ pro každou historickou investici:

- Typ projektu (energetika / infrastruktura / průmysl).
- Obor (vodní / solární / vítr / fosil).
- Velikost (mil USD).
- Geografická lokace (země, region, klimatické podmínky).
- Investující společnost (rating, historie).
- Doba trvání.
- Účetní data (rozvaha + výsledovka).

![[irmank-ann-vstupni-matice.jpeg|Trénovací matice — N+1 historických investic, ANN predikuje realizovatelnost poslední]]

- **Trénovací matice:** $N+1$ řádků (historické investice), poslední řádek = nový případ k predikci.
- **Supervised learning** — historie úspěch/neúspěch jako labely (binární klasifikace, případně regrese na míru úspěchu).
- **Výstup:** míra realizovatelnosti (probability of success) v intervalu $[0, 1]$.
- ANN se naučí komplexní nelineární vzory mezi vstupními parametry a úspěchem investice — vzory, které by analytik s DCF tabulkou přehlédl.

Cross-link: [[umele-neuronove-site]] (ipmrk) — detail metody, backpropagation, architektury.

## Doporučení pro management

Z přednáškového slidu 102 — strategická opatření po citlivostní analýze:

1. **Revize smluv** — fixace cen energie přes PPA (Power Purchase Agreement), fixace opex přes long-term service agreements s dodavateli technologie.
2. **Vlastní financování** — snížit podíl cizího kapitálu (snižuje úrokové riziko a FX riziko z dolarového úvěru, pokud projekt v emerging market).
3. **Remodelování projektu** — případně upravit fázování investice (rychlejší build → kratší riziková fáze, ale vyšší peak CAPEX requirements).
4. **Hedging FX** — pokud projekt v jiné měně než tržby/náklady (forwardy, swapy, natural hedge).
5. **Pojištění proti přírodním katastrofám** — vodní elektrárny jsou exponovány záplavám, suchu, sedimentaci přehrady, zemětřesení.
6. **Politické pojištění** — instituce typu MIGA (Multilateral Investment Guarantee Agency, World Bank) nebo OECD agentury pro emerging markets — pokrývají riziko vyvlastnění, válek, nemožnosti převodu měny.

## Caveat AI metod

Z přednáškového slidu 106:

> „Metody AI jsou **asistenty**, ne náhrada za originální tvůrčí strategické myšlení manažera."

AI metody:

- Provádějí výpočty rychleji než člověk (Monte Carlo se 100 000 scénáři za sekundy).
- Identifikují vzorce v datech, které by člověk přehlédl (nelineární korelace mezi parametry projektů).
- **Nedovedou** abstraktní strategické úvahy, etiku, vize, lidské vztahy s partnery, vyjednávání s vládou.
- **Nenahrazují** zodpovědnost manažera — finální rozhodnutí a jeho důsledky leží na člověku.

Toto je důležitý etický a praktický bod — AI v investičním rozhodování zvyšuje kvalitu analýzy, ale nepřenáší zodpovědnost.

## Praktická aplikace v risk managementu

**Investiční rozhodnutí** = největší rozhodnutí firmy → nejvyšší riziko. Strukturovaný postup:

1. **Klasický DCF výpočet** — NPV, IRR, payback (deterministický základní scénář).
2. **Citlivostní analýza** pro klíčové parametry (opex, cena, diskont, výroba) — identifikace dominantních rizikových faktorů.
3. **Monte Carlo simulace** pro distribuci NPV — místo bodového odhadu poskytuje pravděpodobnostní rozdělení (např. P(NPV<0) = 18 %).
4. **AI validace** (GA, ANN) pro komplexní projekty — independent check klasického modelu, klasifikace podle historických analogií.
5. **Doporučení managementu** s explicit risk mitigation plan — pro každé identifikované riziko konkrétní opatření (PPA, hedging, pojištění).

Cross-link na [[mapa-rizik]] — investiční rizika patří do mapy s vysokým dopadem a střední pravděpodobností. [[taktiky-rizeni-rizik]] — přenos (PPA, pojištění), redukce (diverzifikace lokací), retence (kapitálové rezervy).

## Souvislosti

- [[mereni-rizika]] — rozptyl $\sigma^2$ a koeficient variace KV jako vstup pro Monte Carlo simulaci NPV.
- [[operacni-vyzkum]] — DCF a citlivostní analýza jsou klasickou součástí operačního výzkumu.
- [[expertni-systemy]] — výběr investiční strategie pomocí pravidlové báze (if-then pravidla nad parametry projektu).
- [[mcfarlan-portfolio]] — kategorizace investice (Strategická investice vyžaduje detailní citlivost a scénářovou analýzu).
- Cross-course: [[geneticke-algoritmy]] (ipmrk) — GA pro validaci NPV a optimalizaci fázování, [[umele-neuronove-site]] (ipmrk) — ANN pro klasifikaci investic podle historie, [[predikce]] (ipmrk) — Box-Jenkins prognóza cen energie pro vstup do NPV, [[lagrangeova-metoda]] (imek) — optimalizace investičního portfolia s rozpočtovým omezením.

## Navigace

- **Předchozí:** [[expertni-systemy]]
- **Navazující:** [[krizove-rizeni]]
- **Související:** [[mereni-rizika]], [[mcfarlan-portfolio]]
