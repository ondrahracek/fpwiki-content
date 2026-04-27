---
title: "Oligopol — Cournotův a Stackelbergův model"
course: mikk
type: topic
tags: [mikk, mikroekonomie, oligopol, cournot, stackelberg, duopol, nash, reakcni-krivka]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf, raw/mikk/mikK test KS reseni.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Oligopol — Cournotův a Stackelbergův model

## TL;DR

**Oligopol** je tržní struktura s **malým počtem firem**, jejichž rozhodnutí jsou
**strategicky závislá** — každá firma musí explicitně počítat s reakcí konkurentů,
protože její vlastní volba množství nebo ceny mění tržní výsledek pro všechny.
Tím se oligopol zásadně liší od dokonalé konkurence (kde je firma cenovým
příjemcem), monopolu (kde firma žádnou konkurenci nemá) a monopolistické
konkurence (kde je firem tolik, že individuální reakce zanedbáváme).

Dva základní modely množstevní konkurence v duopolu:

- **Cournotův model (1838):** firmy si volí výstup $Q_1$ a $Q_2$ **simultánně**;
  každá při svém rozhodování považuje výstup konkurenta za **fixní**. Z první
  podmínky maximalizace zisku vyplývají **reakční křivky**, jejichž průsečík
  je **Cournot-Nashova rovnováha**.
- **Stackelbergův model:** rozhodování je **sekvenční**. **Lider** volí $Q_1$
  jako první a ví, že **follower** zareaguje podle své Cournotovy reakční křivky.
  Lider si tuto reakci dosadí do svého TR a maximalizuje. Dostává **first-mover
  advantage** — vyrábí dvojnásobek followera a má dvojnásobný zisk.

Pro symetrický příklad $P = 30 - Q$, $MC_1 = MC_2 = 0$:

| Model | $Q_1$ | $Q_2$ | $Q$ | $P$ | $\pi_1$ | $\pi_2$ | $\sum\pi$ |
|---|---|---|---|---|---|---|---|
| **Koluze (sdílený monopol)** | 7,5 | 7,5 | 15 | 15 | 112,5 | 112,5 | **225** |
| **Stackelberg** (1 = lider) | 15 | 7,5 | 22,5 | 7,5 | 112,5 | 56,25 | 168,75 |
| **Cournot** | 10 | 10 | 20 | 10 | 100 | 100 | 200 |
| **Bertrand / DK** | 15 | 15 | 30 | 0 | 0 | 0 | 0 |

Pro firmy platí pořadí výhodnosti **koluze > Stackelberg-lider > Cournot >
Stackelberg-follower > Bertrand**. Pro spotřebitele přesně naopak: **Bertrand >
Stackelberg > Cournot > koluze**, protože s vyšším $Q$ klesá $P$.

Detailní srovnávací tabulka pro obecné $P = a - bQ$, $MC = 0$ je v sekci
[Srovnávací tabulka](#srovn%C3%A1vac%C3%AD-tabulka-4-model%C5%AF).

## 1. Definice oligopolu

### 1.1 Charakteristika

Oligopol je tržní struktura s těmito znaky:

- **Malý počet firem** — typicky 2 až ~10 hráčů. Pro $n=2$ mluvíme o **duopolu**.
  S rostoucím $n$ se oligopol blíží monopolistické konkurenci (kdy je firem
  tolik, že vzájemnou reakci přestává mít smysl modelovat).
- **Diferenciace produktu existuje, ale není příliš velká.** Typicky jsou
  produkty blízké substituty, někdy přímo homogenní (komodity — ocel, cement,
  ropa).
- **Může jít i o homogenní produkt** — viz Cournotův a Bertrandův model
  (předpokládají homogenitu).
- **Existují bariéry vstupu** — bez nich by se nadprůměrné zisky brzy
  rozplynuly tlakem nově vstupujících firem.

### 1.2 Bariéry vstupu

Standardní seznam:

- **Přirozené bariéry — úspory z rozsahu (scale economies).** Pokud minimální
  efektivní velikost závodu je velký zlomek tržní poptávky, na trh se vejde
  jen několik firem. Klasický příklad: výroba dopravních letadel (Boeing,
  Airbus), železnice, energetika.
- **Patenty.** Farmaceutické firmy chrání molekuly desítky let, technologické
  firmy klíčové vynálezy. Konkurence vstoupit nesmí, dokud patent nevyprší.
- **Speciální technologie / know-how.** Některé výrobní procesy se nedají
  jednoduše replikovat — TSMC v polovodičích, ASML v litografických strojích.
- **Síla značky / dobré jméno.** Coca-Cola, Apple, BMW — i kdyby konkurent
  vyráběl identický produkt, prémiovou cenu by neuhrál.
- **Síťové efekty.** Sociální sítě, platební systémy, marketplace — hodnota
  produktu pro uživatele roste s počtem ostatních uživatelů. Nový hráč nemá
  jak doběhnout.

V oligopolu se kombinují vícero bariér současně. Telekomunikace v ČR (3 hlavní
mobilní operátoři) jsou kombinací úspor z rozsahu, regulovaného přístupu ke
spektru a zákaznických nákladů na přechod.

## 2. Strategická interdependence

### 2.1 Klíčový rozdíl od ostatních tržních struktur

Klíčové pravidlo:

> V dokonalé konkurenci, monopolu a monopolistické konkurenci producenti
> nepředpokládají žádnou reakci ostatních firem ohledně výstupu a ceny.
>
> V oligopolu firmy musí zohlednit reakce konkurentů při volbě výstupu a ceny.

V dokonalé konkurenci je firma cenový příjemce — její individuální výstup je
nulový zlomek trhu, takže její rozhodnutí cenu nemění a o reakci ostatních
nemusí přemýšlet. Monopol naopak žádnou konkurenci nemá. V monopolistické
konkurenci je firem tolik, že efekt jejich vzájemné reakce je zanedbatelný
(každá vystupuje přibližně jako monopolista na své „diferencované niche").

V oligopolu je situace fundamentálně jiná. Pokud firma zvýší výstup, sníží to
tržní cenu znatelně, a tedy ovlivní zisky konkurentů. Konkurent na to bude
chtít zareagovat. Při volbě svého výstupu tedy musíme zohlednit, jak konkurent
zareaguje — a nevyhnutelně se dostáváme k **teorii her** a Nashově rovnováze.

### 2.2 Nashova rovnováha

**Definice:**

> Nashova rovnováha je stav, kdy žádný z hráčů nemůže jednostranným krokem
> zlepšit svoji situaci.

Operativní formulace:

> Firmy dělají to nejlepší co mohou a nemají žádný důvod pro změnu výstupu
> nebo ceny. Všechny firmy předpokládají, že všichni zúčastnění zohledňují
> chování konkurentů do svých rozhodnutí.

A slavný citát z filmu *A Beautiful Mind*:

> „Individuální ambice? Ano — jsou bezesporu nutné. Dělejme však to, co je
> nejlepší pro nás jako jednotlivce, a zároveň nechť je naše počínání v co
> možná největším souladu s potřebami kolektivu."

Nashova rovnováha je matematická formalizace takové situace: každý hráč hraje
nejlepší odpověď ($best\,response$) na strategie ostatních. Pokud by někdo
mohl jednostrannou změnou své strategie získat víc, **nebyli bychom v
rovnováze**.

V Cournotově duopolu hraje firma 1 nejlepší odpověď na $Q_2$ (a naopak). Tato
nejlepší odpověď se zobrazí jako **reakční křivka**. Cournotova rovnováha je
průsečík obou reakčních křivek — místo, kde **každá** firma hraje nejlepší
odpověď na to, co druhá skutečně dělá.

Pro Stackelberga je Nashův koncept rozšířen — hovoříme o **subgame perfect
Nash equilibrium**. Lider očekává, že follower zahraje nejlepší odpověď
v podhře po $Q_1$, a optimalizuje svůj $Q_1$ s touto reakční křivkou v hlavě.

Viz též podrobněji [[mikk-vezno-dilema-teorie-her|Vězňovo dilema a teorie her]].

## 3. Cournotův model

### 3.1 Předpoklady

Autorem je francouzský matematik **Antoine Augustin Cournot** (1838 —
*Recherches sur les principes mathématiques de la théorie des richesses*).
Jde o jeden z prvních formálních modelů strategické konkurence vůbec.

Předpoklady modelu:

1. **Duopol** — dvě firmy. (Model lze zobecnit na $n$ firem; zde řešíme $n=2$.)
2. **Homogenní produkt** — výrobky obou firem jsou dokonalé substituty;
   spotřebitel kupuje od kohokoli za nižší cenu, ale na trhu se ustaví jediná
   tržní cena.
3. **Konkurence přes množství $Q$** — strategickou proměnnou je výstup, ne cena.
   (Pokud by konkurence šla přes cenu, dostali bychom Bertrandův model.)
4. **Stejně silné firmy** — symetrický případ; budeme uvažovat shodné mezní
   náklady. Asymetrický Cournot s různými $MC$ je v sekci 6.
5. **Lineární tržní poptávka** $P = a - bQ$, kde $Q = Q_1 + Q_2$.
6. **Obě firmy maximalizují zisk.**
7. **Simultánní rozhodnutí** — žádná firma neví, co konkurent zvolí, a obě se
   rozhodují najednou.
8. **Každá firma považuje výstup konkurenta za fixní** — při svém rozhodování
   bere $Q_2$ (resp. $Q_1$) jako parametr, ne jako reakci.

Tento osmý bod je kontroverzní:
v rovnováze totiž obě firmy správně **odhadnou** výstup konkurenta, ale
během derivace optimální podmínky ho považují za nezávislé na vlastní volbě
— jako kdyby Q₂ bylo jen číslo. Stackelberg tento předpoklad upouští u lidera.

### 3.2 Intuice — posuny poptávky firmy 1

Nejdřív získáme intuici, jak optimální $Q_1$ závisí na $Q_2$:

- **Pokud $Q_2 = 0$:** firma 1 čelí celé tržní poptávce $D_1(0) = $ tržní
  poptávka. Chová se jako **monopolista**. Pro $P = 30 - Q$, $MC = 0$ je
  monopolní výstup $Q_1 = 15$.
- **Pokud $Q_2 = 50$:** poptávka, kterou vidí firma 1, se posouvá doleva o
  50 jednotek (každá cena platí pro $Q_1 = $ tržní $Q$ minus 50). Firma 1
  tedy dostane $D_1(50)$ a optimalizuje proti ní. Optimum je nižší — řekněme
  $Q_1 = 25$.
- **Pokud $Q_2 = 75$:** ještě další posun doleva. Firma 1 vyrábí ještě méně,
  $Q_1 = 12{,}5$.
- **Pokud $Q_2 = 100$:** poptávka pro firmu 1 je už tak nízko, že její optimum
  je $Q_1 = 0$ — zachycení trhu by si nevyplatilo.

Mapováním všech těchto bodů $(Q_2, Q_1^*)$ získáme **reakční křivku firmy 1**:
funkci $Q_1 = R_1(Q_2)$, která říká, kolik firma 1 vyrobí jako nejlepší odpověď,
pokud bere $Q_2$ jako dané.

### 3.3 Reakční křivka — formální odvození

Tržní poptávka: $P = 30 - Q_1 - Q_2$.

**Total Revenue firmy 1:**

$$
TR_1 = P \cdot Q_1 = (30 - Q_1 - Q_2)\,Q_1 = 30 Q_1 - Q_1^2 - Q_1 Q_2.
$$

**Marginal Revenue firmy 1** (parciální derivace podle $Q_1$, **při fixním $Q_2$**):

$$
MR_1 = \frac{\partial TR_1}{\partial Q_1} = 30 - 2 Q_1 - Q_2.
$$

Podmínka maximalizace zisku (mezní příjem rovný mezním nákladům, $MC_1 = 0$):

$$
MR_1 = MC_1 \;\Leftrightarrow\; 30 - 2 Q_1 - Q_2 = 0 \;\Leftrightarrow\; Q_1 = 15 - \tfrac{1}{2} Q_2.
$$

To je **reakční křivka firmy 1**:

$$
\boxed{\,Q_1 = R_1(Q_2) = 15 - \tfrac{1}{2} Q_2.\,}
$$

Symetricky pro firmu 2:

$$
\boxed{\,Q_2 = R_2(Q_1) = 15 - \tfrac{1}{2} Q_1.\,}
$$

**Interpretace:** Když konkurent nevyrábí ($Q_2 = 0$), firma 1 jede jako
monopolista a vyrábí $Q_1 = 15$. Každá jednotka navíc, kterou konkurent vyrobí,
sníží optimální $Q_1$ o ½ jednotky. Když konkurent zaplaví trh ($Q_2 = 30$),
firma 1 nedělá nic.

### 3.4 Cournotova rovnováha — průsečík

![[mikk-cournot-best-response.jpeg|Best-response funkce dvou firem v Cournotově oligopolu, jejich průsečík (Cournot-Nash) a Stackelbergův bod]]

Rovnováha je bod, kde **obě reakční křivky** jsou splněny současně:

$$
\begin{aligned}
Q_1 &= 15 - \tfrac{1}{2} Q_2, \\
Q_2 &= 15 - \tfrac{1}{2} Q_1.
\end{aligned}
$$

Dosadíme druhou rovnici do první:

$$
Q_1 = 15 - \tfrac{1}{2}\bigl(15 - \tfrac{1}{2} Q_1\bigr) = 15 - 7{,}5 + \tfrac{1}{4} Q_1 = 7{,}5 + \tfrac{1}{4} Q_1.
$$

$$
Q_1 - \tfrac{1}{4} Q_1 = 7{,}5 \;\Rightarrow\; \tfrac{3}{4} Q_1 = 7{,}5 \;\Rightarrow\; \boxed{Q_1 = 10}.
$$

Symetrií $Q_2 = 10$. Celkový tržní výstup $Q = 20$, cena:

$$
P = 30 - 20 = 10.
$$

Zisky:

$$
\pi_1 = (P - MC_1) \cdot Q_1 = 10 \cdot 10 = 100, \qquad \pi_2 = 100.
$$

Celkem $\sum \pi = 200$.

### 3.5 Geometrie reakčních křivek

V rovině $Q_1 \times Q_2$:

- **Reakční křivka firmy 1** je přímka klesající z $(Q_2, Q_1) = (0, 15)$ do
  $(30, 0)$. Sklon $-\tfrac{1}{2}$ (po vyjádření $Q_1$ jako funkce $Q_2$).
- **Reakční křivka firmy 2** je přímka klesající z $(Q_1, Q_2) = (0, 15)$ do
  $(30, 0)$, ale „čtena" pod úhlem 90° — v rovině $(Q_1, Q_2)$ jí odpovídá
  přímka $Q_2 = 15 - \tfrac{1}{2} Q_1$, tedy klesající z $(0, 15)$ do $(30, 0)$
  sklonem $-\tfrac{1}{2}$.

Obě se protínají v bodě $(10, 10)$ — Cournotova rovnováha.

### 3.6 Stabilita rovnováhy a tâtonnement

Klademe dvě otázky:

1. *Jestliže firma neprodukuje v rovnováze, bude se firma snažit rovnováhy
   dosáhnout?* — **Ano.** Jakákoli volba mimo reakční křivku znamená, že firma
   nemaximalizuje zisk při daném $Q_2$. Jednostranná korekce ji k vyššímu zisku
   přivede. Pokud se obě firmy postupně přizpůsobují (firma 1 nejdřív nastaví
   $Q_1 = R_1(Q_2)$, pak firma 2 odpoví $Q_2' = R_2(Q_1)$ atd.), iterace
   konverguje k Cournotově rovnováze.
2. *Je vůbec racionální, že se výstup konkurenta předpokládá fixní?* —
   **Striktně vzato ne.** V rovnováze je předpoklad správný (konkurent
   skutečně fixně drží svůj $Q_2^*$), ale **při derivaci** firma ignoruje, že
   změna jejího $Q_1$ by konkurenta vlastně vyprovokovala k revizi. To je
   Cournotův „zjednodušující předpoklad" a Stackelbergův model jej u lidera
   opouští. Modernější přístupy (modely s **conjectured variations**) zavádějí
   parametr, jak moc firma očekává reakci konkurenta — Cournot je pak speciální
   případ s nulovou domnělou variací.

Viz též [[mikk-oligopol-bertrand-cenova-konkurence|Bertrandův model]] pro
analogickou diskusi v cenové variantě.

## 4. Koluze (sdílený monopol)

### 4.1 Maximalizace společného zisku

Pokud se firmy domluví a chovají se **jako jeden monopolista**, maximalizují
**celkový zisk** $\pi_1 + \pi_2$ vůči celkovému $Q = Q_1 + Q_2$. Tržní poptávka
zůstává $P = 30 - Q$, mezní náklady jsou $MC = 0$.

$$
TR = P \cdot Q = (30 - Q) Q = 30 Q - Q^2.
$$

$$
MR = 30 - 2 Q.
$$

Optimum:

$$
MR = MC \;\Leftrightarrow\; 30 - 2 Q = 0 \;\Leftrightarrow\; \boxed{Q = 15}.
$$

Cena $P = 30 - 15 = 15$, celkový zisk $\pi = 15 \cdot 15 = 225$.

### 4.2 Křivka kontraktu

Otázka, **jak rozdělit** $Q = 15$ mezi dvě firmy, není určena maximalizací zisku.
Všechny kombinace $(Q_1, Q_2)$ s $Q_1 + Q_2 = 15$ dávají stejný celkový zisk.
Tato přímka v $(Q_1, Q_2)$ rovině se nazývá **křivka kontraktu**. Nejčastější
volba je rovnoměrné rozdělení $Q_1 = Q_2 = 7{,}5$, $\pi_1 = \pi_2 = 112{,}5$.

Pro firmy je koluze **lepší než Cournot** ($112{,}5 > 100$) — proto vznikají
kartely. Problém je **nestabilita**: pokud firma 1 dodrží $Q_1 = 7{,}5$, má
firma 2 silnou motivaci podvádět. Z reakční křivky $Q_2 = R_2(7{,}5) =
15 - 3{,}75 = 11{,}25$, tedy firma 2 by jednostranným zvýšením na $11{,}25$
získala vyšší okamžitý zisk. Antimonopolní legislativa (kartelové dohody jsou
v EU i ČR zakázané) i nestabilní pobídky drží reálné kartely při zemi —
viz [[mikk-oligopol-cenovy-vudce-kartel|Kartely a cenové vůdcovství]].

### 4.3 Srovnání 4 modelů v rovině $Q_1 \times Q_2$

V grafu $(Q_1, Q_2)$ leží:

- **Bod koluze** $(7{,}5;\,7{,}5)$ — na křivce kontraktu, **uvnitř** obou
  reakčních křivek (každá firma by samostatně chtěla vyrobit víc).
- **Cournot equilibrium** $(10;\,10)$ — průsečík reakčních křivek.
- **Bertrand / dokonalá konkurence** $(15;\,15)$ — bod, kde $P = MC = 0$ a
  $\pi = 0$. (Tento bod **není** rovnováhou žádného z dosud popsaných modelů
  v duopolu s množstevní konkurencí, ale je referencí pro extrém — odpovídá
  ceně rovné MC.)

> Pro firmu je nejvýhodnější koluze, potom Cournot a nakonec dokonalá
> konkurence.

Pro spotřebitele je hierarchie obrácená.

## 5. Stackelbergův model (sekvenční konkurence)

### 5.1 Předpoklady

Heinrich von Stackelberg (1934) modifikoval Cournotův model jednou změnou:
**rozhodování není simultánní, ale sekvenční**.

- **Firma 1 (lider)** zvolí svůj výstup $Q_1$ jako **první**.
- **Firma 2 (follower)** výstup pozoruje a teprve **potom** volí $Q_2$.
- Mezní náklady jsou stále $MC_1 = MC_2 = 0$ a poptávka $P = 30 - Q$.

Z toho plyne **klíčový rozdíl od Cournota**: firma 2 nedělá předpoklad o
nějakém fixním $Q_1$ — ona ho **vidí**. A firma 1 ví, že firma 2 ho uvidí, takže
si musí domyslet, **jak firma 2 zareaguje**.

### 5.2 Followerova úvaha

Firma 2 stojí přesně před Cournotovým problémem: $Q_1$ je daný (teď opravdu
fixní, protože už byl zvolen). Firma 2 maximalizuje svůj zisk vůči $Q_1$ —
to je **Cournotova reakční křivka firmy 2**:

$$
Q_2 = R_2(Q_1) = 15 - \tfrac{1}{2} Q_1.
$$

### 5.3 Liderova úvaha

Firma 1 ví, jak firma 2 zareaguje, a tuto reakci **dosadí** do svého TR.
Místo aby brala $Q_2$ jako parametr (jak by udělal Cournotův hráč), vidí ji
jako funkci $Q_2 = 15 - \tfrac{1}{2} Q_1$ své vlastní volby.

$$
TR_1 = P \cdot Q_1 = (30 - Q_1 - Q_2) Q_1.
$$

Dosaďme followerovu reakci:

$$
TR_1 = \bigl(30 - Q_1 - (15 - \tfrac{1}{2} Q_1)\bigr) Q_1 = (30 - Q_1 - 15 + \tfrac{1}{2} Q_1) Q_1 = (15 - \tfrac{1}{2} Q_1) Q_1.
$$

$$
TR_1 = 15 Q_1 - \tfrac{1}{2} Q_1^2.
$$

Mezní příjem:

$$
MR_1 = \frac{\mathrm{d} TR_1}{\mathrm{d} Q_1} = 15 - Q_1.
$$

Optimum:

$$
MR_1 = MC_1 \;\Leftrightarrow\; 15 - Q_1 = 0 \;\Leftrightarrow\; \boxed{Q_1 = 15}.
$$

Reakce followera:

$$
Q_2 = 15 - \tfrac{1}{2} \cdot 15 = \boxed{7{,}5}.
$$

Tržní výstup a cena:

$$
Q = Q_1 + Q_2 = 22{,}5, \qquad P = 30 - 22{,}5 = 7{,}5.
$$

Zisky:

$$
\pi_1 = P \cdot Q_1 = 7{,}5 \cdot 15 = 112{,}5,
$$

$$
\pi_2 = P \cdot Q_2 = 7{,}5 \cdot 7{,}5 = 56{,}25.
$$

### 5.4 Shrnutí — first-mover advantage

Stackelbergova rovnováha:

| | Lider (firma 1) | Follower (firma 2) |
|---|---|---|
| Výstup | $Q_1 = 15$ | $Q_2 = 7{,}5$ |
| Zisk | $\pi_1 = 112{,}5$ | $\pi_2 = 56{,}25$ |

> Výstup firmy 1 je dvakrát větší než firmy 2.
> Zisk firmy 1 je dvakrát větší než firmy 2.

A to jsou klíčové numerické výsledky, na kterých se pozná Stackelberg ze
zadání zkoušky:

- **$Q_1 / Q_2 = 2$**.
- **$\pi_1 / \pi_2 = 2$**.
- $Q_1 = $ **monopolnímu výstupu** (15 = $a/(2b)$). To není náhoda: lider se
  fakticky chová jako monopolista, ale s upravenou poptávkovou funkcí, která
  zohledňuje, že follower „ukrojí" půl jeho marginální jednotky.

### 5.5 Otázky k zamyšlení

**Proč je výhodnější moci reagovat?**

Intuice říká, že informace navíc je vždy lepší — follower přece reaguje na
**známý** $Q_1$, což zní jako výhoda. Ale **paradoxně to výhoda není**.
First-mover advantage znamená, že lider svým rozhodnutím **omezuje** prostor
followera. Lider ví, že vyrobí-li hodně, follower bude muset omezit svůj
výstup (jinak by si zhroutil cenu pod své MC). Lider tedy **commitne** vysoký
výstup a follower se musí přizpůsobit.

V Stackelbergu je $Q_1 = 15$ (více než cournotových 10), což followera
„odežene" na $Q_2 = 7{,}5$ (méně než cournotových 10). Lider získává tu část
zisku, kterou by si jinak follower vzal v Cournotu.

**Který model je realističtější?**

Záleží na trhu:

- **Cournot** je vhodný pro trhy, kde se **rozhodování opravdu děje
  simultánně** — typicky homogenní komodity, dlouhý plánovací cyklus, vysoký
  fixní investiční horizont. Příklady: zemědělství (osevní plán na sezonu),
  ropa (OPEC kvóty), těžební průmysl.
- **Stackelberg** je vhodný pro trhy s **jasným tržním lídrem**, který
  rozhoduje první a ostatní reagují. Příklady: Microsoft v 90. letech
  (operační systém Windows určuje pravidla, ostatní se přizpůsobí), Google
  v internetovém vyhledávání, Apple v segmentu prémiových smartphonů
  (uvádí novou generaci a Samsung reaguje).

V realitě bývá interakce mnohem komplexnější — opakované hraní, nedokonalá
informace, dynamická vstupní hra. Cournot a Stackelberg jsou referenční
benchmarky, ne přesné popisy.

## 6. Asymetrický Cournot s rostoucími MC

Varianta duopolu se **dvěma různými nákladovými funkcemi**:

- Tržní poptávka: $P = 100 - Q$, kde $Q = Q_1 + Q_2$.
- **Firma 1**: $MC_1 = 4$ (konstantní, levná technologie).
- **Firma 2**: $MC_2 = Q_2$ (lineárně rostoucí — výrobní omezení, nedostatek
  kapacity).

### 6.1 Heuristika — analogie s vícezávodním monopolem

Ve standardní (symetrické) Cournotově analýze bychom psali dvě reakční křivky
a hledali jejich průsečík. Tady se ale využije šikovnější trik:

> Pravidlo: při $n$ závodech monopolisty platí $MC_1 = MC_2 = \ldots = MC_n = MR$.

Stejná logika platí, pokud chceme najít, jak by se dvě „firmy" s různými
nákladovými funkcemi rozdělily o monopolní zisk: každá vyrábí do bodu, kde se
její $MC$ vyrovná se **společným** mezním příjmem $MR$ na celkovém výstupu.

Tato úloha v originále využívá heuristiku Cournotovy rovnováhy přes podmínku
$MC_1 = MC_2$ (každá firma vyrovnává své MC se společným MR — viz též
[[mikk-monopol-pokrocily|Monopol s více závody]]).

### 6.2 Výpočet

Mezní příjem na **celkovém** $Q$:

$$
MR = 100 - 2 Q.
$$

Z podmínky $MC_1 = MR$ pro firmu 1 (s konstantní $MC_1 = 4$):

$$
4 = 100 - 2 Q \;\Rightarrow\; 2 Q = 96 \;\Rightarrow\; \boxed{Q = 48}.
$$

Cena:

$$
P = 100 - 48 = \boxed{52}.
$$

Rozdělení mezi firmy: musí platit $MC_2 = 4$ (vyrovnáno se společným MR
prostřednictvím $MC_1$). Z $MC_2 = Q_2$ tedy $Q_2 = 4$.

A z $Q_1 + Q_2 = 48$ dostaneme $Q_1 = 44$.

| | Firma 1 (levná) | Firma 2 (drahá) | Celkem |
|---|---|---|---|
| Mezní náklady | $MC_1 = 4$ | $MC_2 = Q_2 = 4$ | — |
| Výstup | $Q_1 = 44$ | $Q_2 = 4$ | $Q = 48$ |
| Cena | — | — | $P = 52$ |

### 6.3 Intuice

Firma 1 má levnou (a konstantní) technologii — vyrábí převážnou část trhu.
Firma 2 má rostoucí MC, takže by velký výstup byl pro ni katastrofálně drahý.
Firma 2 dotáhne výrobu **jen** do bodu, kde její $MC_2$ doběhne $MC_1$ — pak
už by každá další jednotka stála firmu 2 víc, než ji prodá. Levný producent
„dotuje" trh, drahý jen doplňuje.

Tato úloha krásně ilustruje, že **Cournotova rovnováha s heterogenními MC**
přerozdělí trh ve prospěch nákladově efektivnější firmy. V symetrické verzi
by si firmy trh podělily 50/50, tady to vychází 92 % vs. 8 %.

Pozn.: V některých variantách interpretace by se rozdělení dělalo přes klasické
reakční křivky $Q_i = (a - MC_i - Q_j)/(2b)$, ale řešení v testovém přepisu
používá heuristiku přes $MC_1 = MC_2 = MR$ (jako u monopolisty s více závody).
Obě cesty mají v této úloze totožný výsledek díky tomu, že rostoucí $MC_2$
poskytuje řešení automaticky.

## 7. Srovnávací tabulka 4 modelů

### 7.1 Pro $P = a - bQ$, $MC = 0$

Obecné výsledky pro lineární poptávku a nulové mezní náklady:

| Model | $Q_1$ | $Q_2$ | $Q$ | $P$ | $\pi_1$ | $\pi_2$ | $\sum\pi$ |
|---|---|---|---|---|---|---|---|
| **Sdílený monopol (koluze)** | $\dfrac{a}{4b}$ | $\dfrac{a}{4b}$ | $\dfrac{a}{2b}$ | $\dfrac{a}{2}$ | $\dfrac{a^2}{8b}$ | $\dfrac{a^2}{8b}$ | $\dfrac{a^2}{4b}$ |
| **Cournot** | $\dfrac{a}{3b}$ | $\dfrac{a}{3b}$ | $\dfrac{2a}{3b}$ | $\dfrac{a}{3}$ | $\dfrac{a^2}{9b}$ | $\dfrac{a^2}{9b}$ | $\dfrac{2a^2}{9b}$ |
| **Bertrand** | $\dfrac{a}{2b}$ | $\dfrac{a}{2b}$ | $\dfrac{a}{b}$ | $0$ | $0$ | $0$ | $0$ |
| **Stackelberg** (1 = lider) | $\dfrac{a}{2b}$ | $\dfrac{a}{4b}$ | $\dfrac{3a}{4b}$ | $\dfrac{a}{4}$ | $\dfrac{a^2}{8b}$ | $\dfrac{a^2}{16b}$ | $\dfrac{3a^2}{16b}$ |

**Verifikace pro $a = 30$, $b = 1$:**

| Model | $Q_1$ | $Q_2$ | $Q$ | $P$ | $\pi_1$ | $\pi_2$ | $\sum\pi$ |
|---|---|---|---|---|---|---|---|
| Koluze | 7,5 | 7,5 | 15 | 15 | 112,5 | 112,5 | **225** |
| Cournot | 10 | 10 | 20 | 10 | 100 | 100 | 200 |
| Bertrand | 15 | 15 | 30 | 0 | 0 | 0 | 0 |
| Stackelberg | 15 | 7,5 | 22,5 | 7,5 | 112,5 | 56,25 | 168,75 |

Vše sedí.

### 7.2 Odvození jednotlivých řádků

**Sdílený monopol (koluze).** Maximalizujeme $\pi = (a - bQ) Q$ vůči $Q$:

$$
\frac{\mathrm{d}\pi}{\mathrm{d} Q} = a - 2 b Q = 0 \;\Rightarrow\; Q = \frac{a}{2b}.
$$

$P = a - b \cdot \tfrac{a}{2b} = \tfrac{a}{2}$, $\pi = \tfrac{a}{2} \cdot \tfrac{a}{2b} = \tfrac{a^2}{4b}$.
Při rovnoměrném rozdělení $Q_1 = Q_2 = \tfrac{a}{4b}$, $\pi_1 = \pi_2 = \tfrac{a^2}{8b}$. ✓

**Cournot.** Reakční křivky:

$$
MR_1 = a - 2 b Q_1 - b Q_2 = 0 \;\Rightarrow\; Q_1 = \frac{a - b Q_2}{2b}.
$$

Symetrie a dosazení:

$$
Q_1 = \frac{a - b \cdot \tfrac{a - b Q_1}{2b}}{2b} = \frac{a - \tfrac{a - b Q_1}{2}}{2b} = \frac{\tfrac{a + b Q_1}{2}}{2b} = \frac{a + b Q_1}{4b}.
$$

$$
4 b Q_1 = a + b Q_1 \;\Rightarrow\; 3 b Q_1 = a \;\Rightarrow\; Q_1 = \tfrac{a}{3b}. \checkmark
$$

Symetrie $Q_2 = \tfrac{a}{3b}$, $Q = \tfrac{2a}{3b}$, $P = a - b \cdot \tfrac{2a}{3b} = \tfrac{a}{3}$.
Zisk: $\pi_1 = \tfrac{a}{3} \cdot \tfrac{a}{3b} = \tfrac{a^2}{9b}$. ✓

**Bertrand.** Cenová konkurence s homogenním produktem a $MC = 0$ tlačí cenu na
$P = MC = 0$. Trh se rozdělí rovnoměrně: $Q_1 = Q_2 = \tfrac{1}{2} \cdot \tfrac{a}{b} = \tfrac{a}{2b}$, $\pi = 0$.
Detaily v [[mikk-oligopol-bertrand-cenova-konkurence|Bertrand]].

**Stackelberg.** Lider dosadí followera $Q_2 = \tfrac{a - b Q_1}{2b}$:

$$
TR_1 = (a - b Q_1 - b Q_2) Q_1 = \bigl(a - b Q_1 - \tfrac{a - b Q_1}{2}\bigr) Q_1 = \tfrac{a - b Q_1}{2} \cdot Q_1.
$$

$$
TR_1 = \tfrac{a Q_1 - b Q_1^2}{2}, \qquad MR_1 = \tfrac{a - 2 b Q_1}{2}.
$$

$MR_1 = 0 \Rightarrow Q_1 = \tfrac{a}{2b}$. ✓

Follower: $Q_2 = \tfrac{a - b \cdot \tfrac{a}{2b}}{2b} = \tfrac{a/2}{2b} = \tfrac{a}{4b}$. ✓

$Q = \tfrac{a}{2b} + \tfrac{a}{4b} = \tfrac{3a}{4b}$, $P = a - b \cdot \tfrac{3a}{4b} = \tfrac{a}{4}$.

Zisky:

$$
\pi_1 = \tfrac{a}{4} \cdot \tfrac{a}{2b} = \tfrac{a^2}{8b}, \qquad \pi_2 = \tfrac{a}{4} \cdot \tfrac{a}{4b} = \tfrac{a^2}{16b}. \checkmark
$$

Pozn.: Lider ve Stackelbergu má **stejný zisk** jako každá firma v koluzi
($\tfrac{a^2}{8b}$). To je krásný ekonomický fakt: lider „ukradne" celý
monopolní zisk pro sebe, follower si vezme zbytek (poloviční zisk lídra).

### 7.3 Pořadí výhodnosti

| Pohled | Pořadí (od nejlepšího) |
|---|---|
| Pro firmu (jednostranně) | Stackelberg-lider = Koluze > Cournot > Stackelberg-follower > Bertrand |
| Pro firmy souhrnně | Koluze > Cournot > Stackelberg > Bertrand |
| Pro spotřebitele (CS) | Bertrand > Stackelberg > Cournot > Koluze |
| Tržní výstup $Q$ | Bertrand ($a/b$) > Stackelberg ($3a/4b$) > Cournot ($2a/3b$) > Koluze ($a/2b$) |
| Tržní cena $P$ | Koluze ($a/2$) > Cournot ($a/3$) > Stackelberg ($a/4$) > Bertrand ($0$) |

Ze sociálního hlediska (efektivita, deadweight loss) je nejlepší Bertrand,
nejhorší Koluze. Proto antimonopolní úřady cílí kartelové dohody.

## 8. Stabilita Cournotovy rovnováhy a tâtonnement

### 8.1 Co se stane mimo rovnováhu

Vezměme bod $(Q_1, Q_2) = (5, 12)$, který **není** na žádné reakční křivce:

- Firma 1 vidí $Q_2 = 12$. Její optimum: $R_1(12) = 15 - 6 = 9$. Když se přesune
  na $Q_1 = 9$, ziská $\pi_1 = (30 - 9 - 12) \cdot 9 = 9 \cdot 9 = 81$ místo
  $(30 - 5 - 12) \cdot 5 = 13 \cdot 5 = 65$. Zlepšení o 16.
- Firma 2 teď vidí $Q_1 = 9$. Její optimum: $R_2(9) = 15 - 4{,}5 = 10{,}5$.
  Posun z 12 na 10,5: zisk $(30 - 9 - 10{,}5) \cdot 10{,}5 = 10{,}5 \cdot 10{,}5 = 110{,}25$
  místo $(30 - 9 - 12) \cdot 12 = 9 \cdot 12 = 108$.
- Firma 1 znovu reaguje: $R_1(10{,}5) = 15 - 5{,}25 = 9{,}75$. ...

Iterace konverguje k Cournotově rovnováze $(10, 10)$. Tomuto procesu se říká
**Cournotův tâtonnement** (z francouzského „tápání"). V realitě k němu
nikdy nedojde v takto čisté formě, ale ilustruje **stabilitu** rovnováhy: i z
náhodného počátečního stavu by si firmy nakonec sedly na Nashův bod.

### 8.2 Existence a jedinečnost rovnováhy

V symetrickém duopolu s lineární poptávkou a konstantními MC:

- Reakční křivky jsou klesající přímky se sklony $-\tfrac{1}{2}$.
- V kladném ortantu se protnou v jediném bodě.
- Tâtonnement konverguje (sklony $|R_i'| = \tfrac{1}{2} < 1$).

Pro nelineární poptávku a/nebo MC může být situace složitější — vícero
rovnováh, nestabilita, divergentní iterace. Ekonomická praxe se s těmito
patologiemi obvykle nezabývá; učební model je hodný učení právě proto, že
chování je jednoznačné.

## 9. Aplikace v reálných trzích

- **Automobilový průmysl.** Globální oligopol s klíčovými hráči (Toyota,
  Volkswagen, Stellantis, GM, Ford, Hyundai-Kia, Honda, BMW, Mercedes, Tesla).
  Kombinace Cournotovských prvků (kapacita závodů se plánuje předem) a
  diferenciace (segmenty, značky).
- **Telekomunikace v ČR.** Tři velcí mobilní operátoři (O2, T-Mobile, Vodafone)
  + virtuálové. Cenové vůdcovství spíš než Cournot — viz
  [[mikk-oligopol-cenovy-vudce-kartel|Cenové vůdcovství]].
- **Letecké aerolinky.** Na konkrétních trasách často duopol nebo triopol.
  Stackelbergovské chování — incumbent reaguje na vstup nízkonákladové
  konkurence.
- **OPEC a ropný trh.** Klasická koluze prostřednictvím kvót — modelově
  sdílený monopol. Realita je složitější (Saudská Arábie jako swing producer
  funguje jako Stackelbergův lider, ostatní jako followeři).
- **Cloud computing.** AWS, Azure, GCP. Klasický oligopol s vysokými
  bariérami (úspory z rozsahu, síťové efekty).
- **Operační systémy pro PC.** Microsoft Windows historicky Stackelbergův
  lider, Apple a Linux followeři.

## 10. Cvičení k ověření porozumění

### 10.1 Symetrický Cournot — jiná čísla

Tržní poptávka $P = 60 - Q$, $MC_1 = MC_2 = 12$.

Spočítejme reakční křivku firmy 1:

$$
TR_1 = (60 - Q_1 - Q_2) Q_1, \quad MR_1 = 60 - 2 Q_1 - Q_2 = MC_1 = 12.
$$

$$
Q_1 = \tfrac{48 - Q_2}{2} = 24 - \tfrac{Q_2}{2}.
$$

Symetrie a průsečík:

$$
Q_1 = 24 - \tfrac{1}{2} (24 - \tfrac{1}{2} Q_1) = 12 + \tfrac{1}{4} Q_1 \;\Rightarrow\; \tfrac{3}{4} Q_1 = 12 \;\Rightarrow\; Q_1 = 16.
$$

$Q_2 = 16$, $Q = 32$, $P = 28$, $\pi_1 = (28 - 12) \cdot 16 = 16 \cdot 16 = 256$.

Pomocí obecných formulí: efektivní $a = 60 - 12 = 48$ (po posunu o MC), $b = 1$:
$Q_1 = \tfrac{48}{3} = 16$. ✓

### 10.2 Stackelberg — jiná čísla

Stejné zadání jako 10.1, ale firma 1 jde první. Použijme obecný vzorec:

$Q_1 = \tfrac{a}{2b} = 24$ (s posunutým $a$), $Q_2 = \tfrac{a}{4b} = 12$.

$Q = 36$, $P = 60 - 36 = 24$, $\pi_1 = (24 - 12) \cdot 24 = 288$, $\pi_2 = 12 \cdot 12 = 144$.

Lider $Q_1 / Q_2 = 24/12 = 2$ ✓. $\pi_1 / \pi_2 = 288/144 = 2$ ✓.

### 10.3 Koluze — jiná čísla

$P = 60 - Q$, $MC = 12$. Společný monopol: $MR = 60 - 2Q = 12 \Rightarrow Q = 24$,
$P = 36$, $\pi_{tot} = (36 - 12) \cdot 24 = 576$. Rozdělené 50/50: $\pi_1 = \pi_2 = 288$.

Pozor — koluzní zisk firmy 1 (288) je **stejný** jako Stackelbergovský
liderův zisk. Není to náhoda, viz odvozená formule v 7.2.

### 10.4 Asymetrický Cournot — jiná čísla

$P = 60 - Q$, $MC_1 = 0$, $MC_2 = 24$.

Reakční křivky:

$$
Q_1 = \tfrac{60 - 0 - Q_2}{2} = 30 - \tfrac{Q_2}{2},
$$

$$
Q_2 = \tfrac{60 - 24 - Q_1}{2} = 18 - \tfrac{Q_1}{2}.
$$

Průsečík:

$$
Q_1 = 30 - \tfrac{1}{2}(18 - \tfrac{1}{2} Q_1) = 30 - 9 + \tfrac{1}{4} Q_1 = 21 + \tfrac{1}{4} Q_1.
$$

$\tfrac{3}{4} Q_1 = 21 \Rightarrow Q_1 = 28$. $Q_2 = 18 - 14 = 4$. $Q = 32$, $P = 28$.

$\pi_1 = 28 \cdot 28 = 784$. $\pi_2 = (28 - 24) \cdot 4 = 16$.

Levnější firma drží lvi podíl, drahá firma marginalizovaná. Stejný princip jako
v sekci 6.

## 11. Limity modelu a extenze

**Statická hra.** Cournot i Stackelberg jsou jednorázová rozhodnutí. Reálné trhy
jsou opakované — firmy hrají stejnou hru každé období. Repeated game opens dveře
ke koluzi (folk theorem, trigger strategies, tit-for-tat), aniž by formální
kartelová dohoda byla nutná.

**Plná informace.** Předpokládáme, že firmy znají poptávku i náklady konkurenta.
V realitě je to neúplná informace — vede k Bayesovským hrám a signaling.

**Konstantní (nebo známé) MC.** V praxi se MC mění s technologií, kapacitou,
cenami vstupů. Heterogenita MC mění rovnovážné výsledky (sekce 6).

**Homogenní produkt.** Diferenciace mění hru — poptávka pro firmu 1 závisí na
ceně firmy 2 jen částečně. Hotelling-style modely zachycují prostorovou
diferenciaci.

**Konkurence přes množství vs. cenu.** V některých trzích (komodity, kapacitně
omezené odvětví) je $Q$ přirozenou volbou; v jiných (maloobchod, software) je
to $P$. Bertrand (volba ceny) dává radikálně jiné výsledky než Cournot — viz
[[mikk-oligopol-bertrand-cenova-konkurence|Bertrand]].

**Vstup nových firem.** Cournot/Stackelberg modelují $n=2$. Pro $n \to \infty$
se Cournotova rovnováha blíží dokonalé konkurenci ($P \to MC$). Bariéry vstupu
jsou důvod, proč $n$ zůstává nízké.

## 12. Vztah ke zkoušce

V testech ImeK i MikK se objevují tyto typy úloh:

1. **Numerický symetrický Cournot.** Dáno $P = a - bQ$, $MC$, spočítej $Q_i$,
   $P$, $\pi_i$. Postup: napiš $TR_i$, derivuj, dostaneš reakční křivku, dosaď
   symetrii.
2. **Numerický Stackelberg.** Stejná data, ale firma 1 jde první. Postup:
   spočítej followerovu reakční křivku (klasický Cournotův odvod), dosaď do
   $TR_1$, derivuj $TR_1$ podle $Q_1$.
3. **Koluze a srovnání.** Spočítej monopolní zisk pro celý trh, ukáž, že je
   vyšší než $2 \cdot \pi^{Cournot}$, vysvětli nestabilitu kartelu.
4. **Asymetrický Cournot.** S různými MC nebo nákladovými funkcemi. Buď přes
   reakční křivky (sekce 10.4), nebo přes heuristiku $MC_1 = MC_2 = MR$
   v případě monotónně rostoucích MC (sekce 6).
5. **Konceptuální otázky.** Proč first-mover advantage? Proč nestabilita
   koluze? Proč Cournotova rovnováha v $n \to \infty$ konverguje k DK?

V přípravě je rozumné mít **vzorce z tabulky 7.1 nazpaměť** pro $MC = 0$, a
umět je rychle adjustovat na nenulové $MC$ tím, že se pracuje s „efektivním"
$\tilde a = a - MC$ a $\tilde P = P - MC$.

## 13. Cross-reference

- [[mikk|Mikroekonomie 2 (mikK)]] — kurz, do kterého toto téma patří
- [[mikk-oligopol-bertrand-cenova-konkurence|Bertrand — cenová konkurence v duopolu]]
- [[mikk-oligopol-cenovy-vudce-kartel|Cenové vůdcovství a kartely]]
- [[mikk-oligopol-zalomena-poptavka|Zalomená poptávková křivka (Sweezy)]]
- [[mikk-vezno-dilema-teorie-her|Vězňovo dilema a teorie her]] — Nashův koncept
- [[mikk-monopol-pokrocily|Monopol s více závody / cenovou diskriminací]] —
  analogie s heuristikou $MC_1 = MC_2 = MR$
- [[mikk-monopolisticka-konkurence|Monopolistická konkurence]] — sousední tržní
  struktura s velkým $n$
- [[mikk-srovnani-modelu-oligopolu|Srovnání modelů oligopolu]] —
  agregátní přehled
- [[mikk-vzorce-prehled|Přehled vzorců MikK]] — souhrnná stránka pro zkoušku
- [[mikk-vzorove-zkousky|Vzorové zkoušky MikK]]
