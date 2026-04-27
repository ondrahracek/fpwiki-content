---
title: "Risk Management — 2. část přednášky"
course: irmank
type: summary
tags: [irmank, riziko, mapa-rizik, faktoring, akreditiv, npv, expertni-systemy]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Risk Management — 2. část přednášky

Druhá část přednáškového bloku prof. Raise zaměřená na **riziko samotné** — jeho definici, měření, klasifikaci, mapování, taktiky snižování, finanční nástroje a AI metody. První část (modely změny) je v [[irmank-cast-1]].

> [!info] TL;DR
> Tato část staví na trojúhelníku **úspěch — riziko — změna** a postupuje od abstraktní teorie ke konkrétním nástrojům: **definice rizika** → **statistické měření** (σ, KV) → **mapa rizik** (5×5) → **4 taktiky** (vyvárování / udržení / redukce / přenos) → **6 metod snižování** (od retence po monitoring) → **finanční nástroje** (faktoring, forfaiting, akreditiv) → **operační výzkum a AI** (LP, McFarlan portfolio, FEL-EXPERT, GA, ANN) → **investiční rozhodování** (BOT vodní elektrárna 260 mil USD) → **krizové řízení**. Klíčové vzorce: $R = D \times P$, $\sigma = \sqrt{\sigma^2}$, $KV = \sigma / E(r)$.

## Klíčový obsah

### Obsah modulu

8 hlavních témat:

1. Změna strategie, strategická změna a riziko ve firmě.
2. Základní techniky řízení změny + snižování rizika.
3. Základní typy strategií, model změny strategie firmy.
4. Faktory úspěchu/neúspěchu změny strategie + matematické modely.
5. **Riziko** — pojmy, mapa rizik, praktické využití.
6. Metody snižování rizika v jednotlivých funkčních strategiích (case studies).
7. Programové nástroje firemního strategického rozhodování.
8. Informační riziko, právní rizika a jejich prevence.

### Doporučená literatura

- Rais, Smejkal — *Řízení rizik* (Grada, 2003).
- Vaughan — *Risk management* (John Wiley, 1972).
- Dostál, Rais, Sojka — *Pokročilé metody manažerského rozhodování* (Grada, 2005).
- Capman, Ward — *Project Risk Management* (John Wiley, 2001).
- Peters, Waterman — *In Search of Excellence* (Harper Collins, 2012).
- Smejkal, Rais — *Řízení rizik ve firmách a jiných organizacích* (4. aktual. vyd., Grada, 2013).
- Kotter — *Leading Change* (Perseus Books, 2012).
- Mills, Dye, Mills — *Understanding Organizational Change* (Routledge, 2009).
- **Taleb — *Černá labuť*** (Paseka, 2011) — fenomén nepředvídaných jevů s vysokým dopadem (11. září 2001, Google, finanční krize).

### Trojúhelník úspěch–riziko–změna

![[irmank-trojuhelnik-uspech-riziko-zmena.jpeg|Provázanost úspěchu, rizika a změny]]

### Definice rizika

10 základních definic (možnost ztráty, neurčitost, odchylka skutečné × očekávané, pravděpodobnost…). **Podnikatelské riziko má dvě stránky** — pozitivní (vyšší zisk) a negativní (horší výsledky). Tři postoje k riziku: **averze / sklon / neutrální**.

> „Risk comes from not knowing what you do." — Warren Buffett

### Měření rizika

$$\sigma^2 = \sum_{i=1}^{n} (r_i - E(r))^2 \cdot P_i$$
$$\sigma = \sqrt{\sigma^2}$$
$$KV(\%) = \frac{\sigma}{E(r)}$$

**Příklad:** ČS akcie 179.14 Kč, σ ≈ 8.95 Kč ≈ 5 %.

![[irmank-mereni-rizika-odchylky.jpeg|Grafická interpretace odchylek r₁−E, r₂−E, r₃−E od střední hodnoty E]]

### Mapa rizik

$$R = D \times P$$

5 stupňů P (pravděpodobnost: téměř nemožná → hraničící s jistotou).
5 stupňů D (dopad: téměř neznatelný → nepřijatelný).

3 zóny: **kritická (červená) / závažná (žlutá) / běžná (zelená)**. Roční aktualizace.

![[irmank-mapa-rizik-priklad.jpeg|Skutečná mapa rizik s 30+ kódovanými riziky]]

### 4 taktiky řízení rizik

| Pravděpodobnost \\ Dopad | Nízký dopad | Vysoký dopad |
|---|---|---|
| **Nízká** P | Udržení (retence) | Přenos (pojištění) |
| **Vysoká** P | Vyvárování | Redukce |

![[irmank-4-taktiky-matice.jpeg|4 taktiky řízení rizik podle matice P × D]]

### Klasifikace rizik

- Podle dopadu: **kritická / důležitá / běžná**.
- 6 typů podle vlastnosti: **dynamická × statická**, **čistá × spekulativní**, **celková × dílčí**.

### Metody snižování rizika

**6 zvládacích strategií:** ignorance, retence, redukce, vyhýbání, přenos, monitoring.

**Tradiční dělení 2×2:** vyhnutí/redukce, pojištění, retence/redukce, retence.

**Diverzifikace:**

- vertikální × horizontální × příbuzná × nepříbuzná
- geografická, zákaznická, prodejních kanálů, dodavatelská
- české příklady: vinaři, OHL ŽS, Metrostav, GITY, UNIS

### Finanční nástroje

- **Faktoring** — postoupení pohledávek (§524–530 ObčZ), recourse vs. non-recourse, náklady (úrok base+premium, fee 1–3 %), 5 výhod.
- **Forfaiting** — exportní pohledávky bez recourse, medium/long-term.
- **Dokumentární akreditiv** — 7-step flow (Kupující → Banka otevírající → Avizující banka → Prodávající), 3 způsoby krytí v ČR (blokace / úvěr / rezervace).

### Operační výzkum + AI

- **LP a síťová analýza** — deterministické modely.
- **Oddlužení podniků** (64 mld Kč) — princip nettingu A→B(15) / B→C(5) / C→A(10) → Fond národního majetku.
- **McFarlanův portfolio model** — 2×2 matice business × technické znalosti: Strategické / Turnaround / Factory / Support.
- **Expertní systémy** — FEL-EXPERT shell, 37 hypotéz, 30 metod snižování rizika, deployment Úřad vlády 1988–90.
- **Prognostické metody** ([[predikce]]) — kvantitativní (Box-Jenkins, klouzavé průměry, extrapolace, regrese) a kvalitativní (brainstorming, Delphi, prognostické hry, systémová dynamika, simulační ekonometrické modely).
- **Genetické algoritmy** ([[geneticke-algoritmy]]) — 100 tisíc generací, validace NPV.
- **Umělé neuronové sítě** ([[umele-neuronove-site]]) — investiční vektor X = (X₁..Xₘ), supervised learning na N+1 historických případech.

> „AI metody jsou asistenti, ne náhrada za tvůrčí strategické myšlení manažera."

### Case study: BOT vodní elektrárna

- **260 mil USD**, 19 let, 6 % úrok.
- Fázová investice rok 1–6 (20–70 mil USD).
- Opex 25 → 15 mil USD.
- Daň 31 %, energie 89.50 USD/MWh, výstup 480 GWh/rok.
- **Citlivostní analýza:**
  - +2 % provozní náklady → posun návratnosti o roky.
  - +15 % cena → výrazná amplifikace NPV volatility, zejména po roce 12.

![[irmank-npv-citlivost-naklady-2pct.jpeg|NPV citlivost +2 % nákladů]]
![[irmank-npv-citlivost-cena-15pct.jpeg|NPV citlivost +15 % cenové změny]]

### Krizové řízení

- **7 rysů neúspěšného manažera** — tabulka behavior–pitfall–warning.
- **Manažerské problémy v krizi 2008** — pokles poptávky, credit squeeze, nezaměstnanost.
- **Desatero pro manažery v krizi**.
- **Samostatná práce** — volba firmy v krizi, 15 min skupinová, návrh plánu změn pro konkrétní oddělení.
- **Zadání projektu** — 15–20 stran, kritická analýza + vlastní model + metody snižování rizika + harmonogram.

## Mapa diagramů

| Embedovaný obrázek | Topic |
|---|---|
| `irmank-trojuhelnik-uspech-riziko-zmena.jpeg` | [[definice-rizika]], course |
| `irmank-mereni-rizika-odchylky.jpeg` | [[mereni-rizika]] |
| `irmank-katalog-rizik.jpeg` | [[analyza-rizik-proces]] |
| `irmank-mapa-rizik-priklad.jpeg` | [[mapa-rizik]] |
| `irmank-4-taktiky-matice.jpeg` | [[taktiky-rizeni-rizik]] |
| `irmank-proces-rizeni-rizik.jpeg` | [[taktiky-rizeni-rizik]] |
| `irmank-rizik-cyklus-4faze.jpeg` | [[taktiky-rizeni-rizik]] |
| `irmank-tradicni-deleni-2x2.jpeg` | [[metody-snizovani-rizika]] |
| `irmank-volba-metody-3x4.jpeg` | [[metody-snizovani-rizika]] |
| `irmank-faktoring-flow.jpeg` | [[faktoring]] |
| `irmank-akreditiv-flow.jpeg` | [[dokumentarni-akreditiv]] |
| `irmank-mcfarlan-2x2.jpeg` | [[mcfarlan-portfolio]] |
| `irmank-oddluzeni-debt-netting.jpeg` | [[operacni-vyzkum]] |
| `irmank-bot-elektrarna-parametry.jpeg` | [[investicni-rozhodovani-bot]] |
| `irmank-npv-citlivost-naklady-2pct.jpeg` | [[investicni-rozhodovani-bot]] |
| `irmank-npv-citlivost-cena-15pct.jpeg` | [[investicni-rozhodovani-bot]] |
| `irmank-ann-vstupni-matice.jpeg` | cross-link [[umele-neuronove-site]] |
