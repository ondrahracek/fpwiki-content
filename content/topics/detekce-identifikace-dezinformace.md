---
title: Detekce a identifikace dezinformace
course: icink
type: topic
tags: [icink, dezinformace, zpravodajska-analyza, kvalita-informace]
sources: [raw/icink/IcinK-poznamky_z_prednasek.docx]
created: 2026-05-21
updated: '2026-05-21'
---

# Detekce a identifikace dezinformace

[[dezinformace|Dezinformace]] vstupuje do firmy zamaskovaná jako kvalitní informace. Před tím, než vrcholové vedení podle ní bude jednat, musí proběhnout dva strukturované procesy: **detekce** (vyslovení podezření) a **identifikace** (potvrzení nebo vyvrácení podezření důkazy).

> **Klíčový princip:** Důkaz = nevyvratitelná skutečnost. Bez důkazu existuje jen **silné podezření**, a v takovém případě se z opatrnosti **považuje informace za dezinformaci**.

## Procesní mapa: detekce → identifikace → analýza → reakce

```
   ┌──────────────────────┐
   │ Získaná „informace"  │
   └──────────┬───────────┘
              ▼
   ┌──────────────────────┐
   │ FÁZE 1: Detekce      │
   │ (vstupy: obsah,      │
   │  zdroj, kanál, čas)  │
   └──────────┬───────────┘
              ▼
        ╱──────────╲
       ╱  Vážné     ╲   ne
      ╱  podezření?  ╲────────▶ informace OK → pokračovat se ZA
       ╲             ╱
        ╲───────────╱
              │ ano
              ▼
   ┌──────────────────────┐
   │ FÁZE 2: Identifikace │
   │ (9 procesních kroků) │
   └──────────┬───────────┘
              ▼
        ╱──────────╲
       ╱  Existuje  ╲   ano (důkaz kvality)
      ╱   důkaz?    ╲────────▶ informace OK
       ╲            ╱
        ╲──────────╱
              │ ne
              ▼
        ╱──────────╲
       ╱ 7 případů  ╲   ano (alespoň 1)
      ╱  „vždy      ╲────────▶ DEZINFORMACE
       ╲ uvažovat"? ╱
        ╲──────────╱
              │ vše vyvráceno
              ▼
   ┌──────────────────────┐
   │ FÁZE 3: Analýza      │
   │   dezinformace       │
   │ (KDO/CO/.../QUI BONO)│
   └──────────┬───────────┘
              ▼
   ┌──────────────────────┐
   │ FÁZE 4: Reakce       │
   └──────────────────────┘
```

## Detekce dezinformace

**Detekce** = soubor úkonů, které musí být provedeny, aby mohlo být vysloveno **vážné (silné) podezření** na dezinformaci.

### Základní vstupy pro detekci

Detekce pracuje se sedmi typy vstupů, doplněnými podle specifik oboru:

1. Získaná **„informace"** (uvozovky proto, že status pravdivosti je zatím nerozhodnut).
2. **Obsah** informace — čeho se týká, jaká je vnitřní logika.
3. **Zdroj** informace.
4. **Způsob získání** informace.
5. **Informační kanál**, kterým informace dorazila.
6. **Čas vzniku** informace.
7. **Čas získání** informace.

### Časová osa informace

> *Časová analýza je v rámci ZA důležitá — co se děje s informací v časovém úseku mezi vznikem a získáním?*

Mezera mezi vznikem a získáním je analytickým prostorem. Viz [[casova-analyza|Časová analýza a T-analýza]] pro nástroje.

### Co spouští podezření

Informace by měla být **logická v mezích uznávaného narativu a kontextu stávajících procesů**. Pokud se zdá nelogická, mohou nastat tři případy:

1. Informace je nekvalitní (šum, zkreslení nebo dezinformace).
2. Informace je kvalitní, ale **neznáme o jevu vše**, co by její kvalitu potvrdilo.
3. Informace je kvalitní a odhaluje něco nového, dosud nepoznaného.

Volba (1)/(2)/(3) je úkolem identifikační fáze.

### Pravidlo o podvodu

> *Možnost podvodu nelze vyloučit jen proto, že neexistují důkazy. Ani se u dobře provedeného podvodu neočekává, že budou důkazy existovat.*

Detekce proto nikdy nemůže s jistotou tvrdit *„není to dezinformace"*. Může jen potvrdit nebo vyvrátit **vážné podezření**.

### Sedmero otázek CCI vrstvy

V kontextu [[counter-competitive-intelligence|CCI]] se k detekci přidávají otázky **motiv, příležitost, prostředky, způsob** — analogie s vyšetřováním. Viz také [[sedm-otazek-zpravodajske-analyzy|Sedm otázek zpravodajské analýzy]].

### Výsledek detekce

Detekce končí **buď** potvrzením domněnky, že informace je v rozporu s tím, co považujeme za kvalitní (→ silné podezření → identifikace), **nebo** objevením důkazu, že informace je kvalitní (→ věnujeme se obsahu, ne pravdivosti).

## Identifikace dezinformace

**Identifikace** = soubor úkonů provedených v rámci zpravodajského procesu CI za účelem **potvrzení, že získaná informace je dezinformací**.

### Základní pravidlo

Identifikace vyžaduje provedení **dílčích analýz** týkajících se:

- **obsahu** „informace",
- **účelu** „informace",
- **kontextu** „informace".

### Procesní kroky identifikace

#### Krok 1 — Převzetí zprávy z detekce

Přebírá se zpráva vč. **všech dílčích výsledků** etapy detekce:

- obsah, co potvrzuje a co vyvrací,
- časové úseky, aktéři, vazby, podmínky, prostředí,
- procesy související s hlavním procesem.

#### Krok 2 — Posouzení situace firmy

Ujasnění, **v jaké situaci se naše firma nachází**. Použití dezinformace má obvykle důvod — někdo (často protivník) je v krizi a snaží se z ní vyklouznout.

#### Krok 3 — Důležitost zprávy pro firmu

Posouzení, **jak může zpráva změnit naši trajektorii nebo strategii**:

- obsah — co potvrzuje, co vyvrací,
- časové úseky — aktéři, vazby, podmínky, prostředí,
- procesy související s hlavním procesem.

#### Krok 4 — Následky nepravdivosti

Jaké následky firmě vzniknou, **pokud podle informace zařídíme a dezinformace se potvrdí**? Posouzení negativních scénářů: konec firmy? ztráta podstatné části trhu? ztráta prestiže?

Kroky 3 a 4 jsou **spojené nádoby**.

#### Krok 5 — Analýza informace a zdrojů (podruhé)

Znovu provedeme analýzu kvality informace a [[kvalita-informace-zdroj|kvality zdroje]] — tentokrát s vyšším důrazem, protože už máme výsledky detekce a vyšší nároky.

Stanovíme **charakter získané informace**:

- nomologická (pravda),
- heuristická (potvrzená námi),
- operativní.

A provedeme:

- **důslednou analýzu** podle všech 6 znaků kvality,
- stanovení **zdroje** (odbornost, spolehlivost, pověst, schopnosti),
- stanovení **cesty informace** až k nám.

#### Krok 6 — Porovnání s ověřenými skutečnostmi

Porovnání zprávy se známými skutečnostmi. **Vždy vnímat jako podezřelé.** Zkoumat, v jaké situaci se nacházejí **nejvýznamnější konkurenti**, kterým by špatné rozhodnutí pomohlo.

#### Krok 7 — Stanovení úrovně neshody

Porovnání **významnosti neshody** mezi informací a již známými a ověřenými fakty s ohledem na:

- vývoj konkurenčního prostředí,
- odvětví,
- vývoj vědy a techniky,
- atd. dle specifik oboru.

Dva základní případy:

- **Neshoda není významná** (z hlediska budoucnosti) → ne dezinformace.
- **Neshoda je významná** → musí být přijato rozhodnutí, zda nesoulad vznikl náhodou, nedopatřením, **nebo byl záměrně vyvolán**.

#### Krok 8 — Vážné podezření a 7 pravidel

Pokud nebylo potvrzeno, že informace je kvalitní, jde o **vážné podezření na dezinformaci**.

### Sedm případů, kdy vždy uvažovat dezinformaci

> [!warning] V podnikové praxi existují případy, kdy je nutno vždy uvažovat s možností dezinformace
> Platí to i tehdy, když kroky 1–8 vychází, že informace je kvalitní. Sedm následujících bodů musí být **vyvráceno**, jinak se jedná o dezinformaci.

1. **Protivník už podváděl dříve** — má historii klamání.
2. **Informace dorazila v kritickou dobu** — protivník nebo my můžeme mnoho získat nebo ztratit.
3. **Pochybný zdroj** — zdroj se nikdy neosvědčil.
4. **Jediný zdroj** — analýza vychází z jediné „informace" (zdroje).
5. **Vyžaduje změnu základních předpokladů či hodnotových soudů** rozhodnutí.
6. **Vyžaduje vynaložení nebo přesměrování značných zdrojů** firmy.
7. **Vyžaduje setrvalý stav**, přitom vývoj situace nám napovídá učinit změnu.

#### Krok 9 — Prohlášení za dezinformaci

Pokud nebyla dezinformace jednoznačně vyloučena (důkazem), **prohlásí se získaná zpráva za dezinformaci**. Předá se útvaru zpravodajské analýzy pro:

- identifikaci **záměru** dezinformace,
- identifikaci **cíle** dezinformace,
- analýzu **autora** (KDO, viz [[sedm-otazek-zpravodajske-analyzy|7 otázek]]),
- návrh **reakce**.

> *„Opakované obdržení zprávy je podezřelé — mají tam velký bordel, nebo to dělají amatéři."*

## Praktický důsledek pro CI útvar

> [!warning] Politika opatrnosti
> V případě neurčitosti raději klasifikovat jako dezinformaci, než informaci přijmout a podle ní jednat. Jednorázová ztráta z opatrného postoje je menší než systémová ztráta z naletění na dobře připravenou dezinformaci.

- **Detekce a identifikace jsou samostatné procesní kroky** — neprovádí je analytik, který zpracovává obsah. Konflikt zájmů — analytik se přirozeně přiklání k tomu, že informace je kvalitní.
- **Sedm pravidel** je checklist, který musí útvar projít vždy.

## Související stránky

- [[icink|Kurz IcinK]]
- [[dezinformace|Dezinformace]]
- [[kvalita-informace-zdroj|Kvalita informace a zdroje]]
- [[casova-analyza|Časová analýza a T-analýza]]
- [[sedm-otazek-zpravodajske-analyzy|Sedm otázek zpravodajské analýzy + QUI BONO]]
- [[analyza-konkurencnich-hypotez|Analýza konkurenčních hypotéz (ACH)]]
- [[counter-competitive-intelligence|Counter Competitive Intelligence (CCI)]]

## Reference

- BARTES, František. *Konkurenční zpravodajství. Tvorba podkladů pro strategické rozhodování podniku.* Praha: Grada, 2022. ISBN 978-80-271-3504-2. — kapitola o ZA dezinformace.
