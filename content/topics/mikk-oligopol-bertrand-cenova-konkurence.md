---
title: "Oligopol — Bertrandův model cenové konkurence"
course: mikk
type: topic
tags: [mikk, mikroekonomie, oligopol, bertrand, cenova-konkurence]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf, raw/mikk/mikro-FINAL-2-1.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Oligopol — Bertrandův model cenové konkurence

## TL;DR

**Bertrandův model** popisuje oligopol, kde firmy soutěží **cenou**, ne množstvím (na rozdíl od [[mikk-oligopol-cournot-stackelberg|Cournotova a Stackelbergova modelu]]). Při **homogenním produktu** vzniká paradoxní výsledek: již **dvě firmy** stačí k tomu, aby cena spadla na úroveň mezních nákladů, $P = MC$, a ekonomický zisk byl nulový — výsledek identický s dokonalou konkurencí. Tomu se říká **Bertrandův paradox**. Při **diferenciaci produktu** se model výrazně mění: firmy získávají určitou monopolní sílu z odlišnosti svých výrobků a v rovnováze platí $P > MC$ s pozitivním ziskem.

V kurzu [[mikk|Mikroekonomie 2 (mikK)]] je Bertrand jedním ze čtyř standardních modelů oligopolu (Cournot, Stackelberg, Bertrand, [[mikk-oligopol-cenovy-vudce-kartel|cenový vůdce / kartel]]). Pro srovnání všech modelů viz [[mikk-srovnani-modelu-oligopolu|Srovnání modelů oligopolu]].

## Bertrandova hypotéza

Joseph Bertrand v roce 1883 reagoval kritikou na Cournotův model. Jeho výchozí předpoklad zní: firmy v oligopolu obvykle **nestanovují množství**, ale **ceny** — a teprve podle poptávky se rozhoduje o vyrobeném množství.

Základní předpoklady:

1. Na trhu jsou alespoň **dvě firmy** (typicky duopol).
2. Produkt je **homogenní** (zákazník jej vnímá jako identický u obou firem).
3. Firmy stanovují **ceny** $P_1, P_2$ současně a nezávisle.
4. Zákazníci kupují u **nejlevnějšího** prodejce.
5. Pokud jsou ceny stejné ($P_1 = P_2$), trh se **dělí rovnoměrně** (každá firma získá polovinu).
6. Firmy mají **identické mezní náklady** $MC$ a **neomezenou kapacitu** (mohou pokrýt celou poptávku).

> [!info] Klíčový rozdíl proti Cournotovi
> V [[mikk-oligopol-cournot-stackelberg|Cournotově modelu]] je strategickou proměnnou **množství**, cena se dotvoří trhem. V Bertrandovi je strategickou proměnnou **cena** a množství se dotvoří poptávkou. Tento zdánlivě drobný rozdíl vede k zásadně odlišné rovnováze.

## Bertrandův paradox — homogenní produkt

![[mikk-bertrand-konvergence.jpeg|Bertrandova cenová konkurence — payoff matice se sbíháním k Nash (P=MC) a cenová konvergence v poptávkovém diagramu]]

Nejpřekvapivější výsledek modelu: již **dva** soutěžící podseknou cenu až na úroveň $MC$. Postup uvažování:

1. Firma 1 stanoví počáteční cenu $P_1 = MC + \epsilon$, kde $\epsilon > 0$ je malá kladná přirážka. Při této ceně by získala polovinu trhu a malý kladný zisk.
2. Firma 2 ví, že stačí, aby šla **mírně pod** firmu 1, a získá **celý trh**. Stanoví tedy $P_2 = MC + \epsilon/2$.
3. Firma 1 reaguje stejnou logikou: $P_1 = MC + \epsilon/4$.
4. Firma 2 znovu podsekne: $P_2 = MC + \epsilon/8$.
5. Tato sestupná spirála (race to the bottom) končí teprve tehdy, kdy už není kam ustoupit — tedy v bodě $P_1 = P_2 = MC$.

V Nashově rovnováze tedy platí:

$$
P_1^* = P_2^* = MC, \qquad \pi_1 = \pi_2 = 0.
$$

Důkaz, že žádný jiný stav rovnováhou není:

- **Pokud $P_i > MC$:** druhá firma má motivaci nastavit $P_j = P_i - \epsilon$ a získat celý trh. Není to rovnováha.
- **Pokud $P_i < MC$:** firma vyrábí pod náklady a má motivaci zvednout cenu. Není to rovnováha.
- **Jediný stabilní bod je $P_1 = P_2 = MC$.**

> [!warning] Bertrandův paradox
> Při dvou firmách s homogenním produktem a stejnými $MC$ vychází stejný výsledek jako u dokonalé konkurence: $P = MC$, $\pi = 0$. **Stačí dvě firmy** k vyloučení monopolního zisku — proto „paradox": realita ukazuje, že duopol obvykle generuje zisk, takže model musí zachycovat něco zjednodušeně.

## Geometrie a reakční funkce

Reakční funkce (best response) firmy 2 vzhledem k ceně firmy 1 má v homogenním Bertrandovi tvar:

$$
P_2(P_1) = \begin{cases} P_1 - \epsilon, & \text{pokud } P_1 > MC \\ MC, & \text{pokud } P_1 = MC \\ \text{libovolná} \ge MC, & \text{pokud } P_1 < MC \end{cases}
$$

Rovnováha leží na průniku obou reakčních křivek — symetrický bod $(P_1, P_2) = (MC, MC)$. Geometricky tedy nejde o hladký průsečík dvou křivek jako u Cournota, ale o limitní bod sestupné posloupnosti.

## Kritika Bertrandova modelu

Hlavní kritické ohlasy:

1. **Pokud existuje opravdu homogenní zboží, je výhodnější soutěžit množstvím** (Cournot) než cenou. Proč by racionální firma šla do cenové války, když ví, že skončí s nulovým ziskem? Reálný oligopol se obvykle homogenitě vyhýbá.
2. **Při stejné ceně nelze přesně určit tržní podíl.** Předpoklad „rozdělí se napůl" je technický idealismus; ve skutečnosti zákazníci volí podle vzdálenosti, zvyklostí, dostupnosti.
3. **Trh nelze přesně rozdělit** — agregátní poptávka neumí říct, který konkrétní zákazník půjde ke které firmě.
4. **Předpoklad neomezené kapacity** je nereálný. Pokud firma 1 stanoví $P_1 = MC$ a získá celý trh, musí být schopna vyrobit $Q$ pro celou poptávku — ale výrobní kapacity jsou v praxi konečné.
5. **Statická simultánnost** ignoruje fakt, že firmy reagují na konkurenta v čase a mají historii.

## Bertrand–Edgeworth — rozšíření o kapacitní omezení

Pokud uvolníme předpoklad neomezené kapacity, paradox mizí. **Edgeworth (1925)** ukázal, že při kapacitních omezeních:

- Firma s nízkou cenou nedokáže obsloužit celý trh.
- Druhá firma získá zbytkovou poptávku za **vlastní (vyšší) cenu**.
- Vzniká motivace mít cenu **nad MC**, protože se počítá s tím, že konkurent prodá svou kapacitu a zbytek půjde za vyšší cenu.

Výsledek: **rovnováha smíšených strategií** — firmy randomizují mezi několika cenovými hladinami a $P > MC$ je očekávaná cena. Bertrand–Edgeworthův model je most mezi čistým Bertrandem a Cournotem.

Dalším rozšířením je [[mikk-oligopol-zalomena-poptavka|Sweezyho zalomená poptávková křivka]] — model rigidních cen v oligopolu.

## Cenová konkurence při diferenciaci produktu

Reálnější verze Bertranda předpokládá, že **produkty firem nejsou identické**. Tržní podíl pak nezávisí čistě na ceně, ale i na:

- **Designu** (vzhled, ergonomie),
- **Užitných vlastnostech** (funkce, výkon),
- **Životnosti** výrobku,
- **Brandu** a vnímané kvalitě,
- **Lokaci** (vzdálenost, dostupnost),
- **Doplňkových službách** (servis, záruka).

Při diferenciaci se chování poptávky popisuje **lineárními poptávkovými funkcemi** typu:

$$
Q_A = a - b\, P_A + c\, P_B, \qquad Q_B = a - b\, P_B + c\, P_A,
$$

kde $b > c > 0$ — vlastní cena má větší vliv než cena konkurenta (substituty, ne perfektní). Firmy maximalizují zisk vůči **vlastní ceně**, $P_B$ berou jako dané.

Z FOC plyne reakční funkce, např.:

$$
P_A(P_B) = \frac{a + b\, MC + c\, P_B}{2b}.
$$

Symetrické řešení dává **Bertrand–Nashovu rovnováhu s diferenciací**, kde $P^* > MC$ a obě firmy mají **kladný zisk**.

> [!tip] Klíčový závěr
> Diferenciace dává firmám „kus monopolu". Čím je $c$ menší (čím méně si firmy konkurují), tím větší je rovnovážná cenová přirážka nad MC.

## Příklad — diferencovaný Bertrand

Mějme dvě firmy A a B s reakčními funkcemi:

$$
P_A = 30 + 0{,}5\, P_B, \qquad P_B = 30 + 0{,}5\, P_A.
$$

Symetrické řešení (z dosazení):

$$
P_A = 30 + 0{,}5(30 + 0{,}5\, P_A) = 45 + 0{,}25\, P_A
$$

$$
0{,}75\, P_A = 45 \quad\Rightarrow\quad P_A^* = 60, \quad P_B^* = 60.
$$

Pokud $MC = 20$, zisková marže je $P - MC = 40$ na jednotku — výsledek diametrálně odlišný od homogenního Bertranda, kde by bylo $P = 20$.

## Bertrand vs. Cournot — kdy který model

Volba modelu závisí na **časové struktuře rozhodování**:

| Charakteristika | Cournot | Bertrand |
|-----------------|---------|----------|
| Strategická proměnná | Množství / kapacita | Cena |
| Typický kontext | Dlouhý plánovací horizont, fyzická výroba | Rychle nastavitelná cena, služby, software |
| Výsledek (homogenní) | $P > MC$, kladný zisk | $P = MC$, nulový zisk |
| Výsledek (diferenciace) | $P > MC$ (intenzivnější) | $P > MC$ |
| Realismus | Vyšší pro výrobu | Vyšší pro služby a digitální trhy |

**Kreps–Scheinkmanův výsledek (1983):** dvoustupňová hra, kde firmy nejdříve zvolí kapacitu a pak cenu, **dává Cournotovský výsledek**. To teoreticky usmiřuje oba modely — Bertrand popisuje krátkodobou cenovou hru, Cournot dlouhodobou kapacitní.

## Empirické testování

V mnoha trzích Cournot lépe vystihuje data:

- **Genesove–Mullin (1998)**: trh s cukrem v USA — Cournotův model dobře předpovídá ceny.
- **Trh ropy (OPEC)**: kapacitní hra → bližší Cournotu / kartelu.

Naopak v některých trzích vítězí Bertrand:

- **Cloud computing** (AWS vs. Azure vs. GCP) — dynamické cenotvorby, rychlé reakce.
- **Ad-tech aukce** — cenová konkurence v reálném čase.
- **Generika po vypršení patentu** — homogenní produkt → ceny rapidně padají, klasický Bertrandův paradox.

## Detailní příklad — Předtermín B (zalomená poptávka s prvkem cenové volby)

Příklad ze zkouškového Předtermínu B kombinuje monopolistovo cenotvorné rozhodování se zalomenou poptávkou — ukazuje, jak firma volí **cenu**, když má před sebou **dvě poptávkové větve**.

**Zadání:**

$$
TC = 100 + 30Q, \qquad Q_1 = 100 - P \text{ pro } P \le P^*, \qquad Q_2 = 160 - 2P \text{ pro } P > P^*.
$$

Mezní náklady: $MC = \dfrac{dTC}{dQ} = 30$.

**Krok 1 — bod zlomu $P^*$.** V bodě zlomu se obě poptávky musí potkat:

$$
100 - P^* = 160 - 2P^* \quad\Rightarrow\quad P^* = 60, \quad Q^* = 40.
$$

**Krok 2 — inverzní poptávka v každé větvi.**

- Pro $P \le 60$: $P = 100 - Q$, tedy $TR_1 = (100 - Q)Q = 100Q - Q^2$, $MR_1 = 100 - 2Q$.
- Pro $P > 60$: $P = 80 - 0{,}5\, Q$, tedy $TR_2 = 80Q - 0{,}5\, Q^2$, $MR_2 = 80 - Q$.

**Krok 3 — kandidáti na optimum.**

- Větev 1 ($P \le 60$): $MR_1 = MC \Rightarrow 100 - 2Q = 30 \Rightarrow Q = 35$, $P = 65$. **Spor:** vyšlo $P > 60$, takže optimum v této větvi neexistuje a leží buď v bodě zlomu, nebo v druhé větvi.
- Větev 2 ($P > 60$): $MR_2 = MC \Rightarrow 80 - Q = 30 \Rightarrow Q = 50$, $P = 80 - 25 = 55$. **Spor:** vyšlo $P < 60$, takže optimum v této větvi taky neexistuje.

**Krok 4 — optimum je v bodě zlomu.** Protože v jedné větvi $MR > MC$ a ve druhé $MR < MC$, monopolista volí přesně bod zlomu:

$$
P^{**} = 60, \qquad Q^{**} = 40.
$$

**Krok 5 — zisk.**

$$
TR = 60 \cdot 40 = 2\,400, \quad TC = 100 + 30 \cdot 40 = 1\,300, \quad \pi = 1\,100.
$$

> [!note] Souvislost s Bertrandem
> Tento příklad není čistě Bertrandův (jde o jednu firmu se dvěma poptávkovými segmenty), ale ilustruje **rozhodování o ceně**, které je jádrem Bertrandovy logiky. Pokud by stejnou poptávku obsluhovaly dvě homogenní firmy, paradox by je vtáhl k $P = MC = 30$ a zisk by byl nulový. Vidíme tedy, jak silně samotný počet a typ konkurentů ovlivňuje cenu i zisk.

## Edge cases

**1. Diskrétní ceny.** Pokud lze cenu měnit jen po haléřích / centech, rovnováha může být $P = MC + 0{,}01$ — firmy se nedostanou až na $MC$, protože je nelze podseknout o méně než nejmenší cenovou jednotku. V praxi se to projevuje jako mírně kladný zisk.

**2. Asymetrické MC.** Pokud má firma 1 nižší $MC_1 < MC_2$, výsledek se posune k **limit pricingu**: firma 1 stanoví $P = MC_2 - \epsilon$, firma 2 nedokáže ziskově konkurovat a opouští trh (nebo prodává nulu). Firma 1 se stává **kvazi-monopolem** s cenou těsně pod náklady konkurenta.

**3. Více než dvě firmy.** S rostoucím počtem firem je výsledek stejný — paradox neslábne. To je další argument proti realismu: ve skutečnosti zisk monotónně klesá s počtem firem (jak ukazuje [[mikk-oligopol-cournot-stackelberg|Cournot]]).

**4. Dynamická hra (opakovaný Bertrand).** Pokud firmy hrají hru opakovaně, je možná **tichá koluze** — udržování ceny nad MC pomocí trigger strategií. Souvisí s [[mikk-vezno-dilema-teorie-her|vězňovým dilematem]] a teorií her.

## Aplikace v reálném světě

- **Benzinky** v jednom městě — diferencovaný Bertrand. Lokace, značka a doplňkové služby (myčka, občerstvení) drží ceny mírně nad mezními náklady.
- **Generika po vypršení patentu** — klasický homogenní Bertrand. Po expiraci patentu vstupují na trh generika, cena padá blízko k variabilním nákladům.
- **E-commerce platformy a bot pricing** — algoritmy automaticky podsekávají konkurenta, dokud nedosáhnou minimální marže. Dynamický Bertrand v praxi.
- **Ride-sharing** (Uber vs. Lyft) — diferencovaný Bertrand s **síťovými efekty** (větší platforma → kratší čekací doba → vyšší ochota platit).
- **Aerolinie na konkurenční trase** — krátkodobá cenová válka, dlouhodobě kapacitní (Cournot–Edgeworth).
- **Cloud computing a SaaS** — rychlé cenové reakce, ale silná diferenciace přes ekosystém a integrace.

## Srovnání cenových výsledků v modelech oligopolu

Pro stejnou poptávku $P = a - b Q$ a $MC$:

| Model | Cena | Množství | Zisk |
|-------|------|----------|------|
| [[mikk|Dokonalá konkurence]] | $P = MC$ | maximální | nulový |
| **Bertrand (homogenní)** | $P = MC$ | maximální | nulový |
| [[mikk-oligopol-cournot-stackelberg|Cournot]] | $P > MC$ | střední | kladný |
| [[mikk-oligopol-cenovy-vudce-kartel|Kartel / monopol]] | $P \gg MC$ | nejnižší | maximální |
| Bertrand (diferencovaný) | $P > MC$ | střední | kladný |

Detailní vzorce viz [[mikk-vzorce-prehled|Přehled vzorců mikk]].

## Kontrolní otázky

1. Proč je v Bertrandově modelu s homogenním produktem zisk nulový, přestože jsou na trhu jen dvě firmy?
2. Co se stane, pokud má jedna firma nižší $MC$ než druhá? Jak se výsledek změní oproti symetrickému případu?
3. Jak diferenciace produktu mění Bertrandovu rovnováhu?
4. Proč Kreps–Scheinkmanův výsledek smiřuje Bertranda a Cournota? Jakou roli hraje volba kapacity?
5. Vysvětlete, proč Bertrandův paradox neplatí při kapacitních omezeních (Bertrand–Edgeworth).
6. V jakých reálných odvětvích lépe popisuje data Bertrand a v jakých Cournot? Uveďte alespoň jeden příklad pro každý.
7. Kdyby v Předtermínu B byly na trhu dvě homogenní firmy soutěžící Bertrandovsky, jaká by byla rovnovážná cena a zisk?

## Související stránky

- [[mikk|Mikroekonomie 2 (mikK)]] — kurzová hubová stránka.
- [[mikk-oligopol-cournot-stackelberg]] — Cournotův a Stackelbergův model (množstevní konkurence).
- [[mikk-oligopol-cenovy-vudce-kartel]] — model cenového vůdce a koluze / kartel.
- [[mikk-oligopol-zalomena-poptavka]] — Sweezyho zalomená poptávková křivka, rigidita cen.
- [[mikk-vezno-dilema-teorie-her|Vězňovo dilema]] — teoreticko-herní rámec pro koluzi a opakovaný Bertrand.
- [[mikk-monopolisticka-konkurence]] — diferenciace produktu v širším kontextu.
- [[mikk-srovnani-modelu-oligopolu]] — souhrnné srovnání všech modelů.
- [[mikk-vzorce-prehled]] — přehled klíčových vzorců.
- [[mikk-vzorove-zkousky]] — vzorové zkouškové úlohy (včetně Předtermínu B).
