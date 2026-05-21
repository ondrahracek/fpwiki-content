---
title: Časová analýza a T-analýza
course: icink
type: topic
tags: [icink, casova-analyza, zpravodajska-analyza, dezinformace]
sources: [raw/icink/IcinK-poznamky_z_prednasek.docx]
created: 2026-05-21
updated: '2026-05-21'
---

# Časová analýza a T-analýza

**Časová analýza** je dynamický nástroj zpravodajské analýzy — sleduje **tok událostí v čase**, jejich vzájemné ovlivňování a vzorce chování zkoumaných objektů. Doplňková **T-analýza** odhaluje *„bílá místa"* (neexistující, vakuované struktury) — typicky pro identifikaci [[dezinformace|dezinformace]].

> *Pokud bychom vycházeli ze statických stavů (jako většina analytiků), opomeneme dynamiku vývoje zkoumaného procesu.*

## Proč časová analýza

- **Dynamický pohled** na proces — ne snapshot, ale film.
- **Identifikace vzorců chování** zkoumaných objektů, vzájemných vazeb a významných změn.
- **Postmortem analýzy** zpravodajských zpráv — bez časové analýzy nelze rekonstruovat, *proč* se akce povedla nebo nepovedla.
- **„Válečné hry"** — co bude potřeba korigovat, když se kontext změní.

> *Tok událostí je dynamický proces odhalování procesů a jevů včetně jejich vzájemného ovlivňování.* Nutno sledovat analytický proces v **co nejkratší časové ose** a vědět, jaké síly ho ovlivňují.

## Čtyři varianty časové analýzy

Každá varianta pracuje se stejnou časovou osou, ale klade jinou otázku:

```
   t →  ─────────────────────────────────────────▶

   Var 1: Tok událostí
          •────•──•──────•───•───•
          E1   E2 E3     E4  E5  E6      (jediná chronologie, jeden aktér)

   Var 2: Matice událostí
          •────•──•──────•───•───•   ← konkurent A
          •──────•────•───•──•───•   ← konkurent B
          •──•────────•──•─────•─•   ← konkurent C
          (vzájemné vazby napříč aktéry)

   Var 3: Události a příčiny
          E1 ──způsobí──▶ E2
          E1 ──blokuje──▶ (E_x nikdy nenastane)
          (kauzalita + negativní prostor — co se NESTALO)

   Var 4: Historicko-grafická analýza
          ════•═══════•════════•══════•═══
              S1      S2       S3     S4
          (jen strategická rozhodnutí, dlouhý horizont — vzorce myšlení)
```

### 1. Analýza toku událostí

Sestavení **chronologicky seřazené sekvence relevantních událostí** s časovými údaji. Identifikuje **vzdálenosti** mezi událostmi — tj. zpoždění, mezery, anomálie v rytmu.

Úkolem je rekonstruovat, **jak události na sebe navazovaly v čase** a co tento sled vypovídá o záměru aktérů.

### 2. Matice událostí

Pro **všechny konkurenty** (případně **celé odvětví**) sestavit matici:

- Řádky = jednotliví aktéři / konkurenti.
- Sloupce = relevantní události v čase.
- Buňky = jak se konkrétní aktér zachoval k dané události.

Úkolem je **zjistit vazby mezi jednotlivými konkurenty** a relevantními událostmi — kdo s kým drží, kdo se kryje, kdo reaguje koordinovaně.

### 3. Analýza událostí a příčin

**Kauzalita.** Posouzení:

- **Podmínek a příčin**, které vedly ke vzniku události.
- **Důvodů, proč se jiné události NEZREALIZOVALY** (negativní prostor).

Tato varianta je silným nástrojem pro detekci skrytých záměrů — *co se nestalo a proč.*

### 4. Historicko-grafická analýza

**Zaměřeno pouze na důležitá strategická rozhodnutí** v dlouhém horizontu.

Úkolem: získat **přehled strategií konkurenta a úroveň jeho strategického myšlení**. Identifikovat:

- opakující se vzorce (preferuje agresivní vstupy / opatrné expansion / kopírování),
- rozhodovací bias (přeceňování / podceňování konkurentů),
- *„indikátory upřímnosti rozhodnutí"* — kdy si protivník stojí za rozhodnutím a kdy jen předstírá.

## T-analýza

> [!tip] T-analýza jednou větou
> Nehledá to, co je vidět — hledá **to, co tam být MĚLO, ale není**. „Bílá místa" v narativu jsou silnější signál než to, co protivník otevřeně prezentuje.

**T-analýza** je doplňková metoda **zaměřená na detekci dezinformace** a anomálií. Pojmenování pochází z analogie s pasivním radiolokátorem **Věra** (česká vojenská technologie identifikace „neviditelných" letadel).

### Princip

> *Založeno na identifikaci **vakuových struktur** v prostoru — zjišťování „umělého prázdna" vzniklého v prostoru cíleným pohlcováním různých signálů a záření.*

T-analýza nehledá to, co je vidět — hledá **to, co tam být MĚLO, ale není**. Tj. **bílá místa** v narativu.

### Použití v CI

- **Detekce dezinformace** — pokud někdo vytváří umělý narativ, **něco v něm chybí** (informace, které by ve skutečnosti existovaly). T-analýza odhalí absenci.
- **Identifikace anomálií** v toku událostí — diskontinuity, které neodpovídají očekávané dynamice.
- **Vytýčení nepředstavitelných hypotéz** — pomáhá rozšířit množinu hypotéz v ACH ([[analyza-konkurencnich-hypotez|krok 1]]) o varianty, které analytik intuitivně vyloučil.
- **Vyslovení podezření na dezinformaci** určenou ke klamání vrcholového vedení naší firmy.

## Postup časové analýzy (4 kroky)

### Krok 1 — Vypracování seznamu událostí

Vstupní soupis relevantních událostí v dané kauze. Zahrnuje vše, co může mít vztah ke zkoumanému procesu.

### Krok 2 — Doplnění o čas, charakteristiku, zdroj

Ke každé události:

- časový údaj (přesnost dle dostupných informací),
- stručná charakteristika události,
- případný zdroj informace o události.

### Krok 3 — Chronologické seřazení

Seřadit události na časovou osu. Tento krok obvykle odhaluje **vzdálenosti** mezi událostmi — kde byly nahuštěné, kde dlouhé pauzy.

### Krok 4 — Vlastní analýza

Identifikace trendů, odchylek, příčin. Tento krok má vlastní vnitřní strukturu:

#### 4.1 — Kontrola kroků 1–3

- Obsahuje časová osa **všechny důležité události** nezbytné k dosažení výsledku?
- Projít chronologii s důrazem na:
  - Jaké jsou **časové vzdálenosti** mezi klíčovými událostmi?
  - Pokud jsou dlouhé — **co způsobilo zpoždění**?
  - Pokud jsou krátké — je to reálně možné, nebo je to známka koordinace?

#### 4.2 — Trendy, odchylky, příčiny

Analýza vzorců chování v identifikované časové ose. Pro detekci dezinformace se zaměřit na bílá místa (T-analýza).

## Vztah k ostatním metodám

- **ACH** — ([[analyza-konkurencnich-hypotez|Analýza konkurenčních hypotéz]]) — časová analýza dodává **důkazy** do ACH matice (kdy se co stalo, co tomu předcházelo).
- **Porter — 4 rohy** — ([[analyza-konkurenta-porter|Porter]]) — historicko-grafická analýza pomáhá identifikovat **současnou strategii** a **domněnky** konkurenta.
- **7 otázek** — ([[sedm-otazek-zpravodajske-analyzy|7 otázek]]) — odpověď na *KDY?* vyžaduje časovou analýzu.
- **[[predikce|Predikce]]** — časová analýza je vstupem do prognostických metod (Box-Jenkins, Delphi atd.).

## Vliv množství dat na přesnost závěrů

Empirické pozorování (CIA analytik): **závislost přesnosti závěrů na množství dat není lineární**. Po dosažení určitého objemu se přesnost saturuje — další data **nepřidávají hodnotu**, jen prodlužují analýzu. To je důležité pro **rozhodnutí, kdy přestat sbírat** a začít analyzovat.

## Související stránky

- [[icink|Kurz IcinK]]
- [[analyza-konkurencnich-hypotez|Analýza konkurenčních hypotéz (ACH)]]
- [[detekce-identifikace-dezinformace|Detekce a identifikace dezinformace]]
- [[dezinformace|Dezinformace]]
- [[analyza-konkurenta-porter|Analýza konkurenta — 4 rohy podle Portera]]
- [[sedm-otazek-zpravodajske-analyzy|Sedm otázek zpravodajské analýzy + QUI BONO]]
- [[zpravodajsky-proces-ci|Základní zpravodajský proces CI — 9 kroků]]
- [[predikce|Predikce (IpmrK)]]

## Reference

- BARTES, František. *Konkurenční zpravodajství. Tvorba podkladů pro strategické rozhodování podniku.* Praha: Grada, 2022. ISBN 978-80-271-3504-2. — kap. 6 (Vybrané metody).
