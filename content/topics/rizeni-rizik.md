---
title: Řízení rizik
courses: [imork]
type: topic
tags: [imork, rizeni-rizik, iso-31000, iso-27005, nist, hodnoceni-rizik]
sources: [raw/imork/2003 VUT_Bezp Risk Mngmt-2021.pdf, raw/imork/2001 VUT_Bezp Managerská 2022.pdf]
created: 2026-04-12
updated: '2026-05-04'
---

# Řízení rizik

![[rizeni-rizik-proces.jpeg|Proces řízení rizik — šest fází od stanovení kontextu po monitorování]]

Komplexní proces identifikace, analýzy a ošetření rizik ohrožujících bezpečnost informací v organizaci. Tvoří jádro [[isms|ISMS]].

> [!info] Související pohled v kurzu [[irmank|IrmanK]] — Risk management
> Tento topic pokrývá **kybernetické / informační** riziko podle ISO/IEC 27005. Pro **podnikové (enterprise) riziko** v širším smyslu (finanční, strategické, change-driven) viz odpovídající stránky kurzu [[irmank|IrmanK]]:
>
> - [[definice-rizika]] — 10 definic rizika, podnikatelské riziko, postoj k riziku
> - [[mereni-rizika]] — statistické charakteristiky (σ, σ², KV)
> - [[mapa-rizik]] — $R = D \times P$, matice 5×5, tři barevné zóny
> - [[taktiky-rizeni-rizik]] — vyvárování / udržení / redukce / přenos
> - [[klasifikace-rizik]] — kritické × důležité × běžné; dynamické × statické; čisté × spekulativní
> - [[metody-snizovani-rizika]] — 6 strategií, ofenzivní řízení
>
> Oba pohledy se doplňují: ISMS / ISO 27005 je specializace pro **informační rizika**, IrmanK je obecné podnikové riziko.

## Normativní základ

| Norma | Zaměření |
|---|---|
| **ISO 31000:2018** | Obecné směrnice pro management rizik |
| **IEC 31010:2019** | Techniky posuzování rizik |
| **ISO/IEC 27005:2022** | Řízení rizik bezpečnosti informací |
| **NIST SP 800-30** | Průvodce hodnocením rizik |
| **NIST SP 800-39** | Proces řízení bezpečnostních rizik |

## Proces řízení rizik (ISO/IEC 27005)

1. **Stanovení kontextu** — rozsah, kritéria, metodika, role
2. **Identifikace rizik** — aktiva, hrozby, zranitelnosti
3. **Analýza rizik** — kvantifikace nebo kvalitativní popis
4. **Vyhodnocení rizik** — prioritizace dle kritérií
5. **Zvládání rizik** — výběr opatření (redukce, přenos, retence, vyhnutí)
6. **Akceptace rizik** — formální rozhodnutí
7. **Komunikace** — sdílení informací o rizicích
8. **Monitorování** — průběžné přezkoumávání

## Výpočet hodnoty rizika

**Riziko = dopadová hodnota aktiva × hrozba × zranitelnost**

- **Hrozba** — potenciální příčina incidentu (stupnice 1–5)
- **Zranitelnost** — slabé místo aktiva (stupnice 1–5)
- **Dopad** — hodnota aktiva při ztrátě CIA

## Obecný model hodnocení rizik

Hrozba → Systém → Zranitelnost → Zneužitelnost? → Riziko → Přijatelné? → Opatření/Zbytkové riziko

## Klíčové dokumenty

- **RTP** (Risk Treatment Plan) — plán zvládání rizik s vybranými opatřeními pro jednotlivá rizika, odpovědnými osobami, termíny implementace, potřebnými zdroji.
- **SoA / PoA** (Statement of Applicability / Prohlášení o aplikovatelnosti) — seznam všech opatření z Přílohy A normy ISO 27001 s uvedením, zda je opatření aplikováno, zdůvodnění zahrnutí/vyloučení a stavu implementace.

## Metodika pro organizace s KII / VIS

Specifický postup hodnocení rizik dle požadavků zákona o kybernetické bezpečnosti (**ZKB 181/2014 Sb.**) a prováděcích vyhlášek pro organizace provozující:

- **KII** — kritickou informační infrastrukturu
- **VIS** — významné informační systémy

## Bezpečnostní role dle ZKB

- **Výbor pro řízení KB** — organizovaná skupina pro celkové řízení
- **Manažer KB** — odpovědný za ISMS
- **Architekt KB** — návrh a implementace opatření
- **Auditor KB** — provádění auditů
- **Garant aktiva** — zajištění rozvoje a bezpečnosti aktiva

## Tří-úrovňový model (NIST SP 800-39)

| Úroveň | Zaměření | Typ rizika |
|---|---|---|
| Stupeň 1 | Organizace | Strategické riziko |
| Stupeň 2 | Poslání/obchodní procesy | Taktické riziko |
| Stupeň 3 | Informační systémy | Operační riziko |

## Související stránky

- [[isms|ISMS]] — řízení rizik jako součást systému
- [[bcm|BCM]] — kontinuita činnosti při materializaci rizik
- [[imork-dr|Disaster Recovery]] — obnova po havárii
- [[kyberneticka-bezpecnost|Kybernetická bezpečnost]] — kontext hrozeb
- [[imork-risk-management|Záznam přednášky Risk Management]] — bibliografická karta zdroje
- [[imork-manazerska-bezpecnost|Manažerská bezpečnost]] — governance kontext
