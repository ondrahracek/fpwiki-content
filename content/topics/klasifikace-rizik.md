---
title: "Klasifikace rizik"
course: irmank
type: topic
tags: [irmank, klasifikace-rizik, dynamicke-staticke, ciste-spekulativni, kriticka-analyza]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Klasifikace rizik

> [!info] TL;DR
> Riziko klasifikujeme dvěma osami: a) podle **závažnosti** (kritické / důležité / běžné), b) podle **vlastností** (dynamické × statické, čisté × spekulativní, celkové × dílčí). Pro praktické řízení rizik se zaměřujeme na **ovlivnitelná, dynamická, spekulativní, dílčí rizika spojená se selháním podnikatelských subjektů** — právě zde má manažerský zásah největší smysl a největší dopad.

## Klasifikace podle závažnosti

První pohled na riziko vychází z dopadu jeho realizace na chod firmy. tři úrovně závažnosti, které mají přímou vazbu na zóny [[mapa-rizik|mapy rizik]] a na volbu [[taktiky-rizeni-rizik|taktiky řízení rizik]].

### Kritická rizika

- Realizace by způsobila **bankrot firmy** nebo zánik klíčové podnikatelské činnosti.
- Vyžadují prioritu **top managementu** a často i dohled vlastníků nebo dozorčí rady.
- Strategie: redukce, vyvarování, přenos — v praxi obvykle kombinace všech tří taktik.
- Příklady:
 - ztráta licence v regulovaném odvětví (banky, telekomunikace, energetika),
 - kybernetický útok ničící produkční data bez funkční zálohy,
 - požár klíčové výrobny bez pojištění majetku a přerušení provozu.

### Důležitá rizika

- Realizace by vyžadovala **další provoz s úvěrem** nebo zapojení dodatečných zdrojů (rezervní fondy, navýšení kapitálu).
- Vyžadují plán mitigace a **finanční rezervu** odpovídající očekávané ztrátě.
- Strategie: redukce, částečný přenos (spoluúčast, limit pojistného plnění).
- Příklady:
 - výpadek významného dodavatele bez okamžité alternativy,
 - ztráta klíčového zákazníka s podílem nad 20 % obratu,
 - právní spor s velkou finanční expozicí.

### Běžná rizika

- Realizace je **pokrytá aktivy** firmy z běžného cash-flow nebo provozní rezervy.
- Stačí **monitoring** a běžná opatření (procesy, školení, drobné pojištění).
- Strategie: udržení (retence) nebo malá redukce v rámci provozního rozpočtu.
- Příklady:
 - drobné pracovní úrazy,
 - krátké IT výpadky řešené v rámci SLA,
 - lokální stížnosti zákazníků nebo sousedů.

Vztah na zóny [[mapa-rizik|mapy rizik]]: kritická rizika odpovídají **červené zóně**, důležitá rizika **žluté zóně** a běžná rizika **zelené zóně**.

## 6 typů rizik podle vlastností

![[irmank-klasifikace-rizik-3osy.jpeg|Klasifikace rizik podle vlastností — tři binární dimenze (dynamické × statické, čisté × spekulativní, celkové × dílčí)]]

Druhý pohled klasifikuje riziko podle tří binárních dimenzí. Každá dimenze odpovídá jiné otázce a vede k jiné volbě nástroje pro řízení rizika.

### Dimenze 1: Dynamické × Statické

- **Dynamické riziko** — mění se v čase, závisí na ekonomické, technologické nebo společenské situaci.
 - Příklady: kurzové (FX) riziko, technologická diskontinuita (digitální hodinky vs. mechanické), regulační změna, změna chování spotřebitelů.
 - Těžce predikovatelné, vyžaduje **nepřetržitý monitoring** a aktivní reakci.
- **Statické riziko** — neměnné v čase, frekvence i závažnost prakticky konstantní.
 - Příklady: požár, krádež, sabotáž, přírodní katastrofy.
 - Predikovatelné statisticky (pojistné tabulky), proto vhodné pro pojištění.

### Dimenze 2: Čisté × Spekulativní

- **Čisté riziko (pure risk)** — pouze možnost ztráty, ne zisku.
 - Příklady: požár, krádež, úraz, právní spor, výpadek IT.
 - **Pojistitelné** — pojišťovny pracují téměř výhradně s čistými riziky, protože u nich neexistuje motivace pojištěného k vyvolání pojistné události se ziskem.
- **Spekulativní riziko (speculative risk)** — možnost ztráty **i zisku**.
 - Příklady: investice na akciovém trhu, FX spekulace, uvedení nového produktu na trh, akvizice firmy.
 - **Nepojistitelné** běžným způsobem — komerční pojištění zde podporuje *moral hazard* (pojištěný má motivaci přijmout vyšší riziko).
 - Přenos pomocí finančních **derivátů**, hedgingu, opcí a forwardů.

### Dimenze 3: Celkové × Dílčí

- **Celkové (systémové) riziko** — postihuje celý systém, odvětví nebo ekonomiku.
 - Příklady: makroekonomická krize, pandemie, kolaps měnové unie, dlouhodobá recese.
 - Diverzifikace **nepomáhá** — všichni účastníci trhu jsou postiženi současně.
 - Strategie: hedging proti makro-faktorům, geografická diverzifikace mimo systém, držení likvidity.
- **Dílčí (idiosynkratické) riziko** — postihuje jednu firmu nebo jednu organizační jednotku.
 - Příklady: výpadek konkrétního dodavatele, odchod klíčového zaměstnance, lokální požár, IT incident jedné aplikace.
 - **Diverzifikace pomáhá** — viz [[diverzifikace-rizik]].

## Souhrnná tabulka taxonomie

| Dimenze | Varianta A | Varianta B | Pojistitelné? | Diverzifikace pomáhá? |
|---|---|---|---|---|
| Závažnost | Kritické | Běžné | Ano (kritické) | Částečně |
| Časový vývoj | Dynamické | Statické | Statické ano | — |
| Strana zisk/ztráta | Čisté | Spekulativní | Pouze čisté | Ano u dílčích |
| Rozsah | Celkové | Dílčí | Dílčí ano | Pouze dílčí |

Tabulka ukazuje, že **pojištění** jako nástroj funguje výhradně u kombinace **statické + čisté + dílčí** a **diverzifikace** výhradně u **dílčích** rizik. Manažer musí riziko nejprve klasifikovat, aby vůbec mohl zvolit smysluplný nástroj.

## Kritická analýza rizik

**pět vlastností**, podle kterých manažer rizika prioritizuje pro praktické řízení. Tato kombinace vlastností definuje „adresovatelný prostor" rizik, v němž má manažer skutečnou páku.

> [!warning] Na co se zaměřit prioritně
> Pro praktické řízení rizik manažer rozlišuje rizika prioritní podle **pěti vlastností** současně:
> - ✓ **Ovlivnitelná** — manažer má páku, kterou riziko snížit (ne přírodní katastrofa).
> - ✓ **Dynamická** — mění se v čase, vyžaduje aktivní řízení.
> - ✓ **Spekulativní** — nese i potenciál výnosu, ne jen ztráty.
> - ✓ **Dílčí** — postihuje konkrétní firmu, lze diverzifikovat.
> - ✓ **Spojená se selháním podnikatelských subjektů** — relevantní pro firmu, ne abstraktní makro.

Vysvětlení každé vlastnosti:

- **Ovlivnitelná** — manažer má rozhodovací prostor a nástroje, jak riziko snížit. Nevytvoří 5 stupňů Richtera, ale může vybrat lepšího dodavatele, posílit interní kontroly nebo investovat do redundance.
- **Dynamická** — riziko se vyvíjí v čase, takže včasná reakce má smysl. U statických rizik (požár) má smysl jen pojištění, ne aktivní řízení.
- **Spekulativní** — manažer chce „pozitivní stránku" rizika, tedy vyšší výnos, ne jen vyhnout se ztrátě. Čistá rizika se přenášejí, spekulativní se aktivně využívají.
- **Dílčí** — diverzifikace funguje jen pro idiosynkratická rizika. U celkových (systémových) rizik manažer nemá co diverzifikovat.
- **Selhání podnikatelského subjektu** — manažer řídí konkrétní firmu, ne celé odvětví. Makroekonomická rizika sleduje, ale primárně ovlivňuje rizika spojená s vlastním podnikem.

Tyto vlastnosti se v praxi hodnotí najednou: rizika, která splňují všech pět vlastností, mají v portfoliu nejvyšší prioritu a největší přidanou hodnotu pro manažerský zásah.

## Příklady aplikace klasifikace

| Riziko | Závažnost | Dynamická? | Čisté/Spek.? | Celkové/Dílčí? | Doporučená taktika |
|---|---|---|---|---|---|
| Požár sídla bez pojištění | Kritické | Statické | Čisté | Dílčí | Přenos (pojištění) |
| Pokles poptávky o 20 % | Důležité | Dynamické | Spekulativní | Celkové | Redukce (diverzifikace, hedging) |
| Výpadek IT na 1 hodinu | Běžné | Dynamické | Čisté | Dílčí | Udržení + monitoring |
| Nepříznivý FX kurz | Důležité | Dynamické | Spekulativní | Celkové | Přenos (hedging) |
| Odchod klíčového developera | Důležité | Dynamické | Čisté | Dílčí | Redukce (mentoring, redundance) |
| Nový konkurent na trhu | Důležité | Dynamické | Spekulativní | Dílčí | Redukce (inovace, branding) |

Tabulka ukazuje, jak klasifikace přímo určuje **volbu taktiky**: pro čistá statická rizika přenos (pojištění), pro spekulativní celková hedging, pro dílčí dynamická aktivní redukce, pro běžná dílčí pouhá retence s monitoringem.

## Souvislosti

- [[definice-rizika]] — pojmosloví a obecná teorie rizika.
- [[mereni-rizika]] — kvantitativní popis pravděpodobnosti a dopadu.
- [[mapa-rizik]] — zóny korespondují s klasifikací kritická / důležitá / běžná.
- [[taktiky-rizeni-rizik]] — výběr taktiky podle klasifikace.
- [[diverzifikace-rizik]] — funguje pouze pro dílčí rizika.
- [[metody-snizovani-rizika]] — pojištění funguje pouze pro čistá rizika.

## Navigace
- **Předchozí:** [[taktiky-rizeni-rizik]]
- **Navazující:** [[metody-snizovani-rizika]]
- **Související:** [[mapa-rizik]], [[definice-rizika]]
