---
title: "Mapa rizik"
course: irmank
type: topic
tags: [irmank, mapa-rizik, riziko, kriticka-zona, zavazna-zona, prijatelna-zona]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Mapa rizik

> [!info] TL;DR
> **Mapa rizik** je dvourozměrná vizualizace všech identifikovaných rizik firmy v souřadnicích **pravděpodobnost P × dopad D**, s hodnotou rizika $R = D \times P$. Body v matici jsou jednotlivá rizika označená kódy; jejich poloha rozhoduje, jak naléhavě je třeba reagovat. Tři barevné zóny:
>
> - **Kritická červená** — okamžitě jednat, top management, redukce nebo přenos.
> - **Závažná žlutá** — plán mitigace v horizontu 6–12 měsíců.
> - **Běžná zelená** — monitoring a periodické přezkoumávání.
>
> Mapa je **živý dokument**: roční plný cyklus aktualizace, kvartální mini-review, mimořádná revize při trigger událostech. Organizační odpovědnost nese **Výbor pro řízení rizik**, vlastníci jednotlivých rizik (risk owners) jsou linioví manažeři.

## Vzorec hodnoty rizika

Hodnota rizika je definována multiplikativně:

$$R = D \times P$$

kde:
- $R$ — hodnota rizika (Risk score),
- $D$ — dopad (Damage / Impact), 5-stupňová škála,
- $P$ — pravděpodobnost (Probability), 5-stupňová škála.

Přípustné hodnoty $R$ jsou v rozsahu od **0.01** (téměř neznatelný dopad × téměř nemožná pravděpodobnost: $0.1 \times 0.1$) až po **25.0** (nepřijatelný dopad × hraničící s jistotou: $5.0 \times 5.0$).

**Multiplikativní logika** má důležitý důsledek — nízký dopad × vysoká pravděpodobnost dává stejné $R$ jako vysoký dopad × nízká pravděpodobnost:

$$0.5 \times 5.0 = 5.0 \times 0.5 = 2.5$$

Z hlediska výsledné hodnoty jde o ekvivalentní rizika, **ale strategie reakce se liší** (viz [[taktiky-rizeni-rizik]]) — frekventovaná malá rizika se redukují operativně, vzácná katastrofická rizika se přenášejí (pojištění) nebo se proti nim staví kontingenční plán.

## Stupnice pravděpodobnosti P

5-stupňová škála kombinuje slovní popis s číselnou hodnotou pro výpočet:

| Stupeň | Slovní popis | Číselná hodnota |
|---|---|---|
| 1 | Téměř nemožná | 0.1 |
| 2 | Velmi nepravděpodobná | 0.5 |
| 3 | Pravděpodobná | 1.0 |
| 4 | Velmi pravděpodobná | 2.0 |
| 5 | Hraničící s jistotou | 5.0 |

**Slovní popis a číselná hodnota** umožňují kombinovat **kvalitativní vstup** (expertní odhad, brainstorming) s **kvantitativním zpracováním** (násobení, agregace, řazení). Hodnoty nejsou lineární — skok mezi stupni 4 a 5 (z 2.0 na 5.0) je výrazně větší než mezi stupni 1 a 2 (z 0.1 na 0.5). Tato **konvexita** záměrně zdůrazňuje extrémní pravděpodobnosti.

**Časový horizont** je třeba vždy specifikovat — výrok „pravděpodobnost je 0.5" nemá smysl bez kontextu. V praxi se používají horizonty:

- **12 měsíců** — operativní rizika (provozní výpadky, drobné incidenty).
- **3 roky** — taktická rizika (ztráta klíčového zákazníka, vstup nového konkurenta).
- **5–10 let** — strategická rizika (technologická disrupce, regulační reforma).

Pro kvantifikaci pravděpodobnosti se používají historická data, srovnatelné případy v odvětví, expertní Delphi metoda nebo Bayesovské aktualizace (viz [[mereni-rizika]]).

## Stupnice dopadu D

5-stupňová škála má stejnou strukturu jako pravděpodobnost:

| Stupeň | Slovní popis | Číselná hodnota | Příklad |
|---|---|---|---|
| 1 | Téměř neznatelný | 0.1 | Drobné nepříjemnosti |
| 2 | Drobný | 0.5 | Lokální dopad, snadná obnova |
| 3 | Významný | 1.0 | Citelná ztráta, ale řešitelná |
| 4 | Závažný | 2.0 | Vážný zásah do činnosti |
| 5 | Nepřijatelný | 5.0 | Existenční ohrožení firmy |

### Dimenze dopadu

Dopad není jednorozměrný — riziko může mít **více současných dopadů**:

- **Finanční** — přímá ztráta v Kč, % EBITDA, % obratu, NPV projektu.
- **Reputační** — ztráta důvěry zákazníků, mediální pokrytí, NPS pokles.
- **Právní** — pokuty, regulační sankce, žaloby, ztráta licence.
- **Lidský** — pracovní úrazy, fluktuace klíčových lidí, dopad na zdraví.
- **Provozní** — výpadek výroby, ztráta dodavatelského řetězce, IT outage.
- **Strategický** — ztráta konkurenční výhody, znehodnocení investice.

### Vícekriteriální agregace

V praxi se finální $D$ určuje **vícekriteriální agregací** přes dimenze. Dvě běžné metody:

1. **Maximum** — $D = \max(D_{\text{fin}}, D_{\text{rep}}, D_{\text{prav}}, D_{\text{lid}}, D_{\text{prov}})$. Konzervativní přístup: nejhorší dimenze určuje výsledek.
2. **Vážený průměr** — $D = \sum_i w_i \cdot D_i$, kde $\sum_i w_i = 1$. Váhy odrážejí strategické priority firmy.

Maximum je vhodné pro rizika s **fatálními tail-effects** (jeden katastrofický rozměr stačí), vážený průměr pro **rutinní operativní rizika**.

## Skutečná mapa rizik — příklad

![[irmank-mapa-rizik-priklad.jpeg|Skutečná mapa rizik s 30+ kódovanými riziky a třemi zónami]]

Anonymizovaná mapa univerzity / firmy ukazuje plně rozvinutou mapu:

- Mapa obsahuje **30+ rizik** označených třímístnými **kódy** (004, 064, 014, 039, …). Kódy odpovídají záznamům v risk registru, kde je každé riziko popsáno textem, vlastníkem a opatřeními.
- Každé riziko je **jeden bod** v souřadnicovém systému (P na vodorovné ose, D na svislé ose).
- **Tři křivky** (izokvanty hodnoty rizika $R$) rozdělují prostor na tři zóny — křivky mají hyperbolický tvar, protože $R = D \times P = \text{konst.}$ je v souřadnicích $(P, D)$ rovnostranná hyperbola.
- **Legenda** v dolní části mapy převádí kódy na slovní popis rizik a uvádí vlastníka.
- Mapa je **anonymizovaná** — kódy umožňují interní diskusi, aniž by se citlivé detaily dostaly ven.

Vizualizace pomáhá managementu na jeden pohled vidět, **kterých rizik je nejvíc v červené zóně** a kde je třeba prioritní akce.

## Tři zóny mapy rizik

### Kritická zóna (červená) — vysoká P i D

- **Hodnota rizika:** $R \geq 5$ (typický práh).
- **Akce:** **okamžitě**, eskalace na top management nebo představenstvo.
- **Strategie:** redukce, **vyvárování** (avoidance — vystoupit z aktivity), **přenos** (pojištění, outsourcing, hedging).
- **Reportování:** každý měsíc Výboru pro řízení rizik, čtvrtletně představenstvu.
- **Příklady:**
 - Ztráta klíčové dotace nebo zakázky tvořící > 30 % obratu.
 - Kybernetický útok na páteřní informační systém s dlouhodobým výpadkem.
 - Regulační zákaz produktu nebo technologie.
 - Bankrot strategického dodavatele bez náhrady.
 - Existenční žaloba nebo trestní stíhání vrcholových manažerů.

### Závažná zóna (žlutá) — střední R

- **Hodnota rizika:** $1 \leq R < 5$.
- **Akce:** **plán mitigace** v horizontu 6–12 měsíců, vlastník rizika připraví konkrétní opatření.
- **Strategie:** redukce nákladů (snížení D nebo P), monitoring KPI, kontingenční plán.
- **Reportování:** kvartálně Výboru pro řízení rizik.
- **Příklady:**
 - Ztráta klíčového zaměstnance s unikátním know-how.
 - Středně velký požár nebo havárie ve výrobní hale.
 - Výpadek dodavatele s alternativou (po kratším přechodném období).
 - Ztráta certifikace ISO, kterou lze obnovit do 6 měsíců.
 - Pokles tržního podílu o 5–10 %.

### Běžná zóna (zelená) — nízká P nebo D

- **Hodnota rizika:** $R < 1$.
- **Akce:** **monitoring**, periodické přezkoumávání, žádný proaktivní zásah.
- **Strategie:** **udržení** (retence — riziko nese firma sama z provozního rozpočtu) nebo malé redukční opatření v rámci běžné údržby.
- **Reportování:** ročně, agregovaně.
- **Příklady:**
 - Drobné výpadky IT (< 1 hodina, jednou za měsíc).
 - Lokální stížnosti zákazníků bez systémového dopadu.
 - Drobné odchylky kvality vyřešitelné v reklamačním procesu.
 - Krátkodobé výpadky elektrické energie kryté UPS.

## Roční aktualizace

Mapa rizik **není jednorázový artefakt** — je živým nástrojem řízení.

### Trigger události — mimořádná aktualizace

Mimo plánovaný cyklus se mapa aktualizuje, pokud nastane:

- **Velký incident** — realizace rizika z kritické zóny nebo nečekané riziko mimo mapu.
- **Regulační změna** — nový zákon, vyhláška, normativní akt EU (GDPR, NIS2, DORA).
- **M&A** — fúze, akvizice, divestice, joint-venture; mění portfolio rizik.
- **Nová technologie / produkt** — nasazení AI, cloud migrace, nový produkt s neznámým rizikovým profilem.
- **Personální změny v top managementu** — nový CEO/CRO mívá jinou risk apetit.
- **Makroekonomický šok** — krize, sankce, volatilita měn, pandemie.

### Plánovaný cyklus

- **Plný cyklus** — **1× ročně**: kompletní revize všech rizik, expertní workshop, znovu-ohodnocení P a D, přidání nových rizik, archivace zaniklých.
- **Mini-review** — **1× kvartálně**: kontrola statusu rizik z červené zóny, ověření, že mitigační plány postupují, update stavů opatření.

## Postup tvorby mapy rizik

Standardní postup (cyklus, který se opakuje při každé roční aktualizaci):

```
1. Identifikace rizik (viz analyza-rizik-proces).
2. Klasifikace každého rizika do 5×5 matice (P × D).
3. Výpočet R = D × P.
4. Zařazení do 3 zón podle R.
5. Vizualizace v Excel/SW (kód, P, D, R, zóna).
6. Workshop expertů — verifikace, přesun rizik.
7. Schválení Výborem pro řízení rizik.
8. Komunikace odpovědným manažerům.
9. Implementace opatření podle taktik (viz taktiky-rizeni-rizik).
```

Klíčové je **kroku 6** — workshop expertů. Bez konfrontace různých pohledů (provozní, finanční, právní, IT) hrozí, že mapu deformuje **single-perspective bias**.

## Praktické nástroje

- **Excel** — pro jednoduché mapy do cca **100 rizik**. Listy: Risk register (kódy, popis, vlastník), Hodnocení (P, D), Vizualizace (bublinový graf).
- **Specializovaný SW** — pro velké organizace:
 - **RSA Archer** — komplexní GRC platforma.
 - **ServiceNow GRC** — integrace s IT service managementem.
 - **MetricStream** — důraz na regulatorní compliance.
 - **LogicGate, Riskonnect** — modernější cloud řešení.
- **PowerBI / Tableau** — interaktivní dashboardy pro management; mapa je jeden ze srovnávacích pohledů (heatmap, top-10 rizik, trend v čase).
- **Risk register** — jednoznačná evidence v databázi (kód, popis, vlastník, P, D, R, zóna, opatření, status, deadline). Mapa je **vizuální projekcí** registru, ne náhradou.

## Časté chyby a omezení

- **Subjektivita ocenění** — 5-bodová stupnice je **vágní**. Různí experti hodnotí různě, což vede k nekonzistenci napříč organizací. Mitigace: kalibrační workshop, anchor příklady ke každému stupni, slepý odhad s následnou diskusí.
- **Optimistický bias** — manažeři systematicky **podhodnocují pravděpodobnost** (zejména reputačních a etických rizik) a překrývají vysoký dopad rétorikou „to se nestane".
- **Politická hra** — vlastník rizika má motivaci snížit P i D, aby riziko **uniklo do zelené zóny** a on neměl povinnost mitigovat. Mitigace: nezávislá CRO funkce, audit hodnocení.
- **Statická mapa** — pokud se mapa neaktualizuje, **rychle ztrácí význam** (do 12 měsíců je polovina ohodnocení neaktuální). Bývalý problém českých firem v 2010s.
- **Black swans** — extrémní události s velmi nízkou $P$ (pandemie, válka, kybernetický útok státního aktéra) jsou **systematicky podhodnocené** v 5-bodové škále, protože stupeň 1 ($P = 0.1$) zaobaluje vše od „1 za 100 let" po „1 za 10 000 let". Pro tail-risk je třeba doplňkový **scénářový rámec**.
- **Korelace rizik** — mapa zobrazuje rizika **izolovaně**, jako nezávislé body. V praxi se rizika kumulují (krize → současně poklesy poptávky, financování, mezd, nárůst fluktuace). Mitigace: stress testing, scénářová analýza, copula modely.
- **Falešná přesnost** — multiplikací $D \times P$ z 5-bodové stupnice vznikne číslo s desetinnými místy, které vypadá vědecky, ale **nese nejistotu vstupu**. Mapa není kalkulačka.

## Vztah k jiným pojmům

- [[analyza-rizik-proces]] — proces, jehož výstup je mapa rizik (krok identifikace → ohodnocení → vizualizace).
- [[mereni-rizika]] — kvantitativní vstup ($\sigma$, koeficient variace, VaR) pro určení dopadu $D$, zejména u finančních rizik.
- [[klasifikace-rizik]] — taxonomie nezávislá na mapě (kritická / důležitá / běžná podle dopadu); v zásadě se **kryje s zónami** mapy, ale klasifikace je jednorozměrná (jen $D$), zatímco mapa dvourozměrná ($P \times D$).
- [[taktiky-rizeni-rizik]] — výběr taktiky podle pozice rizika v matici (4 kvadranty: nízké P × nízké D = retence; vysoké P × nízké D = redukce P; nízké P × vysoké D = přenos / pojištění; vysoké P × vysoké D = vyvárování).
- [[analyza-siloveho-pole]] — analogická 2D vizualizace, ale pro **síly změny** (driving vs. restraining forces) v change managementu, ne pro rizika.
- **cross-course:** [[rizeni-rizik]] (imork) — ISO 27005 risk matrix má **podobný princip** pro kybernetická rizika (likelihood × impact, 5×5 matrice, zónování), ale s důrazem na CIA triádu (důvěrnost, integrita, dostupnost) jako dimenze dopadu.

## Navigace

- **Předchozí:** [[analyza-rizik-proces]]
- **Navazující:** [[taktiky-rizeni-rizik]]
- **Související:** [[klasifikace-rizik]], [[mereni-rizika]]
