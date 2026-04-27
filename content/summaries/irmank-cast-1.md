---
title: "Risk Management — 1. část přednášky"
course: irmank
type: summary
tags: [irmank, lewin, kaizen, cpm-pert, kriticke-faktory]
sources: [raw/irmank/Rizeni rizik_prvni cast  začátek přednášek   2026 léto fin (1).ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Risk Management — 1. část přednášky

První část přednáškového bloku prof. Raise zaměřená na **vztah úspěch — změna — riziko** a klasické modely řízené změny ve firmě. Druhá část (riziko, měření, snižování) je v [[irmank-cast-2]].

> [!info] TL;DR
> První část buduje teoretický rámec: **co dělá firmu úspěšnou** (7S, EFQM), **proč se firmy musí měnit** (Walton case, KAIZEN vs. inovace), **co stojí změně v cestě** (9 důvodů odporu, švýcarské hodinářství 1940), **jak změnu řídit** (Lewinův model, agent změny, force field), a **jak modelovat čas** (CPM/PERT pro projekty změny).

## Klíčový obsah

### Doporučená literatura

- McCormack — *Co vás nenaučí na Harvardu* (1992)
- Molnár — *Efektivnost informačních systémů* (Grada, 2000)
- Johnson, Scholes — *Cesty k úspěšnému podniku* (Computer Press, 2000)
- Kaplan, Norton — *Balanced Scorecard* (Management Press, 2001)
- Rais, Smejkal — *Řízení rizik firmy* (Grada, 2003 / 4. vyd. 2013)
- Smejkal, Rais — *Řízení rizik ve firmách a jiných organizacích* (Grada, 2010 / 3. vyd.)
- Peters, Waterman — *Hledání dokonalosti* (Svoboda, 1992)
- Dědina — *Podnikové organizační struktury* (Victoria Publishing, 1996)
- Kotter — *Vedení procesu změn* (Management Press, 2000)
- Maurer — *CESTA KAIZEN* (Beta Praha, 2005, ISBN 80-7306-178-3)

### Vztah změna → úspěch → riziko

> „Jediné co je stálé ve firmě, je změna."

Klíčový vztah celého kurzu: **změna** ve firmě je nutná pro **úspěch**, ale nese **riziko** neúspěchu. Provádění změn → konflikt s existujícím stavem.

![[irmank-zmena-uspech-riziko.jpeg|Vztah změna — úspěch — riziko]]

### Kritické faktory úspěchu firmy

- **McKinsey 7S:** STRATEGIE, STRUKTURA, SYSTÉMY, SCHOPNOSTI, STYL, SPOLUPRACOVNÍCI, SDÍLENÉ HODNOTY.
- **EFQM model exelence** (1988, založeno VW, Olivetti, Elektrolux): 9 hlavních + 32 vedlejších kritérií, dělené **50 % předpoklady / 50 % výsledky**, body od 60 do 200.
- **8 „tichých zabijáků"** organizační efektivity: nejasná strategie, konflikt priorit, neefektivní vrcholové vedení, nevhodný řídicí styl, špatná vertikální komunikace, neuspokojivá koordinace, nedostatek řídících schopností, nedostatečná motivace.

### Úspěšný manažer + Sam Walton

Wal-Mart 1985: 1 milion zaměstnanců, 2300 prodejen. Walton odhalil v knize *Made in America* (1992) **desatero úspěchu**, založené na týmu, sdílení rizika a informací, motivaci, oslavě úspěchu, naslouchání zaměstnancům a celoživotním učení.

### Typy změny + KAIZEN

- **Plánovaná × neplánovaná** (legislativa, ekonomické prostředí).
- **Přírůstková (inkrementální) × transformační** (= inovace).
- **Inovace:** drastický proces, masivní propouštění, MBA přístup. Vysoký risk.
- **KAIZEN** (Maurer, Deming 1940s): postupná malá změna, „cesta tisíce mil začíná prvním krokem", každý zaměstnanec je zainteresován.

### Odpor ke změnám

9 důvodů: pocit manipulace, přerušení stereotypů, strach z neznáma, nejasný účel, strach ze selhání, nevýhodný benefit/effort, spokojenost se status quo, tradice (anekdota o vojákovi a trávníku), nedostatečná autorita vůdce.

> Klasický case: **švýcarské hodinářství 1940** odmítlo digitální hodinky. V roce 1940 80 % světové produkce hodinek bylo ze Švýcarska; dnes 80 % všech hodinek je digitálních. Vynálezce prodal nápad japonské Seiko.

### Lewinův model řízené změny

**3 fáze:** rozmrazení → vlastní změna → zmrazení.

**Schéma 8 prvků:** síly pro/proti změně, sponzor změny (Kdo?), nositel změny (Kdo?), intervenční strategie (Co?), operativní metody (Jak?), realizace změny (Jak?), zhodnocení (Jak?).

**4 intervenční oblasti:** lidské zdroje a jejich řízení, organizační struktura, technologie, komunikační a organizační toky.

**4 etapy procesu:** analytická → návrhová → realizační → zpětnovazební.

**Role:** agent změny (nositel), sponzor (zdroje, politika), advokát (podporuje, ale bez pravomoci).

**Analýza silového pole:** podporující × brzdicí síly, ohodnocení (–10, +10). Příklad zavedení nového IS: vedení +9, +7, +6 / techničtí pracovníci –4, –7.

### Síťová analýza projektů

- Síťový graf = model projektu (změny).
- **CPM** (Critical Path Method) — deterministické trvání aktivit; výpočet ES/EF (forward), LS/LF (backward), TM₁ (např. 16 v ukázkovém příkladu), TPⱼ rezervy (kritická cesta = 0).
- **PERT** — pravděpodobnostní trvání (3 odhady).
- **GERT** — variantní průběh.
- **MS Project Manager** jako standardní SW nástroj.

> Závěrečné varování: **i dobře řízený projekt může selhat, pokud neobsahuje zaměstnance** ("špatné zapojení kolegů do projektu").

## Mapa diagramů

| Embedovaný obrázek | Použití v topic |
|---|---|
| `irmank-zmena-uspech-riziko.jpeg` | [[odpor-ke-zmene]], course |
| `irmank-mckinsey-7s.jpeg` | [[kriticke-faktory-uspechu]] |
| `irmank-efqm-model.jpeg` | [[kriticke-faktory-uspechu]] |
| `irmank-walton-desatero.jpeg` | [[kriticke-faktory-uspechu]] |
| `irmank-uspech-manazera.jpeg` | [[kriticke-faktory-uspechu]] |
| `irmank-lewin-3faze.jpeg` | [[lewinuv-model]] |
| `irmank-lewin-schema-8prvku.jpeg` | [[lewinuv-model]] |
| `irmank-etapy-modelovani-zmeny.jpeg` | [[lewinuv-model]] |
| `irmank-analyza-siloveho-pole.jpeg` | [[analyza-siloveho-pole]] |
| `irmank-force-field-priklad-is.jpeg` | [[analyza-siloveho-pole]] |
| `irmank-intervencni-strategie.jpeg` | [[lewinuv-model]] |
| `irmank-cpm-priklad-graf.jpeg`, `irmank-cpm-vypocet-tm1.jpeg`, `irmank-cpm-rezervy-tpj.jpeg` | [[sitova-analyza-cpm-pert]] |
