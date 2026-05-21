---
title: Obchodní tajemství a ochrana informace
course: icink
type: topic
tags: [icink, obchodni-tajemstvi, counter-ci, kvalita-informace]
sources: [raw/icink/IcinK-poznamky_z_prednasek.docx]
created: 2026-05-21
updated: '2026-05-21'
---

# Obchodní tajemství a ochrana informace


**Obchodní tajemství** je právně chráněná kategorie informací podniku. V praxi je primárním předmětem [[counter-competitive-intelligence|CCI]] (Counter Competitive Intelligence) — bez jasně vymezeného obchodního tajemství nelze chránit nic konkrétního a žádné kontrarozvědné opatření nemá smysl.

## Právní rámec

### §504 zákona č. 89/2012 Sb., občanský zákoník (účinný od 1. 1. 2014)

> Obchodním tajemstvím je jakýkoli plán, předloha, metoda nebo soubor informací použitých v byznysu, které poskytují svému majiteli **výhodu před konkurenty** [a splňují další zákonné znaky utajení a hodnoty].

**Znaky obchodního tajemství** podle zákona:

1. **Hospodářská, technická, výrobní nebo provozní povaha.**
2. **Konkurenční hodnota** — poskytuje výhodu vůči konkurenci.
3. **Není v daných obchodních kruzích běžně dostupné.**
4. **Majitel zajišťuje jeho utajení** (aktivní opatření).

**Důsledek:** pokud firma nepodniká aktivní kroky k utajení informace, ta **přestává být** obchodním tajemstvím podle zákona — bez ohledu na svou strategickou hodnotu.

### Předmět obchodního tajemství

Firma musí mít interně **jasně, jednoznačně a písemně** vymezeno, co je jejím obchodním tajemstvím:

- Strategické plány a interní analýzy.
- Výrobní postupy, vzorce, technologické know-how.
- Seznamy zákazníků s nestandardními podmínkami.
- Cenotvorba a marže.
- Bezpečnostní opatření a [[counter-competitive-intelligence|CCI procesy]] samotné.

A musí být **zabezpečeno a toto zabezpečení vyžadováno**. Bez aktivní ochrany nárok na právní ochranu nekalou soutěží zaniká.

### Vlastní firemní definice

Vlastní definice obchodního tajemství ve firemní směrnici **musí vycházet ze zákona** (§504), ale může jít nad jeho rámec — typicky:

- Konkrétní výčet kategorií informací.
- Stupně utajení (např. interní / důvěrné / přísně tajné).
- Pravidla zacházení pro každý stupeň.

## Principy ochrany

### Princip 1 — Need-to-know (fragmentace obchodního tajemství)

> **Každý zná jen to, co potřebuje ke své práci.** Pro sdílení informace mezi pracovníky musí existovat **důvod**.

V praxi:

- Strategický plán nezná každý vedoucí — jen ten, kdo ho realizuje.
- Výrobní postup je rozdělen na **funkční celky** — žádný pracovník nezná kompletní postup.
- Komunikace mezi pracovníky o citlivém tématu **nikdy napřímo** — vždy přes vedoucího. Vedoucí má kontextu více, posoudí oprávněnost sdílení.
- **Nikdy zadání pro dva různé pracovníky na jednom stole** — riziko, že jeden uvidí, co dělá druhý.

### Princip 2 — Nesvěřit nikomu, kdo neumí tajemství udržet

Druhá strana principu need-to-know. Schopnost udržet tajemství je dovednost, kterou musí pracovník prokázat — typicky:

- Průběžné chování v menších otázkách.
- Reakce na pokusy konkurence o vytěžování.
- Životní situace (rizikové skupiny — viz [[counter-competitive-intelligence|CCI]]).

### Vzorec pravděpodobnosti utajení P = s^n

> [!info] Hlavní insight v jedné větě
> Pravděpodobnost, že informace zůstane utajena, **klesá exponenciálně** s počtem zasvěcených — i při vysoké spolehlivosti jednotlivců se rychle blíží nule. Důsledek pro praxi: omezit okruh zasvěcených na minimum.

Empirické pravidlo: **pravděpodobnost utajení informace P** prudce klesá s počtem informovaných osob:

$$P = s^n$$

kde:

- $s \in (0,1)$ — pravděpodobnost, že **jeden** konkrétní pracovník informaci neprozradí (jeho **spolehlivost**).
- $n$ — počet osob, které informaci znají.

```graph
title: Pravděpodobnost utajení P = s^n
alt: Exponenciálně klesající křivka P(n) = s na n-tou, kde n je počet informovaných osob. Posuvník s mění spolehlivost jednotlivce v rozmezí 0,70 až 0,99. Markery vyznačují hodnoty pro n=1, n=10 a n=20. Při výchozí spolehlivosti s=0,95 a n=10 klesá pravděpodobnost utajení přibližně na 0,60; při n=20 na 0,36.
xAxis: { label: "n (počet informovaných)", domain: [0, 30] }
yAxis: { label: "P (pravděpodobnost utajení)", domain: [0, 1] }
params:
  - { name: s, label: "Spolehlivost jednotlivce s", min: 0.7, max: 0.99, default: 0.95, step: 0.01 }
curves:
  - { fn: "s^x", label: "P = s^n", color: "fp-purple" }
markers:
  - { x: 1, label: "n=1" }
  - { x: 10, label: "n=10" }
  - { x: 20, label: "n=20" }
```

**Implikace:**

- I při vysoké spolehlivosti (např. $s = 0{,}95$) pravděpodobnost utajení s rostoucím $n$ rychle klesá: pro 10 osob $P = 0{,}95^{10} \approx 0{,}60$; pro 20 osob $\approx 0{,}36$.
- **Ideál:** jen **dva nositelé** informace — šéf a ten, komu ji svěřil.
- Při sdílení s každou další osobou se vystavujeme riziku exponenciálně rychleji než lineárně.

## Hrozby: kdo a jak útočí

> *Tzv. **průmyslovou špionáž** nelze absolutně odstranit. Čím tvrdší konkurenční boj, tím více se kradou cizí myšlenky.*

### Typy útočníků

- **Konkurence** přímá — ofenzivní [[competitive-intelligence|CI proces]] proti nám.
- **Bývalí zaměstnanci** — zejména ti, kteří neodešli v dobrém. Klasický scénář: bývalý zaměstnanec pozve svého kamaráda z práce *„na skleničku"* a vytěží ho.
- **Stávající zaměstnanci** s vazbou na konkurenci.
- **Zákazníci, dodavatelé, partneři** — strana, která má autorizovaný přístup k části informací.
- **Hackerské skupiny** (kybernetický útok — viz [[kyberneticka-bezpecnost|kybernetická bezpečnost]]).
- **Lovci mozků** — náborové agentury cílící na pracovníky s know-how.

### Princip rychlosti

> *Hlavní obranou před průmyslovou špionáží je **rychlost** — být v inovaci o krok napřed.*

Klasická obrana (utajení) má své meze. Doplňková strategie: **inovovat rychleji než konkurence dokáže krást** — než konkurent informaci aplikuje, je už zastaralá.

## Únik informace

> **Únik informace** = *informace, která se stala známou navzdory snaze o utajení.* (Fuld)

Únik je různý od **prozrazení** (úmyslné, vědomé sdělení) — únik je *bez záměru původce*.

### Deset typických signálů úniku informace

V poznámkách jsou identifikovány signály, podle kterých CCI rozpoznává, že **k úniku došlo**:

1. **Konkurence vyrobila stejný výrobek** v podezřele krátkém čase.
2. **Pokles zisku** v segmentu, kde jsme měli výhradní know-how.
3. **Výsledky tajného výzkumu publikované v zahraničí** (často v akademickém časopise) bez naší participace.
4. **Telefonní hovory** s netypickým obsahem směrem do firmy nebo ven.
5. **Pravidelná evidence v úřadech** — patentové přihlášky, registrační dokumenty konkurence ve stejné nice.
6. **Průzkumy** mezi našimi zaměstnanci, partnery, zákazníky (mystery shopping na nás).
7. **Lovci mozků** se opakovaně objevují u našich klíčových pracovníků.
8. **Styčné plochy v oboru** — známky, že konkurent zná naše vnitřní procesy.
9. **Ztracené dokumenty, ztracené notebooky** — fyzický únik média.
10. **Hackerská aktivita** — penetrační pokusy, phishing zaměřený na naše pracovníky.

Identifikace signálu úniku spouští **[[zpravodajsky-proces-cci|zpravodajský proces CCI]]** — vyšetřování, identifikace zdroje, opravná opatření.

## Ochrana informace a utajení činnosti

Vedle ochrany **statického obchodního tajemství** je nutno chránit také **proces činnosti** — to, že firma na něčem pracuje, **dokud to nelze odhalit**:

- Nezveřejňovat tematické zaměření výzkumu před patentovou ochranou.
- Neoznamovat strategické záměry před jejich realizací.
- Krýt **identitu klíčových osob** projektu (utajit, kdo se na čem podílí).
- Vést **vědomé informační stopy** — symptomy, které mohou konkurenci zmást ohledně našeho zájmu (defenzivní [[dezinformace|dezinformace]]).

## Role v ochranném systému

| Role | Odpovědnost |
|---|---|
| **Vrcholové vedení** | strategická kontrola, klasifikace obchodního tajemství, schvalování Směrnice |
| **Vedoucí CCI útvaru** | provoz kontrarozvědné ochrany, [[zpravodajsky-proces-cci\|9-krokový proces CCI]], vyšetřování úniků |
| **Vlastník informace** | odpovědnost za konkrétní informaci, určení komu se sdělí |
| **Držitel informace** | povinnost utajit, povinnost reportovat snahy o vytěžení |
| **Bezpečnostní útvar** | mechanická a elektronická ostraha, kategorizace objektů |
| **Personální útvar** | screening, školení, ukončování pracovního poměru se zachováním NDA |

## Související stránky

- [[icink|Kurz IcinK]]
- [[counter-competitive-intelligence|Counter Competitive Intelligence (CCI)]]
- [[zpravodajsky-proces-cci|Zpravodajský proces CCI — 9 kroků]]
- [[competitive-intelligence|Competitive Intelligence — vymezení a procesy]]
- [[zdroje-dat-informaci|Zdroje dat a informací]] — HUMINT a útoky na zaměstnance
- [[dezinformace|Dezinformace]] — defenzivní použití
- [[isms|ISMS (ImorK)]]
- [[ochrana-dat|Ochrana dat (ImorK)]]
- [[gdpr|GDPR (ImorK)]] — průniková zóna ochrany informací a ochrany osobních údajů

## Reference

- Zákon č. 89/2012 Sb., občanský zákoník, §504. — definice obchodního tajemství.
- BARTES, František. *Konkurenční zpravodajství. Tvorba podkladů pro strategické rozhodování podniku.* Praha: Grada, 2022. ISBN 978-80-271-3504-2. — kap. 9–10 (Counter Competitive Intelligence).
- FULD, Leonard M. *The New Competitor Intelligence.* 1995. — definice úniku informace.
