---
title: "Síťová analýza projektu (CPM, PERT, GERT)"
course: irmank
type: topic
tags: [irmank, cpm-pert, projektove-rizeni, kriticka-cesta, sitova-analyza]
sources: [raw/irmank/Rizeni rizik_prvni cast začátek přednášek 2026 léto fin (1).ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Síťová analýza projektu (CPM, PERT, GERT)

> [!info] TL;DR
> **Síťová analýza** je formální matematická metoda plánování projektů (i projektů změny). Modeluje projekt jako orientovaný acyklický graf, kde **uzly = stavy** (zahájení/dokončení dílčích činností) a **hrany = aktivity** s časovým, zdrojovým či nákladovým ohodnocením. Existují tři hlavní varianty: **CPM** (Critical Path Method) pro deterministická trvání aktivit, **PERT** (Program Evaluation and Review Technique) pro stochastická trvání u neopakovatelných úloh a **GERT** (Graphical Evaluation and Review Technique) pro projekty s variantním průběhem (větvení, smyčky). Klíčovým pojmem všech tří metod je **kritická cesta** — nejdelší cesta sítí, jejíž délka určuje minimální celkovou dobu projektu, a aktivity ležící na ní mají **nulovou časovou rezervu**, takže jakékoliv jejich zpoždění posune termín dokončení celého projektu.

## Síťový graf jako model projektu

![[irmank-cpm-priklad-graf.jpeg|Síťový graf projektu — uzly = stavy, hrany = aktivity]]

Síťový graf je **orientovaný acyklický graf** (DAG) s následující sémantikou:

- **Uzly** reprezentují **stavy** projektu — okamžiky zahájení nebo dokončení jedné či více aktivit. Číslují se od počátečního uzlu (typicky `1`) ke koncovému (`n`).
- **Hrany** reprezentují **aktivity** (činnosti) projektu. Každá hrana $(i, j)$ vede z uzlu $i$ (počátek aktivity) do uzlu $j$ (konec aktivity) a má ohodnocení $d_{ij}$ — typicky **trvání aktivity**, ale může jít i o náklady, spotřebu zdrojů či kombinaci.
- **Orientovanost a acykličnost** zajišťují, že existuje smysluplný časový tok od počátku ke konci a že žádná aktivita není sama svým předchůdcem (jinak by projekt nebylo možné dokončit).
- **Jediný počáteční** a **jediný koncový** uzel — pokud má projekt více souběžných počátků nebo konců, slučují se přes fiktivní uzly s nulovým ohodnocením.

Síťový graf umožňuje vedle časové analýzy provádět také **zdrojovou analýzu** (kolik pracovníků, strojů či kapitálu je potřeba v každém okamžiku) a **nákladovou analýzu** (kumulované náklady v čase, trade-off mezi zkrácením doby a navýšením nákladů — tzv. *time-cost trade-off*).

## Příklad: zavedení nové výroby ve firmě

![[irmank-cpm-vypocet-tm1.jpeg|Síťový graf zavedení výroby — 8 fází]]

Prof. Rais ilustruje sestavení síťového grafu na projektu změny výroby ve firmě. Stávající výroba bude zastavena, personál proškolen, po jednoduchých stavebních úpravách bude navezena nová technologie, zajištěn výrobní materiál a subdodavatelé, započne se testování výroby a po zkušebním období bude zahájena plná výroba. Projekt obsahuje cca **8 fází** s následujícími hlavními aktivitami:

1. **Zastavení dosavadní výroby** — odstavení strojů, vyklizení haly, uzavření aktuálních zakázek.
2. **Proškolení dělníků a mistrů** — kvalifikace pracovníků pro nové technologické postupy.
3. **Technická příprava výroby** — dokumentace, nástroje, příprava pracovišť (může běžet paralelně se školením).
4. **Stavební úpravy a instalace nové technologie** — fyzická úprava prostor, navezení strojů, jejich zapojení.
5. **Marketing a uzavření obchodních smluv** — inzerce, osobní kontakty, zajištění subdodavatelů a odběratelů.
6. **Zkušební provoz** — testování výroby na omezeném objemu, ladění procesu.
7. **Proškolení prodejců a doplnění prodejní sítě** — distribuční příprava.
8. **Spuštění plného provozu** — uvedení do běžného režimu.

Některé fáze běží **paralelně** (např. proškolení dělníků a stavební úpravy), jiné **sekvenčně** (zkušební provoz musí předcházet plnému provozu). Tyto závislosti jsou vyjádřeny strukturou hran v grafu.

## Metoda kritické cesty (CPM)

CPM je nejstarší a nejjednodušší varianta síťové analýzy. Předpokládá, že **trvání každé aktivity je deterministicky známé** — typicky jde o opakovatelné úlohy, u nichž lze stanovit dobu z norem nebo zkušenosti (stavebnictví, sériová výroba, údržba).

### Klíčové pojmy a značení

| Symbol | Význam |
|---|---|
| $d_{ij}$ | Trvání aktivity vedoucí z uzlu $i$ do uzlu $j$ |
| $TM_i$ (alt. $ES_i$) | Earliest Start — nejdřívější možný termín zahájení uzlu $i$ |
| $EF_i$ | Earliest Finish — nejdřívější možný termín ukončení uzlu $i$ |
| $TP_i$ (alt. $LS_i$) | Latest Start — nejpozdější přípustný termín zahájení uzlu $i$ bez prodloužení projektu |
| $LF_i$ | Latest Finish — nejpozdější přípustný termín ukončení uzlu $i$ |
| $TM_1$ | Minimální celková doba projektu (délka kritické cesty) |
| $R_i$ | Časová rezerva (slack) uzlu $i$, $R_i = TP_i - TM_i$ |

V Raisově značení je $TM_i$ *termín nejdřívější možný* a $TP_j$ *termín nejpozději přípustný*. V anglosaské literatuře se používají $ES$, $EF$, $LS$, $LF$.

### Forward pass — výpočet $TM_i$

V síťovém grafu se postupuje **od počátečního uzlu ke koncovému**:

$$TM_1 = 0$$

$$TM_j = \max_{i \in \text{Pred}(j)} \left( TM_i + d_{ij} \right)$$

kde $\text{Pred}(j)$ je množina všech uzlů, z nichž vede hrana do $j$. Pokud má uzel více předchůdců, bere se **maximum** — uzel může začít až poté, co skončí všechny vstupující aktivity.

**Příklad –61.** Síť má 9 uzlů s následujícími trváními hran: $d_{12} = 8$, $d_{15} = 6$, $d_{13} = 4$, $d_{24} = 2$, $d_{25} = 0$, $d_{36} = 1$, $d_{47} = 3$, $d_{57} = 3$, $d_{56} = 0$, $d_{58} = 5$, $d_{68} = 8$, $d_{78} = 1$, $d_{89} = 4$.

Postupný výpočet:

- $TM_1 = 0$
- $TM_2 = TM_1 + 8 = 8$
- $TM_3 = TM_1 + 4 = 4$
- $TM_4 = TM_2 + 2 = 10$
- $TM_5 = \max(TM_1 + 6, TM_2 + 0) = \max(6, 8) = 8$
- $TM_6 = \max(TM_3 + 1, TM_5 + 0) = \max(5, 8) = 8$
- $TM_7 = \max(TM_4 + 3, TM_5 + 3) = \max(13, 11) = 13$
- $TM_8 = \max(TM_5 + 5, TM_6 + 8, TM_7 + 1) = \max(13, 16, 14) = 16$
- $TM_9 = TM_8 + 4 = 20$

Výsledek $TM_8 = 16$ a celková doba projektu $TM_9 = 20$ je **délka kritické cesty**.

### Backward pass — výpočet $TP_j$

Postupuje se **od koncového uzlu k počátečnímu**:

$$TP_n = TM_n$$

$$TP_i = \min_{j \in \text{Succ}(i)} \left( TP_j - d_{ij} \right)$$

kde $\text{Succ}(i)$ je množina uzlů, do nichž vede hrana z $i$. Pokud má uzel více následníků, bere se **minimum** — uzel musí skončit dost brzy, aby každý následující navazoval bez zpoždění.

**Pokračování příkladu**, $TP_9 = 20$:

- $TP_8 = TP_9 - 4 = 16$
- $TP_7 = TP_8 - 1 = 15$
- $TP_6 = TP_8 - 8 = 8$
- $TP_5 = \min(TP_7 - 3, TP_8 - 5, TP_6 - 0) = \min(12, 11, 8) = 8$
- $TP_4 = TP_7 - 3 = 12$
- $TP_3 = TP_6 - 1 = 7$
- $TP_2 = \min(TP_4 - 2, TP_5 - 0) = \min(10, 8) = 8$
- $TP_1 = \min(TP_2 - 8, TP_5 - 6, TP_3 - 4) = \min(0, 2, 3) = 0$

### Časová rezerva a kritická cesta

Pro každý uzel platí:

$$R_j = TP_j - TM_j$$

Uzly, jejichž **rezerva je nulová** ($R_j = 0$), tvoří **kritickou cestu**. Jsou to uzly, kde nejdřívější a nejpozdější termín splývají — žádná tolerance zpoždění.

Z příkladu výše:

| Uzel | $TM_j$ | $TP_j$ | $R_j$ | Kritický? |
|---|---|---|---|---|
| 1 | 0 | 0 | 0 | ano |
| 2 | 8 | 8 | 0 | ano |
| 3 | 4 | 7 | 3 | ne |
| 4 | 10 | 12 | 2 | ne |
| 5 | 8 | 8 | 0 | ano |
| 6 | 8 | 8 | 0 | ano |
| 7 | 13 | 15 | 2 | ne |
| 8 | 16 | 16 | 0 | ano |
| 9 | 20 | 20 | 0 | ano |

**Kritická cesta:** $1 \to 2 \to 5 \to 6 \to 8 \to 9$ s délkou **20 časových jednotek**. Hrany $5 \to 6$ a $2 \to 5$ s nulovým ohodnocením jsou tzv. **fiktivní aktivity** — vyjadřují pouze závislost mezi stavy, ne skutečnou činnost.

## Praktický postup CPM

Postup pro reálný projekt lze shrnout do následujícího pseudokódu:

```
1. Identifikujte všechny aktivity projektu a jejich trvání d_ij.
2. Sestavte síťový graf (uzly = stavy, hrany = aktivity, šipky = závislosti).
3. Forward pass: spočítejte TM_i (ES, EF) od počátečního uzlu k cílovému.
4. Backward pass: spočítejte TP_i (LS, LF) od cílového uzlu k počátečnímu.
5. Spočítejte rezervy R_j = TP_j − TM_j pro každý uzel.
6. Identifikujte kritickou cestu jako posloupnost uzlů s R_j = 0.
7. Plánujte zdroje a manažerskou pozornost prioritně na aktivity kritické cesty;
 pro nekritické aktivity využijte rezervy k vyhlazení zdrojového vytížení.
```

Manažerská pointa: **pozornost se musí soustředit na kritickou cestu**, protože každý den prodlení zde = den prodlení celého projektu. U nekritických aktivit lze využít rezervu k posunu termínů a vyrovnání nárazů na zdroje (tzv. *resource leveling*).

## Analýza cest a délka projektu

V síťovém grafu existuje obvykle více cest z počátečního do koncového uzlu, každá s vlastní celkovou dobou trvání. Délka projektu je rovna **délce nejdelší cesty** — to je definice kritické cesty.

Ze slidu 58 (jednodušší výukový příklad) jsou v grafu **čtyři cesty** s celkovými trváními 6, 7, 8 a 9 hodin. Doba projektu je tedy **9 hodin** — tato cesta je kritická a všechny uzly na ní mají nulovou rezervu. Cesty kratší než 9 hodin obsahují uzly s **kladnou rezervou** rovnou rozdílu mezi délkou kritické cesty a délkou dané cesty.

Pokud manažer dokáže **zkrátit aktivitu na kritické cestě** (např. nasazením více pracovníků nebo subdodavatele), zkrátí celý projekt — pouze však potud, dokud se kritickou cestou nestane jiná, dosud subkritická cesta. **Crashing** projektu znamená systematické zkracování kritické cesty s rostoucími náklady, dokud mezní náklady na zkrácení nepřevyšují benefit ze zkrácení termínu.

## Embed: výpočet časových rezerv

![[irmank-cpm-rezervy-tpj.jpeg|Síťový graf s časovými rezervami TPj — uzly s nulovou rezervou tvoří kritickou cestu]]

Diagram zobrazuje finální stav výpočtu — každý uzel má dvojici hodnot $TM_j \,|\, TP_j$. Tam, kde se obě hodnoty rovnají (rozdíl 0), leží na kritické cestě a jsou na obrázku vyznačeny tučně. Hodnoty v závorkách u hran představují **mezivýpočty** $TP_j - d_{ij}$ použité v backward passu.

## PERT — Program Evaluation and Review Technique

PERT je rozšířením CPM pro situace, kdy **trvání aktivit nelze stanovit deterministicky** — typicky u **neopakovatelných úloh**: výzkum a vývoj, kosmické a obranné projekty, stavby unikátních konstrukcí, IT projekty s vysokou mírou nejistoty.

### Tři odhady trvání

Pro každou aktivitu $(i, j)$ se odhadují **tři hodnoty trvání**:

- $a_{ij}$ — **optimistický odhad** (best-case): vše proběhne hladce, žádné komplikace.
- $m_{ij}$ — **nejpravděpodobnější odhad** (most likely): typický průběh, modální hodnota.
- $b_{ij}$ — **pesimistický odhad** (worst-case): naskytnou se realistické komplikace, ale ne katastrofa.

### Očekávané trvání a variance

PERT předpokládá, že trvání aktivity má **beta rozdělení** s parametry odhadnutými z trojice $a, m, b$. Po vážení vychází:

$$t_e = \frac{a + 4m + b}{6}$$

$$\sigma^2 = \left( \frac{b - a}{6} \right)^2$$

Hodnota $t_e$ slouží jako **deterministická náhrada** $d_{ij}$ — používá se v běžném CPM výpočtu kritické cesty. Hodnota $\sigma^2$ kvantifikuje **nejistotu** ohledně trvání.

### Pravděpodobnostní analýza termínu

Klíčová odvozená vlastnost PERT: **variance celkové doby projektu** je rovna součtu variancí aktivit na kritické cestě (předpoklad nezávislosti):

$$\sigma^2_{\text{projekt}} = \sum_{(i,j) \in \text{kritická cesta}} \sigma^2_{ij}$$

Z této variance lze za předpokladu přibližné normality (CLT) spočítat **pravděpodobnost dodržení libovolného cílového termínu** $T$:

$$P(T_{\text{projekt}} \leq T) = \Phi \left( \frac{T - t_e^{\text{projekt}}}{\sigma_{\text{projekt}}} \right)$$

Tato statistika je přímý vstup do **risk managementu projektu** — manažer vidí, s jakou pravděpodobností termín skutečně dodrží, a může prosadit rezervu (časový buffer) odpovídající požadované úrovni jistoty (typicky 90–95 %). Statistické charakteristiky střední hodnoty a směrodatné odchylky jsou stejné nástroje, které kurz IrmanK používá v [[mereni-rizika|měření rizika]] obecně (σ jako míra variability, koeficient variace pro porovnání).

## GERT — Graphical Evaluation and Review Technique

GERT je nejobecnější varianta. Oproti CPM/PERT připouští:

- **Variantní průběh** — z uzlu může vést více možných pokračování s **pravděpodobnostmi přechodu** (probabilistické větvení).
- **Smyčky** — aktivita se může opakovat, např. v případě neúspěchu testu se vrátíme k vývoji.
- **Aktivity, které nemusí proběhnout** — některé větve grafu se realizují jen někdy.

GERT je svojí strukturou blízký **rozhodovacím stromům** a **markovským procesům**. Použití:

- **Inovační projekty** s nejistotou ohledně toho, která vývojová varianta vyjde.
- **Klinické a regulatorní procesy** s opakováním zkoušek.
- **Komplexní servisní/výrobní procesy** s rework smyčkami.

Vyhodnocení GERT typicky probíhá **simulací Monte Carlo** — analytické řešení je možné jen pro speciální struktury. Výstupem je **rozdělení pravděpodobnosti** doby trvání projektu, ne jen jedno číslo.

## SW nástroje pro síťovou analýzu

Manuální výpočet CPM/PERT je proveditelný pro malé sítě (do ~20 uzlů). Reálné projekty mají stovky až tisíce aktivit a vyžadují specializovaný software:

- **MS Project Manager** (Microsoft) — standardní nástroj pro malé a střední projekty. Umí CPM, Ganttovy diagramy, vytížení zdrojů, base­liny. V kurzu IrmanK je referenční volbou.
- **Primavera P6** (Oracle) — enterprise třída, určená pro velké inženýrské, energetické a stavební projekty. Plnohodnotný PERT, multi-projektové portfolio.
- **GanttProject** — open-source desktopový nástroj, omezené funkce, vhodné pro výuku a malé projekty.
- **ProjectLibre** — open-source náhrada MS Projectu, kompatibilní formát souborů.
- **Asana, Jira, Monday** — moderní cloudové nástroje primárně pro agilní řízení; síťovou analýzu nepokrývají v plné šíři, ale umí závislosti a kritickou cestu.

## Použití v risk managementu

Síťová analýza je v kurzu IrmanK chápána jako **kvantitativní páteř plánování změny**. Konkrétní role v risk managementu:

- **Modeluje realizační etapu** [[lewinuv-model|Lewinova modelu]] — fáze *change* (vlastní provedení změny) je v technokratickém pojetí projekt, který je modelován síťovým grafem.
- **PERT explicitně počítá riziko zpoždění** — variance součtu na kritické cestě dává pravděpodobnost překročení termínu, což je přímo *kvantitativní rizikový ukazatel*.
- **Identifikuje kritická místa projektu** — uzly s nulovou rezervou jsou rizikově exponovaná místa: jakékoliv zpoždění zde = posun celého termínu. Manažer ví, kde má přidat zdroje a kontrolu.
- **Umožňuje *what-if* analýzu** — manažer simuluje dopad zpoždění, výpadku zdroje či škrtnutí aktivity a vidí změnu v kritické cestě a v termínu.
- **Doporučení** plynoucí z výsledků: posilte zdroje na kritické cestě, zvažte paralelizaci sekvenčních aktivit, monitorujte včas — typické taktiky snižování *rizika prodlení*.

V kombinaci s [[analyza-siloveho-pole|analýzou silového pole]] dostane manažer **kvantitativní časový plán** (síťová analýza) **doplněný o kvalitativní obraz lidských sil pro a proti změně** (force field). Obě metody jsou komplementární a v praxi se používají souběžně.

## Pedagogická poznámka

> [!warning] Lidský faktor
> „I dobře řízený projekt může být neúspěšný. Důvod — špatné zapojení zaměstnanců, kolegů do projektu." (prof. Rais a 63)

Síťová analýza optimalizuje **časové rozložení a alokaci zdrojů**, ale **nemodeluje motivaci, komunikaci, kompetence ani kulturu** týmu. Tu pokrývá [[lewinuv-model|Lewinův model]] (rozmrazení – pohyb – zamrazení), [[analyza-siloveho-pole|analýza silového pole]] a další nástroje řízení změny. Kvalitní projektové řízení v kurzu IrmanK proto vždy kombinuje **tvrdé** (CPM/PERT, finanční ukazatele) a **měkké** (lidé, komunikace, kultura) nástroje. Bez měkké stránky kritická cesta nestihne ani v dokonalém Ganttu.

## Souvislosti

- [[lewinuv-model|Lewinův model]] — síťová analýza modeluje časový plán **realizační etapy** (fáze *change*).
- [[analyza-siloveho-pole|Analýza silového pole]] — **kvalitativní** doplněk síťové analýzy: zatímco CPM kvantifikuje čas a zdroje, force field kvantifikuje lidské síly pro a proti změně.
- [[mereni-rizika|Měření rizika]] — PERT používá $\sigma^2$ pro odhad variability stejně, jako se obecně v risk managementu používá směrodatná odchylka jako míra variability.
- [[definice-rizika|Definice rizika]] — síťová analýza poskytuje konkrétní **rizikový ukazatel** (pravděpodobnost dodržení termínu).
- *Operační analýza / operační výzkum* — síťová analýza je podmnožinou OR/OA disciplíny, příbuzné s lineárním programováním a teorií front.
- Cross-course: [[optimalizace|optimalizace]] (kurz IpmrK) — pokročilé metody (LP, nelineární optimalizace, evoluční algoritmy) lze použít na *resource-constrained scheduling* — komplikovanější varianty síťové analýzy s omezenými zdroji.

## Navigace

- **Předchozí:** [[analyza-siloveho-pole|Analýza silového pole]]
- **Navazující:** [[definice-rizika|Definice rizika]] (začátek 2. části přednášky)
- **Související:** [[lewinuv-model|Lewinův model]], [[kaizen-vs-inovace|KAIZEN vs. inovace]], [[odpor-ke-zmene|Odpor ke změně]]
