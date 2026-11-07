---
title: Audit informačních systémů
course: ipis2k
type: topic
tags: [ipis2k, audit, compliance, soc, sox]
sources: [raw/ipis2k/prezentace.pdf, "https://www.iso.org/standard/27001", "https://www.sec.gov/files/rules/final/33-8238.htm", "https://www.aicpa-cima.com/resources/landing/system-and-organization-controls-soc-suite-of-services", "https://www.iaasb.org/publications/staff-overview-international-standard-assurance-engagements-isae-3402-assurance-reports-controls", "https://www.sec.gov/resources-small-businesses/capital-raising-building-blocks/sec-filer-status-reporting-status"]
created: 2026-11-06
updated: 2026-11-06
---

# Audit informačních systémů

> [!tldr] V kostce
> - Audit porovnává skutečný stav s předem danými kritérii a svůj závěr opírá o důkazy.
> - Předmětem může být informace, proces i návrh a fungování IT kontrol.
> - SOC určuje, čeho se zpráva týká; Type 1 a Type 2 rozlišují okamžik a období ověření.

> [!example] Účetní systém není izolovaný
> Přijímá údaje z objednávek, skladu a banky. Vedoucí proto z obrazovky nepozná, zda se údaje přenesly úplně, zda jsou změny dohledatelné ani zda přístupy odpovídají rolím. Nezávislé ověření těchto otázek je typická úloha auditu IS.

![[ipis2k-audit-ilustrace-v2.png|Pravidla jako kniha, důkazy pod lupou a zpráva se závěrem auditu.]]

## Co audit ověřuje

Audit je objektivní ověření skutečnosti vůči **kritériu**: internímu pravidlu, smluvnímu požadavku, zákonu nebo zvolenému standardu. Nejde o hledání viníka, ale o zpětnou vazbu pro řízení:

- **závěr** říká, zda stav kritériu přiměřeně odpovídá,
- **nález** ukazuje odchylku a prostor pro zlepšení.

V auditu IS může být předmětem ujištění například informace, postup, politika, systémové nastavení nebo kontrola. Auditor si proto nejdřív vyjasní čtyři věci:

| Prvek | Otázka |
|---|---|
| Předmět | Co přesně se posuzuje: například správa účtů v účetní aplikaci? |
| Kritérium | Podle čeho se stav porovná: schválená politika, smlouva nebo standard? |
| Důkaz | Čím se závěr podloží: záznamem, konfigurací, rozhovorem, pozorováním či výběrem případů? |
| Výrok | Jaký závěr lze z důkazů o stavu a případných odchylkách vyvodit? |

Předmět musí být vymezen dostatečně konkrétně. Věta „prověřili jsme bezpečnost“ není ověřitelný rozsah. Naproti tomu „ověřili jsme, zda jsou administrátorské účty schvalovány a jejich použití dohledatelné“ určuje, co hledat a jaké důkazy mají smysl.

> [!important] Pořadí uvažování
> 1. Nejprve je dostupné **kritérium**.
> 2. Potom se hledají důkazy o skutečném stavu.
> 3. Nakonec z nich plyne přiměřený závěr.
>
> Auditor tedy nemá nejprve označit stav za chybný a až pak hledat pravidlo. Prohlášení pracovníka může vysvětlit postup, ale záznam o schválení, konfigurace a výběr reálných případů ukazují, zda se skutečně provádí.

Dobře provedený audit je komplexní v relevantním rozsahu, objektivní, nezávislý a formalizovaný. Komplexnost neznamená kontrolovat vše; znamená nezanedbat vazby, které mohou ovlivnit závěr. Formalizace chrání dohledatelnost postupu. Nezávislost omezuje konflikt zájmů mezi auditorem, zadavatelem a posuzovaným objektem.

![[ipis2k-audit-kriteria-v2.png|Audit porovnává skutečný stav s kritériem; důkazy vedou k auditnímu nálezu nebo závěru.]]

## Kontroly a způsoby jejich ověření

### Obecné IT kontroly a aplikační kontroly

| Druh kontroly | Co pokrývá |
|---|---|
| **Obecné IT kontroly (ITGC)** | Prostředí, ve kterém aplikace fungují: přístupy, provoz, změny a vývoj. |
| **Aplikační kontroly** | Konkrétní zpracování dat a transakcí v podnikovém procesu. Mohou být manuální nebo automatizované. |

Kontrola může být **preventivní** — brání nežádoucímu jednání — nebo **detektivní** — pomáhá jej odhalit. Toto rozlišení neříká, zda jde o aplikační kontrolu, nebo ITGC; popisuje její působení.

### Test kontroly versus test věcné správnosti

| Postup | Na jakou otázku odpovídá |
|---|---|
| **Test kontroly** | Fungovala kontrola v posuzovaném období účinně? |
| **Test věcné správnosti** | Obsahují ověřované informace nebo transakce významnou nesprávnost? |

První postup získává důkaz o fungování kontroly, druhý přímo o správnosti ověřovaných údajů. Správnost několika transakcí proto sama neprokazuje, že kontrola fungovala po celé období.

**CAAT** (*Computer Assisted Audit Techniques*) jsou počítačově podporované auditorské techniky. Nástroje pomáhají zpracovat a prověřit data; nenahrazují vymezení cíle auditu ani úsudek auditora.

## Compliance, finanční výkaznictví a IT

**Compliance** znamená soulad s požadavky, které se na organizaci vztahují:

- právními,
- smluvními,
- dobrovolně přijatým rámcem.

IT do compliance vstupuje, když systém zpracovává regulovaná data, vytváří podklady pro účetnictví nebo zajišťuje kontrolní postup.

Certifikace systému řízení organizace není certifikací každého jejího produktu. ISO uvádí, že organizace mohou zavést ISO/IEC 27001 bez certifikace; pokud certifikaci chtějí, vydává ji externí certifikační orgán. ISO/IEC 27001:2022 stanovuje požadavky na systém řízení bezpečnosti informací, ne obecné tvrzení, že každý produkt organizace je bezchybný nebo bezpečný ve všech situacích.

Účetní selhání, jakým byl případ Enronu, připomíná význam spolehlivého vykazování a kontrol. Audit proto neposuzuje jen aritmetickou správnost částek, ale také procesy a podmínky, za nichž informace vznikají.

Sekce 404 zákona Sarbanes–Oxley (SOX) se věnuje interním kontrolám nad finančním výkaznictvím. U subjektů v jejím rozsahu upravuje odpovědnost vedení za jejich posouzení; samostatné požadavky na auditorské ověření mají výjimky podle postavení emitenta. Z toho neplyne, že každý podnik nebo každý IT systém automaticky podléhá SOX. Dopad na IT vzniká zejména tam, kde IT kontroly podporují spolehlivost finančního výkaznictví.

## Ujištění o kontrolách poskytovatele služeb

Když organizace využívá outsourcing nebo cloudovou službu, nemůže její auditor běžně vstoupit do každého datového centra poskytovatele. Poskytovatel proto může předložit nezávislou zprávu o svých kontrolách. Pro kontroly poskytovatele relevantní k finančnímu výkaznictví zákazníka existuje také mezinárodní standard **ISAE 3402**. Určuje rámec takového ujišťovacího ověření; nejde o univerzální certifikát bezpečnosti služby.

Zpráva je vstupem do posouzení zákazníka, nikoli univerzálním potvrzením, že zákazník nemá žádná vlastní rizika. Stále musí vyhodnotit rozsah služby, svá nastavení a případné odpovědnosti uživatelské organizace.

### SOC 1, SOC 2 a SOC 3: nejprve účel zprávy

Označení **SOC** (*System and Organization Controls*) vyjadřuje zejména účel a zamýšlené uživatele zprávy.

| Zpráva | Hlavní předmět | Typičtí uživatelé |
|---|---|---|
| SOC 1 | Kontroly u poskytovatele, které mohou být relevantní pro interní kontrolu zákazníka nad finančním výkaznictvím | zákaznická organizace a její auditor |
| SOC 2 | Kontroly systému ve vztahu ke kritériím důvěryhodných služeb, například bezpečnosti | určené strany se znalostí potřebných souvislostí |
| SOC 3 | Stručnější zpráva pro obecné použití o stejném typu systémových kontrol jako SOC 2 | širší veřejnost |

SOC 1 tedy neznamená „lepší SOC 2“. Odpovídá na jinou otázku: zda jsou kontroly poskytovatele relevantní pro finanční výkaznictví zákazníka. SOC 2 se zaměřuje na systém a příslušná kritéria důvěryhodných služeb. SOC 3 je určen ke sdílení s širším publikem, proto nemá nahrazovat detailní podklad, který potřebuje auditor zákazníka. Aktuální sadu služeb SOC a její ilustrativní zprávy spravuje AICPA.

SOC 2 pracuje s kategoriemi kritérií důvěryhodných služeb: **bezpečnost, dostupnost, integrita zpracování, důvěrnost a soukromí**. Dostupnost se týká použitelnosti služby, integrita zpracování úplnosti, správnosti, platnosti, včasnosti a oprávněnosti zpracování dat; důvěrnost chrání vymezené důvěrné informace a soukromí se vztahuje k osobním údajům. U konkrétní zprávy je nutné zjistit, které kategorie zahrnuje — samotné označení SOC 2 rozsah neříká.

### Type 1 a Type 2: potom datum nebo období ověření

Type 1 a Type 2 nejsou dalšími druhy SOC vedle SOC 1, SOC 2 a SOC 3. Vyjadřují, zda se posouzení vztahuje k určitému datu, nebo také k fungování během období:

- **Type 1** posuzuje popis systému a vhodnost návrhu kontrol k určitému datu.
- **Type 2** vedle návrhu posuzuje i provozní účinnost kontrol za vymezené období.

> [!example] Účet bývalého zaměstnance
> - **Type 1:** lze doložit, že politika vyžaduje zrušení účtu a kontrola je navržena.
> - **Type 2:** důkazy z období ukazují, zda se skutečné odchody řešily podle ní.
>
> Dokumentovaná politika tedy sama o sobě neprokazuje fungování kontroly.

## Posouzení závažnosti nálezu

Nález získá význam až v kontextu:

- **dopadu** a **pravděpodobnosti**,
- kompenzačních kontrol,
- rozsahu oprávnění, skutečného použití a dostupnosti systému.

Aktivní účet bývalého pracovníka proto může být závažný, ale nehodnotí se jen jeho existence. Stejně tak audit nástroje s umělou inteligencí nezačíná nálepkou technologie: vymezuje oprávnění nástroje, možné následky jeho akcí a důkazy o nastavených kontrolách.

U nástroje s umělou inteligencí se posuzuje i to, kdo schvaluje jeho výstupy a zda lze dohledat provedené akce. Lidské schválení nezbavuje schvalujícího odpovědnosti; u akcí s dopadem nestačí, že výsledek na pohled působí správně.

## Související stránky

- [[rizeni-informatiky-a-itgc|Řízení informatiky a kontroly ITGC]] — kontroly, které mohou tvořit důkazní základ finančního auditu
- [[cloud-computing|Cloud computing]] — rozdělení odpovědností mezi zákazníka a poskytovatele
- [[isms|ISMS]] — řízení bezpečnosti informací
- [[rizeni-rizik|Řízení rizik]] — posouzení dopadu auditních zjištění

## Reference

NOVÁK, Lukáš. *Podnikové informační systémy 2*. Výuková prezentace. Fakulta podnikatelská VUT v Brně, 2026.

- ISO, [ISO/IEC 27001:2022 — Information security management systems](https://www.iso.org/standard/27001).
- Viz také SEC, [SEC Filer Status and Reporting Status](https://www.sec.gov/resources-small-businesses/capital-raising-building-blocks/sec-filer-status-reporting-status), k rozdílům povinností emitentů. U.S. Securities and Exchange Commission, [Management's Report on Internal Control Over Financial Reporting and Certification of Disclosure in Exchange Act Periodic Reports](https://www.sec.gov/files/rules/final/33-8238.htm).
- AICPA & CIMA, [System and Organization Controls: SOC Suite of Services](https://www.aicpa-cima.com/resources/landing/system-and-organization-controls-soc-suite-of-services).

- IAASB, [ISAE 3402 — Assurance Reports on Controls at a Service Organization](https://www.iaasb.org/publications/staff-overview-international-standard-assurance-engagements-isae-3402-assurance-reports-controls).

- AICPA & CIMA, [Trust Services Criteria](https://www.aicpa-cima.com/resources/download/2017-trust-services-criteria-with-revised-points-of-focus-2022).
