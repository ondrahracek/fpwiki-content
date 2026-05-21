---
title: Zdroje dat a informací
course: icink
type: topic
tags: [icink, competitive-intelligence, zpravodajsky-proces, kvalita-informace]
sources: [raw/icink/IcinK-poznamky_z_prednasek.docx]
created: 2026-05-21
updated: '2026-05-21'
---

# Zdroje dat a informací

Sběr informací pro [[competitive-intelligence|Competitive Intelligence]] stojí na dvou rozhodnutích: **z jaké zóny zdrojů** čerpat (otevřené × šedé × tajné) a **jaký typ dat** sbírat (sekundární × primární). Volba určuje **legalitu**, **náklady**, **utajení akce** a **kvalitu** výsledku.

![[icink-zdroje-bila-seda-cerna.jpeg|Trojúhelník tří zón zdrojů — bílá (open source), šedá (neutajované, ale obtížně přístupné), černá (tajné) — s příklady pro každou.]]

## Tři zóny zdrojů

| Zóna | Charakter | Příklady | Legalita |
|---|---|---|---|
| **Bílá** | Open source — veřejně přístupné | výroční zprávy, tiskové zprávy, web, patenty, soudní rozhodnutí, statistiky, sociální sítě, články, registry | plně legální |
| **Šedá** | Neutajované, ale **běžně nepřístupné** | interní dokumenty bez utajení, zaměstnanecké komunikace, rozhovory na konferencích, výpovědi býv. zaměstnanců | legální při etickém získání |
| **Černá** | Tajné, utajované informace | interní strategie, [[obchodni-tajemstvi-ochrana|obchodní tajemství]] konkurence, neveřejné finanční údaje | **nelegální** získání |

Cíl CI: maximalizovat využití **bílé a šedé zóny**. Sahání do černé zóny je nezákonné a etický kodex CI ho výslovně zakazuje.

## Sekundární vs. primární data

### Sekundární data

- Někdo už data nasbíral a zveřejnil (vlastní firma nebo třetí strana).
- Často **zastaralá**, ale snadno dostupná.
- Práce s nimi = **desk research**.
- Po desk research zůstává **informační mezera** — to, co sekundární data neříkají.

### Primární data

- Sbírá si je analytik **sám v terénu** podle aktuální potřeby.
- Nejsou ovlivněna předchozím zpracováním.
- **Zlatá zrnka** — to, podle čeho se rozhoduje, představuje typicky **~20 % objemu** dat, ale **~80 % času** analytika.

## HUMINT — lidské zdroje

**HUMINT** (*Human Intelligence*) = informace získané rozhovorem s lidmi. Hlavní typové zdroje:

- **Interní zaměstnanci** prověřované firmy / konkurence.
- **Dodavatelé, obchodní partneři, zákazníci.**
- **Uklízečky, brigádníci, ostraha, řidiči, externisté.**
- Bývalí zaměstnanci (s opatrností — viz signály úniku v [[obchodni-tajemstvi-ochrana|ochrana obchodního tajemství]]).

**Zásady HUMINT v CI:**

- Vést rozhovor tak, aby zdroj **nepoznal**, že je vytěžován.
- Použít legendu (krytí účelu).
- **Krýt zdroj** — chránit jeho identitu po celý život akce.

## Symptomy a signály

V terénu sběrač sleduje dva typy stop:

| Pojem | Charakter | Příklad |
|---|---|---|
| **Symptom** | průvodní jev procesu, často **nezáměrný** | změna chování v týmu konkurenta, nezvyklé personální pohyby |
| **Signál** | jev viditelný **navenek**, často veřejný | tisková zpráva, patentová přihláška, registrace ochranné známky |

**Klamavé symptomy** — pozor: konkurent může cíleně produkovat symptomy, které mají vést analytika k chybnému závěru. Identifikace klamavých symptomů je úkolem [[detekce-identifikace-dezinformace|detekce dezinformace]].

## Etické, neetické a nezákonné metody

Bartes (a etické kodexy Fuld & Co) rozlišují tři úrovně:

### Etické metody

- Studium otevřených zdrojů (web, výroční zprávy, patenty, akademické publikace).
- Veřejné rozhovory, konference, networking.
- Legální sledování trhu (mystery shopping v rámci práva).
- Zaměstnanecké průzkumy, oficiální komunikace s konkurencí.

### Neetické (ale často legální)

- Technické sledování (např. listening v open prostorech).
- **Tajné pozorování** činnosti konkurence.
- **Fingované nabízení zaměstnání** za účelem rozhovoru.
- Jednání s konkurencí pod záminkou zájmu o patenty.

### Nezákonné

- Špioni, podplácení, vloupání, krádeže.
- Přetahování zaměstnanců **kvůli informacím** (rozdíl od legitimního náboru).
- **Ilegální odposlech** (např. heslo *„Agáta"* pro odposlechy telefonních hovorů mimo operátora).
- Vydírání, hackerské průniky.

## Specifické zdrojové problémy

- **Dezinformace a fámy** — vyžadují vlastní detekční proces; viz [[dezinformace|Dezinformace]] a [[detekce-identifikace-dezinformace|Detekce a identifikace dezinformace]].
- **Agenturní přebírání** — pokud informaci převzala další agentura, je nutné dohledat **nezávislý druhý zdroj**.
- **Zdroj 24/7** — kvalitní sběr dat o konkurenci běží průběžně, ne ad hoc; ekonomicky nezanedbatelné (orientačně ~80 USD/den za seriózní sledovací operaci).

## Kontratějev (Kondratěvův) cyklus a sledování vln

Životní cyklus výrobku konkurence lze odhadovat **sledováním inovační vlny** — z minulých termínů uvedení nových produktů lze vypočítat, **kdy musí konkurent uvést další produkt** → tím se odhalí, **kdy na něm musí pracovat** → kde sběrač hledá symptomy.

## Související stránky

- [[icink|Kurz IcinK]]
- [[competitive-intelligence|Competitive Intelligence — vymezení a procesy]]
- [[zpravodajsky-proces-ci|Základní zpravodajský proces CI — 9 kroků]]
- [[kvalita-informace-zdroj|Kvalita informace a zdroje]]
- [[dezinformace|Dezinformace]]
- [[detekce-identifikace-dezinformace|Detekce a identifikace dezinformace]]
- [[obchodni-tajemstvi-ochrana|Obchodní tajemství a ochrana informace]]
- [[counter-competitive-intelligence|Counter Competitive Intelligence (CCI)]]

## Reference

- BARTES, František. *Konkurenční zpravodajství. Tvorba podkladů pro strategické rozhodování podniku.* Praha: Grada, 2022. ISBN 978-80-271-3504-2. — kap. 3 (Zdroje dat a informací).
- FULD, Leonard M. *The New Competitor Intelligence.* 1995. — etické kodexy CI praxe.
