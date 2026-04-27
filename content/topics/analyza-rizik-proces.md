---
title: "Analýza rizik — proces"
course: irmank
type: topic
tags: [irmank, analyza-rizik, identifikace, katalog-rizik, vyhodnoceni, mapa-rizik]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Analýza rizik — proces

> [!info] TL;DR
> Analýza rizik je strukturovaný **třístupňový proces**:
>
> 1. **Identifikace** — co může selhat (brainstorming s klíčovými stakeholdery, vazba na kritická aktiva a cash flow).
> 2. **Katalog rizik** — vyhodnocení skupinou expertů, sběr ze **3+ informačních zdrojů** (interní dokumenty, externí benchmarky, expertní rozhovory).
> 3. **Vyhodnocení v matici 5×5** — pravděpodobnost (P) × dopad (D), kde $R = D \times P$.
>
> Výsledkem je [[mapa-rizik|mapa rizik]] s prioritizací. Integrované řízení rizik na úrovni firmy/univerzity (E&Y guidance) zajišťuje organizační governance prostřednictvím výboru pro řízení rizik, manažera rizik a risk ownerů. Pro pojmosloví viz [[definice-rizika]], pro kvantitativní vstupy [[mereni-rizika]].

## Třístupňový proces

![[irmank-katalog-rizik.jpeg|Proces katalogu rizik: zdroje 1..n → základní soubor → skupinové hodnocení → mapa rizik]]

Flow analýzy rizik:

1. **Tři informační zdroje** (interní dokumenty, externí benchmarky, expertní rozhovory) — paralelní sběr.
2. **Základní soubor potenciálních rizik** — sloučení a deduplikace, typicky 50–500 položek.
3. **Skupinové hodnocení potenciálních rizik** — workshop expertů, řízená diskuse, prioritizace.
4. **Mapa rizik** — výstupní artefakt s 20–100 nejdůležitějších rizik na matici P × D.

Klíčové je, že proces není sériový pingpong jednoho analytika, ale **kolektivní triangulace** — různé zdroje a různé hlavy se musí potkat nad stejným seznamem.

## Krok 1: Identifikace rizik

První krok odpovídá na otázku „co všechno může selhat". Z metodiky:

- **Brainstorming** s klíčovými stakeholdery — manažeři, zaměstnanci, externí konzultanti, případně dodavatelé a zákazníci.
- **Výběr rizik vztažených k nejdůležitějším aktivům** firmy — nemá smysl identifikovat rizika u marginálního majetku, fokus na to, co tvoří hodnotu.
- Pohled na **cash flow** firmy — riziko, které ohrožuje peněžní toky, je systémově důležitější než riziko izolované ztráty.
- Mapování **klíčových procesů** — pro každý kritický proces identifikovat, co může jeho průběh narušit.
- **Hodnocení úrovně hrozeb** — kvalitativní odhad, jak silné a pravděpodobné jsou jednotlivé hrozby.
- **Hodnocení potenciální ztráty** — kvantitativně (Kč, % obratu) i kvalitativně (reputace, soulad s předpisy, morálka).

Pro pojmosloví („hrozba", „zranitelnost", „aktivum", „dopad") viz [[definice-rizika]]. Identifikace bez ukotvení v terminologii vede k nekonzistentnímu katalogu.

## Krok 2: Katalog rizik

Katalog je **konsolidovaný registr potenciálních rizik** vzniklý z více nezávislých zdrojů. Metodika vyžaduje **minimálně tři informační zdroje**:

1. **Interní dokumenty firmy** — výsledky auditů, deníky incidentů, pojistné události, reklamace, hlášení o neshodách, zápisy z porad managementu, výsledky předchozích analýz rizik.
2. **Externí benchmarky** — publikované mapy rizik z odvětví, zprávy regulátorů (ČNB, NÚKIB, ÚOOÚ), benchmarky konzultačních firem (E&Y, Deloitte, KPMG, PwC), oborové asociace, akademické studie.
3. **Expertní rozhovory** — strukturované rozhovory s manažery jednotlivých útvarů, zaměstnanci v provozu, dodavateli, zákazníky a (kde je přístup) i konkurencí.

### Sloučení do základního souboru

Po sběru dat z těchto zdrojů vznikne **základní soubor potenciálních rizik** — typicky 50–500 položek. Položky se musejí:

- **Deduplikovat** (různé zdroje často popisují totéž jinými slovy).
- **Normalizovat** (jednotná granularita — buď úroveň „výpadek IT" nebo „výpadek SAP modulu FI", ne smíchaně).
- **Klasifikovat** podle taxonomie (viz [[klasifikace-rizik]]).

### Skupinové hodnocení

Výsledný základní soubor jde do workshopu expertů — **skupinové hodnocení**. Jeho cílem je:

- diskutovat smysluplnost každého rizika (některá zaniknou jako duplicity, jiná se rozpadnou na více),
- prioritizovat (hrubě vyřadit zjevně marginální),
- doplnit chybějící (kolektivní paměť doplní, co individuální zdroje neviděly).

**Výstup:** očištěný katalog s **20–100 nejdůležitějších rizik**, který jde do dalšího kroku — kvantitativního vyhodnocení.

## Krok 3: Vyhodnocení rizik

Třetí krok **přiřazuje hodnoty** každému riziku z katalogu. Metoda: řízená diskuse expertů, kde se odhaduje pravděpodobnost (P) a dopad (D) na pětistupňové škále.

### Tabulka pravděpodobnosti P

| Stupeň | Pravděpodobnost | Hodnota |
|---|---|---|
| 1 | Téměř nemožná | 0.1 |
| 2 | Velmi nepravděpodobná | 0.5 |
| 3 | Pravděpodobná | 1.0 |
| 4 | Velmi pravděpodobná | 2.0 |
| 5 | Hraničící s jistotou | 5.0 |

Stupnice je **nelineární** (skoky 0.1 → 0.5 → 1.0 → 2.0 → 5.0) — tím se zvýrazní vysoké pravděpodobnosti při násobení s dopadem.

### Tabulka dopadu D

| Stupeň | Dopad | Hodnota |
|---|---|---|
| 1 | Téměř neznatelný | 0.1 |
| 2 | Málo významný | 0.5 |
| 3 | Významný | 1.0 |
| 4 | Velmi významný | 2.0 |
| 5 | Nepřijatelný | 5.0 |

Dopad může být peněžní (% z obratu, EBITDA), reputační, právní (sankce, ztráta licence) nebo provozní (přerušení činnosti).

### Hodnota rizika

$$R = D \times P$$

Maximální hodnota $R = 5.0 \times 5.0 = 25.0$, minimální $R = 0.1 \times 0.1 = 0.01$. Riziko se umisťuje do matice 5×5 podle stupňů; podrobnosti, prahy a barevné zóny (zelená/žlutá/červená) viz [[mapa-rizik]].

## Integrované řízení rizik (E&Y)

Z metodiky Ernst & Young: **vnitřní kontrolní systém** firmy/univerzity zjišťuje a minimalizuje:

- **operační rizika** (selhání procesů, lidí, IT),
- **finanční rizika** (likvidita, kurz, úvěr),
- **právní rizika** (compliance, sankce, spory),
- **a další** (reputační, strategická, environmentální).

### Integrace napříč firmou

Řízení rizik **prostupuje všemi vrstvami** organizace:

- **Strategická úroveň** — riziková apetence, klíčové strategické sázky, M&A.
- **Taktická úroveň** — projekty, investice, dodavatelské vztahy.
- **Operační úroveň** — denní procesy, incidenty, kontroly.

Bez integrace vznikají **slepá místa**: strategie identifikuje riziko, které operace nezná, nebo naopak operace zaznamenává incidenty, které strategie přehlíží.

### Univerzitní kontext

ČR ministerstvo školství vyžaduje **vnitřní kontrolu rizik na vysokých školách** (zákon o finanční kontrole 320/2001 Sb., metodické pokyny MŠMT). Univerzita je tak ze zákona povinna provozovat formalizovaný proces analýzy rizik — pro FP VUT to znamená pravidelné aktualizace mapy rizik a auditní stopu.

## Organizační zajištění

Aby analýza rizik nezůstala na úrovni cvičení v Excelu, vyžaduje **trvalé organizační role**:

- **Výbor pro řízení rizik** — kolektivní orgán (typicky složený z členů vedení), který kontroluje opatření, schvaluje strategii řízení rizik, projednává zásadní rizika.
- **Manažer rizik** (CRO — Chief Risk Officer / risk manager) — odpovídá za **mapu rizik** v konkrétní části firmy/univerzity, koordinuje workshopy, udržuje registr.
- **Risk owner** — odpovědný za **konkrétní riziko**. Pravidlo „jeden úředník = jedno riziko" — každé riziko má právě jednoho vlastníka, který hlásí stav, navrhuje opatření a je za něj zodpovědný.
- **Audit** — periodicky (interní audit nebo externí) **verifikuje implementaci** opatření, kontroluje, zda risk register odpovídá realitě.

Bez těchto rolí mapa rizik zastará během 6–12 měsíců.

## Praktický postup analýzy mapy rizik

Univerzitní příklad — **pět identifikovaných oblastí**:

1. **Ekonomika** — rozpočet, cash flow, dluhy, závislost na klíčových příjmech.
2. **Dotace a granty** — závislost na konkrétních zdrojích (TAČR, GAČR, OP JAK), audit dotací, vratky.
3. **Činnost** — pedagogická (akreditace, kvalita výuky), výzkumná (publikační výkon, RIV).
4. **Řízení** — rozhodovací procesy, governance, střet zájmů, výběrová řízení.
5. **Provozní podmínky** — infrastruktura, IT, energie, BOZP, požární ochrana.

V každé oblasti se identifikuje **5–50 rizik** podle granularity. Celková velikost katalogu pro střední univerzitu: 50–250 rizik.

## Identifikace procesů a rizik

Alternativní (a komplementární) přístup — **procesní mapa**:

- Identifikace **~200 procesů** firmy/univerzity (např. „přijetí studenta do bakalářského studia", „proplacení faktury", „evidence majetku").
- Pro každý proces — rizika, která **negativně ovlivňují cíle** procesu (zpoždění, chyba, podvod, ztráta dat).
- Zapojení **manažerů jednotlivých procesů** — process owner odpovídá za identifikaci rizik svého procesu (s poradním hlasem manažera rizik).

### Risk register

Jednoznačná evidence — každé riziko má:

| Pole | Význam |
|---|---|
| ID | Unikátní identifikátor (např. EKO-007) |
| Popis | Stručný název + jedno-dvouvětá specifikace |
| Oblast / proces | Kam riziko patří |
| P | Pravděpodobnost (1–5) |
| D | Dopad (1–5) |
| R | $R = P \times D$ |
| Vlastník | Risk owner (jméno, role) |
| Opatření | Aktuální + plánovaná |
| Status | Otevřené / mitigované / přijaté / přenesené |
| Datum revize | Kdy bylo naposledy přehodnoceno |

## Aktualizace mapy rizik

Mapa rizik **není jednorázový artefakt** — je to živý dokument:

- **Tvorba a aktualizace** probíhá ve **skupině expertů** (workshop, řízená diskuse).
- **Možnost anonymity** — anonymní hlasování (např. přes Mentimeter) snižuje politické tlaky a manažeři snáze přiznají nepříjemná rizika ve své oblasti odpovědnosti.
- **Frekvence:**
  - **Roční full review** — kompletní revize katalogu, P, D, opatření.
  - **Kvartální mini-review** — kontrola TOP 10 rizik, status opatření, nově vzniklá rizika.
- **Trigger události** — neplánované aktualizace při:
  - velkém incidentu (např. ransomware útok, požár, smrt na pracovišti),
  - regulační změně (nový zákon, nová direktiva),
  - **M&A** (akvizice, fúze, prodej),
  - **nových technologiích** (cloud migrace, AI, nová ERP),
  - personálních změnách v klíčových rolích.

## Časté chyby v procesu

- **Neidentifikujeme „neznámé neznámé"** — Talebovy černé labutě (události s extrémně nízkou pravděpodobností a extrémně vysokým dopadem) procházejí sítem expertního workshopu, protože nikdo na ně nemyslel. Mitigace: scénářová cvičení (red team, premortem).
- **Politická manipulace** s mapou rizik — odpovědný manažer má motivaci snížit P i D ve své oblasti (aby nevypadal špatně). Mitigace: anonymita, externí facilitátor, audit.
- **Statická mapa** — vytvoří se jednou a léta se neaktualizuje. Mezitím se mění vnější prostředí, technologie, regulace. Mitigace: pevná frekvence aktualizace + trigger události.
- **Zaměření na kvantifikovatelná rizika** a opomíjení reputačních, kulturních a právních (která se hůře měří, ale často mají největší dopad). Mitigace: explicitní kategorie pro „měkká" rizika v taxonomii.
- **Risk register se vytvoří, ale nečte** — analýza je fakticky cvičení do šuplíku. Mitigace: integrace risk registru do strategického a operativního rozhodování (např. povinný odkaz na riziko v každém investičním návrhu nad limitní částku).

## Souvislosti

- [[definice-rizika]] — co je riziko, hrozba, zranitelnost, aktivum, dopad.
- [[mereni-rizika]] — kvantitativní vstup pro krok 3 (směrodatná odchylka σ, koeficient variace KV).
- [[mapa-rizik]] — vizualizace 5×5 (P × D), barevné zóny, prioritizace.
- [[klasifikace-rizik]] — taxonomie rizik používaná při katalogizaci.
- [[taktiky-rizeni-rizik]] — co s riziky dělat (vyvarování / udržení / redukce / přenos).
- cross-course: [[rizeni-rizik]] (imork) — ISO 27005 metodika analýzy informačních rizik, paralelní postup pro doménu InfoSec.

## Navigace
- **Předchozí:** [[mereni-rizika]]
- **Navazující:** [[mapa-rizik]]
- **Související:** [[klasifikace-rizik]], [[taktiky-rizeni-rizik]]
