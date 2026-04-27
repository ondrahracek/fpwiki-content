---
title: "Operační výzkum a snižování rizika"
course: irmank
type: topic
tags: [irmank, operacni-vyzkum, linearni-programovani, sitova-analyza, debt-netting, deterministicke-modely]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Operační výzkum a snižování rizika

> [!info] TL;DR
> **Operační výzkum (OR)**, v české tradici též **operační analýza (OA)**, je matematická disciplína určená pro **algoritmizovatelná, opakovatelná rozhodovací problémy** v operativním a středním řízení firmy. V kontextu risk managementu pomáhá snižovat riziko **kvantifikovatelným optimalizačním řešením**: lineární programování (LP), síťová analýza projektů, debt netting (oddlužení podniků). V investičním rozhodování OR doplňuje statistické přístupy (viz [[mereni-rizika|měření rizika]]) a metody umělé inteligence (viz [[expertni-systemy|expertní systémy]]). Charakteristickým rysem je matematická formulace cíle s omezeními a existence efektivního solveru pro velké instance úlohy.

## Charakteristika OR/OA

**Operační analýza (OA) = operační výzkum (OR)** — terminologie pochází z anglosaského prostředí 2. světové války (operations research), kde matematici optimalizovali konvojové trasy, radarové sítě a alokaci zdrojů. V české akademické a manažerské literatuře se vžil pojem „operační výzkum", průmyslová praxe častěji používá „operační analýza".

OR je vhodný pro **opakovatelné, kvantifikovatelné** rozhodovací problémy s následujícími charakteristikami:

- **Matematicky formulovatelný** — úlohu lze zapsat jako cílovou funkci a soustavu omezení.
- **Měřitelné vstupy a výstupy** — parametry mají číselnou reprezentaci, výsledek lze ověřit.
- **Algoritmizovatelný** — existuje softwarový solver, který úlohu řeší v rozumném čase.
- **Opakovatelný** — jeden algoritmus dokáže řešit mnoho instancí stejné úlohy s různými parametry.

Typické nasazení leží na **operační a střední úrovni** managementu firmy: plánování výroby, logistika, alokace personálu, řízení zásob. Nejedná se o strategická rozhodnutí — ta vyžadují přístupy umělé inteligence a [[expertni-systemy|expertní systémy]], protože jsou špatně strukturovaná, jednorázová a obsahují kvalitativní hodnotové soudy.

## Deterministické modely — typy

OR zahrnuje široké spektrum modelovacích technik. Mezi nejvýznamnější patří:

- **Lineární programování (LP)** — optimalizace lineární cílové funkce s lineárními omezeními. Klasické úlohy: optimalizace výrobního mixu, transportní úlohy, dietní úlohy.
- **Celočíselné programování (ILP, MILP)** — LP s omezením na celočíselné proměnné, např. počty kusů nebo binární rozhodnutí ano/ne.
- **Síťová analýza** — projektové řízení (CPM/PERT/GERT), viz [[sitova-analyza-cpm-pert|síťová analýza]]; problémy průtoku v síti, nejkratší cesty, maximálního toku.
- **Dynamické programování** — víceetapové rozhodování s rekurzivním rozkladem na menší podproblémy.
- **Teorie front (queuing)** — optimalizace obslužného systému, kapacita pokladen, callcenter.
- **Teorie zásob (inventory)** — Wilson EOQ model, just-in-time, bezpečnostní zásoby.
- **Teorie her** — strategická interakce s konkurencí (cross-link [[predikce|predikce]]).

## Lineární programování (LP)

LP je nejstarší a stále nejpoužívanější disciplínou OR. Standardní formulace zní:

$$\max c^T x \quad \text{s.t.} \quad A x \leq b, \; x \geq 0$$

kde:

- $x$ — vektor rozhodovacích proměnných.
- $c$ — koeficienty cílové funkce (zisky nebo náklady).
- $A, b$ — matice koeficientů omezení a vektor pravých stran.

Geometricky úloha hledá vrchol konvexního polytopu (množiny přípustných řešení), v němž cílová funkce dosahuje maxima. Z teorie LP plyne, že optimum vždy leží ve vrcholu — pokud existuje konečné řešení.

**Klasické algoritmy:**

- **Simplexová metoda** (Dantzig, 1947) — pohyb po vrcholech polytopu po hranách směrem ke zlepšení. V praxi velmi rychlá, v nejhorším případě exponenciální.
- **Vnitřní bodové metody** (Karmarkar, 1984) — polynomiální složitost, vhodné pro velmi velké úlohy.
- **Branch-and-bound** pro celočíselné programování — kombinatorické větvení s ořezem podle relaxace LP.

**SW nástroje:**

- **MS Excel Solver** — dostupný, vhodný do ~200 proměnných, ideální pro výuku a malé firemní úlohy.
- **MATLAB** `linprog` / `intlinprog` — cross-link na ipmrk [[optimalizace|optimalizace]], integruje se s ostatními numerickými metodami.
- **CPLEX, Gurobi** — komerční solvery pro velké průmyslové úlohy (statisíce proměnných).
- **GLPK, CBC** — open source alternativy s rozumným výkonem.

Matematický základ omezené optimalizace tvoří [[lagrangeova-metoda|Lagrangeova metoda]] (cross-course imek) — duální proměnné v LP odpovídají Lagrangeovým multiplikátorům.

## Síťová analýza projektů

Síťová analýza je samostatnou kapitolou OR věnovanou projektovému řízení. Detail je v samostatném topiku [[sitova-analyza-cpm-pert|síťová analýza CPM/PERT]]. Zde stručné shrnutí:

- **CPM (Critical Path Method)** — deterministické doby trvání činností, kritická cesta jako nejdelší souvislá posloupnost.
- **PERT (Program Evaluation and Review Technique)** — stochastické doby trvání s tříbodovým odhadem (optimistic / most likely / pessimistic), výpočet $\mu$ a $\sigma^2$ pro každou činnost.
- **GERT (Graphical Evaluation and Review Technique)** — variantní průběh projektu s pravděpodobnostním větvením.

Riziko zpoždění projektu se modeluje rozptylem $\sigma^2$ kumulovaným podél kritické cesty:

$$\sigma^2_{\text{projekt}} = \sum_{i \in \text{kritická cesta}} \sigma^2_i$$

To umožňuje stanovit pravděpodobnost dokončení do daného termínu.

## Debt netting (oddlužování podniků)

![[irmank-oddluzeni-debt-netting.jpeg|Princip nettingu — tří-podnikový dluhový řetězec se redukuje na netto pozice vůči Fondu národního majetku]]

Debt netting je klasickou aplikací OR z období **české privatizace 90. let**, kdy podniková druhotná platební neschopnost dosáhla odhadem **~64 mld Kč**. Po rozpadu RVHP a v transformaci na tržní ekonomiku se mnoho podniků ocitlo v dluhových cyklech, kde formální bankrotování by způsobilo dominové efekty napříč ekonomikou.

**Princip:**

- Mnoho podniků má **vzájemné pohledávky a závazky v cyklech** (A dluží B, B dluží C, C dluží A).
- Jednoduché bankrotování by způsobilo **kaskádové selhání** — když padne A, padne i B, který na A čekal, atd.
- **Netting algoritmus** (síťová úloha průtoku):
  1. **Identifikace kruhových dluhových pozic** — graf orientovaných hran mezi podniky.
  2. **Vzájemné započtení (offsetting)** — souběžné pohledávky a závazky se anulují do výše menší z částek.
  3. **Centrální vyrovnání zbytku** — netto pozice se vypořádají přes prostředníka (Fond národního majetku).

**Příklad ze slidu 88:**

- Podnik A dluží podniku B: **15** jednotek.
- Podnik B dluží podniku C: **5** jednotek.
- Podnik C dluží podniku A: **10** jednotek.

Tradiční řešení vyžaduje **tři samostatné transakce**, každá s nárokem na cash, bankovními poplatky a časovým rozdílem.

**Netting přístup** — každý podnik má jedinou netto pozici:

| Podnik | Dluží | Dostává | Netto |
|--------|-------|---------|-------|
| A      | 15    | 10      | dlužník 5 |
| B      | 5     | 15      | věřitel 10 |
| C      | 10    | 5       | dlužník 5 |

**Fond národního majetku** přijme od A (5) + C (5) = **10**, vyplatí B (**10**). Reziduální dluh = **0**.

### Vzorec úspory cash flow

Kvantitativní vyjádření efektu nettingu:

$$\text{savings\%} = \frac{\sum \text{bilateral} - \sum \text{netting}}{\sum \text{bilateral}}$$

kde:

- $\sum \text{bilateral}$ — součet všech původních bilaterálních toků (před nettingem)
- $\sum \text{netting}$ — součet zbývajících netto plateb (po nettingu)

**Aplikace na příklad ABC:**

- Před nettingem: tři transakce po 15, 5, 10 jednotek $\Rightarrow \sum \text{bilateral} = 15 + 5 + 10 = 30$ jednotek.
- Po nettingu: dvě platby do Fondu (5 + 5) a jedna výplata z Fondu (10) $\Rightarrow \sum \text{netting} = 10$ jednotek (z hlediska potřebné likvidity stačí tato suma projít clearingem).
- $\text{savings\%} = (30 - 10) / 30 \approx 66{,}7\%$ — netting v tomto případě sníží likviditní nárok podniků o dvě třetiny.

V reálných clearingových systémech (mezibankovní RTGS, kryptoměnové DEX) dosahuje úspora často 70–90 %, protože dluhové řetězce mají vyšší řád než tři aktéři a větší cyklickou propletenost.

**Praktický význam:**

- **Snížení likviditních nároků o ~80 %** (typické v praxi clearingových operací).
- **Snížení credit rizika** kaskádových bankrotů — každý podnik vystavuje pouze netto pozici.
- **Politicko-ekonomický nástroj** — Fond národního majetku byl klíčovým hráčem v transformaci ČR po roce 1989.
- **Moderní obdoba:** clearingové domy v bankovnictví (LCH, CME), kryptoměnové DEXy s atomic swaps, mezibankovní RTGS systémy.

Z hlediska OR jde o úlohu **toku v síti** s redukcí počtu hran a minimalizací cash flow. Algoritmicky se řeší LP nebo specializovaným max-flow algoritmem.

## OR a riziko — vztahy

OR poskytuje risk managementu několik konkrétních hodnot:

- **Kvantitativní rozhodování** — místo intuice nebo politických tlaků precizní matematický výpočet s ověřitelným výsledkem.
- **Optimalizace pod omezeními** — najde nejlepší alokaci zdrojů s respektováním rizikových limitů (např. VaR, kapitálová přiměřenost, regulatorní limity).
- **Sensitivity analýza** — jak se výsledek mění při změně parametrů (cross-link [[investicni-rozhodovani-bot|investiční rozhodování]] NPV citlivost). Stínové ceny v LP přímo udávají hodnotu uvolnění daného omezení.
- **What-if scénáře** — testování různých budoucností (změna cen vstupů, výpadek dodavatele, regulatorní změna).
- **Monte Carlo simulace** — distribuce výstupů místo jediného čísla, vstup pro rozhodování pod nejistotou.

## Limity OR

OR není univerzální nástroj. Hlavní omezení:

- **Předpoklad lineárnosti a determinismu** — reálný svět je často nelineární (úspory z rozsahu, prahové efekty) a stochastický (poptávka, ceny vstupů).
- **Statické modely** — klasické LP neumí dobře modelovat learning, adaptaci, dynamické změny preferencí.
- **Vyžadují kvalitní data** — princip „garbage in, garbage out" platí dvojnásob; nepřesné odhady koeficientů vedou k nesmyslným optimům.
- **Komplexní formulace** — vytvoření dobrého LP modelu vyžaduje OR specialistu, ne každý manažer to dokáže.
- Pro **strategická, špatně strukturovaná rozhodnutí** preferujme [[expertni-systemy|expertní systémy]] a [[geneticke-algoritmy|genetické algoritmy]] (cross-link ipmrk), které pracují s heuristikami a evolucí řešení.

## OR ve firemní praxi

Reálné nasazení OR prochází napříč odvětvími:

- **Logistika:** Skladové optimalizace, vehicle routing problem (Amazon, DHL, UPS používají LP a metaheuristiky pro denní plánování milionů zásilek).
- **Energetika:** Optimalizace výrobního mixu (uhlí / plyn / OZE) s respektováním poptávky a regulačních rezerv; unit commitment problem.
- **Bankovnictví:** Optimalizace portfolia (Markowitzův kvadratický model), credit scoring, ALM (asset-liability management).
- **Manufacturing:** Plánování výroby (MRP/ERP systémy obsahují LP solver pro disagregaci master plánu na operační rozvrh).
- **Health:** Plánování operativ, distribuce léků, alokace lůžek na JIP, plánování očkovacích kampaní.
- **Telecoms:** Optimalizace sítí, allocation rádiových frekvencí, plánování pokrytí 5G základnových stanic.

## Souvislosti

- [[sitova-analyza-cpm-pert|síťová analýza CPM/PERT]] — síťová analýza je podmnožinou OR specializovanou na projekty.
- [[mcfarlan-portfolio|McFarlanovo portfolio]] — klasifikační rámec aplikací IT/OR podle strategické důležitosti.
- [[expertni-systemy|expertní systémy]] — komplementární přístup pro nestrukturované strategické problémy.
- [[mereni-rizika|měření rizika]] — $\sigma^2$ jako vstup pro stochastické OR (PERT, Monte Carlo simulace).
- [[investicni-rozhodovani-bot|investiční rozhodování BOT]] — sensitivity analýza NPV jako aplikace OR principů.
- **Cross-course:**
  - [[optimalizace|optimalizace]] (ipmrk) — MATLAB solvery a numerické metody pro velké úlohy.
  - [[lagrangeova-metoda|Lagrangeova metoda]] (imek) — matematický základ omezené optimalizace, dualita v LP.
  - [[geneticke-algoritmy|genetické algoritmy]] (ipmrk) — evoluční optimalizace pro nelineární a kombinatorické problémy mimo dosah LP.

## Navigace

- **Předchozí:** [[dokumentarni-akreditiv]]
- **Navazující:** [[mcfarlan-portfolio]]
- **Související:** [[sitova-analyza-cpm-pert]], [[expertni-systemy]]
