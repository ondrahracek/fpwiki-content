---
title: BCM — Řízení kontinuity činnosti
courses: [imork]
type: topic
tags: [imork, bcm, kontinuita-cinnosti, iso-22301, bia, disaster-recovery]
sources: [raw/imork/2014 VUT_Bezp BCM-2021.pdf, raw/imork/2013 VUT_Bezp DR-2021.pdf]
created: 2026-04-12
updated: '2026-05-04'
---

# BCM — Řízení kontinuity činnosti

![[bcm-rpo-rto.jpeg|Časová osa incidentu — RPO, detekce, MBCO, RTO, plná obnova]]

Identifikuje potenciální dopady incidentů a zajišťuje kontinuitu a obnovu klíčových procesů organizace na předem stanovenou minimální úroveň.

## Klíčové pojmy

| Pojem | Anglicky | Popis |
|---|---|---|
| **BCMS** | Business Continuity Management System | Plánovaný, kontinuální a dokumentovaný systém |
| **BCM** | Business Continuity Management | Činnost identifikující dopady a zajišťující kontinuitu |
| **BIA** | Business Impact Analysis | Identifikace kritických činností (orientace na dopad, ne příčinu) |
| **MBCO** | Minimum Business Continuity Objective | Minimální přijatelná úroveň služeb |
| **RPO** | Recovery Point Objective | Do jakého bodu v minulosti lze obnovit data |
| **RTO** | Recovery Time Objective | Čas potřebný pro obnovu provozu |

## PDCA cyklus pro BCMS

| Fáze | Obsah |
|---|---|
| **Plan** | Kontext, požadavky, rozsah, politika, BIA, posouzení rizik |
| **Do** | Strategie kontinuity, implementace plánů, cvičení |
| **Check** | Monitoring, audit, přezkoumání managementem |
| **Act** | Nápravná opatření, neustálé zlepšování |

## ISO 22301:2019 — struktura

- Kap. 4 — kontext organizace
- Kap. 5 — vedení (leadership)
- Kap. 6 — plánování (BIA, rizika)
- Kap. 7 — podpora (kompetence, dokumentace, komunikace)
- Kap. 8 — provoz (strategie, plány, cvičení)
- Kap. 9 — hodnocení výkonnosti (monitoring, audit)
- Kap. 10 — zlepšování (neshody, nápravná opatření)

## Analýza STEEPLE

| Faktor | Oblast |
|---|---|
| **S**ociální | Zaměstnanost, bezpečnost, komunity |
| **T**echnologický | Závislost na technologiích |
| **E**konomický | Ekonomická situace, finanční instituce |
| **E**tický | Podnikatelská etika, média, veřejnost |
| **P**olitický | Politický systém, hrozba nepokojů |
| **L**egislativní | Předpisy, zákony |
| **E**nvironmentální | Životní prostředí, přírodní hrozby |

## BIA (Business Impact Analysis)

### Dva způsoby provedení

1. **Bottom-up** — sběr od provozních manažerů směrem nahoru; detailní znalost procesů, ale časově náročné.
2. **Top-down** — od vyššího managementu; rychlejší, ale může opomenout provozní detaily.

### Principy BIA

- Orientace na **dopad**, ne na příčinu — nezkoumá *co se stane*, ale *jaké budou následky*.
- **Kalendář klíčových ročních událostí** — identifikuje období se zvýšenou kritičností (uzávěrky, sezónní špičky).

## Mapování procesů

- **Víceúrovňové mapování** — od strategických procesů po operativní detaily.
- **Identifikace zdrojů** — lidé, technologie, prostory, dodavatelé potřební pro každý proces.
- **SPoF** (Single Point of Failure) — identifikace jediných bodů selhání, jejichž výpadek zastaví celý proces.

## Strategie kontinuity

### 4 kroky strategie

1. **Reakce na incident** — okamžitá odezva, aktivace krizového řízení.
2. **Obnova kritických činností** — prioritní obnovení klíčových procesů dle BIA.
3. **Vztahy se stakeholdery** — komunikace se zainteresovanými stranami.
4. **Nekritické činnosti** — postupná obnova ostatních procesů.

### 4 scénáře narušení

1. **Zamezení přístupu** — nedostupnost budov/prostor (požár, povodeň).
2. **Nedostatek pracovníků** — pandemie, hromadná absence.
3. **Selhání technologie** — výpadek ICT, kybernetický útok.
4. **Selhání dodavatele** — přerušení dodavatelského řetězce.

## Implementace plánů

### Obsah plánu kontinuity

Účel a rozsah, role a odpovědnosti, aktivační kritéria, **DRP** (Disaster Recovery Plan) pro IT infrastrukturu, kontaktní seznamy, priority obnovy dle BIA. Dlouhodobá obnova je řízena jako **samostatný projekt**.

## Testování BCM

| Forma | Popis |
|---|---|
| **Tabletop review** | Teoretické procházení scénářů |
| **Walkthrough** | Krokové ověření postupů s účastníky |
| **Full exercise** | Simulace reálného incidentu |

Zásady: **neočekávané testy** pro ověření reálné připravenosti; v krizové situaci **direktivní řízení pod tlakem** (centralizované rozhodování).

## VKB — Vyhláška o kybernetické bezpečnosti

**§15 vyhlášky č. 82/2018 Sb.** vyžaduje:

- **MBCO** — minimální úroveň služeb pro kontinuitu
- **RTO** — maximální přípustná doba výpadku
- **RPO** — maximální přípustná ztráta dat

Příloha č. 5, bod **1.23 Politika řízení kontinuity** — požadavky na dokumentaci a řízení BCM.

## ISO/IEC 27031:2025

Připravenost ICT pro kontinuitu podnikání — propojení mezi kritickou infrastrukturou a BCMS. Aktuální vydání 2025 (první 2011, dlouho jediné, novelizace 2025).

## BCMaaS

**BCM as a Service** — cloudový model poskytování BCM, outsourcing plánování a řízení kontinuity, vhodný zejména pro menší organizace bez vlastních kapacit.

## Disaster Recovery (DR)

Předem stanovený scénář obnovy provozu po havárii — součást BCM.

### 7 úrovní DR (Tiers)

| Tier | Popis |
|---|---|
| 0 | Žádná off-site data |
| 1 | Fyzická záloha + cold site |
| 2 | Fyzická záloha + hot site |
| 3 | Elektronický trezor (electronic vaulting) |
| 4 | Point-in-time recovery |
| 5 | Two-site commit (kontinuální přenos) |
| 6 | Minimální až nulová ztráta dat (zrcadlení) |
| 7 | Automatizovaná obnova (AI monitoring) |

### Cloud DR

- **Cold DR** — nejlevnější, nejdelší odstávka
- **Warm DR** — aktualizované zálohy u poskytovatele
- **Hot DR** — paralelní řešení v tandemu
- **DRaaS** — Disaster Recovery as a Service (řízené/asistované/vlastní)

## Související stránky

- [[isms|ISMS]] — BCM jako součást bezpečnostního systému
- [[rizeni-rizik|Řízení rizik]] — krizové plány pro zbytková rizika
- [[kyberneticka-bezpecnost|Kybernetická bezpečnost]] — reakce na incidenty
- [[imork-bcm|Záznam přednášky BCM]] — bibliografická karta zdroje
- [[imork-dr|Disaster Recovery — záznam přednášky]] — DR detail
