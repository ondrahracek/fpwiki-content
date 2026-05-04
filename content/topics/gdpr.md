---
title: GDPR — Obecné nařízení o ochraně osobních údajů
courses: [imork]
type: topic
tags: [imork, gdpr, ochrana-dat, pii, dpia, iso-27701, privacy-by-design]
sources: [raw/imork/2109 VUT_Bezp Případovka Krádež dat_2020.pdf, raw/imork/2017 VUT_Ochrana dat-2022.pdf, raw/imork/2105 VUT_Bezp_Případovka eHealth_2021.pdf, raw/imork/2204 VUT_Bezp_Případovka Payment_2022.pdf, raw/imork/2004 VUT_Bezp akademici-2021.pdf]
created: 2026-05-04
updated: '2026-05-04'
---

# GDPR — Obecné nařízení o ochraně osobních údajů

**Nařízení Evropského parlamentu a Rady (EU) 2016/679** — General Data Protection Regulation. Účinnost od **25. května 2018** ve všech členských státech EU bez nutnosti transpozice. Pro Českou republiku doplněno **zákonem č. 110/2019 Sb.** o zpracování osobních údajů.

GDPR je v kurzu [[imork|ImorK]] napříč více oblastmi: legislativní rámec [[ochrana-dat|ochrany dat]], povinný kontext pro [[imork-zdravotnictvi|zdravotnická data]], [[imork-payment|platební údaje]] a [[imork-ehealth|eHealth]] služby, a operační rámec definovaný v [[imork-kradez-dat|případové studii o krádeži dat]] (DPIA, Privacy by Design, ISO 27701).

## Klíčové pojmy

| Pojem | Anglicky | Definice |
|---|---|---|
| **Osobní údaj** | Personal data | Jakákoli informace identifikující nebo umožňující identifikaci žijící fyzické osoby |
| **Zvláštní kategorie** | Special category | Citlivá data: zdraví, biometrika, etnicita, sexuální orientace, politické názory, náboženství, členství v odborech |
| **Subjekt údajů** | Data subject | Fyzická osoba, k níž se osobní údaje vztahují |
| **Správce** | Controller | Subjekt, který určuje účely a prostředky zpracování |
| **Zpracovatel** | Processor | Subjekt zpracovávající osobní údaje na pokyn správce |
| **DPO** | Data Protection Officer | Pověřenec pro ochranu osobních údajů — povinný pro orgány veřejné moci a velké zpracovatele |
| **PII** | Personally Identifiable Information | Pojem z NIST SP 800-122; v EU se používá ekvivalentní „osobní údaj" |

## Šest zásad zpracování (čl. 5)

1. **Zákonnost, korektnost, transparentnost** (lawfulness, fairness, transparency)
2. **Účelové omezení** (purpose limitation) — sběr pouze pro stanovené účely
3. **Minimalizace údajů** (data minimisation) — jen nezbytné údaje
4. **Přesnost** (accuracy) — udržovat aktuální, opravovat nepřesné
5. **Omezení uložení** (storage limitation) — uchovávat ne déle než nutné
6. **Integrita a důvěrnost** (integrity, confidentiality) — bezpečnost zpracování

Sedmá zásada **odpovědnost** (accountability, čl. 5 odst. 2) — správce musí být schopen svůj soulad doložit.

## Šest právních titulů (čl. 6)

Zpracování je zákonné jen, je-li založeno na jednom ze šesti důvodů:

1. **Souhlas** subjektu údajů
2. **Plnění smlouvy** se subjektem
3. **Zákonná povinnost** správce
4. **Životně důležité zájmy** subjektu nebo jiné osoby
5. **Veřejný zájem** nebo výkon veřejné moci
6. **Oprávněné zájmy** správce (s testem proporcionality)

## Práva subjektů údajů (čl. 15–22)

- **Právo na informace** — kdo, proč, na základě čeho, jak dlouho zpracovává
- **Právo na přístup** k osobním údajům
- **Právo na opravu** nepřesných údajů
- **Právo na výmaz** („right to be forgotten", čl. 17)
- **Právo na omezení zpracování**
- **Právo na přenositelnost údajů** ke konkurenci (čl. 20)
- **Právo vznést námitku** proti zpracování
- **Právo nebýt předmětem automatizovaného rozhodování** vč. profilování (čl. 22)

## DPIA — Data Protection Impact Assessment (čl. 35)

Posouzení vlivu na ochranu osobních údajů — povinné, pokud zpracování pravděpodobně způsobí vysoké riziko pro práva a svobody subjektů.

### Kdy je DPIA povinná

- Systematické a rozsáhlé hodnocení osobních aspektů (profilování)
- Rozsáhlé zpracování zvláštních kategorií údajů
- Rozsáhlé sledování veřejně přístupných míst (kamery v ulicích, MHD)

### Tři analýzy DPIA (per ISO 27701)

| Analýza | Zaměření |
|---|---|
| **DPIA** | Posouzení dopadu na svobody a práva osob (čl. 35 GDPR) |
| **Datová** | Význam dat, vazby, identifikace osobních a citlivých dat |
| **Procesní** | Kdo a jak přistupuje k osobním datům, automatizované zpracování |

### Pět kroků hodnocení rizik

1. Definice operace zpracování a kontextu
2. Pochopení a hodnocení dopadu (CIA)
3. Definice hrozeb a hodnocení pravděpodobnosti
4. Vyhodnocení rizika (matice pravděpodobnost × dopad)
5. Výběr bezpečnostních opatření

## Privacy by Design & Privacy by Default (čl. 25)

- **Privacy by Design** — proaktivní zahrnutí ochrany od počátku návrhu systému; ochrana zabudovaná do architektury, ne dolepovaná
- **Privacy by Default** — výchozí nastavení musí chránit; ověření účelu, rozsahu, sdílení a možností anonymizace před zpracováním
- Orientace na **subjekt údajů** — analýza rizik z pohledu jednotlivce, ne organizace

## Oznamovací povinnost při porušení zabezpečení (čl. 33–34)

| Příjemce | Lhůta | Podmínka |
|---|---|---|
| **Dozorový úřad** (ÚOOÚ v ČR) | **72 hodin** od zjištění | Vždy, pokud existuje pravděpodobnost rizika pro subjekty |
| **Subjekty údajů** | Bez zbytečného odkladu | Pokud existuje **vysoké** riziko pro jejich práva |

## Sankce (čl. 83)

Pokuty ve dvou pásmech:

- **Až 10 mil. EUR nebo 2 % celosvětového ročního obratu** (vyšší z obou) — porušení procesních povinností (DPO, smlouva se zpracovatelem, oznámení porušení, DPIA)
- **Až 20 mil. EUR nebo 4 % celosvětového ročního obratu** — porušení zásad zpracování, práv subjektů, podmínek souhlasu, předávání mimo EU

## ISO/IEC 27701 — PIMS

Privacy Information Management System — rozšíření ISO 27001/27002 o správu osobních informací. První vydání **2019**, aktuální vydání **2025**. Mapuje požadavky GDPR na konkrétní opatření a slouží jako certifikovatelný průvodce souladem. Zavádí DPIA, datovou a procesní analýzu jako standardní postupy. Detail v [[imork-kradez-dat|případové studii o krádeži dat]] a v hub topiku [[ochrana-dat]].

## Vztah k dalším normám a regulacím

- **NIST SP 800-122** (2010) — Guide to Protecting PII Confidentiality (americký analog)
- **NISTIR 8062** (2017) — Privacy Engineering and Risk Management
- **FIPP** — Fair Information Practice Principles (univerzální zásady, předchůdce GDPR)
- **eIDAS** (nařízení EU 910/2014, novelizováno **nařízením (EU) 2024/1183 — „eIDAS 2.0"**, v účinnosti od května 2024) — elektronická identifikace a služby vytvářející důvěru; eIDAS 2.0 zavádí **evropskou peněženku digitální identity (EUDI Wallet)**. Doplňuje GDPR pro digitální identitu (viz [[ochrana-dat|Ochrana dat]])
- **NIS2** (směrnice 2022/2555) — kybernetická bezpečnost, povinnosti hlášení překrývají GDPR čl. 33
- **DORA** (nařízení EU 2022/2554) — finanční sektor, viz [[imork-financni-sektor|Finanční sektor]]
- **HIPAA** (USA) — americký analog pro zdravotnictví, viz [[imork-zdravotnictvi|Zdravotnictví]]

## Předávání údajů mimo EU (kap. V GDPR)

- **Adekvátní rozhodnutí Komise** — země s odpovídající úrovní ochrany: Andorra, Argentina, Brazílie, Faerské ostrovy, Guernsey, Isle of Man, Izrael, Japonsko, Jersey, Jižní Korea, Kanada (komerční subjekty), Nový Zéland, Spojené království, Švýcarsko, Uruguay, USA (EU-US Data Privacy Framework)
- **Standardní smluvní doložky** (SCC) — od 2021 nová verze po Schrems II
- **Závazná podniková pravidla** (BCR) pro nadnárodní skupiny
- **Výjimky** — výslovný souhlas, plnění smlouvy, životně důležité zájmy

## Aplikační oblasti v kurzu [[imork|ImorK]]

- [[imork-zdravotnictvi|Zdravotnictví]] — zvláštní kategorie (zdravotní data); ISO 27799 + GDPR
- [[imork-ehealth|eHealth]] — soulad s legislativou jako jeden ze tří pilířů důvěryhodnosti elektronického zdravotnictví
- [[imork-payment|Bezpečnost plateb]] — platební údaje a PCI DSS v kombinaci s GDPR
- [[imork-akademicke-prostredi|Akademické prostředí]] — soulad s GDPR jako cíl bezpečnostní politiky univerzity
- [[imork-kradez-dat|Krádež dat]] — provozní implementace GDPR přes ISO 27701, DPIA, Privacy by Design

## Související stránky

- [[ochrana-dat|Ochrana dat]] — technologická vrstva (DLP, šifrování, anonymizace)
- [[isms|ISMS]] — manažerský rámec, ISO 27701 jako rozšíření 27001
- [[rizeni-rizik|Řízení rizik]] — DPIA jako analýza rizik z pohledu subjektů údajů
- [[imork-kradez-dat|Krádež dat — případová studie]] — primární zdroj operačního výkladu
- [[imork-digitalni-identita|Digitální identita a stopa]] — PII a digitální stopa
