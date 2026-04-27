---
title: "Expertní systémy v řízení rizik"
course: irmank
type: topic
tags: [irmank, expertni-systemy, fel-expert, prognoza, box-jenkins, delphi]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Expertní systémy v řízení rizik

> [!info] TL;DR
> **Expertní systémy (ES)** jsou softwarové aplikace, které **kodifikují praktické heuristiky lidských expertů** a aplikují je na nové situace. Místo „naučení se ze vzorků" (jako u [[umele-neuronove-site|umělých neuronových sítí]]) ES pracují s **explicitními pravidly typu IF–THEN**, která jsou strukturovaně extrahována od domain experta.
>
> V kontextu **risk managementu** se ES používají pro:
>
> - **Výběr prognostické techniky** — který nástroj (Box-Jenkins, regrese, Delphi…) je vhodný pro daný typ úlohy.
> - **Klasifikaci rizik** — zařazení rizika do kategorie (operační, finanční, strategické…).
> - **Doporučení metod snižování rizika** — která taktika (vyhnutí, redukce, transfer, retence) je v dané situaci optimální.
>
> **Klíčový československý případ:** **FEL-EXPERT shell** — vyvinut na Fakultě elektrotechnické ČVUT, použit prof. Raisem v habilitaci pro doménu strategického rozhodování firmy. Reálné nasazení **Úřad vlády ČSFR 1988–90** s **37 hypotézami** o budoucnosti firmy a **30 metodami snižování rizika**.
>
> ES jsou jednou ze čtyř hlavních AI metod v risk managementu (vedle ANN, GA a [[fuzzy-logika|fuzzy logiky]]) a často se s nimi kombinují v hybridních systémech jako [[anfis|ANFIS]].
>
> ---

## Architektura expertního systému

![[irmank-expertni-systemy-architektura.jpeg|Architektura expertního systému — báze znalostí, inferenční mechanismus, pracovní paměť, uživatelské rozhraní, vysvětlovací modul a získávání znalostí od experta (FEL-EXPERT shell)]]

Každý ES se skládá ze **tří klíčových komponent** a obvykle z dalších tří podpůrných modulů.

### Tři klíčové komponenty

- **Báze znalostí (BZ / KB — Knowledge Base)** — souhrn pravidel typu „IF... THEN..." získaných od experta. Statická, ale doménově specifická.
- **Inferenční mechanismus (inference engine)** — algoritmus, který kombinuje pravidla a aktuální vstupy → odvozuje závěr. Typicky **forward chaining** (od faktů k závěru) nebo **backward chaining** (od hypotézy k faktům).
- **Uživatelské rozhraní (UI)** — vstup faktů od uživatele (často strukturovaný dotazník), výstup doporučení s vysvětlením.

### Často také

- **Vysvětlovací modul (explanation facility)** — odpovídá na otázku „proč ES dospěl k tomuto závěru?" — ukazuje řetězec aplikovaných pravidel. Klíčová výhoda oproti „black-box" ANN.
- **Modul pro získávání znalostí (knowledge acquisition)** — strukturovaný rozhovor s expertem, často v podobě grafického editoru pravidel.
- **Pracovní paměť (working memory)** — momentální fakta o konkrétním řešeném případu, dynamická součást systému.

### Shell + báze znalostí

**Prázdný shell** (motor + UI bez pravidel) **+ báze znalostí** = ES pro konkrétní doménu. Hlavní výhoda této architektury: **shell se znovupoužívá** pro různé domény jen s jinou bází znalostí. Stejný FEL-EXPERT shell tak může fungovat pro výběr prognostické techniky, pro lékařskou diagnostiku i pro doporučení investiční strategie — stačí vyměnit BZ.

---

## Typy expertních systémů

Podle reprezentace znalostí rozlišujeme čtyři hlavní typy ES:

- **Pravidlové (rule-based)** — IF–THEN pravidla. Klasické příklady: **MYCIN** (lékařská diagnóza infekcí), **FEL-EXPERT** (strategické rozhodování). Nejrozšířenější typ.
- **Případové (case-based reasoning, CBR)** — knihovna minulých případů + metrika podobnosti. Nový případ se řeší tak, že se najde nejpodobnější historický případ a jeho řešení se adaptuje. Vhodné pro domény, kde je obtížné formalizovat pravidla, ale snadné pamatovat si konkrétní příběhy (právo, helpdesk).
- **Modelové (model-based)** — obecný matematický nebo kauzální model dynamiky systému, ne specifická pravidla. Inferuje se simulací modelu pro konkrétní vstupy. Vhodné pro technické diagnostiky (auta, elektrárny).
- **Fuzzy ES** — kombinace s [[fuzzy-logika|fuzzy logikou]] pro nejistou znalost. Místo binárního „IF teplota > 30 THEN horko" pracuje s „IF teplota je vysoká THEN horko je vysoké" s členskými funkcemi. Cross-link: kurz [[ipmrk|Pokročilé metody v rozhodování]].

---

## Příklady heuristik

Aby bylo zřejmé, co znamená „kodifikace expertní zkušenosti", uveďme dva ilustrativní příklady :

### Studentská heuristika

> **Pravidlo:** „Jsou-li zkušební termíny v lednu A profesor je shovívavý, raději se přihlaste na únorový termín, který bývá obtížnější, ALE máte víc času na přípravu."

**Komentář:** Začátečník nezná tento kontextový vzorec — vidí jen „šance v lednu" vs. „šance v únoru" izolovaně. Zkušený student kombinuje tři faktory (datum, charakter zkoušejícího, vlastní příprava) a má heuristiku na jejich spojení. ES tuto heuristiku **zformalizuje a sdílí** s ostatními.

### Hříbková heuristika

> **Pravidlo:** „Jdete-li sbírat houby PŘI úplňku PO třídenním dešti, najdete pětkrát více hříbků."

**Komentář:** Lidová znalost, kterou ES může zformalizovat. Zajímavé je, že **nikdo neumí formálně dokázat, proč to funguje** — ale empirická pozorování to potvrzují.

Tyto „banální" příklady ukazují, jak ES kodifikuje **tichou znalost (tacit knowledge)** — znalost, kterou expert používá, ale obtížně ji formuluje. Knowledge engineer s ním vede strukturovaný rozhovor a převádí jeho intuitivní pravidla do explicitní podoby.

---

## FEL-EXPERT — případová studie

**FEL-EXPERT** je nejvýznamnější československý ES shell a klíčový příklad nasazení ES v risk managementu.

### Kontext

- **FEL-EXPERT shell** — vyvinut na **Fakultě elektrotechnické ČVUT (FEL)** v 80. letech.
- **Habilitace prof. Raise** — disertační/habilitační práce na téma využití ES v ekonomice. Vytvořena báze znalostí pro doménu strategického rozhodování firmy.
- **Doména:** výběr prognostické techniky a metod snižování rizika pro vrcholový management.

### Báze znalostí

- **37 hypotéz** o budoucnosti firmy / odvětví (např. „odvětví vstoupí do recese", „klíčový dodavatel zkrachuje", „regulace omezí export").
- **30 metod snižování rizika** (každá s podmínkami aplikovatelnosti — kdy je metoda vhodná, kdy nikoli).
- Pravidla strukturovaná do **subsystémů**:
 1. **Klient** — charakterizace firmy (velikost, odvětví, finanční zdraví, struktura vlastnictví).
 2. **Prognóza** — výběr vhodné prognostické techniky podle dat a horizontu.
 3. **Data** — dostupnost a kvalita vstupů (délka časové řady, frekvence, sezónnost).

### Reálné nasazení

**Úřad vlády ČSFR 1988–90** pro analýzu strategických rozhodnutí v transformační ekonomice. Toto je významný okamžik — jedno z prvních reálných nasazení ES ve veřejné správě v Československu.

### Výsledky a limity

| Aspekt | Hodnocení |
|--------|-----------|
| Strukturovaná podpora | ANO — vrcholový management dostal konzistentní rámec rozhodování |
| Kombinace dat a heuristik | ANO — kvantitativní vstupy + expertní pravidla |
| Transparence | ANO — vysvětlovací modul ukázal, proč ES doporučuje danou metodu |
| Reakce na novou situaci | NE — BZ je statická, transformační šoky vyžadovaly manuální revize |
| Údržba | Nákladná — pravidla bylo nutné průběžně aktualizovat |

---

## ES pro výběr prognostické techniky

Konkrétní funkční subsystém FEL-EXPERTu — pomáhá uživateli vybrat vhodnou prognostickou techniku z bohaté palety.

### Vstupy uživatele

- **Délka dostupné historie dat** — krátká (< 24 vzorků), střední (24–100), dlouhá (> 100).
- **Frekvence vzorkování** — denní, týdenní, měsíční, čtvrtletní, roční.
- **Stacionarita / sezónnost** — má řada trend? Sezónní složku? Strukturní zlomy?
- **Cílový horizont prognózy** — krátkodobá (do 3 měsíců), střednědobá (3–24 měsíců), dlouhodobá (nad 2 roky).
- **Dostupnost expertů** — máme přístup k panelu znalců pro kvalitativní metody?

### Výstupy ES

- **Doporučená technika** (kvantitativní nebo kvalitativní, viz dále).
- **Alternativy s vysvětlením** — proč právě tato, proč ne jiná.
- **Odhad přesnosti** — typicky interval spolehlivosti.
- **Varování před úskalími** — např. „pozor na strukturní zlom v roce X", „malá data → vysoká nejistota".

---

## Kvantitativní prognostické metody

Metody pracující s číselnými časovými řadami. šest klíčových:

- **Box-Jenkins (ARIMA)** — autoregresní integrovaný klouzavý průměr, **klasická metoda time series**. Modeluje řadu jako $ARIMA(p,d,q)$, kde $p$ = řád autoregrese, $d$ = stupeň diferencování, $q$ = řád MA složky. Vyžaduje **stacionární data** (po diferencování).
- **Klouzavé průměry (moving averages)** — vyhlazení šumu, identifikace trendu. Jednoduché, ale ztrácí informaci na krajích řady.
- **Extrapolace trendů** — lineární / kvadratická / exponenciální regrese. Vhodné pro dlouhodobé monotónní trendy bez zlomů.
- **Regresní modely** — víceproměnné, lze zahrnout **exogenní vlivy** (HDP, kurz, sezónnost, ceny vstupů). Klíčový nástroj v kombinaci s [[mereni-rizika|kvantitativním měřením rizika]].
- **Exponenciální vyhlazování (Holt-Winters)** — rozšíření klouzavých průměrů o trend a **sezónnost**. Vhodné pro maloobchodní data, energetiku.
- **State-space modely (Kalmanův filtr)** — pro **dynamické systémy**, kde se parametry mění v čase. Použití v navigaci, finančních modelech, řízení.

Cross-link [[predikce]] (kurz [[ipmrk]]) — detailní přehled prognostických metod včetně neuronových sítí.

---

## Kvalitativní prognostické metody

Metody pracující s názorem expertů místo s číselnými daty. šest:

- **Brainstorming** — neformální generování nápadů ve skupině. Typicky **4–8 lidí, 30–60 minut**, pravidlo „kvantita před kvalitou", kritika zakázána ve fázi generování.
- **Delfská metoda (Delphi)** — strukturovaný proces s expertními panely. Postup:
 1. **Anonymní iterace** — experti odpovídají písemně bez vzájemné konfrontace (eliminuje skupinový tlak).
 2. **Konsolidace** — moderátor sumarizuje odpovědi a posílá zpět s argumenty.
 3. **Konvergence** — po několika kolech (typicky 3–5) se názory stabilizují a vzniká skupinový konsenzus s mírou nejistoty.
- **Komunikační a prognostické hry** — simulace situací (např. **wargaming** pro armádu, **business gaming** pro krizový management).
- **Systémová dynamika (Forrester 1961)** — kauzální smyčky, **stocks-and-flows** diagramy, simulace složitých systémů s feedback loopy. Klasické dílo: J. Forrester, *Industrial Dynamics*.
- **Simulační modely (ekonometrické)** — **Monte Carlo simulace** ekonomických scénářů. Vhodné pro analýzu citlivosti.
- **Scenario planning (Shell, 1970s)** — generování **několika konzistentních budoucích scénářů** (ne jediná prognóza). Slavný případ: Shell předvídal ropné krize 1973 a byl připraven.

### Kdy použít kvalitativní

- **Málo dat** — historie krátká, nelze regresně modelovat.
- **Strukturní změna** — historie nereprezentativní pro budoucnost (např. po deregulaci trhu, po zavedení nové technologie).
- **Politické / regulační rozhodnutí** — ovlivněné lidskou vůlí, nelze extrapolovat.
- **Disruptivní technologie** — nemá historický precedent.

---

## Vztah AI metod v risk managementu

**čtyři hlavní AI metody** používané v risk managementu. Každá má jiné silné stránky:

| Metoda | Síla | Slabina | Cross-link |
|--------|------|---------|------------|
| **Expertní systémy** | Transparentní pravidla, snadné vysvětlení | Statická BZ, knowledge bottleneck | tato stránka |
| **Umělé neuronové sítě** | Učení end-to-end ze vzorků | Black box, vyžaduje hodně dat | [[umele-neuronove-site]] |
| **Genetické algoritmy** | Optimalizace v prostorech s mnoha lokálními extrémy | Pomalá konvergence, ne pro klasifikaci | [[geneticke-algoritmy]] |
| **Fuzzy logika** | Práce s neurčitou znalostí, lingvistické proměnné | Návrh členských funkcí je obtížný | [[fuzzy-logika]] |

Tyto metody se **kombinují** v hybridních systémech. Nejznámější je **ANFIS = Adaptive Neuro-Fuzzy Inference System** — fuzzy ES, jehož členské funkce a pravidla se ladí pomocí učení neuronové sítě. Cross-link [[anfis]].

---

## Limity expertních systémů

Přes všechny výhody mají ES důležitá omezení:

- **Statická báze znalostí** — nereaguje na nové situace (na rozdíl od ANN, která se může přeučit z nových dat). Po strukturní změně domény je nutné BZ ručně přepsat.
- **Knowledge acquisition bottleneck** — extrakce pravidel od experta je **nákladná**. Expert často nedokáže své heuristiky verbalizovat („vím to, ale neumím to vysvětlit"). Knowledge engineer musí použít strukturované techniky (laddering, repertory grids).
- **Kvalita BZ** — celý systém je tak dobrý, jak je dobrá báze znalostí. **Garbage in, garbage out** platí dvojnásob.
- **Kompozice pravidel** — interakce mnoha pravidel může vést k **neočekávaným závěrům**. Při BZ s 1000+ pravidly je obtížné ověřit konzistenci.
- **Maintenance** — BZ se musí pravidelně updatovat. Bez údržby ES rychle zastará.
- **Vysvětlení vs. přesnost** — jednoduchá pravidla jsou srozumitelná, ale méně přesná než komplikované modely. Trade-off mezi interpretovatelností a výkonem (stejný problém jako u rozhodovacích stromů vs. deep learning).

---

## ES v risk managementu — praktické použití

Konkrétní oblasti, kde se ES dnes nasazují v risk managementu:

- **Selekce metod snižování rizika** — vstup: charakteristiky rizika (frekvence, závažnost, kontrolovatelnost), výstup: doporučená taktika ([[taktiky-rizeni-rizik|vyhnutí, redukce, transfer, retence]]).
- **Risk scoring** — **credit scoring** (skóre žadatele o úvěr), **fraud detection** (podezřelé transakce). V současnosti často kombinováno s ANN, ale ES poskytuje vysvětlení („zamítnuto kvůli pravidlům X, Y, Z").
- **Compliance** — automatická kontrola dodržování regulací: **KYC** (Know Your Customer), **AML** (Anti-Money Laundering), **GDPR**.
- **Diagnostika** — identifikace zdroje problému (např. analýza výpadku IT systému, root cause analysis).
- **Doporučení BCM scénářů** — výběr vhodného scénáře obnovy podnikání. Cross-link [[bcm]] z kurzu [[imork|Management oborových řešení]].

---

## Souvislosti

### Cross-course (kurz [[ipmrk]])

- [[predikce]] — detailní přehled prognostických metod (klasické i AI-based).
- [[fuzzy-logika]] — základ pro fuzzy ES.
- [[geneticke-algoritmy]] — alternativní AI přístup pro optimalizační úlohy.
- [[umele-neuronove-site]] — komplementární AI metoda, učení ze vzorků.
- [[anfis]] — hybridní systém kombinující fuzzy ES s neuronovým učením.

### V rámci kurzu [[irmank]]

- [[mcfarlan-portfolio]] — ES patří do **Strategické** nebo **Turnaround** kvadrantu (vysoký dopad na strategii, vyžaduje speciální péči).
- [[operacni-vyzkum]] — komplementární kvantitativní přístup (LP, IP, simulace).
- [[investicni-rozhodovani-bot]] — ES může pomoci s výběrem investiční strategie (rule-based bot).
- [[mereni-rizika]] — kvantitativní vstup pro ES pravidla (hodnoty pro IF podmínky).
- [[taktiky-rizeni-rizik]] — výstupní doménový prostor ES (THEN doporučení).
- [[analyza-rizik-proces]] — kontext, ve kterém ES běží.

---

## Navigace

- **Předchozí:** [[mcfarlan-portfolio]]
- **Navazující:** [[investicni-rozhodovani-bot]]
- **Související:** [[operacni-vyzkum]]
