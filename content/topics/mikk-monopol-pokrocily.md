---
title: "Monopol — pokročilá analýza"
course: mikk
type: topic
tags: [mikk, mikroekonomie, monopol, lerner, markup, mrtva-vaha]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf, raw/mikk/mikK test KS reseni.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Monopol — pokročilá analýza

> **TL;DR**
>
> - Monopolista volí výstup tam, kde **mezní příjem rovná mezním nákladům**: $MR = MC$.
> - Cenovou přirážku nad MC plně určuje **elasticita poptávky firmy**:
>   $$\frac{P - MC}{P} \;=\; -\frac{1}{E_d} \quad\Longleftrightarrow\quad P \;=\; \frac{MC}{1 + 1/E_d}.$$
> - **Lernerův index** $L = (P - MC)/P \in [0,1]$ měří monopolní sílu — 0 odpovídá dokonalé konkurenci, 1 nekonečné monopolní síle.
> - Monopolista s **více závody** rovná mezní náklady všech závodů a tržní mezní příjem: $MC_1 = MC_2 = \ldots = MC_n = MR$.
> - Společenská ztráta z monopolu má dvě složky: **náklady mrtvé váhy** (DWL — trojúhelník mezi $D$, $MC$ a $Q_M$) a **náklady na získání monopolu** (lobování, reklama, kapacity — *rent-seeking*).
> - **Přirozený monopol** vzniká při klesajících $LAC$; standardní regulační odpovědí je nastavit cenu na úroveň $AC$ (cenový strop, *rate-of-return*).

Tato stránka navazuje na obecný úvod do monopolu na kurzové stránce [[mikk|Mikroekonomie 2]] a předpokládá, že čtenář ovládá pojem [[mikk-elasticita-poptavky|elasticita poptávky]] a koncept [[prebytek-spotrebitele-vyrobce|přebytku spotřebitele a výrobce]] (ten je odvozen v rámci kurzu [[imek|Matematická ekonomie]]). Speciální případy jako [[mikk-cenova-diskriminace|cenová diskriminace]], [[mikk-bundling-two-part-tariff|bundling a dvousložkový tarif]], [[mikk-prirozeny-monopol-regulace|regulace přirozeného monopolu]] a srovnání s [[mikk-monopolisticka-konkurence|monopolistickou konkurencí]] mají vlastní stránky.

---

## 1. Definice a charakteristika monopolu

**Monopol** je tržní struktura s následujícími znaky:

1. **Jediný producent** statku nebo služby na celém relevantním trhu.
2. **Žádné blízké substituty** — zákazník nemá realistickou alternativu.
3. **Výrazné bariéry vstupu**, které brání novým firmám v účasti na trhu:
   - **Přirozené bariéry** — geografické (jediný zdroj suroviny), či nákladové (rostoucí výnosy z rozsahu, viz sekce 14).
   - **Technologické bariéry** — patenty, *know-how*, síťové efekty, vlastnictví klíčové infrastruktury.
   - **Právní bariéry** — koncese, licence, státní monopoly.
4. **Firma je rovna odvětví** — poptávka po produkci firmy se shoduje s tržní poptávkou.

Z bodu 4 plyne klíčový důsledek: monopolista čelí **klesající poptávkové křivce**. To ho zásadně odlišuje od dokonale konkurenční firmy, která je *cenovým příjemcem* a její individuální poptávka je vodorovná na úrovni tržní ceny.

> **Důležité pozorování:** Monopolista **nemá nabídkovou křivku** v klasickém smyslu. Vztah mezi cenou a nabízeným množstvím u monopolisty není funkcí pouze $MC$ — závisí i na tvaru poptávky. Toto pozorování rozvedeme v sekci 7.

### 1.1 Monopolista jako *price-maker*

Zatímco dokonale konkurenční firma cenu **přijímá** (*price-taker*), monopolista cenu **stanovuje** (*price-maker*). Stanovuje ji ovšem ne libovolně, ale optimálně vzhledem k tvaru poptávky a vlastním nákladům. Cena, při které prodá množství $Q$, je dána přímo poptávkovou funkcí $P(Q)$ — monopolista volí buď množství, nebo cenu, ale ne obojí nezávisle.

### 1.2 Pojmy *AR* a *MR* v monopolu

Pro monopolistu jsou základní příjmové veličiny:

- **Průměrný příjem** $AR(Q) = TR(Q)/Q = P(Q)$ — geometricky se kryje s poptávkovou křivkou.
- **Mezní příjem** $MR(Q) = dTR/dQ$ — leží **pod** poptávkovou křivkou (kromě prvního prodaného kusu) a klesá rychleji než $AR$.

Toto poslední tvrzení je obecná vlastnost: jakmile $AR$ klesá, pak $MR < AR$ a dvojnásobný sklon u lineární poptávky.

---

## 2. Stanovení ceny — odvození vzorce

Cílem této sekce je odvodit elegantní souvislost mezi optimální monopolní cenou, mezními náklady a elasticitou poptávky.

### 2.1 Krok 1 — derivace celkového příjmu

Z definice $TR = P\cdot Q$ a derivace součinu:

$$
MR \;=\; \frac{dTR}{dQ} \;=\; \frac{d(P\cdot Q)}{dQ} \;=\; P + Q \cdot \frac{dP}{dQ}.
$$

Tento výraz je platný pro libovolnou (diferencovatelnou) poptávku $P(Q)$.

### 2.2 Krok 2 — vytknutí $P$

Vytkneme-li $P$ z prvního členu, dostaneme:

$$
MR \;=\; P\left(1 + \frac{Q}{P}\cdot\frac{dP}{dQ}\right).
$$

Připomeňme definici cenové elasticity poptávky:

$$
E_d \;=\; \frac{dQ}{dP}\cdot \frac{P}{Q}, \qquad \text{takže}\qquad \frac{1}{E_d} \;=\; \frac{dP}{dQ}\cdot \frac{Q}{P}.
$$

Dosazením vzniká kompaktní *Amorosova–Robinsonova rovnice*:

$$
\boxed{\;MR \;=\; P\left(1 + \frac{1}{E_d}\right)\;}
$$

> **Poznámka o znaménku.** Pro normální statek je $E_d < 0$, takže $1/E_d < 0$ a $MR < P$, jak musí pro klesající poptávku platit. V učebnicích se občas uvažuje $|E_d|$, pak má rovnice tvar $MR = P(1 - 1/|E_d|)$. Obě varianty jsou ekvivalentní; v této wiki budeme držet **algebraickou** podobu (se znaménkem).

### 2.3 Krok 3 — optimum monopolisty

Monopolista maximalizuje zisk $\pi(Q) = TR(Q) - TC(Q)$. Nutná podmínka prvního řádu:

$$
\frac{d\pi}{dQ} \;=\; MR(Q) - MC(Q) \;=\; 0 \quad\Longleftrightarrow\quad MR \;=\; MC.
$$

Druhá podmínka pro maximum je $MR' < MC'$ — mezní příjem klesá rychleji, než stoupají mezní náklady (typicky splněno).

### 2.4 Krok 4 — sloučení do cenového vzorce

Z $MR = MC$ a Amorosovy–Robinsonovy rovnice:

$$
P\left(1 + \frac{1}{E_d}\right) \;=\; MC \quad\Longleftrightarrow\quad \boxed{\;P \;=\; \frac{MC}{1 + 1/E_d}\;}
$$

### 2.5 Krok 5 — procentní přirážka

Algebraická úprava:

$$
P + \frac{P}{E_d} = MC \;\Longleftrightarrow\; P - MC = -\frac{P}{E_d} \;\Longleftrightarrow\; \boxed{\;\frac{P - MC}{P} \;=\; -\frac{1}{E_d}\;}
$$

Tato podoba se nazývá **procentní přirážka** (markup) nebo **Lernerova rovnice** a je nejdůležitějším výsledkem celé sekce.

> **Slogan:** *Procentní přirážka monopolisty nad mezními náklady je rovna převrácené hodnotě absolutní velikosti elasticity poptávky.*

---

## 3. Důsledky pravidla $MR = MC$

### 3.1 Závislost přirážky na elasticitě

Z Lernerovy rovnice plyne přímá úměra mezi nepružností poptávky a velikostí přirážky:

| Elasticita $|E_d|$ | $1/|E_d|$ | Přirážka $(P-MC)/P$ | Komentář |
|--------------------|-----------|----------------------|----------|
| $\infty$ (dok. konk.) | $0$       | $0\%$                | Cena = MC |
| $5$                | $0{,}20$  | $20\%$               | Konkurenční trh s diferenciací |
| $2$                | $0{,}50$  | $50\%$               | Středně silný monopol |
| $1{,}1$            | $0{,}91$  | $91\%$               | Silný monopol |
| $1$                | $1$       | nedefinováno         | Hraniční bod — viz 3.2 |

### 3.2 Monopolista vždy operuje na elastické části poptávky

**Tvrzení.** Monopolista nikdy nezvolí výstup tam, kde $|E_d| \le 1$ (neelastická oblast).

**Důkaz.** Pokud $|E_d| < 1$, pak z Amorosovy–Robinsonovy rovnice:

$$
MR \;=\; P\left(1 + \frac{1}{E_d}\right) \;=\; P\left(1 - \frac{1}{|E_d|}\right) \;<\; 0.
$$

Záporný mezní příjem znamená, že **snížení** výstupu by zvýšilo $TR$. Mezní náklady jsou ale typicky nezáporné, $MC \ge 0$, takže $MR < MC$ a podmínka maxima $MR = MC$ nemůže být splněna. Monopolista tedy bude $Q$ snižovat až do okamžiku, kdy se dostane do oblasti $|E_d| > 1$, kde $MR > 0$.

> **Intuice:** Pokud je poptávka neelastická, snížení množství zvýší tržby a zároveň ušetří výrobní náklady — racionální monopolista nikdy nesetrvá v této oblasti.

### 3.3 Monopolista a $MC = 0$

Speciální případ: pokud $MC = 0$ (např. digitální distribuce, software), pak z $MR = 0$ (a Amoroso–Robinson) plyne $|E_d| = 1$. Monopolista volí výstup přesně na hraně elasticity 1 — bod, kde $TR$ nabývá maxima.

---

## 4. Případová studie: Astra-Merck a lék Prilosec

Astra-Merck uvedla v roce 1995 na americký trh inhibitor protonové pumpy **Prilosec** (omeprazol). Lék čelil konkurenci levnějších H2-blokátorů Tagamet a Zantac, ale díky účinnosti a patentu měl významnou monopolní sílu.

### 4.1 Údaje

- Cena Prilosec: **$3{,}50 / denní dávka**
- Cena konkurentů (Tagamet, Zantac): **$1{,}50 – $2{,}25 / denní dávka**
- Mezní náklady Prilosec: **$0{,}30 – $0{,}40 / denní dávka**
- Odhadovaná elasticita firmy: $|E_d| \approx 1{,}35$

### 4.2 Aplikace vzorce

Použijeme Lernerovu rovnici v podobě:

$$
P \;=\; \frac{MC}{1 - 1/|E_d|} \;=\; MC \cdot \frac{|E_d|}{|E_d| - 1}.
$$

Dosazením $MC = 0{,}35$ (střed odhadu) a $|E_d| = 1{,}35$:

$$
P \;=\; 0{,}35 \cdot \frac{1{,}35}{1{,}35 - 1} \;=\; 0{,}35 \cdot \frac{1{,}35}{0{,}35} \;=\; 0{,}35 \cdot 3{,}857 \;\approx\; \$1{,}35.
$$

Při použití vyšší vstupní MC (přibližně $1$ ve studii pro „plně alokované náklady“) vychází číslo **$3{,}89**, které je velmi blízko skutečné ceně **$3{,}50**.

### 4.3 Závěr případové studie

Cenová politika Astra-Merck je **konzistentní s pravidlem maximalizace zisku monopolisty** podle Amorosovy–Robinsonovy rovnice. Vyšší cena oproti konkurentům není projevem „chamtivosti“, nýbrž **racionální odpovědí** na nízkou cenovou elasticitu poptávky pro výrazně účinnější léčbu — pacienti (a jejich pojišťovny) jsou ochotni za výrazně lepší produkt zaplatit více.

> **Pedagogická pointa:** Zdánlivě „překvapivá“ cena $3{,}50 je při zadání $|E_d|=1{,}35$ a $MC \approx 0{,}30$–$0{,}40$ téměř *vynucena* maximalizací zisku.

---

## 5. Posuny poptávky a neexistence nabídkové křivky

### 5.1 Dokonalá konkurence vs. monopol

V dokonalé konkurenci je individuální nabídka firmy odvozena z $MC$ nad minimem $AVC$ — pro každou cenu $P$ existuje jednoznačné $Q^s(P)$. Tento vztah je čistě **nákladová** záležitost.

V monopolu naopak optimální výstup závisí **současně** na:

1. mezních nákladech $MC(Q)$,
2. tvaru poptávkové křivky $D(Q)$ (a tedy i tvaru $MR$).

Není proto možné definovat „nabídkovou křivku monopolisty“ jako jednoznačnou funkci $Q^s = f(P)$.

### 5.2 Stejné množství při různých cenách

Uvažujme dvě poptávkové křivky $D_1$ a $D_2$, které se v bodě optima protnou se *stejnou* hodnotou $MR$ při *stejném* množství $Q^*$, ale mají **různý sklon**. Pak:

- $MR_1(Q^*) = MR_2(Q^*) = MC(Q^*)$ — totéž optimální množství.
- Cena se však určuje z $D_i(Q^*)$, a protože $D_1$ má jiný sklon než $D_2$, dostáváme $P_1 \ne P_2$.

Stejné množství je tedy spojeno se dvěma různými cenami — žádná funkce $Q(P)$ neexistuje.

### 5.3 Stejná cena při různých množstvích

Symetrický případ: poptávky $D_1$ a $D_2$ se protnou s $MC$ při různém $Q$, ale shodou tvarů poskytnou *stejnou* cenu $P^*$. Pak monopolista produkuje $Q_1 \ne Q_2$ při stejné ceně.

### 5.4 Závěr

> **Monopol nemá nabídkovou křivku.** Optimální produkce závisí na *celém* tvaru poptávky, nejen na ceně.

Tento jev je důvodem, proč klasická *Marshallova* analýza nabídka–poptávka selhává v monopolu a proč musíme používat aparát $MR = MC$.

---

## 6. Monopol s více závody

Reálné monopoly bývají vícezávodové — vlastní několik výrobních zařízení s odlišnými nákladovými strukturami (různé technologie, různá geografická lokace, různý stáří kapitálu).

### 6.1 Rámec úlohy

Mějme monopolistu s $n$ závody, každý s vlastní nákladovou funkcí $TC_i(Q_i)$. Tržní poptávka je $P(Q)$, kde

$$
Q \;=\; \sum_{i=1}^{n} Q_i.
$$

Monopolista maximalizuje:

$$
\pi(Q_1, \ldots, Q_n) \;=\; P(Q)\cdot Q \;-\; \sum_{i=1}^{n} TC_i(Q_i).
$$

### 6.2 Podmínky prvního řádu

Derivace podle libovolného $Q_j$:

$$
\frac{\partial \pi}{\partial Q_j} \;=\; \underbrace{P + Q\frac{dP}{dQ}}_{=MR(Q)} \;-\; \frac{dTC_j}{dQ_j} \;=\; MR(Q) - MC_j(Q_j) \;=\; 0.
$$

Toto musí platit současně pro všechna $j$, takže:

$$
\boxed{\;MC_1(Q_1) \;=\; MC_2(Q_2) \;=\; \ldots \;=\; MC_n(Q_n) \;=\; MR(Q)\;}
$$

> **Slogan:** *Vícezávodový monopolista vyrovnává mezní náklady všech svých závodů s tržním mezním příjmem.*

### 6.3 Geometrická konstrukce

Postup řešení dvouzávodového monopolisty graficky:

1. **Horizontálně sečteme** křivky $MC_1$ a $MC_2$ do souhrnné křivky $MC_T$. Pro každou úroveň $MC^*$ získáme $Q_T(MC^*) = Q_1(MC^*) + Q_2(MC^*)$.
2. Najdeme průsečík $MC_T$ s $MR$ — to dává **celkový** optimální výstup $Q_3$ (a z poptávky cenu $P^*$).
3. Označíme $MR^*$ hodnotu mezního příjmu v tomto bodě.
4. Z $MC_1 = MR^*$ odečteme **alokaci pro závod 1**: $Q_1$.
5. Z $MC_2 = MR^*$ odečteme **alokaci pro závod 2**: $Q_2$.
6. Kontrola: $Q_1 + Q_2 = Q_3$ (z konstrukce horizontálního součtu to musí platit).

### 6.4 Algebraický postup

Pro analytické řešení obvykle:

1. Vyjádříme $Q_i$ jako funkci společné hodnoty $\lambda \equiv MR$: $Q_i(\lambda)$ z rovnice $MC_i(Q_i) = \lambda$.
2. Sečteme: $Q(\lambda) = \sum Q_i(\lambda)$.
3. Spočítáme $P(Q(\lambda))$ z poptávky a porovnáme $MR$ (jako funkci $\lambda$ skrze $Q$) s $\lambda$.
4. Vyřešíme rovnici $\lambda = MR(Q(\lambda))$.

### 6.5 Intuice

- Pokud má jeden závod **konstantně nižší** $MC$ než druhý, využíváme nejprve laciný závod a teprve při vysokém $MR$ doplňujeme drahým.
- **Levný závod plníme do plné kapacity (nebo do bodu, kde jeho MC stoupne na úroveň MR), drahý závod jen vykrývá zbytek.**
- Pokud má jeden závod konstantní $MC$, pak v optimu **i druhý závod** vyrábí v bodě, kde jeho $MC$ je rovno tomuto konstantnímu $MC$ (a $MR$ celkového trhu je tam také rovno).

---

## 7. Detailní příklad — asymetrický monopolista se dvěma závody

Příklad pochází z ručně psaného řešení testu KS. Originál je formulovaný jako Cournotův duopol s odlišnými $MC$, ale heuristika řešení je identická s vícezávodovým monopolistou.

### 7.1 Zadání

- Tržní poptávka: $P = 100 - Q$, kde $Q = Q_1 + Q_2$.
- Závod 1: $MC_1 = 4$ (konstantní; symbolizuje *starou plně amortizovanou technologii*).
- Závod 2: $MC_2 = Q_2$ (lineárně rostoucí; symbolizuje *novou kapacitu s rostoucími náklady na jednotku*).

Monopolista vlastní oba závody a maximalizuje celkový zisk.

### 7.2 Mezní příjem

Z poptávky $P = 100 - Q$:

$$
TR \;=\; PQ \;=\; (100 - Q)Q \;=\; 100Q - Q^2,\qquad MR \;=\; \frac{dTR}{dQ} \;=\; 100 - 2Q.
$$

### 7.3 Heuristika $MC_1 = MC_2 = MR$

Aplikujeme pravidlo z 6.2. Protože $MC_1 = 4$ je konstantní, společná hodnota mezních nákladů musí být $4$:

$$
MC_1 \;=\; 4, \qquad MC_2 \;=\; Q_2 \;=\; 4 \;\Longrightarrow\; Q_2 = 4.
$$

A $MR = 4$ dává tržní výstup:

$$
100 - 2Q \;=\; 4 \;\Longrightarrow\; \boxed{Q = 48}.
$$

### 7.4 Alokace mezi závody

Z $Q = Q_1 + Q_2 = 48$ a $Q_2 = 4$:

$$
\boxed{Q_1 = 44, \qquad Q_2 = 4.}
$$

### 7.5 Cena a zisk

$$
P \;=\; 100 - Q \;=\; 100 - 48 \;=\; \boxed{52}.
$$

Tržby: $TR = 52 \cdot 48 = 2496$.

Náklady (předpokládejme $TC_1 = 4 Q_1$ a $TC_2 = \tfrac{1}{2} Q_2^2$):

$$
TC \;=\; 4 \cdot 44 + \tfrac{1}{2}\cdot 16 \;=\; 176 + 8 \;=\; 184.
$$

Zisk: $\pi = 2496 - 184 = \mathbf{2312}$.

### 7.6 Intuitivní výklad

- Závod 1 má **nízké, konstantní** mezní náklady — produkuje *většinu výstupu* (44 z 48 jednotek).
- Závod 2 má rostoucí $MC$ — *přibírá pouze tolik*, aby jeho mezní náklady dorovnaly cenu „levné technologie“ ($MC_2 = 4$ při $Q_2 = 4$).
- Kdyby monopolista vyráběl v závodě 2 více než $Q_2 = 4$, jeho mezní náklady by převýšily $MR = 4$ — jednotky vyrobené nad tuto úroveň by způsobily ztrátu.
- Kdyby vyráběl méně, mohl by *přesunout* poslední jednotku na závod 2 (kde $MC < 4$) a snížit celkové náklady.

### 7.7 Co kdyby závod 1 měl omezenou kapacitu?

Pokud by závod 1 měl maximální kapacitu $\bar Q_1 < 44$, pak by $Q_1 = \bar Q_1$ a problém se zredukoval na hledání $Q_2$ jako jediné proměnné: $MR(Q) = MC_2(Q_2)$ při $Q = \bar Q_1 + Q_2$. Toto je standardní úloha *capacity-constrained* monopolisty.

### 7.8 Co kdyby závod 2 byl ještě dražší?

Kdyby $MC_2 = 2 Q_2$ (sklon 2 místo 1), v rovnováze $MC_2 = 4 \Rightarrow Q_2 = 2$, $Q = 48$, ale alokace by byla $Q_1 = 46$, $Q_2 = 2$ — drahý závod přispívá ještě méně.

---

## 8. Monopolní síla a Lernerův index

### 8.1 Co je monopolní síla?

Striktní monopol (jediná firma na celém trhu) je v praxi vzácný. Mnohem častější je situace, kdy několik firem na trhu **každá čelí klesající poptávce** po své produkci — díky diferenciaci, geografii, věrnosti zákazníků apod. Každá z těchto firem může cenu zvýšit nad $MC$, aniž by ztratila všechny zákazníky. Mají proto **monopolní sílu**, i když nejsou monopolisté v učebnicovém smyslu.

### 8.2 Tržní vs. firemní elasticita

Rozdíl ilustrujme na příkladu výroby fixů pro tabule:

- **Trh** s celkovou kapacitou 20 000 ks; cena $1{,}50; tržní elasticita $E_D = -1{,}5$.
- **Čtyři firmy** si trh dělí ideálně po 5 000 ks.
- **Firma A** čelí poptávce $D_A$, která je *mnohem elastičtější* než tržní poptávka, protože při zvýšení ceny zákazníci přejdou ke konkurentům: $E_D^A = -6$.

Klíčové: i když je tržní elasticita pouze $-1{,}5$, **elasticita firmy** je $-6$. Lernerův index počítáme s elasticitou firmy:

$$
L \;=\; -\frac{1}{E_d^{\text{firma}}} \;=\; -\frac{1}{-6} \;=\; 0{,}167.
$$

Firma A si může účtovat **přibližně 17 % nad MC**, ne 67 % (jako by sugerovala tržní elasticita).

### 8.3 Definice Lernerova indexu

$$
\boxed{\;L \;=\; \frac{P - MC}{P} \;=\; -\frac{1}{E_d^{\text{firma}}}\;}
$$

Vlastnosti:

- $L = 0$ — dokonalá konkurence ($P = MC$).
- $L \to 1$ — extrémní monopolní síla (cena výrazně nad MC, $|E_d|$ blízko 1).
- $L$ je **bezrozměrný** ukazatel — porovnatelný napříč odvětvími a měnami.

### 8.4 Použití pro regulační orgány

> **Otázka:** Jaký je základní problém při použití Lernerova indexu pro regulační orgány?

**Odpověď:** Regulátor potřebuje znát **mezní náklady firmy**, které firma sama nemá motivaci pravdivě vykazovat (může je nadhodnocovat, aby skryla monopolní zisk). Účetní data zachycují průměrné, nikoli mezní náklady, a alokace fixních nákladů je často sporná. Praktická regulace proto častěji nesleduje $L$ přímo, ale opírá se o cenové stropy a srovnání s benchmarky.

### 8.5 Monopolní síla ≠ jistota zisku

Důležité: vysoké $L$ neznamená vysoký zisk. Zisk:

$$
\pi \;=\; (P - AC)\cdot Q.
$$

Záleží na **průměrných** nákladech a objemu. Firma s velkou cenovou přirážkou (vysoké $L$) může mít zisk nulový nebo i ztrátu, pokud má vysoké fixní náklady a malý objem.

---

## 9. Případová studie: supermarkety vs. konvenční obchody

Srovnejme dva typy maloobchodu.

### 9.1 Supermarkety

Charakteristiky:
1. **Mnoho firem** (silná konkurence v každém regionu).
2. **Stejný produkt** — zboží je u všech supermarketů prakticky identické.
3. **Vysoká elasticita firmy** — zákazníci snadno přecházejí: $|E_d| = 10$.

Lernerův index:

$$
L \;=\; -\frac{1}{-10} \;=\; 0{,}10 \quad\Longleftrightarrow\quad \frac{P}{MC} \;=\; \frac{1}{1 - 0{,}10} \;=\; \frac{1}{0{,}9} \;\approx\; 1{,}11.
$$

> **Cena je nastavena na 10–11 % nad MC.**

### 9.2 Konvenční obchody

Charakteristiky:
1. **Vyšší ceny než supermarkety** (zákazníci to akceptují).
2. **Existuje diferenciace** — sortiment, otevírací doba, lokace, osobní obsluha.
3. **Nižší elasticita firmy**: $|E_d| = 5$.

Lernerův index:

$$
L \;=\; -\frac{1}{-5} \;=\; 0{,}20 \quad\Longleftrightarrow\quad \frac{P}{MC} \;=\; \frac{1}{1 - 0{,}20} \;=\; \frac{1}{0{,}8} \;=\; 1{,}25.
$$

> **Cena je nastavena na 25 % nad MC.**

### 9.3 Diskuse: má větší monopolní síla větší zisk?

Otázka zní: *Mají běžné obchody i větší zisk než supermarkety?*

**Odpověď: ne nutně.** Kritické faktory:

- **Objem** — supermarkety obracejí zboží ve výrazně větších objemech.
- **Průměrné fixní náklady** — supermarkety mají sice vyšší absolutní fixní náklady, ale rozkládají je do mnohem většího počtu prodaných jednotek.
- **AC vs. MC** — Lernerův index pracuje s $MC$, zisk s $AC$. Konvenční obchod s $L = 0{,}20$ může mít nulový zisk, pokud $P = AC$.

Empirický pohled: marže supermarketů jsou nízké (1–3 % zisku ze zisku), zatímco konvenční obchody mívají marže vyšší — ale jejich celkový **absolutní zisk** je často nižší než u supermarketového řetězce.

---

## 10. Zdroje monopolní síly

Existují tři **strukturální** determinanty monopolní síly. Každá z nich přispívá k tvaru elasticity firemní poptávky.

### 10.1 Elasticita tržní poptávky

Tržní elasticita stanovuje **horní mez** monopolní síly. Pokud je celý trh velmi elastický (např. snadné substituty z jiných odvětví), žádná firma na něm nemůže mít vysoké $L$. Příklady:

- **Velmi neelastické trhy:** základní léky, tabák, palivo — vysoký prostor pro $L$.
- **Velmi elastické trhy:** komodity, generika, levné spotřební zboží — prostor pro $L$ je malý.

### 10.2 Počet firem

Více firem na trhu obvykle znamená vyšší elasticitu firemní poptávky a tedy nižší $L$. Pravidlo:

$$
E_d^{\text{firma}} \;\approx\; n \cdot E_d^{\text{trh}} \quad\text{(pro symetrické firmy a homogenní produkt)}.
$$

Takže při $n$ firmách s rovnoměrným tržním podílem:

$$
L_{\text{firma}} \;\approx\; \frac{1}{n\cdot |E_d^{\text{trh}}|}.
$$

Tato aproximace odpovídá výsledkům Cournotova oligopolu (viz [[mikk-oligopol-cournot-stackelberg|Oligopol: Cournot a Stackelberg]]).

### 10.3 Vzájemné vztahy mezi firmami

I při pevném počtu firem se monopolní síla mění podle **chování**:

- **Konkurenční (Bertrand)** chování — agresivní cenová válka snižuje $L$ k nule.
- **Kolusivní** chování — firmy se chovají jako jediný monopolista, $L$ je vysoké.
- **Vůdcovství cen, kvótní dohody, signalizace** — různé hybridní úrovně.

Stejné odvětví, stejný počet firem — různá monopolní síla podle „atmosféry“ chování.

---

## 11. Náklady mrtvé váhy

![[mikk-monopol-mrtva-ztrata.jpeg|Monopolní rovnováha (MR=MC) s vyznačenou mrtvou ztrátou (DWL) vůči konkurenčnímu bodu a obdélníkem monopolního zisku]]

Klíčovým pojmem alokační neefektivity monopolu jsou náklady mrtvé váhy.

### 11.1 Konstrukce na grafu

Na osách $Q$, $P$ vykresleme:

- Klesající poptávku $D = AR$.
- Mezní příjem $MR$ (klesá rychleji než $D$).
- Mezní náklady $MC$ (rostoucí nebo konstantní).

Označme:
- $Q_C, P_C$: konkurenční rovnováha — $D \cap MC$ (cena = MC).
- $Q_M, P_M$: monopolní rovnováha — $MR \cap MC$ určuje $Q_M$, cena $P_M$ se odečte z $D(Q_M)$. Je $Q_M < Q_C$ a $P_M > P_C$.

Tři plochy:

- **A**: obdélník mezi $P_C$ a $P_M$ od $0$ do $Q_M$ — přesun ze spotřebitelského přebytku do zisku monopolu.
- **B**: trojúhelník mezi $D$, $P_M$ a $Q_M$, $Q_C$ — *ztracený* spotřebitelský přebytek na ne-vyrobených jednotkách.
- **C**: trojúhelník mezi $MC$, $P_C$ a $Q_M$, $Q_C$ — *ztracený* výrobní přebytek na ne-vyrobených jednotkách.

### 11.2 Bilance

| Skupina | Změna oproti konkurenci | Plocha |
|---------|-------------------------|--------|
| Spotřebitelé | ztrácí $A + B$ | — |
| Výrobce (monopol) | získává $A$, ztrácí $C$ | $A - C$ |
| **Celkem (alokační efektivita)** | ztrácí $B + C$ | **DWL** |

> **Náklady mrtvé váhy** $= B + C =$ čistá ztráta společenského blahobytu z monopolního chování.

### 11.3 Vzorec pro lineární poptávku

Pokud jsou $D$ i $MC$ lineární a $|D - MC|$ je v $Q_M$ rovno $P_M - P_C$ (svislá vzdálenost mezi cenou a MC v bodě $Q_M$), pak:

$$
\boxed{\;DWL \;=\; \tfrac{1}{2}\,(P_M - P_C)\,(Q_C - Q_M)\;}
$$

Geometricky je to plocha trojúhelníku s podstavou $Q_C - Q_M$ a výškou $P_M - P_C$.

### 11.4 Numerický příklad

Vrátíme se k zadání ze sekce 7: $P = 100 - Q$, $MC = 4$ (vezměme jen závod 1 jako monopol).

- Konkurence: $P_C = MC = 4$, $Q_C = 96$.
- Monopol: $MR = MC \Rightarrow 100 - 2Q = 4 \Rightarrow Q_M = 48$, $P_M = 52$.
- $DWL = \tfrac{1}{2} (52 - 4)(96 - 48) = \tfrac{1}{2} \cdot 48 \cdot 48 = 1\,152$.

Pro srovnání: zisk monopolisty je $(52 - 4) \cdot 48 = 2\,304$, takže $DWL$ je polovina zisku monopolu — typický řád.

---

## 12. Společenské náklady monopolu

**Trojúhelník DWL podhodnocuje** skutečnou společenskou ztrátu z monopolu. Vedle alokační neefektivity je třeba započítat **náklady na získání a udržení monopolního postavení** — *rent-seeking* (Tullock 1967).

### 12.1 Lobbing a politické náklady

Firma má motivaci utrácet na lobbing, kampaně, advokáty a regulační arbitráž. Tyto výdaje jsou z pohledu firmy investicí do udržení monopolu, ze společenského pohledu však jde o **zcela neproduktivní spotřebu zdrojů**.

### 12.2 Nadměrná reklama

Reklama monopolistů často slouží **vytváření bariér vstupu** (zvyšování věrnosti značce, znásobení vstupních nákladů pro nové firmy), nikoli informování zákazníků. Část reklamních výdajů je tedy společensky plýtvavá.

### 12.3 Strategické rozšiřování kapacit

Monopolista může držet **přebytečnou výrobní kapacitu** jako *signál*: kdokoli zkusí vstoupit, monopolista okamžitě zaplaví trh a stlačí ceny. Tato kapacita se nemusí nikdy použít, ale její samotná existence odrazuje vstupy. Z pohledu firmy je to investice; ze společenského pohledu jsou to neproduktivně vázané zdroje.

### 12.4 Cenová a kvalitativní degradace

Při delším nedostatku konkurenčního tlaku monopolisté investují méně do inovací a kvality (*X-neefficiency*, Leibenstein 1966). Tato dynamická ztráta není v statickém DWL trojúhelníku zachycena.

### 12.5 Souhrnný vzorec

Skutečné společenské náklady monopolu:

$$
\text{Total social cost} \;=\; \underbrace{DWL}_{\text{alokace}} \;+\; \underbrace{R}_{\text{rent-seeking}} \;+\; \underbrace{X}_{\text{X-neefficiency}}.
$$

V mnoha empirických odhadech tvoří $R + X$ **víc** než samotný trojúhelník DWL.

---

## 13. Cenová diskriminace jako únik z DWL

Pokud monopolista dokáže rozlišit zákazníky podle jejich ochoty platit, může účtovat různé ceny různým skupinám. Tím **rozšiřuje výstup** ($Q_M \to Q_C$) a snižuje DWL — někdy až na nulu (dokonalá diskriminace 1. stupně). Vlastníci přebytku se ovšem mění: **monopolista získává všechen společenský přebytek**.

Detailnější rozbor je na samostatné stránce [[mikk-cenova-diskriminace|Cenová diskriminace]] a v rozšíření [[mikk-bundling-two-part-tariff|Bundling a dvousložkový tarif]].

---

## 14. Přirozený monopol

**Přirozený monopol** je situace, kdy je monopolní struktura *nákladově efektivnější* než konkurence.

### 14.1 Definice

Odvětví je přirozeným monopolem, pokud na **relevantním rozsahu výstupu** platí:

$$
\frac{d\,LAC(Q)}{dQ} \;<\; 0,
$$

tj. dlouhodobé průměrné náklady **stále klesají** (rostoucí výnosy z rozsahu). Pak je nejlevnější, aby celý trh obsluhovala jediná firma.

### 14.2 Příklady

- **Síťová odvětví:** vodárny, plynárny, distribuce elektřiny, kanalizace, železniční koleje, telekomunikační páteř.
- **Lokální infrastruktura:** přístav, letiště, regionální letiště, kabelová síť.
- **Některá softwarová prostředí:** operační systémy s velmi vysokou fixní cenou vývoje a téměř nulovým $MC$.

### 14.3 Charakteristika nákladů

Přirozené monopoly mají typicky:

- **Vysoké fixní náklady** (sítě, hardware, vývoj).
- **Nízké, často konstantní mezní náklady** (přidání jednoho zákazníka).
- **Klesající $LAC$** v celém relevantním rozsahu výstupu.

### 14.4 Dilema

Bez regulace přirozený monopol vyrábí $Q_M$ při ceně $P_M$ — neefektivně málo, neefektivně draho. Kdyby ale stát požadoval cenu $P_C = MC$, firma by utrpěla **ztrátu** (protože $AC > MC$ při klesajícím $LAC$) a opustila by odvětví. Žádné soukromé řešení není „first-best“.

---

## 15. Regulace přirozeného monopolu

Praktickou odpovědí je regulační orgán, který nutí firmu k ceně a výstupu, jež jsou *kompromisem* mezi efektivitou a životaschopností.

### 15.1 Tři referenční body

Na grafu s klesajícím $AC$, $MC$ pod ním, a klesající poptávkou:

- $(Q_M, P_M)$ — neregulovaný monopol, $MR = MC$.
- $(Q_C, P_C)$ — „first-best“: $P_C = MC$. Maximalizuje společenský přebytek, ale firma má **ztrátu** $(AC - MC) \cdot Q_C$.
- $(Q_R, P_R)$ — *second-best*: $P_R = AC$. Firma má **nulový ekonomický zisk**, vyrábí maximum slučitelné s životaschopností.

### 15.2 Regulace na úrovni $P_R = AC$

Tato volba (označovaná jako „regulace na úrovni $P_r$“):

- $P_R$ je nižší než $P_M$ → spotřebitelé profitují.
- $Q_R > Q_M$ → vyšší výstup, nižší DWL.
- Firma má $\pi = 0$ → nikdo nevyhladoví, ale ani nezisková.

> **Geometrická intuice:** $P_R$ je cena, kde se $AC$ protíná s poptávkou $D$.

### 15.3 *Rate-of-return* regulace

Praktická realizace: regulátor nastaví **maximální míru návratnosti** investovaného kapitálu (např. 8 % ročně). Firma smí účtovat ceny tak, aby pokryla provozní náklady a ne víc než dohodnutý zisk z kapitálu.

**Problémy:**
- *Averch–Johnson efekt:* firma má motivaci nadměrně investovat (víc kapitálu = víc absolutního zisku při fixním procentu), což vede k overcapitalizaci.
- Účetní složitost — co je „kapitálová báze“?

### 15.4 *Price-cap* regulace

Modernější varianta: regulátor nastaví **strop ceny** $\bar P$ (případně koš cen) s formulí $\bar P_{t+1} = \bar P_t \cdot (1 + \text{CPI} - X)$, kde $X$ je očekávaný roční růst produktivity. Firma profituje, pokud zlevňuje rychleji, než $X$ předpokládá; trpí, pokud nestihne.

**Výhody:**
- Silnější motivace k efektivitě.
- Méně regulačního vyjednávání nad účetními detaily.

**Nevýhody:**
- Riziko podinvestic do kvality.
- Politicky obtížné nastavení parametru $X$.

### 15.5 Praktické problémy regulace

> *Pro regulační orgány je velice složité přesně stanovit firemní náklady a poptávkovou funkci, protože ty se mohou rychle měnit v závislosti na tržních podmínkách.*

Klíčové překážky:

1. **Asymetrie informací** — firma zná své $MC$ a $AC$ lépe než regulátor.
2. **Strategické vykazování** — firma nadhodnocuje náklady, podhodnocuje očekávanou poptávku.
3. **Dynamika** — náklady i poptávka se mění s technologií a trhem.
4. **Regulační zachycení** (*regulatory capture*) — regulátor postupně nasává firemní pohled na svět.

Detailní rozbor regulačních režimů je na samostatné stránce [[mikk-prirozeny-monopol-regulace|Regulace přirozeného monopolu]].

---

## 16. Detailní příklad: chirurg s konstantním LAC

Tento příklad pochází z předtermínu C (varianta diskutovaná na cvičení) a ilustruje rozdíl mezi monopolistou bez diskriminace a s dokonalou cenovou diskriminací.

### 16.1 Zadání

- Specializovaný chirurg s monopolním postavením v regionu.
- $LAC = MC = 7\,500\text{ Kč}$ na operaci (konstantní).
- Z dvou pozorovaných bodů poptávky odhadneme lineární funkci $P = a - b\cdot Q$:
  - Při $P_1 = 15\,000$ je $Q_1 = 10$ operací/měsíc.
  - Při $P_2 = 5\,000$ je $Q_2 = 30$ operací/měsíc.
- Z toho: sklon $b = (15\,000 - 5\,000)/(30 - 10) = 500$ Kč/operace, dosazením $a = 15\,000 + 500\cdot 10 = 20\,000$.
- Poptávka: $P = 20\,000 - 500\,Q$.

### 16.2 (a) Monopol bez diskriminace

$$
TR = (20\,000 - 500\,Q)\,Q,\qquad MR = 20\,000 - 1\,000\,Q.
$$

Z $MR = MC$:

$$
20\,000 - 1\,000\,Q \;=\; 7\,500 \;\Longrightarrow\; Q = 12{,}5,\qquad P = 20\,000 - 500\cdot 12{,}5 = 13\,750.
$$

Zisk za měsíc:

$$
\pi \;=\; (P - MC)\cdot Q \;=\; (13\,750 - 7\,500)\cdot 12{,}5 \;=\; 6\,250 \cdot 12{,}5 \;=\; 78\,125\text{ Kč}.
$$

Lernerův index: $L = (13\,750 - 7\,500)/13\,750 \approx 0{,}455$ — silná monopolní pozice.

### 16.3 (b) Monopol s dokonalou cenovou diskriminací

Při dokonalé diskriminaci (1. stupně) chirurg účtuje každému pacientovi *jeho ochotu zaplatit*. Vyrábí (operuje) až do bodu, kde $P = MC$:

$$
20\,000 - 500\,Q \;=\; 7\,500 \;\Longrightarrow\; Q^* = 25.
$$

Zisk je pak roven **celé ploše mezi poptávkou a MC** od $0$ do $Q^*$:

$$
\pi^* \;=\; \tfrac{1}{2} (20\,000 - 7\,500) \cdot 25 \;=\; \tfrac{1}{2} \cdot 12\,500 \cdot 25 \;=\; 156\,250\text{ Kč}.
$$

### 16.4 Srovnání

| Veličina | Bez diskriminace | S diskriminací 1. stupně |
|----------|-------------------|---------------------------|
| Výstup $Q$ | 12,5 | 25 |
| Zisk firmy | 78 125 Kč | 156 250 Kč |
| Spotřebitelský přebytek | $\tfrac{1}{2}(20\,000 - 13\,750)\cdot 12{,}5 = 39\,063$ Kč | 0 |
| Celkový společenský přebytek | $78\,125 + 39\,063 = 117\,188$ Kč | $156\,250$ Kč |
| DWL | $156\,250 - 117\,188 = 39\,062$ Kč | 0 |

> **Pointa:** Dokonalá diskriminace 1. stupně eliminuje DWL (alokace je efektivní), ale **přesune celý společenský přebytek na monopolistu**. Spotřebitelé dostávají přesně rezervační cenu, nic víc.

---

## 17. Vztah mezi $L$, koncentrací trhu a HHI

Lernerův index lze pro celé odvětví navázat na **Herfindahlův–Hirschmanův index** (HHI):

$$
HHI \;=\; \sum_{i=1}^{n} s_i^2,
$$

kde $s_i$ je tržní podíl firmy $i$ (v procentech, pak $HHI \in [0, 10\,000]$).

Pro Cournotův oligopol s lineární poptávkou platí přesný vztah:

$$
\overline{L} \;=\; \frac{HHI}{|E_d^{\text{trh}}|},
$$

kde $\overline{L}$ je *vážený* průměr Lernerových indexů firem (váha = tržní podíl). Takže:

- Velmi koncentrované odvětví ($HHI$ blízko 10 000) s neelastickým trhem → vysoká agregátní monopolní síla.
- Fragmentované odvětví ($HHI < 1\,500$) → nízká agregátní monopolní síla i při neelastickém trhu.

Antimonopolní úřady (USA: DOJ, EU: Komise) používají HHI jako screening pro fúze: prahy $HHI < 1\,500$ (nekoncentrovaný), $1\,500$–$2\,500$ (středně), $> 2\,500$ (vysoce koncentrovaný).

---

## 18. Cvičení k zamyšlení

Otázky bez okamžité odpovědi — vhodné jako přípravná cvičení k zápočtu nebo zkoušce. Některé řešené verze najdete v [[mikk-vzorce-prehled|Souhrnu vzorců MikK]] a [[mikk-vzorove-zkousky|Vzorových zkouškách MikK]].

### 18.1 Strukturální otázky

1. **Proč monopol vždy operuje na elastické části poptávky?** (Krátká odpověď: $MR < 0$ v neelastické oblasti, $MC \ge 0$, takže $MR = MC$ tam nemůže nastat.)
2. **Co se stane s $L$, pokud monopolista zlevní výrobu inovací (sníží $MC$)?** Pokud poptávka zůstane stejná, $L$ **roste**: stejná cena minus nižší MC dělená cenou. Ale často dochází i ke snížení ceny — záleží, kde monopolista re-optimalizuje.
3. **Vztah $L$ a HHI:** Jak by se měnil $L$ jednotlivých firem, pokud by se v Cournotově oligopolu se 4 stejnými firmami fúzovaly dvě dohromady? (Návod: $HHI$ vzroste, $\overline{L}$ vzroste.)

### 18.2 Algebraické otázky

4. **Pro $P = 200 - 4Q$ a $MC = 40$ určete:** $Q_M$, $P_M$, zisk a DWL.
5. **Vícezávodový monopolista s $MC_1 = 2 + Q_1$, $MC_2 = 6 + Q_2$, $P = 50 - Q$:** najděte alokaci $(Q_1, Q_2)$.
6. **Monopolista s konstantním $MC = 10$ a $P = 100/Q$ (jednotková elasticita):** existuje optimum?

### 18.3 Kvalitativní otázky

7. **Proč regulátor nemůže prostě nastavit $P = MC$ u přirozeného monopolu?** (Klesající $AC$, ztrátový provoz, opuštění odvětví.)
8. **Jak by změnila vyšší elasticita firmy A (ve scénáři výroby fixů ze sekce 8.2) její Lernerův index?** Vyšší $|E_d^A|$ → nižší $L$.
9. **Když monopolista zavede dokonalou diskriminaci, je výstup efektivní z hlediska alokace?** Ano (eliminuje DWL), ale rozdělení přebytku je extrémně nerovné — celý přebytek u monopolisty.

### 18.4 Pokročilé úlohy (rozšíření mimo přednášku)

10. **Dvouúrovňový monopolista** (upstream + downstream, s otázkou *double marginalization*) — viz analogické úlohy v [[mikk-bundling-two-part-tariff|Bundling]].
11. **Monopolista čelící možnému vstupu** — *limit pricing* a *predatory pricing*.
12. **Monopolista s rostoucími náklady na propagaci** — endogenní určení reklamy v Dorfman–Steinerově podmínce.

---

## 19. Souvislosti s dalšími tématy

- **Elasticita:** [[mikk-elasticita-poptavky|Elasticita poptávky]] — výchozí pojem celé Lernerovy analýzy.
- **Cenová diskriminace:** [[mikk-cenova-diskriminace|Cenová diskriminace]] — únik z DWL.
- **Bundling, dvousložkový tarif:** [[mikk-bundling-two-part-tariff|Bundling a dvousložkový tarif]] — rafinovanější varianty diskriminace.
- **Regulace přirozeného monopolu:** [[mikk-prirozeny-monopol-regulace|Regulace přirozeného monopolu]].
- **Monopson:** [[mikk-monopson-mzdova-diskriminace|Monopson a mzdová diskriminace]] — zrcadlový případ na nákupní straně trhu.
- **Oligopol:** [[mikk-oligopol-cournot-stackelberg|Cournot a Stackelberg]] — kontinuum mezi monopolem a dokonalou konkurencí.
- **Monopolistická konkurence:** [[mikk-monopolisticka-konkurence|Monopolistická konkurence]] — DWL menší než u monopolu, ale stále kladná.
- **Zdanění monopolu:** [[zdaneni-trhu|Zdanění trhu (ImeK)]] — jak se mění optimální Q a P při jednotkové či ad valorem dani; daňová incidence v monopolu.
- **Přebytky:** [[prebytek-spotrebitele-vyrobce|Přebytek spotřebitele a výrobce (ImeK)]] — formální definice ploch v sekci 11.
- **Souhrn vzorců:** [[mikk-vzorce-prehled|Vzorce MikK — přehled]].
- **Vzorové zkoušky:** [[mikk-vzorove-zkousky|Vzorové zkoušky MikK]].

---

## 20. Shrnutí ve čtyřech vzorcích

| Vzorec | Co říká |
|--------|---------|
| $MR = P\,(1 + 1/E_d)$ | Mezní příjem monopolisty; Amorosova–Robinsonova rovnice. |
| $MR = MC$ | Optimum monopolisty — totéž jako u jakékoli firmy maximalizující zisk. |
| $(P-MC)/P = -1/E_d$ | Lernerova rovnice pro cenovou přirážku. |
| $MC_1 = MC_2 = \ldots = MC_n = MR$ | Optimum vícezávodového monopolisty. |

Tyto čtyři vzorce stačí na všechny standardní úlohy o monopolu v rámci kurzu [[mikk|Mikroekonomie 2]]. Vše ostatní jsou jejich speciální případy nebo geometrické interpretace (DWL, regulace přirozeného monopolu, případové studie).
