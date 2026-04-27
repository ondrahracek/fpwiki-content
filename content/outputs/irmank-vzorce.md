---
title: "IrmanK — Přehled vzorců a klíčových modelů"
course: irmank
type: output
tags: [irmank, vzorce, modely, npv, sigma, mapa-rizik, cpm-pert]
sources:
  - raw/irmank/Rizeni rizik_prvni cast  začátek přednášek   2026 léto fin (1).ppt
  - raw/irmank/Řízení rizik druhá část.ppt
created: 2026-04-27
updated: '2026-04-27'
---

# IrmanK — Přehled vzorců a klíčových modelů

## Úvod

Tento referenční list shrnuje **všechny klíčové vzorce a modely** kurzu [[irmank|Risk management (IrmanK)]] potřebné pro přípravu na zkoušku. Pro každý vzorec je uveden:

- **vzorec** v LaTeX zápisu,
- **význam jednotlivých proměnných**,
- **kdy a proč se používá**,
- **odkaz na příslušnou topic stránku** s plným výkladem.

Stránka je strukturovaná podle tematických bloků kurzu: měření rizika → mapa rizik → taktiky a metody snižování → síťová analýza projektu → investiční rozhodování → strategické modely (McFarlan, Lewin, EFQM, 7S) → finanční nástroje → diverzifikace a klasifikace.

---

## 1. Měření rizika — statistické charakteristiky

Plný výklad: [[mereni-rizika]].

### 1.1 Rozptyl σ²

$$\sigma^2 = \sum_{i=1}^{n} (r_i - E(r))^2 \cdot P_i$$

- $r_i$ — i-tá hodnota proměnné (výnos, cena akcie, kurz),
- $E(r)$ — střední hodnota (očekávaná hodnota), $E(r) = \sum r_i \cdot P_i$,
- $P_i$ — pravděpodobnost i-té hodnoty (nebo $1/n$ pro empirické rozdělení),
- $n$ — počet pozorování.

**Jednotka:** kvadrát původní jednotky (Kč², %²) — interpretačně nepraktická, proto se v praxi používá σ.

### 1.2 Směrodatná odchylka σ

$$\sigma = \sqrt{\sigma^2}$$

- Stejné jednotky jako $r_i$ — typická odchylka výnosu od průměru.
- Pravidlo **68–95–99,7 %** pro normální rozdělení.
- **Vyšší σ → vyšší volatilita → vyšší riziko.**

### 1.3 Koeficient variace KV

$$KV\,(\%) = \frac{\sigma}{E(r)} \cdot 100\,\%$$

- **Bezrozměrný** — umožňuje srovnání rizik **různě velkých aktiv** (akcie 200 Kč × dluhopis 10 000 Kč).
- Vyšší KV = vyšší relativní riziko na jednotku výnosu.

### 1.4 Příklad — akcie ČS

| Veličina | Hodnota |
|---|---|
| Cena akcie ČS, $E$ | 179,14 Kč |
| Směrodatná odchylka, $\sigma$ | 8,95 Kč |
| Koeficient variace, $KV$ | ≈ 5 % |

Typická odchylka ceny od průměru je ±8,95 Kč; v intervalu 170,19 – 188,09 Kč by mělo ležet ~68 % pozorování.

### 1.5 Variance portfolia (2 aktiva)

$$\sigma_p^2 = w_1^2 \sigma_1^2 + w_2^2 \sigma_2^2 + 2 w_1 w_2 \rho \sigma_1 \sigma_2$$

- $w_1, w_2$ — váhy aktiv v portfoliu, $w_1 + w_2 = 1$,
- $\sigma_1, \sigma_2$ — směrodatné odchylky výnosů jednotlivých aktiv,
- $\rho$ — korelační koeficient výnosů obou aktiv.

**Klíč pro [[diverzifikace-rizik|diverzifikaci]]:** při $\rho < 1$ je $\sigma_p < w_1\sigma_1 + w_2\sigma_2$ — kombinace nedokonale korelovaných aktiv snižuje portfolio riziko.

---

## 2. Hodnota rizika a mapa rizik

Plný výklad: [[mapa-rizik]].

### 2.1 Vzorec rizika

$$R = D \times P$$

- $R$ — hodnota rizika (Risk score), $0{,}01 \leq R \leq 25{,}0$,
- $D$ — dopad (Damage / Impact), škála 0,1–5,0,
- $P$ — pravděpodobnost (Probability), škála 0,1–5,0.

### 2.2 Tři zóny mapy rizik

| Zóna | Hodnota R | Akce |
|---|---|---|
| **Kritická (červená)** | $R \geq 5$ | Okamžitě, top management, redukce/přenos |
| **Závažná (žlutá)** | $1 \leq R < 5$ | Plán mitigace 6–12 měsíců |
| **Běžná (zelená)** | $R < 1$ | Monitoring, periodické přezkoumávání |

### 2.3 Stupnice pravděpodobnosti P

| Stupeň | Slovní popis | Hodnota |
|---|---|---|
| 1 | Téměř nemožná | 0,1 |
| 2 | Velmi nepravděpodobná | 0,5 |
| 3 | Pravděpodobná | 1,0 |
| 4 | Velmi pravděpodobná | 2,0 |
| 5 | Hraničící s jistotou | 5,0 |

### 2.4 Stupnice dopadu D

| Stupeň | Slovní popis | Hodnota |
|---|---|---|
| 1 | Téměř neznatelný | 0,1 |
| 2 | Drobný | 0,5 |
| 3 | Významný | 1,0 |
| 4 | Závažný | 2,0 |
| 5 | Nepřijatelný | 5,0 |

---

## 3. Čtyři taktiky řízení rizik

Plný výklad: [[taktiky-rizeni-rizik]].

| | **Nízký dopad D** | **Vysoký dopad D** |
|---|---|---|
| **Nízká P** | Udržení (retence) | Přenos (pojištění) |
| **Vysoká P** | Vyvárování | Redukce |

- **Udržení (retence)** — riziko nese firma sama z provozního rozpočtu.
- **Přenos** — pojištění, outsourcing, hedging, faktoring.
- **Vyvárování (avoidance)** — vystoupit z činnosti, nedělat danou aktivitu.
- **Redukce** — snížit P (preventivní opatření) nebo D (kontingenční plán).

---

## 4. Šest metod snižování rizika

Plný výklad: [[metody-snizovani-rizika]].

1. **Ignorance** — riziko není rozpoznáno (anti-pattern, ne strategie).
2. **Retence (akceptace)** — vědomé převzetí rizika.
3. **Redukce** — snížení P nebo D opatřeními.
4. **Vyhýbání** — eliminace zdroje rizika.
5. **Přenos** — pojištění, outsourcing, smluvní přenos.
6. **Monitoring** — sledování a včasné varování.

### 4.1 Tradiční dělení 2×2

| | **Nízká P** | **Vysoká P** |
|---|---|---|
| **Vysoký D** | Pojištění | Vyhnutí / redukce |
| **Nízký D** | Retence | Retence / redukce |

---

## 5. Síťová analýza projektu — CPM

Plný výklad: [[sitova-analyza-cpm-pert]].

### 5.1 Výpočetní veličiny

- **ES** (Earliest Start) — forward pass: $ES_i = \max(EF_{\text{predchudce}})$
- **EF** (Earliest Finish): $EF_i = ES_i + d_{ij}$
- **LS** (Latest Start) — backward pass: $LS_i = LF_i - d_{ij}$
- **LF** (Latest Finish): $LF_i = \min(LS_{\text{naslednik}})$
- **TM₁** (celková doba projektu) = max $EF$ v koncovém uzlu = délka kritické cesty.
- **TPⱼ** (celková časová rezerva uzlu): $TP_j = LS_j - ES_j = LF_j - EF_j$
- **Kritická cesta** — posloupnost uzlů s $TP_j = 0$. Zpoždění libovolné aktivity na ní zpožďuje celý projekt.

### 5.2 Postup výpočtu

```
1. Forward pass:  ES, EF od počátečního uzlu k koncovému.
2. Backward pass: LS, LF od koncového uzlu zpět.
3. TPⱼ = LSⱼ − ESⱼ pro každý uzel.
4. Kritická cesta = uzly s TPⱼ = 0.
```

---

## 6. PERT — stochastické trvání

Plný výklad: [[sitova-analyza-cpm-pert]].

### 6.1 Tři odhady času (β-rozdělení)

- $a$ — **optimistický** odhad,
- $m$ — **nejpravděpodobnější** odhad,
- $b$ — **pesimistický** odhad.

### 6.2 Očekávané trvání aktivity

$$t_e = \frac{a + 4m + b}{6}$$

### 6.3 Variance aktivity

$$\sigma^2_{\text{aktivita}} = \left(\frac{b - a}{6}\right)^2$$

### 6.4 Variance projektu

$$\sigma^2_{\text{projekt}} = \sum_{i \in \text{kriticka cesta}} \sigma^2_{\text{aktivita}_i}$$

Předpoklad nezávislosti aktivit. Z $\sigma^2_{\text{projekt}}$ se odvozuje pravděpodobnost dokončení do plánovaného termínu pomocí standardizace na normální rozdělení.

---

## 7. Investiční vzorce

Plný výklad: [[investicni-rozhodovani-bot]].

### 7.1 Net Present Value (NPV)

$$NPV = \sum_{t=0}^{T} \frac{CF_t}{(1 + r)^t}$$

- $CF_t$ — čistý peněžní tok v roce $t$ ($CF_0$ obvykle počáteční investice, záporné),
- $r$ — diskontní sazba (cost of capital, WACC),
- $T$ — doba životnosti projektu.

**Pravidlo:** $NPV > 0$ → projekt přijatelný; vyšší NPV → lepší projekt.

### 7.2 Internal Rate of Return (IRR)

$$\sum_{t=0}^{T} \frac{CF_t}{(1 + IRR)^t} = 0$$

- IRR je sazba, při které $NPV = 0$.

**Pravidlo:** $IRR > r$ → projekt přijatelný.

### 7.3 Payback period

- **Prostá doba návratnosti** — rok $T_p$, kdy kumulovaný $CF$ poprvé překročí 0:
$$\sum_{t=0}^{T_p} CF_t \geq 0$$
- **Diskontovaná doba návratnosti** — totéž s diskontovanými $CF_t / (1+r)^t$.

### 7.4 BOT vodní elektrárna — case study

Parametry projektu: **260 mil USD investice, 19 let provozu, 6 % diskontní sazba**.

- Citlivost na **+2 % opex** → posun bodu návratnosti o roky.
- Citlivost na **+15 % cena výstupu** → výrazná amplifikace NPV po roce 12.
- Demonstruje, že **dlouhé projekty jsou hyper-citlivé** na drobné změny vstupů.

---

## 8. McFarlanův 2×2 portfolio model

Plný výklad: [[mcfarlan-portfolio]].

| | **Nízká business hodnota** | **Vysoká business hodnota** |
|---|---|---|
| **Vysoké tech znalosti** | **Factory** (klíčové) | **Strategické** |
| **Nízké tech znalosti** | **Support** (podpůrné) | **Turnaround** (potenciální) |

- **Strategic** — IS/IT rozhoduje o konkurenceschopnosti, kritická investice.
- **Turnaround** — vysoký byznys potenciál, ale zatím nezvládnutá technologie; pilotní projekty.
- **Factory** — kritický pro provoz, ale ne pro budoucí strategii; spolehlivost a TCO.
- **Support** — administrativní podpora; outsourcing nebo standardní řešení.

---

## 9. Lewinův model — tři fáze změny

Plný výklad: [[lewinuv-model]].

1. **Rozmrazení (Unfreezing)** — analýzy, komunikace nutnosti změny, snížení odporu, alokace zdrojů, identifikace agenta změny.
2. **Vlastní změna (Moving)** — agent provede zásah ve **4 intervenčních oblastech**:
   - lidé (HR — nábor, rekvalifikace),
   - struktura (organigram, role),
   - technologie (IS/IT, výrobní postupy),
   - komunikace (procesy, informační toky).
3. **Zmrazení (Refreezing)** — fixace nového stavu, KPI, rituály, kultura, prevence relapsu.

### 9.1 Osm prvků schématu změny

Síly → sponzor → nositel (agent) → strategie → metody → realizace → zhodnocení (+ kontingenční plán). Plný popis v [[lewinuv-model]].

---

## 10. EFQM model excelence

Plný výklad: [[kriticke-faktory-uspechu]].

Celkem **1000 bodů**, paritně rozdělených na předpoklady (50 %) a výsledky (50 %).

### 10.1 Předpoklady (500 bodů)

| Kritérium | Body |
|---|---|
| Vedení | 100 |
| Pracovníci | 90 |
| Politika a strategie | 90 |
| Partnerství a zdroje | 90 |
| Procesy | 140 |

### 10.2 Výsledky (500 bodů)

| Kritérium | Body |
|---|---|
| Výsledky pracovníci | 90 |
| Výsledky zákazníci | 200 |
| Výsledky společnost | 60 |
| Klíčové výsledky výkonnosti | 150 |

**Procesy (140) a Zákazníci (200)** jsou nejvíce vážená kritéria — odrážejí orientaci modelu na procesní výkonnost a zákaznickou hodnotu.

---

## 11. McKinsey 7S framework

Plný výklad: [[kriticke-faktory-uspechu]].

Sedm vzájemně propojených prvků organizace (3 „hard" + 4 „soft"):

| Prvek | Charakteristika |
|---|---|
| **Strategy** (strategie) | hard — směr a konkurenční výhoda |
| **Structure** (struktura) | hard — organigram, hierarchie |
| **Systems** (systémy) | hard — procesy, IS, řízení |
| **Skills** (schopnosti) | soft — klíčové kompetence firmy |
| **Style** (styl) | soft — manažerský styl, kultura vedení |
| **Staff** (spolupracovníci) | soft — lidé, talent, fluktuace |
| **Shared values** (sdílené hodnoty) | soft — kultura, vize, etika |

**Zlaté pravidlo 7S:** všechny prvky musejí být **vzájemně konzistentní**. Změna jednoho prvku vyvolává tlak na ostatní.

---

## 12. Faktoring — náklady

Plný výklad: [[faktoring]].

Tři složky nákladů faktoringu (postoupení pohledávek):

- **Úrok** = base rate (PRIBOR / EURIBOR) + premium **1–4 %** podle bonity klienta a sektoru.
- **Service fee** = **1–3 %** objemu pohledávek (administrativa, vymáhání, evidence).
- **Rezerva** = **5–10 %** zálohy zadržené do úhrady dlužníkem (kryje vratky, sporné pohledávky).

**Recourse vs. non-recourse:** s recourse (regrese) postupitel ručí za nedobytnost; non-recourse přenáší kreditní riziko na faktora — vyšší marže.

---

## 13. Diverzifikace — typy

Plný výklad: [[diverzifikace-rizik]].

### 13.1 Strategické dělení

- **Vertikální** — integrace v hodnotovém řetězci (dodavatelé, odběratelé).
- **Horizontální** — rozšíření v rámci stejné úrovně (nové produkty pro stávající zákazníky).
- **Příbuzná** — synergie know-how, technologie, distribuce.
- **Nepříbuzná** — konglomerát, čistá portfolio diverzifikace.

### 13.2 Operativní dělení

- **Geografická** — regiony, země, kontinenty.
- **Zákaznická** — segmenty, žádný zákazník nad 20 % obratu.
- **Prodejních kanálů** — retail, e-shop, B2B, marketplaces.
- **Dodavatelská** — multi-sourcing, alternativní materiály.

### 13.3 Limit diverzifikace

Diverzifikace **funguje jen pro dílčí (idiosynkratická) rizika** — specifická rizika jednoho aktiva, která se eliminují kombinací nezávislých aktiv. **Systémové (tržní) riziko** zůstává — tržní krach postihne portfolio bez ohledu na počet aktiv.

---

## 14. Klasifikace rizik

Plný výklad: [[klasifikace-rizik]].

### 14.1 Podle závažnosti

- **Kritická** — ohrožuje existenci firmy.
- **Důležitá** — zásadní zásah do činnosti, ale řešitelný.
- **Běžná** — operativní, kryté provozním rozpočtem.

### 14.2 Podle vlastností (3 dichotomie)

| Pojem | Protiklad | Význam |
|---|---|---|
| **Dynamické** | Statické | Mění se v čase × stabilní v čase |
| **Čisté** | Spekulativní | Jen ztráta × ztráta i zisk |
| **Celkové (systémové)** | Dílčí (specifické) | Postihuje celý trh × jen jednu firmu |

### 14.3 Kritická analýza — pět vlastností

Riziko je předmětem prioritní mitigace, pokud splňuje:

1. **Ovlivnitelné** firmou,
2. **Dynamické** (mění se),
3. **Spekulativní** (oboustranné),
4. **Dílčí** (specifické pro firmu),
5. **Selhání podnikatelských subjektů** (nejen externí příčiny).

---

## 15. Postoje k riziku

Plný výklad: [[definice-rizika]].

| Postoj | Charakteristika |
|---|---|
| **Averze** | Preferuje nižší výnos s nižším rizikem; vyžaduje rizikovou prémii |
| **Sklon** | Preferuje vyšší výnos i za cenu vyššího rizika |
| **Neutrální** | Rozhoduje pouze podle očekávané hodnoty $E(r)$ |

Postoj k riziku je **subjektivní** a vstupuje do hodnocení projektů přes **diskontní sazbu** (averzní investor → vyšší $r$ → nižší NPV).

---

## 16. Použití u zkoušky

> **Tip:** Studenti ke zkoušce by měli umět napsat **vzorce zpaměti** ($\sigma^2$, $KV$, $R = D \times P$, $t_e$, $NPV$, $IRR$) a vysvětlit jejich **praktické použití na konkrétní firmě** — typický typ úlohy zkoušky kombinuje výpočet (numerický příklad) a interpretaci (proč zrovna tato metoda).

Doporučený postup u typové úlohy:

1. **Identifikujte typ problému** — měření rizika, hodnocení projektu, plánování síťové analýzy, klasifikace rizika.
2. **Vyberte správný vzorec** z této stránky.
3. **Vyjmenujte proměnné** a jejich hodnoty z textu úlohy.
4. **Spočítejte** — ručně nebo s kalkulačkou.
5. **Interpretujte** — slovně vysvětlete, co výsledek znamená pro rozhodování.

---

## 17. Související přehledy

- [[irmank-glosar|Glosář pojmů kurzu]] — abecední slovník ~80 pojmů.
- [[irmank|Risk management (IrmanK) — kurz]] — hub všech topic stránek.
- [[irmank-cast-1]] — 1. část přednášky (modely změny, síťová analýza).
- [[irmank-cast-2]] — 2. část přednášky (riziko a jeho měření, snižování, AI metody).
