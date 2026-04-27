---
title: "McFarlanův model aplikačního portfolia"
course: irmank
type: topic
tags: [irmank, mcfarlan, is-it-strategie, aplikacni-portfolio, strategicke, factory-support]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# McFarlanův model aplikačního portfolia

> [!info] TL;DR
> McFarlanův model aplikačního portfolia (Harvard Business School, F. Warren McFarlan) je **2×2 matice klasifikace IS/IT aplikací** firmy podle dvou os: **business znalosti** (jak je aplikace klíčová pro strategii) a **technické znalosti** (jak je technologicky náročná). Čtyři kvadranty — Strategické, Turnaround (potenciální), Factory (klíčové), Support (podpůrné) — vyžadují různé řízení rizik a investiční přístupy.

## Autor a kontext

- **F. Warren McFarlan** — emeritní profesor Harvard Business School, klasik IS/IT strategie.
- **Kontext modelu:** klasifikace IS/IT investic firmy podle jejich strategické důležitosti.
- První publikace 1980s, stále standardní rámec v IT governance.
- Cíl modelu: **správně alokovat řízenou pozornost a investice** podle rizikového profilu aplikace.

Model vznikl v době, kdy se firmy poprvé masově potýkaly s otázkou, jak řídit rostoucí portfolio IT aplikací — od kritických systémů po experimentální nasazení. McFarlan navrhl jednoduchý dvourozměrný rámec, který umožňuje managementu **rychle se zorientovat** v tom, kam směřovat pozornost a kapitál.

## Dvě osy modelu

### Osa Y: Business znalosti (strategická hodnota pro firmu)

- **Vysoká:** aplikace dává firmě konkurenční výhodu, podporuje růst, transformaci.
- **Nízká:** aplikace je „komodita", všichni v branži ji mají.

### Osa X: Technické (speciální) znalosti

- **Vysoké:** vyžaduje vlastní specializovaný tým, customizaci, integrace.
- **Nízké:** standardní řešení, lze koupit / pronajmout.

Kombinací těchto dvou os vznikají čtyři charakteristické kvadranty, z nichž každý má vlastní investiční logiku, sourcing strategii a rizikový profil.

## Čtyři kvadranty

![[irmank-mcfarlan-2x2.jpeg|McFarlanův 2×2 model aplikačního portfolia]]

| | **Nízká business hodnota** | **Vysoká business hodnota** |
|---|---|---|
| **Vysoké tech znalosti** | **Factory** (klíčové) | **Strategické** |
| **Nízké tech znalosti** | **Support** (podpůrné) | **Turnaround** (potenciální) |

### Strategické aplikace (high business / high tech)

- Aplikace, která **definuje konkurenční pozici** firmy.
- Přínos transformační: nový business model, segmentace, nové trhy.
- Příklady: doporučovací systém Netflix, vyhledávač Google, autopilot Tesla.
- **Risk management:** vlastní vývoj, top investice, top management ownership, in-house tým, nepřetržitý monitoring rizik.
- **Failure tolerance:** velmi nízká — selhání zničí strategii.

### Factory aplikace (low business / high tech)

- **Klíčová operativní aplikace** firmy: ERP, výrobní systém, CRM.
- Bez ní firma nefunguje, ale neodlišuje od konkurence.
- Příklady: SAP ERP, Oracle Database, Microsoft Exchange.
- **Risk management:** vysoká dostupnost (SLA), redundance, BCM (cross-link [[bcm]] z [[imork|Management oborových řešení]]), DR.
- **Failure tolerance:** velmi nízká pro dostupnost; transformace ne nutná.

### Turnaround aplikace (low business / low tech)

- **Potenciálně strategické**, ale ještě neprokázané.
- Aplikace v inkubaci nebo technologie ve fázi adoption.
- Příklady: experimentální AI feature, blockchain pilot, IoT zařízení v prvních pilotech.
- **Risk management:** rychlý prototyping, validace business hypotézy, malé investice, rapid iteration.
- **Failure tolerance:** vysoká — selhání = lekce, malý dopad.

### Support aplikace (low business / low tech)

- **Podpůrné**, často administrativní.
- Aplikace, které nepřidávají hodnotu, ale firma je potřebuje.
- Příklady: účetní software, intranet, HR self-service portal.
- **Risk management:** outsourcing, SaaS, cloud (commoditizace).
- **Failure tolerance:** střední — můžete pár dní bez toho fungovat, ale produktivita klesne.

## Implikace pro investiční rozhodování

| Kvadrant | Investiční politika | Sourcing |
|---|---|---|
| Strategické | Maximální investice, prioritní | In-house, vlastní tým |
| Factory | Vysoké investice na stabilitu | Hybrid, ověřená řešení |
| Turnaround | Malé experimentální investice | Pilot, agile, partnerství |
| Support | Minimální, optimalizace nákladů | Outsourcing, SaaS, cloud |

Investiční politika přímo navazuje na rizikový profil — strategické aplikace jsou „bet the company" investice, zatímco support se řídí logikou minimalizace nákladů. Sourcing strategie pak rozhoduje, kde firma drží vlastní know-how a kde naopak využívá trhu.

## Risk profile per quadrant

- **Strategické:** Nejvyšší riziko (technologické + tržní + konkurenční), ale i nejvyšší výnos. Vyžaduje aktivní [[taktiky-rizeni-rizik|redukci rizika]].
- **Factory:** Riziko **dostupnosti**, kybernetické (cross-link [[kyberneticka-bezpecnost]] z [[imork|Management oborových řešení]]). [[bcm|BCM]] kritický.
- **Turnaround:** Riziko **neúspěchu pilotního projektu**, ale finančně omezené. Lze tolerovat (retence).
- **Support:** Nízké riziko, řešitelné standardními metodami (SaaS SLA, pojištění).

Klíčová pointa: **stejné riziko (např. výpadek aplikace) má v každém kvadrantu jiný dopad** — výpadek strategické aplikace ohrožuje konkurenční pozici, výpadek support aplikace zhorší produktivitu na pár dní.

## Vývoj aplikací mezi kvadranty

Aplikace **migrují** v čase:

- **Turnaround → Strategické** — pilot uspěl, business value se prokázala. Investice se navyšují.
- **Strategické → Factory** — konkurence dohnala, aplikace se stala „table stakes". Optimalizace nákladů.
- **Factory → Support** — technologie zkomoditovala, dostupné jako SaaS.
- **Strategické → Support** (vzácný path, často po failure) — aplikace ztratila strategický význam.

**Risk management** musí reflektovat tuto migraci — co bylo strategické, je dnes možná Support. Pravidelný review klasifikace aplikací (typicky ročně) je proto stejně důležitý jako review samotné [[mapa-rizik|mapy rizik]].

## Kombinace s portfolio analýzou

- Firma má **portfolio aplikací** v různých kvadrantech.
- Cíl: vyvážené portfolio (ne všechny strategické, ne všechny support).
- Reportingově: **Risk Committee** dostává mapu aplikací × kvadrantů × rizikových profilů.
- Roční review (analogicky [[mapa-rizik|mapě rizik]]).

Vyvážené portfolio znamená, že firma investuje **do strategických aplikací** (růst), zároveň **udržuje factory aplikace** (provoz), **experimentuje s turnaround** (budoucnost) a **minimalizuje náklady na support** (efektivita). Nerovnováha v jakémkoli směru je signál pro management.

## Kritika a omezení

- **Subjektivita** klasifikace — co je „high business value" je na úsudku managementu.
- **Statický pohled** — model nezachycuje dynamiku.
- **Příliš jednoduchý** pro velké firmy s hybridními aplikacemi.
- **Nezohlední technický dluh** — staré aplikace mohou být „strategicky" potřebné, ale technicky katastrofální.
- **Alternativy:** Gartner Pace Layered Architecture, ITIL service portfolio.

Přesto zůstává McFarlanův model **základním orientačním nástrojem** v IT governance — jeho síla je v jednoduchosti a komunikovatelnosti vůči netechnickému managementu.

## Souvislosti

- [[operacni-vyzkum]] — McFarlan klasifikuje aplikace, OR optimalizuje uvnitř.
- [[expertni-systemy]] — patří do kvadrantu Strategické nebo Turnaround.
- [[investicni-rozhodovani-bot]] — investiční rozhodování o klíčových IS/IT projektech.
- [[mapa-rizik]] — analogická 2×2 vizualizace, ale pro rizika.
- [[taktiky-rizeni-rizik]] — strategie liší podle kvadrantu.
- cross-course: [[bcm]] (imork) — BCM zejména pro Factory aplikace, [[kyberneticka-bezpecnost]] (imork) — pro všechny kvadranty s různou intenzitou.

## Navigace
- **Předchozí:** [[operacni-vyzkum]]
- **Navazující:** [[expertni-systemy]]
- **Související:** [[investicni-rozhodovani-bot]]
