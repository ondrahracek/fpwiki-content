---
title: "Oligopol — model cenového vůdce a kartely"
course: mikk
type: topic
tags: [mikk, mikroekonomie, oligopol, kartel, cenovy-vudce, opec, koluze]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Oligopol — model cenového vůdce a kartely

## TL;DR

**Model dominantní firmy** popisuje oligopolní trh, kde jeden velký hráč drží rozhodující tržní podíl a kolem něj operuje **konkurenční lem** (fringe) drobných firem. Dominantní firma stanovuje cenu na základě **zbytkové poptávky** $D_D = D - S_F$ a maximalizuje zisk přes $MR_D = MC_D$; lem cenu **bere jako given** a chová se jako dokonalá konkurence.

**Barometrická firma** je proměnlivý cenový vůdce, který reaguje jako první na tržní změny a plní pro ostatní funkci „barometru" tržních podmínek. Vzniká často jako reakce na bezohlednou konkurenci a fluktuaci cen.

**Kartel** = explicitní dohoda firem o ceně a/nebo výstupu. Úspěch závisí na (i) **neelastické tržní poptávce**, (ii) **neelastické nabídce lemu**, (iii) **vnitřní soudržnosti** s mechanismem postihu za podvádění a (iv) kontrole rozhodující části zdrojů. **OPEC** je úspěšný (ropa má málo substitutů, lem ne-OPEC reaguje pomalu); **CIPEC** (měď) selhal, protože poptávka i nabídka substitutů (hliník, železo) jsou elastické.

---

## 1. Model s dominantní firmou

### 1.1 Předpoklady

Model dominantní firmy (dominant-firm model) je zjednodušený model oligopolu, který kombinuje **monopolní chování velkého hráče** s **chováním lemu jako v dokonalé konkurenci**. Předpoklady jsou:

1. **Jedna velká firma** s rozhodujícím tržním podílem (typicky 40–80 %).
2. **Mnoho malých firem** dohromady tvořících **konkurenční lem** (fringe firms). Každá z nich je sama o sobě cenovým příjemcem.
3. **Zboží téměř homogenní** — diferenciace je malá, kupující rozhoduje hlavně podle ceny.
4. **Asymetrie informací a nákladů** — dominantní firma má typicky nižší $MC$ (úspory z rozsahu, lepší technologie, kapitálová převaha).
5. **Volný vstup do lemu** — drobné firmy mohou vstoupit, ale nikdy nedosáhnou rozsahu dominantní firmy.

> [!note] Klíčový rozdíl od monopolu
> Dominantní firma **není** monopol — nedrží 100 % trhu. Kolem ní existuje konkurenční lem, který reaguje na cenu. Proto poptávka, které dominantní firma čelí, **není totožná** s tržní poptávkou.

### 1.2 Geometrické odvození zbytkové poptávky

![[mikk-cenovy-vudce-dominantni-firma.jpeg|Model cenového vůdce s konkurenčním lemem — odvození reziduální poptávky D_D = D_T − S_F a optima dominantní firmy]]

Postup konstrukce poptávky dominantní firmy:

1. **Tržní poptávka $D$** — celková poptávka po produktu na trhu.
2. **Nabídka konkurenčního lemu $S_F$** — horizontální součet $MC_i$ křivek malých firem nad jejich AVC. Lem se chová jako dokonale konkurenční odvětví: při ceně $P$ vyrobí $Q_F(P)$ tak, aby $P = MC_i$.
3. **Zbytková poptávka $D_D$** — pro každou cenu $P$:

$$
D_D(P) = D(P) - S_F(P)
$$

To je množství, které **zbude** dominantní firmě poté, co lem prodá své množství při dané ceně.

> [!important] Vlastnosti $D_D$
> - Při ceně, kdy $S_F = D$ (lem pokryje celý trh), platí $D_D = 0$ — dominantní firma vůbec neprodá.
> - Při velmi nízké ceně (kdy lem nedodává nic, $S_F = 0$) platí $D_D = D$ — dominantní firma má celou poptávku pro sebe.
> - $D_D$ je obecně **strmější** (méně elastická?) NE — naopak typicky **elastičtější** než $D$, protože lem nahradí část objemu, pokud dominantní firma zvedne cenu. To je důležitý detail.

### 1.3 Maximalizace zisku dominantní firmy

Dominantní firma se chová jako monopol vůči své zbytkové poptávce $D_D$:

1. Z $D_D$ odvodí **mezní příjem** $MR_D$ (klesá rychleji než $D_D$, stejné pravidlo dvojnásobného sklonu u lineární poptávky).
2. Optimum: $MR_D = MC_D$ → optimální množství $Q_D$.
3. Cena $P^*$ se odečte z $D_D$ při množství $Q_D$.

Při ceně $P^*$:
- **Lem** prodává $Q_F = S_F(P^*)$ (vyplývá z $S_F$).
- **Dominantní firma** prodává $Q_D$.
- **Celkový tržní výstup** je $Q_T = Q_D + Q_F$, ležící na $D$ při ceně $P^*$.

> [!example] Numerický příklad
> Tržní poptávka $D: P = 100 - Q$. Nabídka lemu $S_F: P = 20 + 0{,}5 Q_F$ (tedy $Q_F = 2P - 40$). Náklady dominantní firmy $MC_D = 10 + Q_D$.
>
> 1. $D_D: Q_D = D - Q_F = (100 - P) - (2P - 40) = 140 - 3P$, tedy $P = (140 - Q_D)/3$.
> 2. $MR_D = (140 - 2Q_D)/3$.
> 3. Z $MR_D = MC_D$: $(140 - 2Q_D)/3 = 10 + Q_D$ → $140 - 2Q_D = 30 + 3Q_D$ → $Q_D = 22$.
> 4. $P^* = (140 - 22)/3 \approx 39{,}3$.
> 5. $Q_F = 2 \cdot 39{,}3 - 40 \approx 38{,}7$, $Q_T \approx 60{,}7$.

### 1.4 Implikace modelu

- Dominantní firma má **menší tržní moc** než monopolista — lem reaguje na cenu a může absorbovat poptávku.
- Existence lemu **omezuje cenu** dominantní firmy: pokud by zvedla cenu příliš, lem rozšíří produkci a sníží $D_D$.
- Lem typicky **vydělá více na jednotku** (operuje při vyšším $MC$, ale za stejnou cenu $P^*$), kdežto dominantní firma vydělá více **v absolutních číslech** kvůli rozsahu.

---

## 2. Strategie dominantní firmy vůči lemu

Dominantní firma si může cíleně volit cenovou strategii podle dlouhodobých záměrů.

### 2.1 Limit pricing

**Limit pricing** = záměrně nízká cena, která **odradí vstup nových firem** do lemu nebo nutí stávající firmy odejít. Cena leží pod ziskově maximalizační úrovní, ale stále nad $MC_D$. Logika: vstupující firma s vyššími náklady by při této ceně neuhájila pozitivní zisk.

### 2.2 Predatory pricing

**Predatory pricing** = cena dočasně **pod úrovní MC** (nebo i AVC) s cílem **vytlačit lem**. Po jeho odchodu dominantní firma cenu zvýší a vybere monopolní zisk.

> [!warning] Právní aspekt
> Predatory pricing je ve většině jurisdikcí **nezákonný** — porušuje antimonopolní právo (USA: Sherman Act §2; EU: článek 102 SFEU; ČR: §11 zákona 143/2001 Sb.). Důkazní břemeno je ale obtížné — žalobce musí prokázat (a) cenu pod nákladem a (b) pravděpodobnost pozdějšího "recoupment" zisku.

### 2.3 Price umbrella

**Price umbrella** = dominantní firma cenu **úmyslně udržuje vysoko** tak, aby lem mohl přežívat. Důvody:
- vyhnutí se obvinění z monopolu,
- zachování obrazu „konkurenčního trhu",
- udržení odběratelské základny pro celé odvětví.

Nevýhoda: lem se může postupně rozrůstat a převzít část tržního podílu.

### 2.4 Reálné příklady

- **Saudi Arabia v OPEC** — největší producent, často jednostranně tlumí těžbu (cenový umbrella) nebo naopak zvyšuje (price war proti shale).
- **Walmart v US retailu** — limit pricing v menších městech, kde vytlačí lokální obchody.
- **Microsoft Office v 90. letech** — Office tvořil cenový strop, IBM Lotus a Corel WordPerfect žily jako lem, ale postupně byly zatlačeny.
- **De Beers v diamantech** — historicky kontroloval ~80 % trhu, dnes ~30 % (ztratil dominanci, viz kapitola 8).

---

## 3. Model s barometrickou firmou

### 3.1 Charakteristika

**Barometrická firma** (barometric price leader) je **proměnlivý cenový vůdce**. Na rozdíl od dominantní firmy:

- Nemá rozhodující tržní podíl.
- Nemá nutně nejnižší náklady.
- Mění se v čase — různé firmy v různých obdobích.

Barometrická firma **uskutečňuje cenové změny jako první** a plní pro ostatní firmy úlohu **barometru tržních podmínek**. Ostatní firmy ji následují, **pokud její strategie odráží podmínky společné celému odvětví**.

### 3.2 Vznik barometrického vůdcovství

Empirické studie ukazují, že barometrické vůdcovství vzniká jako reakce na:

- **Značnou fluktuaci cen** — firmy jsou unaveny chaosem a hledají referenční bod.
- **Bezohlednou konkurenci** s velkými ztrátami — potřeba **stabilizace** odvětví.
- **Nejistotu o tržních podmínkách** — barometr přebírá náklady na sběr informací.

### 3.3 Rozdíl oproti dominantní firmě

| Aspekt | Dominantní firma | Barometrická firma |
|--------|------------------|--------------------|
| Tržní podíl | Velký (40–80 %) | Variabilní, střední |
| Náklady | Typicky nejnižší | Nejsou nutně nejnižší |
| Stabilita vůdce | Stabilní v čase | Mění se |
| Mechanismus | Cílí $MR_D = MC_D$ | Reaguje na podmínky a signalizuje |
| Reálné příklady | Saudi Arabia, Walmart | US Steel (historicky), banky v ČR po 2020 |

> [!tip] Klíč k rozlišení
> Dominantní firma **stanovuje cenu z vlastní pozice síly**. Barometrická firma **odhaduje, kam se trh hýbe, a vede ostatní k novému rovnovážnému bodu**. V praxi jde často o tichou koluzi — viz kapitola 9.

---

## 4. Kartel — definice a charakteristika

### 4.1 Definice

**Kartel** je **zřejmá (explicitní) dohoda firem** o:
- **výstupu** (kvótě produkce každého člena),
- **ceně** (minimální či cílové),
- **nebo obojím**.

Charakteristické znaky:

1. **Zřejmá dohoda** — písemná či ústní, ale prokazatelná. Liší se od tiché koluze (kapitola 9).
2. **Nemusí zahrnovat všechny firmy** v odvětví — typicky existuje **konkurenční lem nečlenů**.
3. **Velmi často mezinárodní** — vyhne se národní antimonopolní legislativě (např. OPEC operuje mimo americký Sherman Act).

### 4.2 Podmínky úspěchu kartelu

Podmínky úspěchu:

1. **Síla zabraňující podvádění** — mechanismus enforcement (postih za porušení kvóty). Bez něj má každý člen motivaci vyrobit nad kvótu a vydělat na vyšší ceně.
2. **Aspoň částečná monopolní síla** — **neelastická tržní poptávka**. Pokud poptávka silně reaguje na cenu, zvýšení ceny kartelem vede k velké ztrátě objemu.
3. **Kontrola rozhodující části zdrojů** ovlivňujících nabídku — kartel musí pokrýt téměř celé odvětví, jinak lem vyplní mezeru.
4. **Neelastická nabídka nekartelových firem** (lemu) — pokud lem rychle reaguje na vyšší cenu zvýšenou produkcí, kartel ztrácí podíl.
5. **Stabilní složení členů** — častá fluktuace členství zvyšuje koordinační náklady.
6. **Nízké koordinační náklady** — geograficky blízké firmy, podobná struktura nákladů.

> [!warning] Pozor — častý překlep
> Některé prameny uvádějí, že „celková poptávka musí být velmi cenově **elastická**" — jde o chybu. Správně musí být **neelastická**. Neelastická poptávka znamená, že kartel zvedne cenu, aniž by ztratil mnoho zákazníků — to je samotný princip monopolní síly.

---

## 5. Úspěšné a neúspěšné kartely

### 5.1 Příklady úspěšných kartelů

| Kartel | Komodita | Aktivní | Klíč úspěchu |
|--------|----------|---------|--------------|
| **OPEC** | ropa | 1960– | nízká elasticita poptávky, rozhodující podíl |
| **International Bauxite Association** | bauxit | 1974–1994 | omezený zdroj, vysoká koncentrace |
| **Mercurio Europeo** | rtuť | historicky | omezené světové zdroje |
| **De Beers** | diamanty | 1888–~2000 | kontrola těžby + marketing |
| **OPEC+** | ropa (rozšíření) | 2016– | OPEC + Rusko a další |

### 5.2 Příklady neúspěšných kartelů

| Pokus o kartel | Komodita | Důvod selhání |
|----------------|----------|---------------|
| **CIPEC** | měď | substituty (hliník, ocel), elastická poptávka |
| Cín | cín | rozpad ITC v 1985 |
| Káva | káva | mnoho zemí, nemožnost kontroly nabídky |
| Čaj | čaj | různé regiony, rozdílná kvalita |
| Kakao | kakao | volatilní úroda, nelze koordinovat |

**Příčina rozdílu**: u úspěšných kartelů je **tržní poptávka neelastická** a **konkurenční lem slabý**; u neúspěšných je obojí silně elastické.

---

## 6. OPEC — analýza úspěšného kartelu

### 6.1 Pozadí

**OPEC** = Organization of the Petroleum Exporting Countries, založen 1960 v Bagdádu. Zakládající členové: Írán, Irák, Kuvajt, Saudská Arábie, Venezuela. Dnes ~13 členů.

OPEC kontroluje cca **40 % světové produkce ropy** a **70 % prokázaných rezerv**. Není ovšem monopolista — existuje rozsáhlý **lem ne-OPEC** (USA shale, Norsko, Kanada, Brazílie, Rusko před OPEC+).

### 6.2 Geometrická konstrukce

OPEC se modeluje **přesně jako dominantní firma**:

1. **Tržní poptávka po ropě $TD$** — světová poptávka, **velmi neelastická** v krátkodobu (ropa nemá v dopravě rychlé substituty).
2. **Nabídka konkurenčního lemu $S_C$** — ne-OPEC produkce, **neelastická v krátkodobu** (těžební infrastruktura má dlouhou návratnost).
3. **Poptávka po OPEC ropě $D_{OPEC} = TD - S_C$** — relativně elastičtější než $TD$, ale stále s prostorem pro tržní moc.
4. **$MC_{OPEC}$ velmi nízké** — Saudi Arabia má těžební náklady ~10 USD/barel, někteří členové (Venezuela) dražší.
5. Optimum: $MR_{OPEC} = MC_{OPEC}$ → $Q_{OPEC}$, cena $P^*$.

### 6.3 Srovnání s konkurenční cenou

**Konkurenční cena** $P_C$ by nastala, kdyby OPEC nekoordinoval a každá země vyráběla podle vlastního $MC$:

$$
P_C \text{ tam, kde } D_{OPEC} = MC_{OPEC}
$$

OPEC dokáže udržet $P^* \gg P_C$, **protože $TD$ je málo elastická** — zvýšení ceny nezpůsobí dramatický pokles spotřeby.

### 6.4 Historické cenové epizody

- **1973** — embargo proti USA, cena ropy 4× za rok.
- **1979–1980** — íránská revoluce, cena ropy z 14 na 35 USD/barel.
- **1986** — Saudská Arábie zvedla těžbu („price war"), cena spadla z 27 na 10 USD.
- **2008** — vrchol 147 USD/barel, pak finanční krize a propad pod 40.
- **2014–2016** — Saudi vs. shale: OPEC nesnížil těžbu, cena z 110 na 30 USD; cílem bylo vytlačit americký shale (částečně se podařilo, mnoho firem zkrachovalo).
- **2020 (COVID)** — krátkodobě záporná cena WTI futures.
- **2022** — invaze na Ukrajinu, sankce na ruskou ropu, cena 120+ USD.

> [!note] OPEC+ od 2016
> Po krizi 2014–2016 OPEC rozšířil koordinaci o **ne-OPEC** producenty, hlavně **Rusko**. Tím se kartel stal silnějším — pokrývá ~50 % světové produkce.

---

## 7. CIPEC — analýza neúspěšného kartelu

### 7.1 Pozadí

**CIPEC** = Conseil Intergouvernemental des Pays Exportateurs de Cuivre (Mezivládní rada zemí vyvážejících měď), založen 1967. Členové: Chile, Peru, Zair (DRC), Zambie. Pokus o „měďový OPEC".

### 7.2 Proč selhal

Geometrická analýza odhalí příčinu:

1. **Tržní poptávka po mědi $TD$ je elastická** — měď má **substituty**:
   - **Hliník** v elektrickém vedení a kabeláži.
   - **Železo a ocel** v konstrukci.
   - **Optická vlákna** v telekomunikacích (od 80. let).
2. **Nabídka lemu $S_C$ elastická** — produkce mimo CIPEC (USA, Kanada, Austrálie) reaguje na cenu rychle.
3. **$D_{CIPEC} = TD - S_C$ je velmi elastická**.
4. CIPEC tudíž **má malou monopolní sílu**: $P^* \approx P_C$.

### 7.3 Závěr

**CIPEC fakticky nedokázal udržet cenu nad konkurenční úrovní.** Dohoda existovala formálně, ale ekonomické podmínky pro úspěch nebyly splněny. CIPEC formálně existoval do roku 1992, kdy byl rozpuštěn.

> [!important] Univerzální poučení
> Úspěch kartelu **není volbou** — je to důsledek **strukturálních vlastností trhu**: elasticit poptávky a lemu. Žádná dohoda neudrží cenu, pokud trh „chce" konkurenční rovnováhu.

---

## 8. Vnitřní problém kartelu — podvádění

### 8.1 Pobídka k porušení dohody

Jednotlivá firma má **silnou motivaci** porušit kartelovou kvótu:

- Při kartelové ceně $P^* > MC_i$ je vyrábět víc **velmi výnosné**.
- Pokud podvádí jen jedna firma (a ostatní drží kvóty), cena se prakticky nezmění.
- Jakmile ale podvádí **mnoho firem současně**, nabídka prudce roste a cena padá ke konkurenční úrovni.

To je klasické **vězňovo dilema** v opakované hře — viz [[mikk-vezno-dilema-teorie-her]].

### 8.2 Mechanismy enforcement

Aby kartel přežil, musí mít systém:

1. **Kvóty produkce** — explicitní limit pro každého člena.
2. **Monitoring** — sledování skutečné produkce (satelitní snímky terminálů, exportní statistiky).
3. **Postihy** — sankce za překročení kvóty (snížení budoucí kvóty, vyloučení).
4. **Tit-for-tat strategie** — pokud jeden poruší, ostatní dočasně také vyrábějí nad kvótu, dokud se viník nevrátí.

### 8.3 Reálné případy podvádění

- **OPEC v 80. letech** — Saudi Arabia opakovaně tolerovala překračování kvót; v 1985 ztratila trpělivost a sama zaplavila trh (cenový propad 1986).
- **Vitamíny (Roche, BASF, Aventis)** — globální kartel 1990–1999, pravidelná setkání, ale Roche přesto podváděla na některých substancích.

---

## 9. Tichá koluze (tacit collusion)

### 9.1 Definice

**Tichá koluze** = firmy **bez explicitní dohody** koordinují cenové chování pouhým **sledováním a napodobováním**. Není to kartel, protože chybí prokazatelná komunikace.

### 9.2 Mechanismy

- **Cenový vůdce signalizuje změnu**, ostatní následují.
- **Veřejné cenové oznámení** (v energetice, telekomunikacích).
- **Repeated game equilibria** — firmy implicitně rozumí, že porušení vyvolá odvetu.

### 9.3 Příklady

- **Telekomunikace v ČR** — 3 operátoři (T-Mobile, O2, Vodafone), ceny tarifů velmi podobné, žádná prokazatelná dohoda.
- **Letecké linky** na konkurenčních trasách — dynamic pricing často konverguje k podobným hladinám.
- **Benzínové pumpy** — synchronizované týdenní cenové cykly v Kanadě, Austrálii.

> [!warning] Právní hranice
> Tichá koluze je **obtížně postihovatelná**, protože antimonopolní právo typicky vyžaduje důkaz dohody. ÚOHS i Evropská komise se snaží postihovat „concerted practice" (jednání ve shodě), ale důkazní břemeno je vysoké.

---

## 10. Antitrust legislativa a sankce

### 10.1 USA

- **Sherman Antitrust Act (1890)** — §1 zakazuje „every contract, combination, or conspiracy in restraint of trade", §2 zakazuje monopolizaci.
- **Clayton Act (1914)** — doplňuje fúze a cenovou diskriminaci.
- **Sankce**: pokuty do 100 mil. USD pro firmy, 1 mil. USD a 10 let vězení pro jednotlivce. **Treble damages** v civilních žalobách.

### 10.2 EU

- **Článek 101 SFEU** — zákaz dohod narušujících soutěž.
- **Článek 102 SFEU** — zákaz zneužití dominantního postavení.
- **Sankce**: pokuty až **10 % celosvětového obratu**. Rekord: Google (2018, 4,34 mld. €).

### 10.3 ČR

- **Zákon č. 143/2001 Sb.** o ochraně hospodářské soutěže.
- **§3** zákaz kartelových dohod, **§11** zákaz zneužití dominance.
- **ÚOHS** (Úřad pro ochranu hospodářské soutěže) — pokuty do 10 % obratu.
- Trestní postih dle §248 trestního zákoníku (porušení předpisů o pravidlech hospodářské soutěže).

### 10.4 Leniency programs

**Program shovívavosti** = první firma, která sama oznámí kartel a poskytne důkazy, dostane **úplné prominutí pokuty**. Druhá ~50 % slevu, třetí ~30 %.

Mechanismus rozkládá kartely zevnitř — vytváří **závod kdo dřív zradí**.

---

## 11. Slavné kartelové kauzy

### 11.1 Vitaminový kartel (1990–1999)

Globální kartel výrobců vitaminů (Roche, BASF, Aventis, Takeda). Pravidelná tajná setkání, kvóty, ceny. Odhalen v 1999. Sankce: **EU 855 mil. €**, **USA ~1 mld. USD**, pokuty pro vrcholné manažery.

### 11.2 LIBOR (2007–2012)

Banky (Barclays, UBS, Deutsche Bank, RBS) manipulovaly **LIBOR** (London Interbank Offered Rate) — referenční úrokovou sazbu. Zaměstnanci si posílali zprávy s žádostmi o úpravu kotací. Sankce: ~9 mld. USD globálně.

### 11.3 Auto-component kartely (EU)

Sériové kartely výrobců součástek pro auta v EU 2010–2020:
- **Ložiska** (NSK, NTN, JTEKT, SKF) — pokuta 953 mil. €.
- **Bezpečnostní pásy a airbagy** (Takata, TRW) — 368 mil. €.
- **Zapalovací svíčky** (Bosch, Denso, NGK) — 76 mil. €.

### 11.4 Generické léky (USA, 2010s)

Kartel výrobců generik (Mylan, Teva, Sandoz) — koordinace cen léků na hypertenzi, cholesterol. DOJ vznesl trestní obvinění; pokuty miliardy USD.

### 11.5 ČR — pohonné hmoty

ÚOHS opakovaně sankcionoval čerpací stanice za jednání ve shodě (synchronizované zvýšení cen). Poslední velký případ 2018: pokuta ~80 mil. Kč.

---

## 12. Aplikace v reálném světě

### 12.1 Aktuální kartely a koluzní podezření

- **OPEC+** — formální kartel, právně chráněný (suverenita států, mimo Sherman Act).
- **Námořní kontejnerová doprava** — aliance (2M, Ocean Alliance, THE Alliance) sdílí kapacitu na linkách. Formálně právně povoleny, ale fakticky koordinují kapacitu.
- **De Beers** — historicky dominantní, dnes diverzifikovaný trh (Rio Tinto, Alrosa, kanadské doly), formální kartel rozpuštěn.
- **Aerolinky na transatlantických linkách** — antitrust immunity pro joint ventures (např. Star Alliance + ATI).

### 12.2 Případy v ČR

- **Pekárny** (2003) — kartel 7 pekáren, pokuta 51 mil. Kč.
- **Stavební společnosti** (2014) — bid rigging na dálničních zakázkách.
- **Distributoři léků** (2019) — koordinace marží.

---

## 13. Shrnutí — kdy kartel funguje

| Podmínka | Vliv | OPEC | CIPEC |
|----------|------|------|-------|
| Tržní poptávka neelastická | Nutná | ANO (ropa nemá rychlý substitut) | NE (hliník, ocel) |
| Lem nabídky neelastický | Nutná | ANO (krátkodobě) | NE |
| Kontrola zdrojů | Nutná | 40 % produkce, 70 % rezerv | <50 %, snadný vstup |
| Vnitřní soudržnost | Nutná | Saudi enforcement, OPEC+ | Slabá |
| Mezinárodní rámec | Pomáhá | ANO (suverenita) | ANO, ale to nestačilo |
| **Výsledek** | | **Úspěšný** | **Selhání** |

> [!tip] Praktická heuristika
> Když se v médiích mluví o „novém kartelu", zeptej se: (a) **kolik substitutů** má produkt? (b) **jak rychle** může lem zvednout produkci? (c) **má kartel mechanismus enforcement**? Pokud odpověď není „málo / pomalu / silný", kartel je odsouzen ke krátké životnosti.

---

## Související

- [[mikk|Mikroekonomie 2 (mikK)]]
- [[mikk-oligopol-cournot-stackelberg|Cournotův a Stackelbergův model]] — modely množstevní konkurence v oligopolu
- [[mikk-oligopol-bertrand-cenova-konkurence|Bertrandův model — cenová konkurence]]
- [[mikk-oligopol-zalomena-poptavka|Model zalomené poptávky]] — alternativní vysvětlení cenové rigidity
- [[mikk-vezno-dilema-teorie-her|Vězňovo dilema a teorie her]] — formální základ pro analýzu podvádění v kartelu
- [[mikk-monopol-pokrocily|Monopol — pokročilé téma]] — kartel jako kolektivní monopol
- [[mikk-elasticita-poptavky|Elasticita poptávky]] — klíčový faktor úspěchu kartelu
- [[mikk-srovnani-modelu-oligopolu|Srovnání modelů oligopolu]] — přehledová tabulka
- [[mikk-vzorce-prehled|Přehled vzorců Mikroekonomie 2]]
