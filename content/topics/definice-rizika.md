---
title: "Definice a podstata rizika"
course: irmank
type: topic
tags: [irmank, riziko, podnikatelske-riziko, postoj-k-riziku, volatilita, buffett]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Definice a podstata rizika

> [!info] TL;DR
> **Riziko** je pojem **multidimenzionální** — současně znamená *možnost ztráty*, *neurčitost budoucího vývoje* a *pravděpodobnost odchylky* skutečnosti od plánu. V podnikatelském kontextu má **dvě stránky**: negativní (ztráta, nedosažení cíle, bankrot) a pozitivní (nadprůměrný zisk, prolomení trhu, konkurenční náskok). **Postoj k riziku** — averze, sklon, neutralita — je individuální i kulturní charakteristika a přímo určuje strategii firmy. Úspěšný manažer nemůže mít silnou averzi, ale ani extrémní sklon.

Tato stránka shrnuje **definiční vrstvu** kurzu [[irmank|Řízení rizik (IrmanK)]]. Kvantitativní popis rizika (rozptyl, směrodatná odchylka, koeficient variace) je oddělen do [[mereni-rizika]]; taxonomie do [[klasifikace-rizik]]; vizualizační nástroje do [[mapa-rizik]]; rozhodovací rámec „co s rizikem dělat" do [[taktiky-rizeni-rizik]].

## Trojúhelník úspěch — riziko — změna

![[irmank-trojuhelnik-uspech-riziko-zmena.jpeg|Trojúhelník úspěch — riziko — změna]]

Trojúhelník **úspěch — riziko — změna** je **centrálním pojmem celého kurzu** [[irmank|IrmanK]]. Vyjadřuje, že tyto tři kategorie jsou **neoddělitelně spjaté**:

- **Bez ochoty riskovat není úspěch.** Riziko a výnos jsou spojené nádoby — kdo chce nadprůměrný zisk, musí přijmout nadprůměrnou nejistotu. Stabilní bezrizikové investice (státní dluhopisy) generují bezrizikovou — tedy nízkou — sazbu.
- **Bez změny se firma nedokáže přizpůsobit.** Trh, technologie, regulace, konkurence — všechno se mění. Firma, která se nemění, ztrácí konkurenceschopnost a v dlouhodobém horizontu zaniká. Otázka tedy není zda měnit, ale **jak rychle a jakým způsobem** (viz [[lewinuv-model]] a [[analyza-siloveho-pole]]).
- **Každá změna nese riziko.** Změna je pohyb do neznáma — ze stabilního stavu do nejistého. I dobře připravená změna se nemusí povést. Proto je řízení rizik součástí každého změnového projektu (viz [[odpor-ke-zmene]], [[lewinuv-model]]).

Manažerský důsledek: žádná z těchto tří veličin se nedá ignorovat. Firmy, které potlačují riziko, ztrácejí schopnost využít příležitosti; firmy, které potlačují změnu, stagnují; firmy, které potlačují úspěch jako cíl, ztrácejí smysl podnikání.

## 10 definic rizika

Charakteristickým rysem oboru je, že **neexistuje jediná definice rizika**. Pluralita definic odráží různé pohledy — finanční, pojišťovnický, technický, kybernetický, manažerský. Pro praktické řízení rizik se vybírá ta definice, která nejlépe odpovídá kontextu rozhodnutí.

1. **Možnost vzniku ztráty** (např. finanční). — Klasické pojišťovnické pojetí. Riziko = potenciální újma.
2. **Možnost odchylky** skutečných výsledků od očekávaných. — Statistické pojetí; odchylka může být i pozitivní.
3. **Pravděpodobnost vzniku negativního jevu.** — Užší pojetí, často v technické bezpečnosti.
4. **Variabilita možných výsledků** (rozptyl σ², směrodatná odchylka σ). — Finanční pojetí (volatilita); rozpracováno v [[mereni-rizika]].
5. **Nebezpečí nesplnění cíle**, vzniku chyby, škody nebo ztráty. — Projektové řízení.
6. **Neurčitost spojená s vývojem hodnoty aktiva** (finanční riziko). — Aktivní investiční pojetí (akcie, dluhopisy, deriváty).
7. **Střední hodnota ztrátové funkce.** — Pojistně-matematické pojetí: očekávaná ztráta E[L].
8. **Možnost, že specifická hrozba zneužije specifickou zranitelnost.** — Pojetí kybernetické bezpečnosti (ISO 27005, viz [[rizeni-rizik]] z [[imork|ImorK]]). Riziko = funkce(hrozba, zranitelnost, dopad).
9. **Kombinace pravděpodobnosti události a jejího následku** — definice **ISO 31000**. Riziko = vliv nejistoty na cíle.
10. **Možná negativní (ale i pozitivní) odchylka skutečnosti od plánu.** — Manažersko-podnikatelské pojetí, zdůrazňující obě stránky rizika.

> [!note] Komentář
> Tato pluralita není slabost oboru, je to **rys oboru**. Nikdo nemá jednu kanonickou definici. Pro praktické řízení rizik vždy vybíráme tu, která se hodí kontextu — pro pojišťovnu definice 1 nebo 7, pro investora 4 nebo 6, pro CISO definice 8, pro projektového manažera 5 nebo 10, pro top management ISO definice 9.

## Pozitivní a negativní stránka rizika

V manažerské praxi je klíčové rozlišovat dvě stránky téhož pojmu.

### Negativní stránka

- Ztráta, nedosažení cíle, bankrot.
- **Klasické pojetí** rizika — to, co intuitivně vnímáme jako „riziko".
- Důvod existence pojištění, rezerv, kapitálových polštářů.
- Nástroje řízení: prevence, retence, transfer, vyhnutí se (viz [[taktiky-rizeni-rizik]]).

### Pozitivní stránka

- Nadprůměrný zisk, prolomení trhu, konkurenční náskok.
- **„Bez rizika neexistuje výnos."** Tržní teorie kapitálu (CAPM): očekávaný výnos = bezriziková sazba + riziková prémie.
- Inovace, vstup na nový trh, akvizice — všechno jsou rizikové projekty s asymetricky velkým upside potenciálem.

### Symetrie versus asymetrie

- **Finanční trhy** obvykle pracují se **symetrickým** rizikem: cena akcie může stoupnout i klesnout o stejnou velikost (volatilita σ je symetrická míra). Standardní portfoliové modely (Markowitz, CAPM) na tento předpoklad spoléhají.
- **Podnikatelské projekty** mívají **asymetrické** rozložení: ztráty jsou ohraničené investovanou částkou (maximum = celá investice), zisky jsou teoreticky neomezené. Tato asymetrie je důvodem, proč je rizikový kapitál ekonomicky racionální navzdory vysoké míře neúspěchu.

## Podnikatelské riziko

> [!definition] Podnikatelské riziko
> **Ztráty firmy vznikají kombinací volatility finančních proměnných (cena, kurz, úrok, sazba) a celkové angažovanosti firmy k těmto proměnným.**
>
> riziko = volatilita × angažovanost

### Co tato definice znamená

- **Volatilita** = velikost kolísání tržních proměnných v čase. Měří se zpravidla směrodatnou odchylkou denních/měsíčních změn (viz [[mereni-rizika]]).
- **Angažovanost (exposure)** = velikost pozice firmy v dané proměnné. Příklady: čistý FX-úvěr v EUR, objem komodity ve skladu, otevřená pozice úrokově citlivého aktiva.
- **Riziko** je součin obou. Volatilní trh + nulová angažovanost = nulové riziko. Stabilní trh + obrovská angažovanost = nízké riziko, ale **citlivé na šok**.

### Příklad: FX-úvěr v EUR

Česká firma má eurový úvěr ve výši 100 mil. Kč. Měsíční volatilita kurzu EUR/CZK je řádově 1,5 %. Roční směrodatná odchylka kurzové ztráty je tedy okolo 5 mil. Kč. Pokud kurz výrazně pohne (např. 10 % oslabení koruny), firma utrpí ztrátu okolo 10 mil. Kč na přecenění úvěru — bez ohledu na to, jak dobře se daří jejímu hlavnímu byznysu.

### Princip kontroly rizika

**Kontrola rizika = kontrola součinu (volatilita × angažovanost).** Volatilitu trhu nelze ovlivnit, ale lze:

- snížit angažovanost (deleveraging, hedging),
- diverzifikovat angažovanost (více měn, více komodit, více trhů),
- omezit angažovanost limity (VaR limity, stop-loss, position limits).

### Případ „Private Investors"

Modelový případ z přednášky ilustruje firmu, která akumulovala neřízenou angažovanost ve více třídách aktiv. Při nárazovém poklesu trhu nebyla schopna pokrýt ztráty z provozního cash-flow a musela likvidovat pozice na dně — a tedy realizovat maximální možnou ztrátu. Klíčové selhání: **chyběla agregace angažovanosti** napříč třídami a chyběl limit na celkovou expozici.

## Postoj k riziku

Postoj k riziku je individuální i kulturní charakteristika rozhodovatele. Rozlišujeme tři typy.

### Averze k riziku (risk-averse)

- Preferuje **jistotu** před nejistotou.
- Při stejné očekávané hodnotě volí variantu s nižším rozptylem.
- Klasická formulace: raději 90 mil. Kč jistě než 50% šance na 200 mil. Kč (i když očekávaná hodnota je 100 mil. Kč).
- Typické pro: konzervativní bankovní instituce, pojišťovny, regulované sektory.

### Sklon k riziku (risk-seeking)

- Vyhledává **vyšší výnos i za cenu vyššího rizika**.
- Při stejné očekávané hodnotě volí variantu s vyšším rozptylem (a vyšším upside).
- Typické pro: startupy, venture kapitál, hedgeové fondy, deriváty.

### Neutrální postoj (risk-neutral)

- Rozhoduje **pouze podle očekávané hodnoty** E[X], rozptyl je irelevantní.
- Teoreticky čistá pozice; v praxi se reálně objevuje u velkých diverzifikovaných hráčů, kde zákon velkých čísel rozpouští individuální volatilitu.

> [!warning] Klíčová poznámka
> **Úspěšný manažer nemůže mít silnou averzi.** Firma, která systematicky odmítá rizika, postupně ztrácí schopnost růst, inovovat a konkurovat. Současně **extrémní sklon k riziku** vede k volatilním, nestabilním firmám, které sice mohou krátkodobě excelovat, ale dlouhodobě selhávají na první výrazný šok. Cílem je **kalkulované riziko** — vědomé přijetí rizika, jehož velikost a důsledky firma rozumí a unese.

### Vliv firemní kultury

Postoj jednotlivce je modifikován **firemní kulturou**:

- **Konzervativní bankovní firma** — i přirozený risk-seeker je tlačen k opatrnosti procesy, pravidly, schvalovacími orgány.
- **Startup** — i risk-averse člen týmu je tlačen k akceleraci, pivotům, agresivnímu růstu.
- **Strukturovaný konflikt** mezi business development (tlak na výnos a riziko) a risk management (tlak na opatrnost) je v dobře řízené firmě **zdravý** — vede k diskutovaným, vědomým rozhodnutím.

## Riziko a manažerská praxe

Definice je teorie. Praxe začíná otázkami, které manažer musí umět zodpovědět o své firmě.

> [!example] Jak pracujete s rizikem?
> - Identifikujete **klíčová rizika** svých rozhodnutí dříve, než je realizujete?
> - Měříte je **kvantitativně** (pravděpodobnost × dopad), nebo jen kvalitativně intuicí?
> - Existuje ve vaší firmě **mapa rizik** (viz [[mapa-rizik]])? Aktualizujete ji alespoň jednou ročně?
> - Jaké je **top 10 rizik** vaší firmy? Umí je vyjmenovat top management bez přípravy?
> - Kdo je **odpovědný** za jednotlivá rizika (risk owner)? Existují eskalační pravidla?
> - Existují **limity** (kapitál, pozice, koncentrace) a kdo je schvaluje?

Pokud je odpověď na většinu těchto otázek negativní nebo neurčitá, firma **neřídí** rizika — pouze je *má*.

## Slavné citáty o riziku

> „Risk comes from not knowing what you do."
> — **Warren Buffett**

> „Kdo neriskuje, nevyhrává?"
> — české pořekadlo

### Co Buffett ve skutečnosti říká

Buffettova poznámka má hlubokou strukturální vrstvu: riziko je primárně **z nevědomosti**, ne z působení nepředvídatelných sil. Tedy:

- Riziko ≠ neřiditelný osud.
- Riziko = oblast, kde rozhodovatel nedělá svou domácí úlohu.
- Snížení rizika = **znalost, příprava, due diligence**.

To je v ostrém kontrastu s českým „kdo neriskuje, nevyhrává", které je psychologicky pravdivé (riziko je nutné), ale operativně zavádějící (sugeruje, že riskování samo je hodnota). Buffett v podstatě říká: **riskovat informovaně je práce; riskovat neinformovaně je hazard**.

## Heuristiky a iluze kontroly rizika

V praxi lidé používají **heuristiky** — zjednodušená rozhodovací pravidla. Heuristiky jsou užitečné v rutinních situacích, ale **selhávají v extrémech**.

### Slavná selhání řízení rizik

- **Lehman Brothers (2008)** — investiční banka padla na neřízené angažovanosti v subprime hypotékách a nadměrné páce.
- **Silicon Valley Bank (2023)** — pád na klasickém úrokovém riziku (long-duration státní dluhopisy financované krátkodobými vklady), které banka nehedgovala.
- **Wirecard (2020)** — kombinace fraud a selhání auditu; zdánlivě nízké riziko se ukázalo být fundamentálně neexistujícím byznysem.
- Spojuje je: **přehlížení známých rizik**, ne neviditelné šoky.

### Riziko nikdy není nulové

Případ z Jeseníků (přednáška): situace, kterou všichni hodnotili jako bezpečnou, se ukázala obsahovat **neidentifikovaná rizika** (nečekané záplavy, geologické anomálie). Manažerské poučení: i po vyčerpávající analýze zbývá **zbytkové riziko**, které je třeba kapitalizovat (rezervou, pojištěním, plánem B), nikoli ignorovat.

### Černé labutě (Taleb)

Termín z Talebovy knihy *The Black Swan*: **nepředvídatelné události s velkým dopadem**. Charakteristiky:

- Před událostí: vnímané jako téměř nemožné.
- Po události: zpětně racionalizované jako logicky odvoditelné.
- Příklady: 11. září 2001, vznik Googlu, finanční krize 2008, COVID-19.

Pro řízení rizik to znamená, že **klasické modely založené na normálním rozdělení podceňují tlusté chvosty** distribuce. Reálné rozdělení ztrát má více extrémních událostí, než předpovídá normální křivka.

## Riziko jako součást řízení

Klíčová teze: **řízení rizik je integrální součástí řízení firmy**, ne separátní funkce delegovaná na risk officera.

- **Strategie** — strategická rozhodnutí (vstup na trh, akvizice, R&D investice) jsou rozhodnutí o riziku.
- **Operace** — provozní procesy generují operační rizika (chyby, výpadky, fraud).
- **Reporting** — finanční výkaznictví má svá vlastní rizika (chybné účetní zachycení, fraud reporting).

Risk management tedy není samostatné oddělení vedle ostatních — je to **horizontální vrstva** procházející všemi funkcemi. V dobře řízené firmě je odpovědnost za riziko **na vlastníkovi procesu** (risk owner), risk management funkce poskytuje metodiku, agregaci a kontrolní pohled.

Cross-link na navazující stránky: [[mapa-rizik]] (vizualizace R = D × P), [[taktiky-rizeni-rizik]] (co s identifikovaným rizikem dělat), [[mereni-rizika]] (kvantitativní popis).

## Souvislosti

- [[mereni-rizika]] — kvantitativní popis rizika: rozptyl σ², směrodatná odchylka σ, koeficient variace KV.
- [[klasifikace-rizik]] — taxonomie: kritické / důležité / běžné, dynamické / statické, systematické / nesystematické.
- [[mapa-rizik]] — vizualizace R = Dopad × Pravděpodobnost; nástroj pro prioritizaci.
- [[taktiky-rizeni-rizik]] — čtyři základní taktiky: vyhnutí, redukce, transfer, retence.
- **Cross-course:** [[rizeni-rizik]] (z [[imork|ImorK]]) — kybernetické pojetí rizika, ISO 27005 / ISO 31000, hrozba × zranitelnost × dopad.

## Navigace

- **Předchozí:** [[sitova-analyza-cpm-pert]]
- **Navazující:** [[mereni-rizika]]
- **Související:** [[klasifikace-rizik]], [[mapa-rizik]]
