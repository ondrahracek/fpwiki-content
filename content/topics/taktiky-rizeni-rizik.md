---
title: "Taktiky řízení rizik"
course: irmank
type: topic
tags: [irmank, taktiky, vyvarovani, retence, redukce, prenos, iso-31000]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Taktiky řízení rizik

> [!info] TL;DR
> Pro každé riziko v [[mapa-rizik|mapě rizik]] (po vyhodnocení P × D) volíme jednu ze čtyř **taktik** podle pozice ve 2×2 matici pravděpodobnost × dopad:
>
> - **Vyvárování** (high P / low D) — častá drobná rizika tlumíme prevencí a standardizací.
> - **Udržení / retence** (low P / low D) — vědomě akceptujeme, prevence se nevyplatí.
> - **Redukce** (high P / high D) — nejzávažnější kvadrant, snižujeme P i D souběžně.
> - **Přenos** (low P / high D) — vzácná, ale závažná rizika přesouváme na třetí stranu (pojištění, smluvní převod).
>
> Tyto čtyři taktiky se aplikují v **cyklickém procesu** řízení rizik ve firmě (strategie → procesy → měření → analýza → výběr metod → úprava → zpět) a mapují se na **4 fáze ISO 31000-like modelu**: stanovení kontextu → analýza → vyhodnocení → zvládání. Výběr taktiky není jednorázový — riziko se mění s časem a taktika se musí periodicky přehodnocovat.

## Čtyři taktiky podle 2×2 matice

![[irmank-4-taktiky-matice.jpeg|4 taktiky řízení rizik podle matice pravděpodobnost × dopad]]

| | **Nízký dopad D** | **Vysoký dopad D** |
|-----------------|----------------------------|---------------------------|
| **Nízká P** | **Udržení (retence)** | **Přenos (pojištění)** |
| **Vysoká P** | **Vyvárování** | **Redukce** |

### Vyvárování (high P / low D)

- **Charakter rizik:** časté drobné incidenty — drobné vady ve výrobě, krátkodobé IT výpadky, administrativní chyby.
- **Strategie:** standardizace, automatizace, kontrolní postupy.
- **Cíl:** snížit **pravděpodobnost** P (dopad je už malý, takže se neřeší).
- **Příklad opatření:** SOP (standard operating procedures), pravidelné školení zaměstnanců, automatizovaná kontrola kvality, dvojí kontrola kritických kroků.
- **Logika:** drobné incidenty samy o sobě nebolí, ale jejich frekvence se sčítá do významných nákladů — proto se vyplatí prevence.

### Udržení / retence (low P / low D)

- **Charakter rizik:** vzácná drobná rizika, bagatelní svým dopadem.
- **Strategie:** vědomě riziko **akceptujeme** a počítáme s ním v rozpočtu.
- **Cíl:** nevyplácí se investovat do prevence — náklady na opatření by převýšily očekávanou ztrátu.
- **Příklad:** drobné stížnosti zákazníků (řeší se ad hoc), mimořádné výdaje pod reportingovou hranicí, ojedinělé poškození drobného inventáře.
- **Detail viz [[metody-snizovani-rizika]]** — retence má více forem: vědomá vs. nevědomá, dobrovolná vs. nedobrovolná. Rozdíl je v tom, zda firma riziko skutečně identifikovala a vědomě s ním pracuje, nebo o něm jen neví.

### Redukce (high P / high D)

- **Charakter rizik:** **nejzávažnější kvadrant** matice — vyžaduje pozornost top-managementu.
- **Strategie:** snížit P i D **souběžně** — preventivní opatření (snížení P) + nápravné/zmírňující opatření (snížení D).
- **Cíl:** posunout riziko z červené zóny mapy do žluté nebo zelené.
- **Příklad opatření:** zavedení BCM (cross-link [[bcm|Business Continuity Management]] z [[imork|ImorK]]), redundance kritických systémů, diverzifikace dodavatelů (viz [[diverzifikace-rizik]]), krizový plán, redundantní zálohování.
- **Logika:** v tomto kvadrantu nelze riziko jen akceptovat ani jen pojistit — pojistné by bylo neúnosně drahé a akceptace by ohrozila existenci firmy.

### Přenos (low P / high D)

- **Charakter rizik:** vzácné, ale extrémně závažné — typické „black swan" události.
- **Strategie:** **přesun rizika** na třetí stranu (pojišťovna, finanční partner, dodavatel).
- **Cíl:** omezit finanční ztrátu, pokud k riziku dojde — firma platí pravidelnou „prémii" (pojistné, poplatek) výměnou za to, že kryje extrémní scénář někdo jiný.
- **Příklad:** pojištění proti přírodním katastrofám, hedging FX rizika derivativy, [[faktoring]] (přenos credit rizika z pohledávek na faktora), [[forfaiting]] (přenos středně- a dlouhodobého exportního rizika), [[dokumentarni-akreditiv]] (přenos rizika nezaplacení v mezinárodním obchodě).

## Hraniční případy a kombinace

V praxi rizika nezapadají úhledně do jednoho kvadrantu — situace je typicky složitější:

- **Kombinace taktik** — některá rizika přesahují více kvadrantů, takže se aplikuje **kombinace**. Příklad: rozsáhlý požár výrobní haly se řeší **redukcí** (sprinklery, hasicí systém, požární bezpečnostní opatření) **i přenosem** (majetkové pojištění + pojištění přerušení provozu).
- **Dynamika v čase** — riziko se mění s vývojem firmy, technologií i externího prostředí. Taktika, která dávala smysl loni, nemusí dnes fungovat. Proto se mapa rizik a volba taktik **periodicky přehodnocuje**, typicky při ročním update mapy rizik nebo po významné změně (akvizice, nový produkt, regulatorní změna).
- **Pojistitelnost** — pojištění je dostupné **jen pro určitá rizika**. Reputační rizika, strategická rizika a většina kybernetických rizik mají v pojistných smlouvách významné výjimky (exempty) — pro ně přenos prakticky nelze plnohodnotně aplikovat a zbývá redukce.
- **Náklady taktiky vs. expozice** — pokud je pojistné nebo cena prevence vyšší než očekávaná ztráta z rizika, ekonomicky vychází retence i pro středně závažné riziko.

## Proces řízení rizik ve firmě (cyklický)

![[irmank-proces-rizeni-rizik.jpeg|Cyklický proces řízení rizik ve firmě]]

Řízení rizik není jednorázová aktivita — funguje jako **uzavřený cyklus** se zpětnou vazbou. Šest typických kroků:

1. **Strategie firmy** (např. IS/IT strategie) — určuje, kde firma operuje a jaká rizika jsou pro ni relevantní. Strategie je zdrojem rizikových oblastí.
2. **Firemní procesy** (např. informační toky, výroba, prodej, HR) — konkrétní místa, kde rizika reálně působí a kde se projevují jejich dopady.
3. **Měření rizik a monitorování** (cross-link [[mereni-rizika]]) — kvantifikace P a D, sledování KRI (key risk indicators), detekce změn rizikového profilu.
4. **Analýza rizik** (např. analýza rizik informačního systému firmy) — viz [[analyza-rizik-proces]]. Identifikace, posouzení a zhodnocení rizik.
5. **Výběr a implementace metod snižování rizika** — pro každé významné riziko se zvolí jedna ze **4 taktik** (vyvárování / udržení / redukce / přenos) a konkrétní metoda v rámci té taktiky.
6. **Úprava procesu** (např. úprava informačního systému, změna SOP, doplnění kontrol) → zpětná vazba do **strategie firmy** v dalším cyklu.

Cyklus probíhá kontinuálně — typicky s ročním formálním reviewem a průběžnými ad hoc úpravami při významných událostech.

## Čtyřfázový model (ISO 31000-like)

![[irmank-rizik-cyklus-4faze.jpeg|Čtyři fáze řízení rizik: stanovení kontextu → analýza → vyhodnocení → zvládání]]

Komplementární pohled — **čtyřfázový model**, který je blízký mezinárodnímu standardu **ISO 31000** pro risk management:

1. **Stanovení kontextu** — rozsah řízení rizik, cíle, kritéria pro hodnocení, zainteresované strany (stakeholders), externí a interní prostředí. Pro detail ISO 31000 viz cross-link [[rizeni-rizik|Řízení rizik]] z kurzu [[imork|ImorK]].
2. **Analýza rizik** — identifikace rizik + jejich posouzení (P × D). Detail v [[analyza-rizik-proces]].
3. **Vyhodnocení rizik** — prioritizace rizik, srovnání s kritérii přijatelnosti, mapování. Výstupem je [[mapa-rizik]].
4. **Zvládání rizik** — výběr a implementace **4 taktik** (přesně téma této stránky). Pro každé riziko nad přijatelnou hranicí se rozhodne, zda se eliminuje, akceptuje, redukuje, nebo přenese.

### Mapování 4 taktik prof. Raise na ISO 31000 risk treatment

| Taktika prof. Raise | ISO 31000 risk treatment |
|-----------------------------|---------------------------------------------------|
| Vyvárování | Risk avoidance / risk reduction (probability) |
| Udržení (retence) | Risk acceptance |
| Redukce | Risk reduction (impact + probability) |
| Přenos | Risk transfer / risk sharing |

Terminologie se liší, podstata je shodná — obě klasifikace pokrývají stejný prostor reakcí na riziko, jen ho dělí mírně odlišnými řezy.

## Praktická doporučení

- **Pravidelně přehodnocujte** — riziko se mění s časem (nové regulace, technologie, makroekonomické otřesy, nová konkurence). Volba taktiky platná před rokem nemusí být platná dnes.
- **Dokumentujte rozhodnutí** — proč byla zvolena konkrétní taktika, kdo je **vlastník rizika** (risk owner), kdy je naplánovaný review, jaké jsou KRI pro spuštění mimořádného přehodnocení.
- **Křížové vazby s BCM** — kombinace **redukce + přenos** je často základem [[bcm|BCM strategie]] (cross-link na [[imork|ImorK]]). BCM definuje, jak firma přežije realizaci závažného rizika.
- **Komunikace napříč firmou** — taktiky a jejich logika musí být známé na všech úrovních organizace, ne jen v Risk Committee. Operativní pracovníci jsou těmi, kdo skutečně realizují prevenci a kontroly.
- **Sladění s rozpočtem** — každá taktika má jiné nákladové profily (vyvárování = průběžné OPEX, redukce = CAPEX + OPEX, přenos = pravidelné pojistné, retence = rezerva). Plán řízení rizik musí být sladěn s finančním plánem.

## Časté chyby

- **Nadužívání pojištění** — některá rizika pojistné smlouvy nepokrývají nebo mají významné výjimky (kybernetické incidenty, válečné konflikty, pandemie, reputační škody). Spoléhat na přenos tam, kde realita pojistné výjimky nepokryje, je nebezpečná falešná jistota.
- **Falešná retence** — firma deklaruje, že riziko „akceptuje", ale nemá vytvořené finanční rezervy ani plán reakce. Když riziko nastane, firma zjistí, že akceptace nebyla vědomá, ale jen nedbalost.
- **Inerce taktik** — jednou zvolená taktika se nepřehodnocuje, i když se kontext dramaticky změnil. Klasický příklad: firma pojišťuje riziko, které už dávno není relevantní, a neřeší rizika nově vzniklá.
- **Záměna redukce a vyvárování** — terminologicky se zaměňují. **Vyvárování** snižuje primárně **P** (prevence, aby riziko nenastalo). **Redukce** snižuje **obojí** — P prevencí a D nápravnými/zmírňujícími opatřeními pro případ, že riziko přesto nastane.
- **Ignorace zbytkového rizika** — i po aplikaci taktiky zůstává **reziduální riziko**, které je třeba explicitně vyhodnotit a buď akceptovat, nebo dále řešit.

## Souvislosti

- [[mapa-rizik]] — vstup pro výběr taktiky (P × D určuje kvadrant).
- [[metody-snizovani-rizika]] — konkrétní metody pro každou ze 4 taktik (6 metod celkem).
- [[analyza-rizik-proces]] — předchozí krok cyklu (identifikace + posouzení rizik).
- [[diverzifikace-rizik]] — jedna z konkrétních metod redukce.
- [[faktoring]], [[forfaiting]], [[dokumentarni-akreditiv]] — finanční nástroje realizující taktiku přenosu.
- [[mereni-rizika]] — kvantitativní podklad pro výběr taktiky.
- **Cross-course:** [[rizeni-rizik]] z [[imork|ImorK]] — ISO 31000 / ISO 27005 v kontextu informační bezpečnosti, [[bcm]] z [[imork|ImorK]] — kontinuita podnikání jako součást taktiky redukce.

## Navigace

- **Předchozí:** [[mapa-rizik]]
- **Navazující:** [[klasifikace-rizik]]
- **Související:** [[metody-snizovani-rizika]]
