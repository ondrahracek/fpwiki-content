---
title: Analýza konkurenčních hypotéz (ACH)
course: icink
type: topic
tags: [icink, ach, zpravodajska-analyza, dezinformace, competitive-intelligence]
sources: [raw/icink/IcinK-poznamky_z_prednasek.docx]
created: 2026-05-21
updated: '2026-05-21'
---

# Analýza konkurenčních hypotéz (ACH)

**Analýza konkurenčních hypotéz** (*Analysis of Competing Hypotheses*, ACH) je strukturovaná analytická metoda původně vyvinutá Richardsem J. Heuerem Jr. (CIA) pro odhady ve zpravodajské činnosti. V CI ji používáme k **predikci budoucího vývoje** konkurenčního prostředí a k **odolnosti proti kognitivním zkreslením**.

![[icink-ach-matice.jpeg|Matice ACH — sloupce hypotézy H1–H4, řádky důkazy D1–Dn, buňky obsahují ++/+/−/−−; vyznačena diagnosticita důkazů.]]

> **Niels Bohr:** *„Předpovídání je obtížné, zejména týká-li se budoucnosti."*

Otázky, na které ACH odpovídá:

1. Jak se bude situace vyvíjet?
2. Co můžeme očekávat v budoucnu?
3. Jak nás to může ohrozit / kde leží příležitost?

## Osm kroků metody ACH

### Krok 1 — Stanovení hypotéz

Klíčový krok. **Bez kvalitních hypotéz nelze získat kvalitní výsledek.**

Probíhá ve **dvou fázích**:

1. **Vytvoření množiny hypotéz** — uvažovat o **všech možnostech**, brainstorming. Rozdíl mezi **námětem** a **návrhem**: náměty se třídí, návrhy zbydou.
2. **Posuzování hypotéz** — vyřadit zjevně nesmyslné. **Pozor na rozdíl:**
   - **Vyvrácená hypotéza** — existuje **důkaz**, že je chybná.
   - **Neprokázaná hypotéza** — neexistuje důkaz, že je správná, ani že je chybná.

#### Požadavky na hypotézy

- **Vzájemně konkurenční** — platnost jedné musí vyvracet ostatní.
- **Vyvrácení hypotézy** — postačuje **jediný důkaz**.
- **Kompletnost** — typický počet 3–7 hypotéz; musí pokrýt klíčové možnosti.

### Krok 2 — Stanovení důkazů a argumentů

- Sestavení **seznamu obecných důkazů** ke všem hypotézám.
- Pro každou hypotézu **vyvolat další otázky**: *„Pokud je tato hypotéza správná, měli bychom vidět/najít...?"*
- **Pokud takový důkaz nevidíme**, je to proto, že:
  - se to dosud nestalo,
  - důkaz existuje, ale jsme ho přehlédli,
  - důkaz byl zatajen,
  - hypotéza je chybná.

> **Zaznamenat existenci, ale i neexistenci důkazu.** Pozornost se přirozeně upíná k tomu, co je ve zprávě uvedeno, ne k tomu, co tam není. Klasický příklad: čtení **výroční zprávy firmy** — co tam zaměrně chybí.

### Krok 3 — Vytvoření matice

- **Vodorovně** (sloupce) — soubor hypotéz $H_1, H_2, \ldots, H_k$.
- **Svisle** (řádky) — důkazy $D_1, D_2, \ldots$ a argumenty.
- **Buňky** — hodnocení každého důkazu pro každou hypotézu:

| Symbol | Význam |
|---|---|
| `++` | důkaz silně **potvrzuje** hypotézu |
| `+` | důkaz potvrzuje |
| `−` | důkaz vyvrací |
| `−−` | důkaz silně **vyvrací** hypotézu |
| `(prázdné)` | důkaz není pro hypotézu relevantní |

Postup: **jdeme po důkazech** (po řádcích matice) a posuzujeme každý důkaz pro **všechny hypotézy** zvlášť — ne naopak.

### Diagnosticita důkazu

> **Diagnosticita** = jak silně důkaz ukazuje na konkrétní hypotézu vs. ostatní.

- Důkaz, který je **slučitelný se všemi hypotézami**, má **nulovou diagnostickou hodnotu** — nepomáhá rozlišit.
- **Vysoce diagnostické důkazy** jsou ty, které potvrzují jen jednu hypotézu a ostatní vyvracejí.

**Pozor — psychologická past:** většina důkazů má tendenci **potvrzovat tu nejpravděpodobnější (nejintuitivnější) hypotézu**. To není známka její pravdivosti — analytici hledají to, co znají.

### Krok 4 — Vyčištění matice

Přesné znění hypotéz je **kritické** pro závěry, které lze z analýzy učinit. V tomto kroku:

- **Sloučit** dvě hypotézy do jedné (pokud se ukázaly jako synonymní).
- **Rozdělit** hypotézu na dvě (pokud zahrnovala dva různé scénáře).
- **Přeformulovat** nepřesně formulovanou hypotézu.

Znovu zkoumat důkazy — k jedné vybrané hypotéze, vyvrací nebo potvrzují?

> **Iterace:** Při přeformulaci nebo rozdělení hypotéz je nutné **zopakovat kroky 1–4**. Matice musí odrážet aktuální formulace.

### Krok 5 — Předběžné závěry

Na každou hypotézu pohlížet jako celek:

- Hledat **důkazy pro vyřazení** hypotéz nebo jejich označení za nepravděpodobné.
- **Akceptovat** hypotézy, které nelze vyřadit.
- Stanovit **relativní pravděpodobnost** každé hypotézy — spočítání **přidělených negativních bodů** (váha mínusů). Hypotéza s nejmenším počtem mínusů je **nejpravděpodobnější**.
- Případně **přisouzení vah** jednotlivým důkazům podle jejich důležitosti.

> **Důležité:** Matice **odráží náš úsudek, není závěrem.** My musíme učinit rozhodnutí. Matice nám ale dá poměrně dobrý přehled o situaci.

### Krok 6 — Analýza citlivosti

Klíčová otázka: **Jak silně závisí závěr na jednotlivých předpokladech?**

- Sporné předpoklady?
- Mohl by být důkaz nekompletní?
- Důsledky v případě, že by důkazy nebyly správné.

V závěrečné zprávě musí být **prodiskutovány alternativní názory a úsudky**. ACH není o jediném výstupu, ale o tom, jak je výstup robustní.

### Krok 7 — Zpráva s milníky

Připravit zprávu pro vedení obsahující:

- nejpravděpodobnější hypotézu a důvody,
- alternativy a jejich pravděpodobnost,
- **milníky** (*milestones*) — události, jejichž výskyt by potvrdil nebo vyvrátil hypotézu.

> **Bezpečnostní pravidlo:** Milníky se **nesmí ve zprávě objevit veřejně** — nesmí opustit místnost útvaru CI. Pokud by je viděl protivník, mohl by je úmyslně produkovat (vznikl by hodnotný signál pro protivníka, jak nás klamat).

### Krok 8 — Sledování milníků (monitoring)

Průběžné sledování, zda dochází k milníkům. Při výskytu / nevýskytu zpřesnit pravděpodobnosti hypotéz; v případě potřeby spustit nový ACH cyklus.

## Výhody ACH

- **Matice není nezměnitelná** — průběžně se vyvíjí s novými důkazy.
- **Vyhnutí se kognitivnímu zkreslení** — *confirmation bias*, *anchoring*, *availability heuristic*. Strukturovaný postup nutí analytika zvažovat alternativy.
- **Větší objektivnost** v analýze a rozhodnutí.
- **Transparentnost úsudku** — třetí strana (revize, soudní řízení, audit) vidí, jak se ke závěru dospělo.

## Praktická úskalí

- **Kvalita hypotéz** — slabý krok 1 znehodnotí celou metodu.
- **Pseudo-přesnost** — symbolické hodnocení (`++`, `+`, `−`, `−−`) může vypadat objektivně, ale stále jde o subjektivní úsudek analytika.
- **Diagnosticita důkazů** — bez explicitního označení diagnostické hodnoty se závěry „rozpadnou" pod tíhou nediagnostických důkazů.
- **Časová náročnost** — ACH se vyplatí u strategických rozhodnutí, ne u rutinních otázek.

## Vztah k dezinformaci

ACH je hlavní metoda **analýzy dezinformace** ve fázi 3 procesu práce s dezinformací (viz [[dezinformace|Dezinformace]] — *4 kroky práce s dezinformací*). Hypotézy pak typicky vyjadřují alternativní motivy autora ([[sedm-otazek-zpravodajske-analyzy|KDO, PROČ, QUI BONO]]).

## Související stránky

- [[icink|Kurz IcinK]]
- [[zpravodajsky-proces-ci|Základní zpravodajský proces CI — 9 kroků]]
- [[dezinformace|Dezinformace]]
- [[detekce-identifikace-dezinformace|Detekce a identifikace dezinformace]]
- [[casova-analyza|Časová analýza a T-analýza]]
- [[analyza-konkurenta-porter|Analýza konkurenta — 4 rohy podle Portera]]
- [[sedm-otazek-zpravodajske-analyzy|Sedm otázek zpravodajské analýzy + QUI BONO]]
- [[expertni-systemy|Expertní systémy (IrmanK)]] — strukturované hypotézové uvažování ve FEL-EXPERT

## Reference

- BARTES, František. *Konkurenční zpravodajství. Tvorba podkladů pro strategické rozhodování podniku.* Praha: Grada, 2022. ISBN 978-80-271-3504-2. — kap. 6 (Charakteristiky vybraných metod CI).
- HEUER, Richards J. Jr. *Psychology of Intelligence Analysis.* CIA Center for the Study of Intelligence, 1999. — původní formulace ACH.
