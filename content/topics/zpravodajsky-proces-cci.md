---
title: Zpravodajský proces CCI — 9 kroků
course: icink
type: topic
tags: [icink, counter-ci, zpravodajsky-proces, obchodni-tajemstvi]
sources: [raw/icink/IcinK-poznamky_z_prednasek.docx]
created: 2026-05-21
updated: '2026-05-21'
---

# Zpravodajský proces CCI — 9 kroků

Defenzivní protějšek ofenzivního [[zpravodajsky-proces-ci|zpravodajského procesu CI]]. Devět činností [[counter-competitive-intelligence|Counter Competitive Intelligence]], které musí firma kvalitně zabezpečit, aby chránila své [[obchodni-tajemstvi-ochrana|obchodní tajemství]] a identifikovala zpravodajskou činnost konkurence proti sobě.

> **Bartes (kniha 2022, kap. 10):** Ve firmách obvykle **není vybudována tato složka CI** na úrovni odpovídající ofenzivnímu procesu. CCI proces se výrazně liší — má jiný postup, jiné role, jiný typ výstupu.

## Devět činností CCI procesu

```
       ┌──────────────────┐
       │ 1. Zadání úkolu  │ ← vedení / systém včasného varování / incident
       └────────┬─────────┘
                ▼
       ┌──────────────────┐
       │ 2. Ověření       │   ← VNITŘNÍ funkce (Red Team, audit obrany)
       │   funkčnosti     │   ← VNĚJŠÍ funkce (monitoring konkurence)
       │   obrany         │
       └────────┬─────────┘
                ▼
       ┌──────────────────┐
       │ 3. Analýza a     │
       │   formulace      │
       │   problému       │
       └────────┬─────────┘
                ▼
       ┌──────────────────┐
       │ 4. Plánování     │   stanovit co a kdo bude chránit
       │   postupu        │
       └────────┬─────────┘
                ▼
       ┌──────────────────┐
       │ 5. Sběr dat      │   vnitřní + vnější + kontrola zpracovatelů
       │   a informací    │
       └────────┬─────────┘
                ▼
       ┌──────────────────┐
       │ 6. Zpracování    │   třídění, kvalita, detekce dezinformace
       │   údajů          │
       └────────┬─────────┘
                ▼
       ┌──────────────────┐
       │ 7. Analýza       │   ACH; hypotézy = „kdo a proč nás vytěžuje"
       │   informace      │
       └────────┬─────────┘
                ▼
       ┌──────────────────┐
       │ 8. Zajištění     │   důkazy musí obstát v právním řízení
       │   důkazů         │
       └────────┬─────────┘
                ▼
       ┌──────────────────┐
       │ 9. Aktivní zásah │   organizační + právní + operativní kroky;
       │   + vyhodnocení  │   postmortem a poučení
       └──────────────────┘
```

### 1. Zadání úkolu

Vstupuje typicky:

- **Z vrcholového vedení** — strategické zadání ochrany konkrétní oblasti.
- **Z vlastní iniciativy CCI útvaru** — na základě **systému včasného varování** (identifikované signály úniku, podezřelé aktivity v okolí).
- **Z bezpečnostního incidentu** — reaktivní spuštění po identifikovaném úniku.

Stejně jako u ofenzivního CI: zadání bývá neúplné a vyžaduje **analýzu a zpřesnění** (krok 2).

### 2. Ověření funkčnosti obrany

> **Zásadní krok specifický pro CCI** — než řešíme externí hrozby, prověříme **vlastní systém ochrany**.

CCI proces má dvě paralelní funkce:

#### 2a. Vnitřní funkce CCI

Prověření stávajícího systému ochrany [[obchodni-tajemstvi-ochrana|obchodního tajemství]]:

- Jak je obchodní tajemství **definováno vedením** firmy?
- Jaké jsou **rozsah pravomocí a povinností** — systém pro ukládání informací, materiálů?
- Existuje **„zpětná vazba"**, jak jsou povinnosti plněny? Tzn. **kontrolní mechanismus**.
- **Systém včasné identifikace** jevů vybočujících z nastaveného rámce.
- **Posuzování vlastní zranitelnosti** — např. **Red Team analýza** (interní tým hraje roli útočníka).
- Pokud se najde chyba: **při jaké chybě se může prozradit obrana** a **jaká bude úroveň ohrožení systému**?

#### 2b. Vnější funkce CCI

**Monitorování konkurenčního prostředí** — sledování, zda dochází k:

- Omezování našich aktivit konkurencí.
- Ohrožení dosažení strategických cílů.
- Narušení vlastnictví obchodního tajemství.

### 3. Analýza a formulace problému

Analogická k ofenzivnímu CI: převedení zadání (krok 1) plus výstupů ověření funkčnosti obrany (krok 2) na **jednoznačné pochopení problému**:

- Co konkrétně je ohroženo?
- Co je v sázce — strategicky, finančně, reputačně?
- Co lze a co nelze chránit?

### 4. Plánování postupu řešení

Konkrétní plán reakce. V rámci CCI obvykle zahrnuje:

- **Vyhodnocení situace** z hlediska ekonomického i personálního.
- **Rozmístění zdrojů** informací a dat, vč. bezpečnostních opatření (kdo má co kde uloženo).
- Případně **novou organizační strukturu** a fungování firmy — přehodnocení rozsahu, kdo přístup ke kterému typu informace.
- **Stanovit, co se bude chránit a kdo a jak to bude chránit.**
- **Nastavit systém tak, abychom věděli, že stanovená pravidla jsou dodržována.**
- Validace: **nový systém funguje, jak bylo požadováno?**

> Důraz na **funkční kontrolu zavedeného opatření** — nestačí vydat směrnici, je nutné ověřit, že se podle ní pracuje.

### 5. Sběr potřebných dat a informací

CCI sběr má dvojí povahu:

- **Co budou pracovníci plnit a jaké výstupy budou dávat** — z interních zdrojů.
- **Co dělá konkurence v okolí naší firmy** — z vnějších zdrojů.

> **Klíčové opatření:** Musí být vytvořena **kontrola samotných zpracovatelů** těchto výstupů. Vedoucí CCI útvaru musí být schopen **odhalit případná pochybení** svých vlastních lidí.

### 6. Zpracování získaných údajů

Třídění a posouzení sebraných údajů:

- **Rozdělení na informace** s různou váhou (relevantní, podpůrné, šum).
- Kvalita informace a zdroje — viz [[kvalita-informace-zdroj|Kvalita informace a zdroje]].
- Detekce možné [[dezinformace|dezinformace]] — viz [[detekce-identifikace-dezinformace|Detekce a identifikace dezinformace]].

### 7. Analýza informace

Vlastní zpravodajská analýza v kontextu CCI. Doporučená metoda: **[[analyza-konkurencnich-hypotez|ACH — Analýza konkurenčních hypotéz]]**.

Specifika ACH v CCI:

- **Hypotézy** typicky formulujeme jako varianty „kdo a proč se nás snaží vytěžit": konkurent A vs. konkurent B vs. interní špatný úmysl vs. náhoda vs. státní subjekt.
- Důkazy zahrnují signály úniku ([[obchodni-tajemstvi-ochrana|10 signálů]]), HUMINT pozorování, kybernetické indicators.
- Posouzení **zdrojů a metod práce útvarů CCI jednotlivých konkurenčních firem** — zrcadlový pohled, jak by oni hráli proti nám.

Vedlejší: **pracovní plán CCI** — jak budou pokračovat budoucí činnosti při různých scénářích.

> **Stanovit závažnost zjištěných skutků** — ne každý nález má stejnou váhu.

### 8. Zajištění důkazů

Klíčový krok, který odlišuje CCI od ofenzivního CI:

- **Zajištěné důkazy musí odpovídat závažnosti zjištěných skutečností.**
- Důkazy musí být použitelné v **navazujícím řízení** — pracovněprávním, soudním, jednání s konkurencí.
- Forma, řetězec dokumentace, identifikace svědků.
- Pokud se dezinformace nebo únik prokáže, ale **bez důkazů**, firma nemá co dělat.

### 9. Aktivní zásah + Vyhodnocení

#### 9a. Aktivní zásah

Podstata = **zabránit v aktivní činnosti** protivníka. **Některé kroky oficiální, jiné ne.**

- **Organizační opatření** uvnitř firmy — přesun pracovníků, ukončení pracovních poměrů s rizikovými osobami.
- **Právní kroky** — žaloby, NDA enforcement, stížnosti na nekalou soutěž.
- **Operativní kroky** — defenzivní [[dezinformace|dezinformace]] (vyvolání chybného obrazu u protivníka), uzavření kanálu úniku.
- **Výstrahy a kontrolní akce** — preventivní signál, že firma o aktivitách ví.

#### 9b. Vyhodnocení a poučení

Postmortem CCI akce — co fungovalo, co se povedlo, co je potřeba **dále zlepšit / změnit / nahradit**.

Výstup: **návrhy na opatření** zpracované do plánu činnosti organizace + realizace **v co nejkratší době**.

## Porovnání s ofenzivním CI procesem

| Krok | Ofenzivní CI | Defenzivní CCI |
|---|---|---|
| **1** | Zadání úkolu (predikce konkurence) | Zadání úkolu (ochrana / vyšetřování) |
| **2** | Analýza a formulace úkolu | **Ověření funkčnosti vlastní obrany** (vnitřní + vnější) |
| **3** | Plánování postupu | Analýza a formulace problému |
| **4** | Sběr dat | Plánování postupu |
| **5** | Zpracování údajů | Sběr dat (vnitřní + vnější + monitoring konkurence) |
| **6** | Zpravodajská analýza | Zpracování údajů |
| **7** | Vytvoření zprávy | Analýza informace (ACH) |
| **8** | Distribuce zprávy | **Zajištění důkazů** |
| **9** | Vyhodnocení procesu | **Aktivní zásah + vyhodnocení** |

Klíčové rozdíly:

- **CCI začíná u sebe** (krok 2 — ověření vlastní obrany), CI začíná u konkurenta.
- **CCI končí akcí** (krok 9 — aktivní zásah), CI končí zprávou pro vedení.
- **Důkazní břemeno** v CCI je formální — výstup musí být použitelný v právním řízení.

## Praktická úskalí

- **Tichá fáze** — pokud CCI proces zachytí zpravodajskou činnost konkurence, firma musí **neprozradit**, že to ví. Jakmile by konkurent věděl, že je odhalen, **změní svou činnost** — informační hodnota odhalení se ztratí.
- **Insider threat** — pravděpodobně 60–80 % úniků pochází zevnitř, ne zvenku. CCI musí umět prověřit vlastní lidi.
- **Politický tlak** — vrcholové vedení často nechce slyšet, že někdo z jeho okruhu může být kanálem úniku.

## Související stránky

- [[icink|Kurz IcinK]]
- [[counter-competitive-intelligence|Counter Competitive Intelligence (CCI)]]
- [[obchodni-tajemstvi-ochrana|Obchodní tajemství a ochrana informace]]
- [[zpravodajsky-proces-ci|Základní zpravodajský proces CI — 9 kroků]]
- [[zpravodajsky-cyklus-vs-proces|Zpravodajský cyklus vs. zpravodajský proces]]
- [[analyza-konkurencnich-hypotez|Analýza konkurenčních hypotéz (ACH)]]
- [[detekce-identifikace-dezinformace|Detekce a identifikace dezinformace]]
- [[dezinformace|Dezinformace]] — defenzivní použití

## Reference

- BARTES, František. *Konkurenční zpravodajství. Tvorba podkladů pro strategické rozhodování podniku.* Praha: Grada, 2022. ISBN 978-80-271-3504-2. — kap. 10 (Zpravodajský proces Counter Competitive Intelligence).
