---
title: "Užitková teorie a preference (pokročilé)"
course: mikk
type: topic
tags: [mikk, mikroekonomie, uzitecnost, preference, mrs, indiferencni-krivky]
sources: [raw/mikk/Prednaska 1. a 2. blok.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Užitková teorie a preference (pokročilé)

> [!abstract] TL;DR
> Při analýze rozhodování spotřebitele používáme **dva paralelní přístupy**: **kardinální teorie užitku** (užitek lze kvantifikovat a sčítat — jednotka *util*) a **ordinální teorie indiference** (užitek lze pouze uspořádat — preferuji X před Y). Úhelným pojmem propojujícím oba přístupy je **MRS** (mezní míra substituce ve spotřebě), která říká, kolik jednotek statku Y je spotřebitel ochoten obětovat za jednu dodatečnou jednotku statku X při zachování stejné úrovně užitku. Indiferenční křivka má **čtyři klíčové vlastnosti**: je klesající, neprotíná se s jinou IC stejného spotřebitele, každým bodem prochází právě jedna a je konvexní vzhledem k počátku. Existují **čtyři typické tvary** preferencí — dokonalé substituty (lineární IC), dokonalé komplementy (L-tvar), neutrální zboží (vertikální nebo horizontální IC) a nežádoucí zboží (rostoucí IC).

Tato stránka rozšiřuje úvod do teorie užitečnosti známý z [[uzitecnost|Užitečnost (ImeK primer)]] o pokročilejší vrstvu typickou pro [[mikk|Mikroekonomii 2]]: formální axiomatiku, odvození MRS přes totální diferenciál, geometrický důkaz neprotínání IC a typologii speciálních preferencí. Navazuje na ni stránka [[mikk-rovnovaha-spotrebitele]], která řeší optimalizační úlohu maximalizace užitku při rozpočtovém omezení, a [[mikk-substitucni-duchodovy-efekt]], kde se pracuje s posuny po IC při změně cen.

## 1. Dva teoretické přístupy

V mikroekonomické literatuře existují **dva komplementární přístupy** k popisu rovnováhy spotřebitele. Oba sdílejí stejný základní předpoklad: spotřebitel je **motivován uspokojovat své potřeby** a současně **omezen disponibilním důchodem** (rozpočtovým omezením).

| Přístup | Předpoklad | Výstup |
|---------|------------|--------|
| **Kardinální (teorie užitku)** | Lidé jsou schopni *kvantifikovat* své preference číslem (užitkem v *utilech*) | Užitková funkce $U(X,Y)$ s konkrétními hodnotami |
| **Ordinální (teorie indiference)** | Lidé jsou schopni pouze *uspořádat* své preference (X je lepší než Y) | Soustava indiferenčních křivek bez absolutních hodnot |

> [!info] Historická poznámka
> Kardinální přístup je starší (W. S. Jevons, A. Marshall — konec 19. století) a v dnešní mikroekonomii slouží spíše jako didaktický most k pochopení mezního užitku. Ordinální přístup (V. Pareto, J. R. Hicks — 20. století) je dominantním rámcem současné teorie spotřebitele, protože nevyžaduje měřitelnost užitku — stačí porovnatelnost.

### Kdy který použít

- **Kardinální teorie** je užitečná, pokud máme **explicitní funkční tvar** užitkové funkce (typicky $U = X^a Y^b$ nebo $U = aX + bY - cX^2 - dY^2$). V tom případě umíme spočítat mezní užitky $MU_X, MU_Y$ a aplikovat podmínku rovnováhy ve tvaru $MU_X / P_X = MU_Y / P_Y$.
- **Ordinální teorie** stačí, když chceme **kvalitativní výsledky** — tvar IC, směr substituce, geometrii rovnováhy. Pracuje s mapou IC, kde *vyšší křivka znamená vyšší užitek*, ale konkrétní hodnota užitku je libovolnou monotónní transformací.

## 2. Axiomy užitku

Aby byly oba přístupy konzistentní, musí preference spotřebitele splňovat **tři základní axiomy** (přijatá tvrzení bez důkazu):

> [!info] Tři axiomy preferencí
> 1. **Úplnost** — spotřebitel umí pro libovolnou dvojici košíků $A, B$ rozhodnout, zda $A \succ B$, $A \prec B$, nebo $A \sim B$. Klasická ilustrace: *osel a seno* — osel mezi dvěma stejně velkými hromadami sena nemůže váhat, jinak hladoví.
> 2. **Tranzitivita** — pokud preferuje $A \succ B$ a $B \succ C$, pak nutně i $A \succ C$. Klasická ilustrace: *párek, hamburger, řízek* — pokud mám raději řízek než hamburger a hamburger než párek, musím mít raději i řízek než párek.
> 3. **Nepřesycení** ("více je lépe", *nonsatiation*) — větší množství zboží přináší vyšší užitek, alespoň lokálně. Tento axiom platí pro běžné statky; nežádoucí zboží (smog, hluk) ho porušuje.

Pokud kterýkoliv z axiomů selže, ztrácíme konzistenci preferencí a mapa indiferenčních křivek se rozpadá. Například při porušení tranzitivity by se mohly **dvě IC protnout** (viz důkaz sporem v sekci 9).

## 3. Mezní užitek

**Mezní užitek** $MU_X$ je dodatečný užitek z jedné další jednotky statku $X$ při zachování spotřeby ostatních statků. Formálně se jedná o **parciální derivaci** užitkové funkce:

$$
MU_X = \frac{\partial U}{\partial X}, \qquad MU_Y = \frac{\partial U}{\partial Y}
$$

### Zákon klesající mezní užitečnosti

> [!tip] Law of diminishing marginal utility
> S rostoucím objemem spotřebovaného zboží **mezní užitek klesá**. První pivo v horku přináší obrovský užitek, druhé už menší, páté může být dokonce nepříjemné.

Matematicky je zákon klesající mezní užitečnosti vyjádřen jako $\frac{\partial^2 U}{\partial X^2} < 0$ (druhá derivace je záporná, funkce je tedy konkávní v $X$). U funkce $U = 10X - 0{,}5X^2$ je například $MU_X = 10 - X$, takže pro $X = 0$ máme $MU_X = 10$, pro $X = 5$ je $MU_X = 5$ a pro $X = 10$ klesá na $MU_X = 0$ — bod nasycení.

### Praktický význam

Klesající mezní užitek je důvod, proč **diverzifikujeme spotřebu**: kdyby byl mezní užitek konstantní, racionální spotřebitel by utratil veškerý důchod za jediný statek. Klesající $MU$ vytváří motivaci kombinovat různé statky tak, aby se mezní užitky vyrovnaly přes všechny směry spotřeby — a právě to vede k podmínce rovnováhy v sekci 4.

### Historický kontext — Gossenův první zákon

Zákon klesající mezní užitečnosti je v ekonomické literatuře označován také jako **Gossenův první zákon** (Hermann Heinrich Gossen, 1854, *Entwicklung der Gesetze des menschlichen Verkehrs*). Gossen formuloval tři základní zákony hedonistické psychologie spotřeby:

1. **Gossenův 1. zákon** — zákon klesající mezní užitečnosti, jak je popsán výše.
2. **Gossenův 2. zákon** — zákon rovnosti vážených mezních užitků (vyrovnání $MU/P$ napříč statky), který je přímo podmínkou rovnováhy ze sekce 4.
3. **Gossenův 3. zákon** — výrobek má hodnotu pouze tehdy, je-li jeho dostupné množství menší než množství, při kterém by byl spotřebitel nasycen (motivace ekonomické směny).

Gossenovo dílo bylo dlouho přehlíženo a oceněno až v 70. letech 19. století během tzv. **marginalistické revoluce** (Jevons, Menger, Walras), která teorii mezního užitku převzala a formálně rozpracovala. Marshallovo *Principles of Economics* (1890) tyto myšlenky integrovalo do mainstreamu.

### Proč je $MU$ kladná, ale klesající

V rámci axiomu nepřesycení musí být $MU > 0$ (více je lépe). Současně klesající $MU$ znamená, že **přírůstek užitku se stále zmenšuje**, ale nikdy nedosáhne nuly (před bodem nasycení). Matematicky: $\frac{\partial U}{\partial X} > 0$ a $\frac{\partial^2 U}{\partial X^2} < 0$. Funkce s touto kombinací vlastností se nazývá **rostoucí konkávní** — typickým představitelem jsou logaritmické (např. $U = \ln X$), odmocninové ($U = \sqrt{X}$) nebo mocninné funkce s exponentem $0 < a < 1$ ($U = X^a$).

## 4. Rovnováha při dvou statcích — kardinální verze

Hlavní výsledek kardinální teorie říká, že v optimu spotřebitel rozdělí svůj rozpočet tak, aby **vážený mezní užitek na korunu byl stejný napříč všemi statky**:

$$
\boxed{\;\frac{MU_X}{P_X} = \frac{MU_Y}{P_Y}\;}
$$

> [!example] Intuice "poslední koruny"
> Podmínka znamená, že **poslední koruna utracená za X přináší stejný užitek jako poslední koruna utracená za Y**. Pokud by tomu tak nebylo — řekněme $\frac{MU_X}{P_X} > \frac{MU_Y}{P_Y}$ — pak by spotřebitel získal víc užitku přesunem koruny z Y na X. Při přesunu by ovšem $MU_X$ klesal (zákon klesající mezní užitečnosti) a $MU_Y$ rostl, takže by se nerovnost postupně vyrovnala.

### Zobecnění na $n$ statků

Pro $n$ statků se podmínka rovnováhy zobecňuje na soustavu rovnic:

$$
\frac{MU_1}{P_1} = \frac{MU_2}{P_2} = \dots = \frac{MU_n}{P_n} = \lambda
$$

kde $\lambda$ je **mezní užitek důchodu** (kolik dodatečného užitku přinese jedna dodatečná koruna příjmu). Tento výsledek získáme přímo Lagrangeovou metodou (viz [[mikk-rovnovaha-spotrebitele]]) — je to standardní podmínka prvního řádu pro maximalizaci $U(X,Y)$ při omezení $P_X X + P_Y Y = I$.

### Numerický příklad

Mějme spotřebitele s $U = 2X + 3Y - 0{,}1 X^2 - 0{,}1 Y^2$, ceny $P_X = 4$, $P_Y = 6$ a důchod $I = 100$.

Mezní užitky:
$$MU_X = 2 - 0{,}2 X, \qquad MU_Y = 3 - 0{,}2 Y$$

Podmínka rovnováhy $MU_X / P_X = MU_Y / P_Y$:
$$\frac{2 - 0{,}2 X}{4} = \frac{3 - 0{,}2 Y}{6}$$

Po roznásobení: $6(2 - 0{,}2X) = 4(3 - 0{,}2Y)$, tedy $12 - 1{,}2X = 12 - 0{,}8Y$, odkud $1{,}2X = 0{,}8Y$, tedy $Y = 1{,}5 X$.

Dosazení do rozpočtového omezení $4X + 6Y = 100$:
$$4X + 6 \cdot 1{,}5X = 4X + 9X = 13X = 100 \;\Rightarrow\; X^* \approx 7{,}69$$
$$Y^* = 1{,}5 \cdot 7{,}69 \approx 11{,}54$$

Optimum tedy leží v bodě $(X^*, Y^*) \approx (7{,}69; 11{,}54)$.

## 5. Mezní míra substituce ve spotřebě (MRS)

**MRS** (Marginal Rate of Substitution in Consumption, $MRS_C$) je poměr, v němž je spotřebitel ochoten **nahrazovat jeden statek druhým**, aniž by se měnil celkový užitek. Geometricky je to **záporná směrnice indiferenční křivky** v daném bodě.

### Odvození z totálního diferenciálu

Vyjdeme z užitkové funkce $U = U(X, Y)$ a vytvoříme její **totální diferenciál**:

$$
dU = \frac{\partial U}{\partial X}\, dX + \frac{\partial U}{\partial Y}\, dY = MU_X\, dX + MU_Y\, dY
$$

Pohyb po jediné indiferenční křivce znamená, že se **užitek nemění**, tedy $dU = 0$:

$$
MU_X\, dX + MU_Y\, dY = 0
$$

Z toho po úpravě:

$$
\boxed{\;MRS_C = -\frac{dY}{dX}\Big|_{U=\text{konst.}} = \frac{MU_X}{MU_Y}\;}
$$

> [!info] Znaménková konvence
> Záporné znaménko $-dY/dX$ kompenzuje fakt, že IC je **klesající** (negativní směrnice), takže $MRS_C$ vyjde **kladně** jako absolutní hodnota poměru. V některých učebnicích se MRS uvádí přímo se záporným znaménkem; v této wiki používáme kladnou konvenci, která je u zkoušky standardní.

### Zákon klesající MRS

Při pohybu po IC zleva doprava (více X, méně Y) **klesá mezní míra substituce**: čím víc X už máme, tím méně Y jsme ochotni za další jednotku X obětovat. Tato vlastnost je matematickým důsledkem **konvexity IC** vzhledem k počátku a empiricky odpovídá tomu, jak se spotřebitelé skutečně chovají — touha po pestrosti spotřeby.

## 6. Indiferenční křivka

![[mikk-mapa-ic-axiomy.jpeg|Mapa indiferenčních křivek a axiomy preferencí (úplnost, tranzitivita, reflexivita, konvexnost)]]

> [!abstract] Definice
> **Indiferenční křivka** (IC) je množina všech kombinací statků $X$ a $Y$, které spotřebiteli přinášejí *stejný celkový užitek*. Mezi libovolnými dvěma body téže IC je spotřebitel **indiferentní** — ani jeden není pro něj lepší ani horší než druhý.

Definice tří souvisejících pojmů:

- **Preference** — konstatování spotřebitele, že některý statek je pro něj **důležitější** než jiný statek.
- **Uspořádání preferencí** — pořadí všech možných kombinací spotřeby vytvořené podle toho, jak jim spotřebitel dává přednost. Předpokládáme, že to **lze udělat** (axiom úplnosti + tranzitivity).
- **Indiference** — výrok spotřebitele, že statek X pro něj není ani lepší, ani horší než statek Y.

### Logika konstrukce IC

Konstrukce IC vychází z **tabulky kombinací**: pro daný užitek $U_0$ vyjmenujeme všechny dvojice $(X, Y)$ takové, že $U(X, Y) = U_0$. Tyto body propojíme spojitou křivkou v rovině X-Y. Pro vyšší úroveň užitku $U_1 > U_0$ leží IC výše a vpravo od původní (axiom nepřesycení).

### Mapa indiferenčních křivek

Soustava IC pro různé úrovně užitku se nazývá **mapa indiferenčních křivek**. V kardinální teorii nesou IC konkrétní čísla (např. $U_0 = 100$ utilů, $U_1 = 200$ utilů); v ordinální teorii pouze **pořadí** (vyšší křivka = vyšší užitek), ale konkrétní hodnoty jsou irelevantní.

## 7. Srovnání ordinálního a kardinálního přístupu

> [!info] Klíčový rozdíl
> **Kardinální teorie** říká, *o kolik* je $U_1 > U_0$ (např. $U_1 - U_0 = 80$ utilů). **Ordinální teorie** říká pouze *že* $U_1 > U_0$, bez kvantifikace rozdílu.

| Vlastnost | Kardinální | Ordinální |
|-----------|------------|-----------|
| Měřitelnost užitku | ano (utily) | ne |
| Sčítání užitků různých lidí | (teoreticky) ano | ne |
| Užitkové funkce ekvivalentní | jen ty, které liší o aditivní/multiplikativní konstantu | libovolná **monotónní transformace** |
| Praktický nástroj | $MU/P$ pravidlo | mapa IC |
| Empirické testování | obtížné (užitek nepozorovatelný) | snadné (preference odhalené) |

### Pareto-Hicksova revoluce

Přechod od kardinálního k ordinálnímu pojetí byl klíčovou změnou mikroekonomie 20. století. Ukázalo se, že pro odvození všech standardních výsledků (poptávková funkce, Slutského rozklad, viz [[mikk-substitucni-duchodovy-efekt]]) **stačí ordinální užitek**, takže silnější kardinální předpoklad není nutný a empiricky je nepodložený.

## 8. Čtyři vlastnosti indiferenčních křivek

Čtyři klíčové vlastnosti IC:

> [!tip] Vlastnosti IC
> 1. **Klesající** (negativní směrnice) — důsledek **nepřesycení**
> 2. **Neprotínají se** — důsledek **tranzitivity**
> 3. V každém bodě prostoru spotřeby prochází **právě jedna IC** — důsledek **úplnosti**
> 4. **Konvexní vzhledem k počátku** — důsledek **zákona klesající MRS**; toto **není** podmínka racionality, ale popisuje chování *většiny* spotřebitelů

Probereme je jednu po druhé:

### 8.1 Klesající směrnice

Pokud spotřebitel získá více $X$, musí dostat **méně $Y$**, aby zůstal na stejné úrovni užitku. V opačném případě (kdyby IC stoupala) by větší kombinace $(X,Y)$ ležela na stejném užitku jako menší — což odporuje nepřesycení ("více je lépe"). IC je tedy klesající **wherever** platí nepřesycení; výjimkou jsou nežádoucí statky a neutrální zboží (viz sekce 11).

### 8.2 Nikdy se neprotínají

Pokud by se dvě IC téhož spotřebitele protnuly, došlo by ke **sporu s tranzitivitou** (viz důkaz sporem v sekci 9).

### 8.3 Každým bodem prochází právě jedna IC

Tato vlastnost je důsledkem axiomu úplnosti: spotřebitel umí každou kombinaci $(X,Y)$ srovnat se všemi ostatními, takže každý bod má svůj jednoznačný **užitek**, a tudíž leží na právě jedné IC.

### 8.4 Konvexita vzhledem k počátku

IC je konvexní = nezakřivená "ven" od počátku, ale "dovnitř". Geometricky to znamená, že **průměry kombinací jsou preferovány před extrémy**: je-li spotřebitel indiferentní mezi $A = (10, 2)$ a $B = (2, 10)$, pak průměr $C = (6, 6)$ leží na **vyšší** IC než A a B.

> [!info] Konvexita ≠ racionalita
> Skutečnost, že IC jsou **konvexní**, není podmínkou racionálního chování. Existují výjimečné spotřebitelé s konkávními IC (extrémně preferují jeden statek před diverzifikací) — model jim však *nezakazuje* být racionální. Konvexita je **empirická generalizace** chování běžných spotřebitelů.

### Matematická definice konvexity preferencí

Formálně preference jsou **konvexní**, pokud pro libovolné dva košíky $A$ a $B$ takové, že $A \sim B$ (spotřebitel je mezi nimi indiferentní), platí pro libovolný **konvexní průměr** $C = tA + (1-t)B$ s $t \in [0,1]$:

$$
C \succeq A \quad \text{(C je alespoň tak dobrý jako A)}
$$

**Striktní konvexita** vyžaduje $C \succ A$ pro $t \in (0,1)$ — průměr je *striktně* preferován před extrémy. Striktní konvexita zaručuje **jednoznačnost optima** v úloze maximalizace užitku, což je výhodné pro matematickou analýzu.

### Geometrická interpretace

Konvexnost se geometricky projeví tím, že **úsečka mezi libovolnými dvěma body téže IC leží nad** (nebo na) IC, nikdy pod ní. Pokud bychom IC nahradili přímkou (lineární užitková funkce, tedy dokonalé substituty), dostali bychom **slabě konvexní** preference (úsečka leží *na* IC, ne nad). Pro Cobb-Douglas a podobné hladké funkce máme **striktně konvexní** preference.

## 9. Důkaz, že se dvě IC nemohou protnout (sporem)

Tento důkaz je klasická ukázka geometrické intuice.

> [!example] Důkaz sporem
> Předpokládejme, že dvě indiferenční křivky $IC_1$ (užitek $U_1$) a $IC_2$ (užitek $U_2 > U_1$) téhož spotřebitele se **protínají** v bodě $P$.
>
> 1. Bod $P$ leží na $IC_1$, takže má užitek $U_1$.
> 2. Bod $P$ leží i na $IC_2$, takže má užitek $U_2$.
> 3. Ale platí $U_1 \ne U_2$ (jsou to dvě různé IC) — **spor**: jeden bod nemůže mít dva různé užitky.
>
> Alternativně přes tranzitivitu: vezměme bod $A$ na $IC_1$ vlevo od průniku a bod $B$ na $IC_2$ vpravo od průniku, tak aby $A$ a $B$ ležely v okolí průniku $P$. Pak:
> - $A \sim P$ (oba na $IC_1$)
> - $P \sim B$ (oba na $IC_2$)
> - z tranzitivity: $A \sim B$
> - ale $B$ má víc obou statků než $A$ (leží severovýchodně), takže $B \succ A$ podle nepřesycení — **spor**.
>
> Protože v obou variantách dochází ke sporu, dvě IC téhož spotřebitele se **nemohou protnout**. ∎

## 10. Speciální typy preferencí

Standardní IC jsou klesající, hladké a konvexní. Existují však **speciální preferenční struktury**, kde je tvar IC výrazně jiný a má samostatný ekonomický význam.

### 10.1 Dokonalé substituty

Dokonalé substituty jsou statky, které spotřebitel nahrazuje **v pevném poměru bez ohledu na již spotřebovaná množství**. Klasické příklady: dvě značky stejné minerálky, kostky cukru identické značky, eura a 100 dolarových bankovek (jako prostředek směny).

**Užitková funkce:** $U(X, Y) = aX + bY$ (lineární)

**Tvar IC:** přímky se sklonem $-a/b$

**MRS:** $MRS_C = a/b = $ **konstantní** (nezávisí na $(X,Y)$)

> [!example] Káva a čaj v poměru 1:1
> Pro spotřebitele, kterému je úplně jedno, zda pije kávu nebo čaj, je užitková funkce $U = X + Y$. MRS je konstantně 1: vždy je ochoten vyměnit 1 čaj za 1 kávu. IC jsou rovnoběžné přímky se sklonem $-1$. V optimu spotřebuje **pouze ten levnější** statek (rohové řešení).

### 10.2 Dokonalé komplementy

Dokonalé komplementy jsou statky, které je třeba **konzumovat v pevném poměru** — samostatně přinášejí nulový užitek. Klasické příklady: levá a pravá bota, auto a benzín (pokud nemůžeme jít pěšky), káva a hrnek.

**Užitková funkce:** $U(X, Y) = \min(aX, bY)$ (Leontiefova funkce)

**Tvar IC:** **L-tvar** (vodorovný segment + svislý segment, propojené v rohu na přímce $aX = bY$)

**MRS:** **nedefinováno** v rohu (nediferencovatelná funkce); na vodorovných segmentech $MRS = 0$, na svislých $MRS = \infty$

> [!example] Levá a pravá bota
> $U(X, Y) = \min(X, Y)$, kde $X$ = levé boty, $Y$ = pravé boty. Mít 5 levých a 2 pravé boty znamená užitek $\min(5,2) = 2$ — třetí pravá bota by užitek nezvýšila bez dalšího levého protějšku. Celé další levé boty také nepřinášejí užitek bez pravých. **Optimum** vždy leží na přímce $X = Y$.

### 10.3 Neutrální zboží

Neutrální zboží **nepřináší ani neodebírá užitek** — spotřebiteli je úplně lhostejné, kolik ho má. Příklad: spam v emailové schránce, který se ani nečte, ani neobtěžuje.

**Užitková funkce:** pokud $Y$ je neutrální, pak $U(X, Y) = U(X)$ — funkce nezávisí na $Y$

**Tvar IC:** **vertikální přímky** (pokud $Y$ je neutrální, spotřebitel je indiferentní mezi $(X, 1)$ a $(X, 100)$)

Nebo horizontální přímky, je-li neutrální $X$.

### 10.4 Nežádoucí zboží

Nežádoucí zboží (anti-statek, *bad*) má **záporný mezní užitek** — spotřebitel by ho rád neměl. Příklady: znečištění ovzduší, hluk, riziko, daňová zátěž.

**Užitková funkce:** záporný mezní užitek vůči nežádoucímu statku, např. $U = X - Z^2$, kde $Z$ je hluk

**Tvar IC:** **rostoucí přímky** (kladná směrnice). Aby spotřebitel zůstal indiferentní při zvýšení nežádoucího $Z$, potřebuje **kompenzaci** ve formě více "dobrého" statku $X$.

> [!example] Příjem vs. znečištění
> Vyjádříme-li IC v rovině *(příjem $I$, znečištění $Z$)*, dostaneme rostoucí křivku. Spotřebitel je ochoten snášet vyšší znečištění jen výměnou za vyšší příjem. Tento princip stojí za **kompenzačními platbami** v ekonomii životního prostředí.

### 10.5 Lidé nemají stejné preference

Mapy IC dvou různých spotřebitelů mohou mít **úplně jiné tvary**, i když jde o tytéž statky. Spotřebitel A může mít rád pivo víc než víno (strmé IC v rovině pivo-víno), spotřebitel B obráceně (mírné IC). To je teoretický základ **marketingové segmentace**: nelze předpokládat homogenní preference, a proto firmy cílí různé produkty na různé segmenty s odlišnými mapami IC.

### 10.6 Souhrnná tabulka tvarů IC

| Typ preferencí | Užitková funkce | Tvar IC | MRS | Optimum |
|----------------|-----------------|---------|-----|---------|
| Standardní | $X^a Y^b$ (CD) | hladká, konvexní, klesající | $\frac{aY}{bX}$ | vnitřní (tečna IC = rozpočtová přímka) |
| Dokonalé substituty | $aX + bY$ | rovnoběžné přímky | $\frac{a}{b}$ konst. | rohové (ve směru levnějšího) |
| Dokonalé komplementy | $\min(aX, bY)$ | L-tvar | $0$ nebo $\infty$ | v rohu IC ($aX = bY$) |
| Neutrální Y | $U(X)$ | vertikální přímky | $\infty$ | $X = I/P_X$, $Y$ = libovolné |
| Nežádoucí Z | $U(X) - g(Z)$ | rostoucí přímky | záporná | rohové ($Z=0$ je-li možné) |
| Kvazi-lineární | $f(X) + Y$ | vertikálně posunuté | $f'(X)$ | $f'(X^*) = P_X / P_Y$ |

## 11. Změna směru preferencí — saturace

V některých případech se může směr preferencí **měnit s úrovní spotřeby**. Nejčastější případ:

> [!info] Bod nasycení (saturation point)
> Pro statek $X$ existuje **maximum** $X^*$, po jehož překročení další jednotky **snižují** užitek (statek se mění na nežádoucí). Před $X^*$ jsou IC klesající, po $X^*$ rostoucí. V bodě $X^*$ je **MU = 0** — tečna IC je vodorovná.

Geometricky: IC kolem bodu nasycení mají tvar **uzavřených oválů** (jako vrstevnice kopce). Optimum potom leží na vrcholu kopce, **nezávisle na cenách a důchodu** — pokud je rozpočet dostatečně velký, spotřebitel se prostě "nasytí" a další utrácení mu nezvýší užitek.

### Praktický důsledek pro modelování

V mikroekonomických modelech se obvykle **vyhýbáme** funkcím s bodem nasycení, protože vedou k nestandardnímu chování:

- Pokud je důchod dostatečně velký, **rozpočtové omezení přestane být závazné** ($\lambda = 0$ v Lagrangeově úloze).
- Komparativní statika (reakce na změnu cen) přestane platit standardním způsobem.
- Tržní rovnováha může vést k **přebytkům**, pokud nasycený spotřebitel nechce nakoupit dodatečné množství.

Z těchto důvodů se v základním kurzu MikK pracuje **na restrikci** $X < X^*$ a $Y < Y^*$, kde se chování chová standardně (klesající MU, kladná MRS). Hraniční jevy se probírají jako rozšíření.

## 12. Příklad — kvadratická užitková funkce

Z poznámek ke cvičení MikK:

$$
U(X, Y) = 10X + 24Y - 0{,}5 X^2 - 0{,}5 Y^2
$$

### Mezní užitky

$$
MU_X = \frac{\partial U}{\partial X} = 10 - X
$$
$$
MU_Y = \frac{\partial U}{\partial Y} = 24 - Y
$$

### MRS

$$
MRS_C = \frac{MU_X}{MU_Y} = \frac{10 - X}{24 - Y}
$$

### Bod nasycení

Nastavíme $MU_X = 0$ a $MU_Y = 0$:

$$
10 - X = 0 \;\Rightarrow\; X^* = 10
$$
$$
24 - Y = 0 \;\Rightarrow\; Y^* = 24
$$

Bod nasycení je $(X^*, Y^*) = (10, 24)$. Pro $X < 10$ a $Y < 24$ jsou oba mezní užitky kladné a IC jsou standardně klesající. Po překročení bodu nasycení se mezní užitky stávají zápornými.

> [!example] Interpretace — koblihy
> Pokud $X$ představuje koblihy ke snídani, pak po desáté koblize $MU_X = 0$ — další kobliha už nepřináší žádné dodatečné potěšení (nasycení). Jedenáctá kobliha už dokonce vyvolává nepříjemný pocit, takže $MU_X < 0$. Tato kvadratická forma je **realistická pro běžné statky s konečným bodem nasycení**, na rozdíl od Cobb-Douglasovy funkce, která nasycení neumožňuje.

## 13. Cobb-Douglasova užitková funkce

Cobb-Douglasova forma (často probíraná v kontextu produkce — viz [[imek|Matematická ekonomie]] a [[produkce|Produkční funkce (ImeK)]]):

$$
U(X, Y) = X^a Y^b, \qquad a, b > 0
$$

### Mezní užitky

$$
MU_X = a X^{a-1} Y^b
$$
$$
MU_Y = b X^a Y^{b-1}
$$

### MRS

$$
MRS_C = \frac{MU_X}{MU_Y} = \frac{a X^{a-1} Y^b}{b X^a Y^{b-1}} = \frac{a}{b} \cdot \frac{Y}{X}
$$

> [!tip] Důležitý vzorec
> Pro Cobb-Douglas platí $MRS_C = \frac{a Y}{b X}$ — MRS závisí pouze na **poměru** $Y/X$, nikoli na absolutních úrovních. Tato vlastnost se nazývá **homotetické preference**.

### Speciální případ $a + b = 1$

Pokud parametry splňují $a + b = 1$, hovoříme o **standardizované Cobb-Douglasově funkci**. V kontextu produkce odpovídá **konstantním výnosům z rozsahu** (zdvojnásobení vstupů = zdvojnásobení výstupu); v kontextu užitku je interpretace, že parametry $a, b$ představují **podíly utráceného důchodu** za jednotlivé statky:

$$
\text{podíl důchodu na X} = \frac{a}{a+b} = a \quad \text{(když } a+b=1\text{)}
$$

Tato vlastnost je velmi užitečná v aplikované ekonomii, protože $a$ a $b$ se dají odhadnout přímo ze spotřebitelských dat.

### Odvození poptávkových funkcí pro CD

Z podmínky tečnosti $MRS_C = P_X / P_Y$:
$$\frac{aY}{bX} = \frac{P_X}{P_Y} \;\Rightarrow\; aY P_Y = bX P_X$$

Spojením s rozpočtovým omezením $P_X X + P_Y Y = I$ a substitucí $P_Y Y = \frac{b}{a} P_X X$:
$$P_X X + \frac{b}{a} P_X X = I \;\Rightarrow\; P_X X \cdot \frac{a+b}{a} = I$$

Odkud Marshallova poptávka:
$$\boxed{\;X^*(P_X, I) = \frac{a}{a+b} \cdot \frac{I}{P_X}, \qquad Y^*(P_Y, I) = \frac{b}{a+b} \cdot \frac{I}{P_Y}\;}$$

> [!tip] Praktický závěr
> Pro Cobb-Douglas spotřebitel utratí **konstantní podíl** důchodu na každý statek bez ohledu na ceny. To je zvláštní vlastnost CD, která je velmi pohodlná pro výpočty, ale empiricky platí jen přibližně (typicky se s rostoucím důchodem mění podíly — tzv. **Engelovy křivky** nejsou lineární).

## 14. Kvazi-lineární užitek

**Kvazi-lineární** užitková funkce má lineární tvar v jednom statku (typicky $Y$, který představuje peníze nebo *všechno ostatní zboží*) a obecnou funkci $f(X)$ ve druhém statku:

$$
U(X, Y) = f(X) + Y, \quad f'(X) > 0, \; f''(X) < 0
$$

### Mezní užitky a MRS

$$
MU_X = f'(X), \quad MU_Y = 1
$$
$$
MRS_C = \frac{MU_X}{MU_Y} = f'(X)
$$

> [!info] Klíčová vlastnost
> MRS závisí **pouze na $X$**, nikoli na $Y$. Důsledkem je **nulový důchodový efekt** pro statek $X$ — při změně důchodu se mění jen poptávka po $Y$, zatímco poptávka po $X$ zůstává konstantní (viz [[mikk-substitucni-duchodovy-efekt]]). IC jsou navzájem **vodorovně posunuté** kopie téže křivky.

### Použití

Kvazi-lineární užitek se v ekonomii **velmi často používá** v dílčích aplikacích:
- **Welfare ekonomie** — analýza spotřebitelského přebytku, kde Y je peněžní vyjádření.
- **Aukční teorie** — ochota platit za jednotlivé předměty bez interakce s důchodem.
- **Behaviorální experimenty** — laboratorní studie s reálnými penězi (peníze hrají roli "ostatních statků").

## 15. Aplikace v reálném světě

### Marketingová segmentace

Lidé nemají stejné preference. V praxi **každý segment trhu má jinou mapu IC**, a tedy jiný optimální produkt. Tento poznatek je teoretickým základem několika praktik:

- **Tržní segmentace** — firma identifikuje skupiny zákazníků s podobnými IC a navrhne pro ně specifické produkty (např. mléčné výrobky pro vegany vs. masné produkty pro masojedy).
- **Cenová diskriminace** — různé skupiny mají různou ochotu platit; firma účtuje různé ceny tak, aby maximalizovala přebytek z každého segmentu.
- **Personalizace** — algoritmy doporučování (Spotify, Netflix) odhadují individuální IC z chování a doporučují produkty z **vyšších** IC daného uživatele.

### Komplementy a balíčkování (bundling)

Dokonalé komplementy (sekce 10.2) vysvětlují, proč firmy nabízejí **balíčky komplementárních produktů**:

- **Tiskárna + tonery** (Hewlett-Packard model) — tiskárna se prodává levně, tonery draho. Funguje, protože komplementární vztah činí spotřebitele "uzamčeným" v ekosystému.
- **Console + hry** (Sony, Nintendo) — konzole jako loss-leader, hry s vysokou marží.
- **Mobil + paušál** (Apple + operátor) — paušál subvencuje cenu mobilu.

### Saturace a penetrace trhu

Bod nasycení (sekce 11) vysvětluje, proč mají **trhy fáze růstu a fáze stagnace**: pokud většina cílové populace dosáhla bodu nasycení (např. každá domácnost má lednici), poptávka stagnuje a růst musí přijít z **inovace**, která posune bod nasycení (např. chytrá lednice s WiFi).

### Behaviorální anomálie a meze klasické teorie

Klasická užitková teorie pracuje s racionálním spotřebitelem, který má stabilní preference splňující všechny tři axiomy. Behaviorální ekonomie (Kahneman, Tversky) ovšem dokumentuje **systematické porušování** těchto axiomů:

- **Porušení tranzitivity** — efekt rámování (framing effect): tytéž alternativy popsané různými způsoby vedou k odlišnému uspořádání preferencí.
- **Reference-dependent preferences** — užitek závisí na **referenčním bodě** (status quo, očekávání), nikoli jen na absolutní úrovni spotřeby. Toto je teoretický základ **prospect theory**.
- **Endowment effect** — vlastněné statky mají vyšší subjektivní užitek než nevlastněné, což porušuje konzistenci IC.
- **Hyperbolické diskontování** — preference v čase nejsou tranzitivní (preferujeme malou okamžitou odměnu před větší pozdější, ale když oba odsuneme do budoucna, naše volba se obrátí).

Tyto anomálie nejsou součástí klasického MikK kurzu, ale je dobré vědět, že **standardní teorie užitku je idealizace**. V reálných aplikacích (zejména marketingu a public policy) se kombinuje s behaviorálními korekcemi.

## 16. Souvislost s dalšími tématy

- **[[mikk-rovnovaha-spotrebitele]]** — formální optimalizace $\max U(X,Y)$ s.t. $P_X X + P_Y Y = I$, Lagrangeova metoda, podmínka $MRS_C = P_X / P_Y$.
- **[[mikk-substitucni-duchodovy-efekt]]** — Slutského rozklad reakce spotřebitele na změnu ceny; pracuje s pohyby po IC (substituční efekt) a přechody mezi IC (důchodový efekt).
- **[[mikk-marshall-hicks-poptavka]]** — odvození Marshallovy a Hicksovy poptávky z mapy IC.
- **[[mikk-elasticita-poptavky]]** — citlivost poptávky na ceny a důchod, vychází z optimalizace na IC.
- **[[uzitecnost|Užitečnost (ImeK primer)]]** — základní úvod do mezního užitku z [[imek|Matematické ekonomie]].
- **[[mikk-vzorce-prehled|Přehled vzorců MikK]]** — souhrnný cheat-sheet všech vzorců včetně MRS, $MU_X / P_X$ a Cobb-Douglas vzorců.

## 17. Klíčové vzorce — shrnutí

> [!tip] Cheat-sheet
> $$MU_X = \frac{\partial U}{\partial X}, \qquad MU_Y = \frac{\partial U}{\partial Y}$$
>
> $$\text{Rovnováha (kardinálně):}\quad \frac{MU_X}{P_X} = \frac{MU_Y}{P_Y}$$
>
> $$\text{Totální diferenciál:}\quad dU = MU_X\, dX + MU_Y\, dY$$
>
> $$\text{MRS:}\quad MRS_C = -\frac{dY}{dX}\Big|_{U=\text{konst.}} = \frac{MU_X}{MU_Y}$$
>
> $$\text{Cobb-Douglas } U=X^aY^b:\quad MRS_C = \frac{aY}{bX}$$
>
> $$\text{Kvazi-lineární } U=f(X)+Y:\quad MRS_C = f'(X)$$
>
> $$\text{Dokonalé substituty } U=aX+bY:\quad MRS_C = \frac{a}{b} = \text{konst.}$$
>
> $$\text{Dokonalé komplementy } U=\min(aX,bY):\quad \text{IC ve tvaru L}$$

## 18. Časté chyby a úskalí u zkoušky

> [!info] Pozor na tyto pasti
> 1. **Záměna MRS a poměru cen.** V optimu platí $MRS_C = P_X / P_Y$, ale jde o **podmínku rovnováhy**, nikoliv o definici MRS. MRS je definována jen z užitkové funkce, nezávisle na cenách.
> 2. **Dělení nulou v Cobb-Douglas.** Pro $X = 0$ je $MRS_C = \infty$ — to neznamená chybu, ale **rohové řešení** (spotřebitel chce nekonečně mnoho X za jednu Y).
> 3. **Konvexita ≠ konkávnost užitku.** Užitková funkce může být **konkávní** (klesající mezní užitek), zatímco IC jsou **konvexní** vzhledem k počátku. Nezaměňujte tyto dva pojmy.
> 4. **Dokonalé komplementy a derivace.** $U = \min(aX, bY)$ není diferencovatelná na přímce $aX = bY$ — nelze počítat MRS klasickým parciálním derivováním. Optimum je vždy v rohu IC.
> 5. **Nepřesycení vs. saturace.** Globální nepřesycení (axiom) říká "více je lépe všude". Saturace připouští bod nasycení a pak "více je hůř". Tyto dva koncepty se vylučují — pokud má funkce bod nasycení, axiom nepřesycení neplatí globálně.

---

Pro propojení s [[lagrangeova-metoda]] z [[imek|ImeK]] viz [[mikk-rovnovaha-spotrebitele]].
