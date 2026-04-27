---
title: "Elasticita poptávky a nabídky (pokročilé)"
course: mikk
type: topic
tags: [mikk, mikroekonomie, elasticita, krizova-elasticita, duchodova-elasticita]
sources: [raw/mikk/Prednaska 1. a 2. blok.pdf, raw/mikk/mik2K reseni prikladu 1 blok.pdf, raw/mikk/mikK test KS reseni.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Elasticita poptávky a nabídky (pokročilé)

> [!abstract] TL;DR
> **Elasticita** je bezrozměrná míra citlivosti jedné veličiny na změnu druhé. V kurzu [[mikk|Mikroekonomie 2]] pracujeme se třemi typy poptávkové elasticity: **cenovou** $E_D = (P/Q)\cdot dQ/dP$ (klasifikace neelastická / jednotková / elastická), **křížovou** $E_{XY}$ (rozlišuje substituty od komplementů) a **důchodovou** $E_I$ (rozlišuje normální, luxusní a inferiorní statky). Nabídková elasticita $E_S$ se počítá analogicky, ale bez znaménka. **Geometricky** lze cenovou elasticitu na poptávkové křivce změřit jako poměr délek $E_D = AC/EC$ (od bodu k oběma osám). Speciální případ je **konstantní elasticita** $P = AQ^a$, kde $E_D = 1/a$ je nezávislá na bodě — pak nelze maximalizovat tržby. Pro lineární poptávku platí: $E_D=-1$ právě v bodě, kde tržní potenciál $P\cdot Q$ dosahuje maxima.

## 1. Klasifikace elasticity — cheat-sheet

![[mikk-elasticita-5typu.jpeg|Pět typů cenové elasticity poptávky — E=0, E<1, E=1, E>1, E=∞ — vedle sebe]]

Elasticita popisuje, **o kolik procent se změní jedna veličina, když se druhá veličina změní o 1 %**. Pro cenovou elasticitu poptávky platí znaménková konvence: matematicky $E_D < 0$ (klesající poptávka), v běžné mluvě a v tabulkách se uvádí absolutní hodnota $|E_D|$. Tato wiki používá konvenci, že hodnoty v textu jsou kladné (absolutní), zatímco v matematickém zápisu může být znaménko mínus uvedeno explicitně.

| Hodnota $\lvert E\rvert$ | Název                           | Reakce množství | Tržby (TR) při růstu ceny |
|--------------------------|---------------------------------|-----------------|---------------------------|
| $0$                      | dokonale neelastická            | nemění se       | rostou proporcionálně s cenou |
| $0 < \lvert E\rvert < 1$ | neelastická (nepružná)          | mírná           | rostou                    |
| $\lvert E\rvert = 1$     | jednotková (unitární) elasticita | proporcionální | nemění se (TR konstantní) |
| $1 < \lvert E\rvert < \infty$ | elastická (pružná)         | silná           | klesají                   |
| $\infty$                 | dokonale elastická              | skoková (přesun) | klesají na 0 (drobné zvýšení ceny) |

> [!info] Intuice TR vs. cena
> Pravidlo pro maximalizaci tržeb: **zvyšujte cenu, dokud poptávka neelastická; snižujte cenu, dokud je elastická; v bodě $E_D = -1$ jsou tržby maximální**. Tento bod je zároveň bodem, kde $MR = 0$ (mezní příjem nulový) — viz [[mikk-monopol-pokrocily|Monopol (pokročilé)]].

### Vztah mezi $E_D$ a $MR$

Pro libovolnou poptávkovou funkci platí

$$MR = P \left(1 + \frac{1}{E_D}\right).$$

Z toho přímo plyne **Lernerův index** monopolní moci $L = (P-MC)/P = -1/E_D$. Detailní odvození je v [[mikk-monopol-pokrocily|Monopol (pokročilé)]].

## 2. Cenová elasticita poptávky $E_D$

### Definice

$$E_D = \frac{\%\;\Delta Q_D}{\%\;\Delta P} = \frac{\Delta Q/Q}{\Delta P/P}.$$

Pro infinitezimální změny dostáváme **bodovou elasticitu**:

$$\boxed{\; E_D \;=\; \frac{P}{Q}\cdot\frac{dQ}{dP} \;=\; \frac{P}{Q}\cdot\frac{1}{dP/dQ} \;}$$

Pro velké, ale konečné změny se používá **oblouková (midpoint) elasticita**:

$$\boxed{\; E_D^{\,arc} \;=\; \frac{(Q_2-Q_1)/[(Q_1+Q_2)/2]}{(P_2-P_1)/[(P_1+P_2)/2]} \;=\; \frac{(Q_2-Q_1)/(Q_1+Q_2)}{(P_2-P_1)/(P_1+P_2)} \;}$$

> [!tip] Proč midpoint?
> Klasický vzorec $\Delta Q/Q_1 \div \Delta P/P_1$ dává různé výsledky podle toho, který bod bereme jako výchozí (asymetrie). Midpoint normalizuje na **průměr** výchozího a koncového bodu, takže elasticita z $A$ do $B$ je shodná s elasticitou z $B$ do $A$.

### Mini-příklad: bodový výpočet

Mějme poptávku $Q = 3000 - 600\sqrt{P}$ (z testu KS, viz [[mikk-vzorce-prehled|Přehled vzorců MikK]]). Spočítejme $E_D$ v bodě $P=4$.

1. Derivace: $\dfrac{dQ}{dP} = -\dfrac{600}{2\sqrt{P}} = -\dfrac{300}{\sqrt{P}}$. V $P=4$: $\dfrac{dQ}{dP} = -\dfrac{300}{2} = -150$.
2. Hodnota množství: $Q = 3000 - 600\cdot 2 = 1800$.
3. Elasticita: $E_D = \dfrac{4}{1800}\cdot(-150) = -\dfrac{600}{1800} = -\dfrac{1}{3} \approx -0{,}33$.

Závěr: poptávka je v okolí $P=4$ **neelastická** ($\lvert E_D\rvert < 1$). Pokud by firma drobně zvýšila cenu, tržby by porostly.

### Proč u lineární poptávky elasticita není konstantní

Pro lineární $P = a - bQ$ (resp. $Q = (a-P)/b$) platí $dQ/dP = -1/b$ a tedy

$$E_D = \frac{P}{Q}\cdot\left(-\frac{1}{b}\right) = -\frac{P}{a - P}.$$

Z toho:
- v bodě $P\to 0$: $E_D \to 0$ (dokonale neelastická — nasycený trh),
- v bodě $P\to a$: $E_D \to -\infty$ (dokonale elastická — výplazení trhu),
- v polovině: $P = a/2$, $Q = a/(2b)$, takže $E_D = -1$ (unitární — maximální tržby).

Tato struktura odpovídá intuici z trhu i z grafu (sklon je všude stejný, ale poměr $P/Q$ se mění).

## 3. Geometrická interpretace $E_D = AC/EC$

V daném bodě poptávkové křivky lze elasticitu přečíst přímo z grafu jako poměr délek dvou úseček na **tečně** (u lineární poptávky je to celá poptávková přímka).

**Konstrukce.** Označme bod $A$ na poptávkové křivce. Tečna v $A$ protíná osu $Q$ v bodě $C$ (vodorovná osa) a osu $P$ v bodě $E$ (svislá osa). Pak

$$\boxed{\; \lvert E_D\rvert \;=\; \frac{\overline{AC}}{\overline{AE}} \;}$$

kde $\overline{AC}$ je vzdálenost od $A$ k průsečíku tečny s **vodorovnou** osou (osou množství) a $\overline{AE}$ je vzdálenost od $A$ k průsečíku tečny se **svislou** osou (osou ceny). Některé učebnice používají označení $E_D = AC/EC$, kde $E$ je na svislé ose a $C$ na vodorovné — výsledek je ekvivalentní.

> [!info] Intuice geometrického vzorce
> Čím **blíže** je bod $A$ k vodorovné ose (k $C$), tím je úsečka $AC$ kratší a tudíž $E_D$ menší — poptávka je v této části křivky neelastická (nízké ceny, vysoké množství). Naopak blízko svislé osy (vysoké ceny, malé množství) je $AE$ malé a $E_D$ velké — elastická část.

### Příklad měření

Zadání: lineární poptávka, hledáme $E_D$ v určitém bodě pomocí pravítka.

**Měření pravítkem na obrázku:**
- Délka úseku $A = 51\,\text{mm}$ (od bodu k jedné ose).
- Délka úseku $B = 34\,\text{mm}$ (od bodu k druhé ose).

$$E_D = \frac{A}{B} = \frac{51}{34} = 1{,}5.$$

**Kontrola pomocí Pythagorovy věty.** Z grafu lze odečíst, že úsek $A$ má vodorovnou složku 120 a svislou složku 120 (jednotek souřadnic), takže

$$A = \sqrt{120^2 + 120^2} = \sqrt{14\,400 + 14\,400} = \sqrt{28\,800} = 169{,}7056\,\text{j}.$$

Analogicky úsek $B$ má vodorovnou složku 40 a svislou 80:

$$B = \sqrt{40^2 + 80^2} = \sqrt{1\,600 + 6\,400} = \sqrt{8\,000} = 113{,}1371\,\text{j}.$$

$$E_D = \frac{A}{B} = \frac{169{,}7056}{113{,}1371} = 1{,}4999\ldots \approx 1{,}5.$$

Měření pravítkem (1,5) i analytický výpočet (1,5) se shodují — geometrická konstrukce je **přesná** pro lineární poptávku a v tečné aproximaci pro nelineární.

## 4. Konstantní elasticita $P = A Q^a$

Speciální tvar poptávky $P = A\,Q^a$ s $a < 0$ má **konstantní cenovou elasticitu** v každém bodě.

### Odvození

$$\frac{dP}{dQ} = a\,A\,Q^{a-1}.$$

$$E_D = \frac{P}{Q}\cdot\frac{1}{dP/dQ} = \frac{A\,Q^a}{Q}\cdot\frac{1}{a\,A\,Q^{a-1}} = \frac{A\,Q^{a-1}}{a\,A\,Q^{a-1}} = \frac{1}{a}.$$

$$\boxed{\; P = A\,Q^a \;\Longrightarrow\; E_D = \dfrac{1}{a} \;\text{(konstanta)}\;}$$

### Důsledky konstantní elasticity

1. **Nezávislost na bodě**: ať si zvolíme jakoukoliv cenu nebo množství, elasticita zůstává stejná.
2. **Nelze najít bod $E_D = -1$**, pokud $a \ne -1$. V důsledku **nelze maximalizovat tržby** v konečném bodě — limita je v $\infty$ nebo v $0$.
3. Logaritmické vyjádření: $\ln P = \ln A + a \ln Q$. V log-log grafu je poptávka přímkou se sklonem $a$.

### Příklad — konstantní elasticita $E_D = -3$

Mějme poptávku $P = 66\,Q^{-1/3} = \dfrac{66}{\sqrt[3]{Q}}$ a mezní náklady $MC = 2$.

Z obecného vzorce přímo: $a = -1/3$, takže $E_D = 1/a = -3$ — konstantně, v každém bodě.

**Kontrola výpočtem:**

$$\frac{dP}{dQ} = -\tfrac{1}{3}\cdot 66\,Q^{-4/3} = -22\,Q^{-4/3}.$$

$$E_D = \frac{P}{Q}\cdot\frac{1}{dP/dQ} = \frac{66\,Q^{-1/3}}{Q}\cdot\frac{1}{-22\,Q^{-4/3}} = \frac{66}{-22}\cdot\frac{Q^{-4/3}}{Q^{-4/3}} = -3.\;\checkmark$$

Tato funkce je tedy elastická v každém bodě a maximalizace tržeb v ní není možná v konečném $Q$ — viz Příklad II níže.

## 5. Jiné postupy výpočtu

Cenovou elasticitu lze ekvivalentně zapsat jako součin **podílu ceny a množství** s **převrácenou hodnotou směrnice tečny** poptávkové křivky:

$$E_D = \frac{P}{Q}\cdot\frac{1}{\delta P/\delta Q} = \frac{P}{Q}\cdot k,$$

kde $k = 1/(dP/dQ)$ je převrácená směrnice. U lineární poptávky $P = a - bQ$ je $k = -1/b$ konstantní, takže celá variabilita $E_D$ pochází z poměru $P/Q$.

Další ekvivalentní zápis pro **dva diskrétní body** $(P_1,X_1)$ a $(P_2,X_2)$:

$$e_{ID} = \frac{X_2 - X_1}{P_2 - P_1}\cdot\frac{P_1 + P_2}{X_1 + X_2}.$$

> [!tip] Postup výpočtu krok za krokem
> 1. Identifikuj poptávkovou funkci (zda je $Q(P)$ či $P(Q)$).
> 2. Spočítej derivaci ve správném směru.
> 3. Dosadž bod $(P, Q)$, ve kterém měříš.
> 4. Aplikuj $E_D = (P/Q)\cdot dQ/dP$.
> 5. Pokud je zadání diskrétní, použij midpoint (oblouk).

## 6. Determinanty cenové elasticity poptávky

Co určuje, zda je poptávka po určitém statku elastická či neelastická? Klíčové faktory:

### 6.1 Možnosti substituce

**Existence substitutů** je nejvýznamnější determinant. Čím více **blízkých substitutů**, tím elastičtější poptávka.

- **Dokonalé substituty** (homogenní zboží různých výrobců): záměna není plynulá — spotřebitel se přesune **najednou** ze statku $X$ na statek $Y$, jakmile cenový rozdíl překročí prah. Poptávka po výrobku jednoho výrobce je téměř dokonale elastická.
- **Nedokonalé substituty** se nahrazují postupně, kombinací obou. Poptávka je elastická, ale konečně.

Příklad: poptávka po Coca-Cole je elastická (spotřebitel přechází na Pepsi), ale poptávka po nealko nápojích jako kategorii je neelastická.

### 6.2 Podíl na rozpočtu

Důchodový efekt cenové změny je tím silnější, čím **větší podíl** statek zaujímá v celkových výdajích. Krabička zápalek má cenovou elasticitu téměř nulovou ($E_D \approx 0{,}1$), protože změna ceny zápalek o 50 % je v rozpočtu nepostřehnutelná. Naopak nákup automobilu reaguje silně ($E_D = 1{,}87$).

> [!info] Proverbium: Sůl nad zlato
> Sůl je životně nezbytná, ale zaujímá tak malý podíl na rozpočtu, že její cena prakticky nemá vliv na množství poptávané. $E_D(\text{sůl}) = 0{,}1$.

### 6.3 Důchodový efekt (normální vs. inferiorní)

Pro **normální statek** vede pokles ceny → růst reálného důchodu → růst spotřeby. Důchodový efekt **zesiluje** substituční efekt. Detail viz [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]].

Pro **inferiorní statek** vede pokles ceny → růst reálného důchodu → **pokles** spotřeby. Důchodový efekt **oslabuje** substituční efekt. Normální statky proto mají typicky vyšší cenovou elasticitu než inferiorní.

### 6.4 Krátké vs. dlouhé období

V **krátkém období** spotřebitel nemůže snadno změnit chování (např. má auto, jezdí do práce, musí kupovat benzin). V **dlouhém období** může změnit auto za úspornější, přestěhovat se, změnit zaměstnání. Důsledek: **dlouhodobá elasticita je obvykle větší než krátkodobá** (často 3-10×).

### 6.5 Charakter potřeby

Statky uspokojující **nezbytné** potřeby (chléb, léky, bydlení) mají nízkou elasticitu. **Luxusní** statky (cesty do zahraničí, klenoty) mají vysokou elasticitu.

> [!warning] Pozor — věrnost značce
> Vysoká věrnost značce snižuje elasticitu poptávky. To je výhoda při zvyšování ceny (zákazník neuteče), ale nevýhoda při snižování ceny (nepřitáhne nové). Strategický cíl marketingu: budovat věrnost, ale **zachovat schopnost cenové diskriminace** mezi loajálními a citlivými zákazníky — viz [[mikk-cenova-diskriminace|Cenová diskriminace]].

## 7. Empirické tabulky cenové elasticity

### 7.1 Vybrané statky

Tabulka $E_D$ pro 30+ produktů (americká data, ale ilustrativně platí i pro ČR):

| Statek                   | $\lvert E_D\rvert$ | Statek                  | $\lvert E_D\rvert$ |
|--------------------------|--------------------|-------------------------|--------------------|
| Bydlení                  | 0,01               | Nábytek                 | 1,0                |
| Sůl                      | 0,1                | Železniční doprava      | 1,4                |
| Zápalky                  | 0,1                | Marihuana               | 1,5                |
| Zubní kartáček           | 0,1                | Porcelán                | 1,54               |
| Elektřina pro domácnosti | 0,13               | Os. automobily          | 1,87               |
| Chléb                    | 0,15               | Legální hazardní hry    | 1,9                |
| Oděvy                    | 0,2                | Strava v restauracích   | 2,27               |
| Autobusová doprava       | 0,2                | Jehněčí a skopové maso  | 2,65               |
| Káva                     | 0,25               | Zelený hrášek           | 2,8                |
| Lékařská péče            | 0,31               | Letecká doprava (DO)    | 2,4                |
| Noviny a časopisy        | 0,42               | Cesty do zahraničí (DO) | 4,0                |
| Cigarety                 | 0,48               | Automobily Chevrolet    | 4,0                |
| Ryby                     | 0,5                | Rajská jablíčka         | 4,6                |
| Právní služby            | 0,61               |                         |                    |
| Hovězí maso              | 0,64               |                         |                    |

(Zdroj: Gwartney, Stroup, Macpherson, Sobel — *Economics: Private and Public Choice*, 2005, 11. vyd.)

> [!info] Jak číst tabulku
> Hodnoty pod 1 = neelastická poptávka (zboží blízko statku životně nezbytného). Hodnoty nad 1 = elastická poptávka (luxus, dobře substituovatelné). Nejvyšší hodnoty (rajčata 4,6) ukazují na zboží, kde má spotřebitel mnoho alternativ — když rajčata zdraží, koupí okurky.

### 7.2 Krátké vs. dlouhé období

| Statek                | $\lvert E_D\rvert$ krátké období | $\lvert E_D\rvert$ dlouhé období |
|-----------------------|----------------------------------|----------------------------------|
| Benzin                | 0,4                              | 1,5                              |
| Zahraniční cesty      | 0,14                             | 1,77                             |
| Elektřina pro domácnosti | 0,13                          | 1,8                              |
| Tabákové výrobky      | 0,46                             | 1,89                             |
| Toaletní potřeby      | 0,2                              | 3,04                             |
| Zemní plyn            | 0,1                              | 0,5                              |
| Pneumatiky            | 0,9                              | 1,2                              |
| Letecká doprava       | 0,1                              | 2,4                              |
| Vlastní bydlení       | (krátké období nelze)            | 1,2                              |

> [!info] Intuice — proč benzin?
> V krátkém období musí řidič dojíždět do práce, ať benzin stojí cokoli. V dlouhém období může koupit hybrid, přestěhovat se blíž k práci, dojíždět veřejnou dopravou. **Dlouhodobá elasticita je 3,75× vyšší.** Podobně elektřina (poměr 13,8×!).

### 7.3 Český kontext

Studie Luňáčka a Feldbabela (Acta univ. agric. silvic. Mendel. Brun., 2011, LIX, č. 7, s. 225–236) měřila elasticitu českého spotřebitele. Detailní hodnoty viz [[mikk-odhad-poptavky|Odhad poptávky]].

## 8. Cenová pružnost nabídky $E_S$

Definice analogická poptávce, ale **bez znaménka mínus** — nabídka roste s cenou, takže elasticita je přirozeně kladná:

$$\boxed{\; E_S = \frac{P}{Q}\cdot\frac{dQ_S}{dP} \;\geq\; 0 \;}$$

### Dva archetypy nabídky

> [!example] „Pěstování brambor" vs. „Reklama na internetu"
> **Pěstování brambor** — fyzická produkce, sezónní cyklus, omezené pole, omezené sklady. Když cena vyskočí, zemědělec **nemůže** rychle zvětšit produkci. Nabídka **neelastická**, $E_S \to 0$ v krátkém období.
>
> **Reklama na internetu** — digitální služba, nulové fixní náklady na další jednotku, neomezená kapacita. Když cena reklamy vyskočí, agentura zvládne během dne nabrat další klienty. Nabídka **dokonale elastická**, $E_S \to \infty$.

### Strategie firem v závislosti na $E_S$

> [!tip] Postup — kdy je pružnost výhodná?
> Vysoká pružnost umožňuje firmě **agresivně reagovat** na cenové signály (růst poptávky → rychle navýšit produkci → využít zisku). Ale pružnost **něco stojí** (nadbytečné kapacity, držení zásob).
>
> - Strategie **Cost Leadership** (nízké náklady) ⇒ nemůže si dovolit drahou pružnost.
> - Strategie **Differentiation** ⇒ může pružnost financovat z vyšších marží.
>
> Vysoké $E_S$ vyžaduje:
> - dostupné výrobní zdroje a distribuční kanály,
> - nevyužité kapacity (rezervy),
> - možnost vyrábět na sklad (skladovatelnost),
> - nízké fixní náklady.

## 9. Tržní potenciál (MP) a maximalizace tržeb

**Definice (Kotler, *Marketing Management*, s. 261).** Potenciál trhu MP je *maximální objem prodeje (ve fyzických nebo peněžních jednotkách), který může být dosažen na určitém trhu v určitém čase, při dané úrovni marketingového úsilí a při daných podmínkách prostředí*.

V peněžním vyjádření: $MP = P\cdot Q$, kde $P$ je cena a $Q$ množství. Protože $Q = D(P)$, je $MP = P\cdot D(P)$ funkcí ceny.

### Maximum MP nastává v bodě $E_D = -1$

Maximalizace $MP(P) = P\cdot Q(P)$ vede přes podmínku $dMP/dP = 0$:

$$\frac{dMP}{dP} = Q + P\cdot\frac{dQ}{dP} = Q\left(1 + \frac{P}{Q}\cdot\frac{dQ}{dP}\right) = Q\,(1 + E_D).$$

Z $1 + E_D = 0$ vyplývá $E_D = -1$.

> [!info] Důsledek pro praxi
> Pokud chce firma maximalizovat tržby (ne zisk!), musí cenu nastavit do bodu, kde je poptávka **jednotkově elastická**. Při ceně nižší než toto optimum je poptávka neelastická a růst ceny zvýší tržby; nad optimem je elastická a růst ceny tržby snižuje. To je úzce svázáno s [[mikk-monopol-pokrocily|monopolním rozhodováním]] — monopol ale obvykle maximalizuje zisk, ne tržby, takže produkuje **méně** než $E_D = -1$ bod.

### Vazba MP na cenovou elasticitu nabídky

Skutečně dosažitelný MP závisí i na nabídce. Strategie firmy: zvyšovat $E_D$ pomocí **substituovatelnosti** (Marketingový mix — promotion, branding) nebo zvyšovat $E_S$ vlastní nabídky (kapacitou, automatizací).

## 10. Křížová elasticita poptávky $E_{XY}$

### Definice

$$\boxed{\; E_{XY} = \frac{\%\;\Delta Q_X}{\%\;\Delta P_Y} = \frac{\Delta Q_X / Q_X}{\Delta P_Y / P_Y} \;}$$

Měří, **jak se změní poptávka po statku $X$ při změně ceny statku $Y$**.

### Klasifikace

| $E_{XY}$ | Vztah $X$ a $Y$ | Příklad |
|----------|-----------------|---------|
| $> 0$    | substituty      | máslo a margarín, hovězí a vepřové |
| $< 0$    | komplementy     | auto a benzin, boty a tkaničky |
| $\to 0$  | nezávislé statky | chleba a kancelářské potřeby |

> [!info] Intuice
> Substituty: zdraží-li $Y$, spotřebitel přejde na $X$, takže $Q_X$ roste — kladný $E_{XY}$. Komplementy: zdraží-li $Y$, koupí se méně $Y$ a tím i méně $X$, který se s $Y$ konzumuje — záporný $E_{XY}$.

### Empirická tabulka $E_{XY}$

| Statek $X$    | Statek $Y$    | $E_{XY}$ | Interpretace            |
|---------------|---------------|----------|-------------------------|
| máslo         | umělé tuky    | 0,81     | silné substituty        |
| umělé tuky    | máslo         | 0,67     | substituty (asymetrie)  |
| zemní plyn    | nafta         | 0,44     | substituty              |
| hovězí maso   | vepřové maso  | 0,28     | mírné substituty        |
| elektřina     | zemní plyn    | 0,20     | slabé substituty        |
| zábava        | jídlo         | -0,72    | komplementy (rozpočtový efekt) |
| obilniny      | ryby          | -0,87    | silné komplementy v jídelníčku |

> [!warning] Asymetrie $E_{XY} \ne E_{YX}$
> Křížová elasticita **není symetrická**. Vliv změny ceny másla na poptávku po margarinu (0,81) je silnější než opačně (0,67), protože máslo má vyšší podíl na rozpočtu než margarín.

### Příklad — tkaničky a boty

Z Lidových novin (18. 4. 1998): „Maloobchodní tržby klesly o 5,3 %... Šetření se projevuje tím, že **klesly nákupy nových bot a zvýšila se poptávka po tkaničkách**."

**Otázka.** Jsou tkaničky a boty komplementy, nebo substituty?

**Analýza.** Nominálně **komplementy** — tkaničky se používají do bot, takže prodej bot a tkaniček by měl korelovat. Ale v této krizové situaci pozorujeme **opačný** vztah: klesající poptávka po botách → rostoucí poptávka po tkaničkách. Vysvětlení: tkaničky **substituují celé nové boty** v období úspor. Zákazník si boty neopravuje výměnou bot, ale **prodlužuje životnost** stávajících bot novými tkaničkami. V této specifické situaci jde tedy fakticky o **substituty na úrovni opotřebení obuvi**.

**Poučka.** Klasifikace komplement/substitut není absolutní vlastnost statků, ale závisí na **kontextu spotřeby** a **cenové hladině**. Marketingový vhled: v krizi nabídnout opravárenské služby, prodej náhradních dílů, bazarové zboží.

## 11. Důchodová (příjmová) elasticita poptávky $E_I$

### Definice

$$\boxed{\; E_I = \frac{\%\;\Delta Q_X}{\%\;\Delta I} = \frac{\Delta Q_X / Q_X}{\Delta I / I} \;}$$

kde $I$ je důchod spotřebitele.

### Klasifikace statků podle $E_I$

| $E_I$       | Typ statku              | Příklad                   |
|-------------|-------------------------|---------------------------|
| $> 1$       | **luxusní**             | luxusní toaletní potřeby (3,74 v DO), automobily (1,07 v DO), cesty do zahraničí |
| $0 < E_I < 1$ | **normální nezbytný** | hovězí maso (0,45), oděvy, lékařské služby (krátkodobě 0,28) |
| $E_I = 0$   | neutrální (málo realistické) | sůl při velmi nízké úrovni důchodu |
| $E_I < 0$   | **inferiorní (podřadný)** | levné brambory, autobusová doprava (oproti autu), méněhodnotné maso |

Speciálně:
- **Engelův zákon**: s rostoucím důchodem klesá podíl výdajů na potraviny — potraviny jako celek jsou nezbytný statek ($0 < E_I < 1$).
- **Giffenův statek**: extrémní případ inferiorního statku, kde důchodový efekt převažuje substituční (klesá-li cena, klesá poptávka). Diskuse v [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]].

### Empirická tabulka — krátké vs. dlouhé období

| Statek                  | $E_I$ krátké období | $E_I$ dlouhé období |
|-------------------------|---------------------|---------------------|
| vepřové maso            | 0,27                | 0,18                |
| hovězí maso             | 0,51                | 0,45                |
| nábytek                 | 2,6                 | 0,53                |
| automobily              | 5,5                 | 1,07                |
| lékařské služby         | 0,28                | 1,15                |
| oděvy                   | 0,95                | 1,17                |
| benzin                  | 0,55                | 1,36                |
| boty                    | 0,9                 | 1,5                 |
| soukromé bydlení        | 0,07                | 2,45                |
| luxusní toaletní potřeby | 0,25               | 3,74                |

> [!info] Pozorování
> - **Automobily**: v krátkém období extrémně reagují na zvýšení důchodu (5,5), v dlouhém se efekt rozpouští (1,07). Krátkodobě je nárůst důchodu spotřebován na nákup auta; dlouhodobě se podíl ustaluje.
> - **Soukromé bydlení**: opačný profil. Krátkodobě prakticky nereaguje (0,07 — bydlení nelze rychle pořídit), dlouhodobě silně luxusní (2,45 — investice do nemovitostí).
> - **Vepřové maso**: $E_I < 1$ a klesá v dlouhém období → s růstem bohatství se postupně stává **inferiorním** (přechod na hovězí, ryby, vegetariánství).

### Strategické využití

> [!tip] Postup — výběr oboru podnikání podle $E_I$
> Pokud ekonomika roste (růst $I$), volte obory s **vysokým** $E_I$ (luxus, soukromé bydlení) — tržby porostou rychleji než HDP. Pokud ekonomika stagnuje, volte obory s $E_I$ blízkým nule (nezbytné statky) — tržby zůstanou stabilní. Pokud klesá, volte obory s $E_I < 0$ (inferiorní statky) — paradoxně mohou růst.
>
> Aplikace: <https://tellusant.com/income-elasticity/> nabízí mezinárodní mapy $E_I$ pro segmentaci trhů.

## 12. Veblenův efekt a statky postavení

Standardní mikroekonomická poptávka je klesající ($dQ/dP < 0$). Existují však **anomálie**, kde poptávka **roste s cenou**.

### Veblenův efekt (statky postavení)

Thorstein Veblen (1899, *Theory of the Leisure Class*) popsal **demonstrační spotřebu**: spotřebitel kupuje drahý statek právě proto, že je drahý — vysoká cena signalizuje **status**. Růst ceny → růst poptávky.

> [!example] Praktické příklady Veblenova efektu
> - **Pleťové krémy Dr. Středa** (česká přednáška): firma se chystala bankrotovat při nízkých cenách. Po **razantním zvýšení cen** byla zachráněna — vyšší cena zvedla vnímanou prestiž.
> - **Šampaňské Perrier-Jouet**: marketing se opírá o nedostupnost. Sleva by zničila kategorii.
> - **Luxusní hodinky, kabelky, parfémy**: cena je součástí produktu.

### Bandwagon vs. Veblen vs. Snob

Tři příbuzné nestandardní efekty (Leibenstein, 1950):

| Efekt        | Popis                                              | Vliv na elasticitu        |
|--------------|----------------------------------------------------|---------------------------|
| **Bandwagon** | „Chci to, protože to mají ostatní" (móda, hype)  | zvyšuje elasticitu (silnější reakce) |
| **Snob**     | „Chci to, protože to ostatní nemají"              | snižuje elasticitu        |
| **Veblen**   | „Chci to, protože je to drahé" (status)           | převrací znaménko ($E_D > 0$) |

> [!warning] Pozor — Veblen NENÍ Giffen
> Veblenův statek roste s cenou kvůli **prestiži** (psychologie). Giffenův statek roste s cenou kvůli **důchodovému efektu** v rozpočtu chudých (typicky inferiorní zákl. potravina). Mechanismy se zcela liší — viz [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]].

## 13. Příklad I — kompletní řešení

**Zadání.** Firma má funkci celkového příjmu $TR(Q) = 200Q - Q^2$. Mezní příjem $MR$ je v určitém bodě roven $40$. Najděte cenovou elasticitu poptávky $E_D$ v tomto bodě **třemi metodami**: (a) bodovým vzorcem, (b) obloukovým vzorcem, (c) grafickou interpretací.

### Krok 1: Odvodit poptávkovou funkci

Z $TR = P\cdot Q$ plyne $P = TR/Q = (200Q - Q^2)/Q = 200 - Q$. Poptávka je tedy lineární: $\boxed{P = 200 - Q}$.

### Krok 2: Najít bod, kde $MR = 40$

Mezní příjem: $MR = dTR/dQ = 200 - 2Q$. Z podmínky $MR = 40$:

$$40 = 200 - 2Q \;\Rightarrow\; 2Q = 160 \;\Rightarrow\; Q = 80.$$

Cena v tomto bodě: $P = 200 - 80 = 120$.

Pracujeme v bodě $(Q, P) = (80, 120)$.

### Metoda (a): Bodový vzorec

$$E_D = \frac{P}{Q}\cdot\frac{dQ}{dP} = \frac{P}{Q}\cdot\frac{1}{dP/dQ}.$$

Z $P = 200 - Q$ je $dP/dQ = -1$, tedy $dQ/dP = -1$.

$$E_D = \frac{120}{80}\cdot(-1) = -\frac{3}{2} = -1{,}5.$$

### Metoda (b): Oblouková (midpoint) — body symetricky kolem $(80, 120)$

Vezměme $Q_1 = 79$, $Q_2 = 81$. Příslušné ceny z poptávky:
- $P_1 = 200 - 79 = 121$,
- $P_2 = 200 - 81 = 119$.

Aplikace midpoint vzorce:

$$E_D^{\,arc} = \frac{(Q_2 - Q_1)/(Q_1 + Q_2)}{(P_2 - P_1)/(P_1 + P_2)} = \frac{(81 - 79)/(79 + 81)}{(119 - 121)/(121 + 119)} = \frac{2/160}{-2/240}.$$

Výpočet: $\dfrac{2/160}{-2/240} = \dfrac{2}{160}\cdot\dfrac{240}{-2} = \dfrac{480}{-320} = -1{,}5$.

$$\boxed{\; E_D^{\,arc} = -1{,}5 \;}$$

Shoda s bodovou elasticitou je **přesná**, protože bereme body symetricky a poptávka je lineární.

### Metoda (c): Grafická interpretace $E_D = AC/EC$

V bodě $(Q, P) = (80, 120)$ na lineární poptávce $P = 200 - Q$:
- Tečna = sama poptávka (přímka).
- Průsečík s osou $P$ ($Q = 0$): $P = 200$, tedy bod $E = (0, 200)$.
- Průsečík s osou $Q$ ($P = 0$): $Q = 200$, tedy bod $C = (200, 0)$.

**Délka úsečky $AC$** (od $(80, 120)$ ke $(200, 0)$):

$$\overline{AC} = \sqrt{(200-80)^2 + (0-120)^2} = \sqrt{120^2 + 120^2} = \sqrt{28\,800} = 169{,}71.$$

**Délka úsečky $AE$** (od $(80, 120)$ ke $(0, 200)$):

$$\overline{AE} = \sqrt{(0-80)^2 + (200-120)^2} = \sqrt{80^2 + 80^2} = \sqrt{12\,800} = 113{,}14.$$

$$\lvert E_D\rvert = \frac{\overline{AC}}{\overline{AE}} = \frac{169{,}71}{113{,}14} = 1{,}500.$$

Při zachování znaménka pro klesající poptávku: $E_D = -1{,}5$. ✓

### Závěr příkladu I

Všechny tři metody dávají $E_D = -1{,}5$. V tomto bodě je poptávka **elastická**.

> [!info] Praktický pohled
> $E_D = -1{,}5$ znamená, že 1 % zvýšení ceny způsobí 1,5 % pokles množství. Tržby tedy **klesnou** zvýšením ceny. Pro maximalizaci tržeb by firma měla cenu **snížit** směrem k bodu $E_D = -1$, tj. $P = 100$, $Q = 100$, $TR_{\max} = 10\,000$.

## 14. Příklad II — konstantní elasticita

**Zadání.** Poptávka má tvar $P = \dfrac{66}{\sqrt[3]{Q}} = 66\,Q^{-1/3}$ a mezní náklady $MC = 2$.

Úkoly: (a) určete cenovou elasticitu, (b) najděte množství maximalizující zisk, (c) zjistěte, zda lze maximalizovat tržby (obrat), (d) zobecněte výsledek pro $P = A\,Q^a$.

### (a) Cenová elasticita

Z obecného vzorce: $a = -1/3$, takže $E_D = 1/a = -3$ — **konstantní v každém bodě**.

**Detailní kontrola.**

$$\frac{dP}{dQ} = -\tfrac{1}{3}\cdot 66\,Q^{-4/3} = -22\,Q^{-4/3}.$$

$$E_D = \frac{P}{Q}\cdot\frac{1}{dP/dQ} = \frac{66\,Q^{-1/3}}{Q}\cdot\frac{1}{-22\,Q^{-4/3}} = \frac{66}{-22}\cdot\frac{Q^{-1/3-1}}{Q^{-4/3}} = -3\cdot\frac{Q^{-4/3}}{Q^{-4/3}} = -3.$$

$$\boxed{\; E_D = -3 \;\text{(konstantně)} \;}$$

### (b) Maximalizace zisku ($MR = MC$)

Spočtěme tržby:
$$TR = P\cdot Q = 66\,Q^{-1/3}\cdot Q = 66\,Q^{2/3}.$$

Mezní příjem:
$$MR = \frac{dTR}{dQ} = 66\cdot\tfrac{2}{3}\,Q^{-1/3} = 44\,Q^{-1/3} = \frac{44}{\sqrt[3]{Q}}.$$

Podmínka $MR = MC$:
$$\frac{44}{\sqrt[3]{Q}} = 2 \;\Rightarrow\; \sqrt[3]{Q} = \frac{44}{2} = 22 \;\Rightarrow\; Q^* = 22^3 = 10\,648.$$

Cena: $P^* = 66\cdot 22^{-1} = 66/22 = 3$. Tržby: $TR^* = 3\cdot 10\,648 = 31\,944$. Náklady (variabilní část): $VC = 2\cdot 10\,648 = 21\,296$. „Příspěvek" na zisk: $TR - VC = 10\,648$.

> [!info] Kontrola pomocí Lernerova indexu
> Optimální cena má splňovat $L = (P-MC)/P = -1/E_D = 1/3$. Skutečně: $(3-2)/3 = 1/3$. ✓ Detail v [[mikk-monopol-pokrocily|Monopol (pokročilé)]].

### (c) Maximalizace tržeb (obratu)

Tržby maximální, když $E_D = -1$ resp. $MR = 0$. **Ale** zde je $E_D = -3$ konstantně, nikdy se nedostaneme k $-1$. Alternativně z $MR = 44\,Q^{-1/3} = 0$ nemá konečné řešení; $MR \to 0$ pouze pro $Q \to \infty$.

Geometricky: $TR = 66\,Q^{2/3}$ je **rostoucí** funkce. Tržby rostou bez ohraničení — **nelze maximalizovat** v konečném $Q$.

$$\boxed{\; \text{Konstantní elasticita s } \lvert E_D\rvert > 1 \;\Longrightarrow\; \text{TR neohraničené, max nelze} \;}$$

### (d) Obecný tvar $P = A\,Q^a$

Odvodili jsme v sekci 4: $E_D = 1/a$ konstantně.

- Pro $a = -1/3$: $E_D = -3$ (silně elastická).
- Pro $a = -1$: $E_D = -1$ (jednotková) — pak $P\cdot Q = A$ konstantní, tržby konstantní vždy a max degenerované.
- Pro $a = -2$: $E_D = -1/2$ (neelastická) — pak by maximalizace tržeb byla ne v konečném $Q$, ale v $Q\to 0$.

Důsledek: konstantní elasticita je **patologický případ** pro klasickou tržní strategii. V praxi je vhodný spíše log-log model jen jako lokální aproximace.

## 15. Aplikace cenové elasticity v ekonomii a managementu

### 15.1 Maximalizace TR (marketing tržeb)

Bod maximalizace tržeb leží v $E_D = -1$. Marketingová strategie zaměřená na **růst tržeb** (např. vstup na trh, fáze získávání podílu) tlačí cenu k tomuto bodu — typicky agresivní cenotvorba a slevy.

### 15.2 Daňová ekonomie — kdo nese daň

Kritické pro veřejné finance. Při zavedení daně $t$ na statek je rozdělení dopadu mezi spotřebitele a výrobce dáno **poměrem elasticit nabídky a poptávky**:

$$\frac{\text{daň nesená spotřebitelem}}{\text{daň nesená výrobcem}} = \frac{E_S}{\lvert E_D\rvert}.$$

> [!example] Daň z cigaret
> Cigarety: $\lvert E_D\rvert = 0{,}48$, $E_S$ vysoká (snadno se vyrobí víc). Spotřebitel nese **téměř celou daň** — proto stát rád daně právě na neelastické zboží (cigarety, alkohol, benzin).

Detail v [[mikk-trzni-rovnovaha-dynamika|Tržní rovnováha a její dynamika]].

### 15.3 Marketing — cenová politika a diskriminace

- **Skimming** (oškramování smetany): vstoupit s vysokou cenou pro neelastické (loajální) zákazníky, postupně snižovat pro elastické. Detail v [[mikk-cenova-diskriminace|Cenová diskriminace]].
- **Penetrace**: vstoupit s nízkou cenou, abychom využili elastickou stranu trhu (přesvědčit nové zákazníky), pak postupně zvyšovat.
- **Bundling**: spojit elastický statek s neelastickým, abychom zvýšili průměrnou marži.

### 15.4 Regulace a kartely

OPEC kontroluje **neelastickou** poptávku po ropě — proto kartelové dohody fungují. Naopak kartely v elastických trzích (např. levné textilie) selhávají, protože substituty rychle přicházejí.

### 15.5 Predikce poptávky a empirický odhad

Odhad poptávky a její elasticity je samostatné téma — viz [[mikk-odhad-poptavky|Odhad poptávky]] a obecnější [[mikk-marshall-hicks-poptavka|Marshallova vs. Hicksova poptávka]]. Pro studenty s předchozím absolvováním ImeK je doporučeno revidovat [[elasticita|Elasticita (ImeK primer)]].

## 16. Otázka k zamyšlení — parfémy

**Zadání.** *Nizozemského výrobce parfémů zachránilo před krachem razantní zvýšení cen jeho produkce. Při vyšších cenách lidé začali kupovat podstatně vyšší objem jeho produkce. Znamená to, že parfémy jsou Giffenovým statkem? Svůj závěr zdůvodněte.*

### Argumentace

**Závěr: NE, parfémy nejsou Giffenovým statkem.** Mechanismus, který zachránil firmu, je **Veblenův efekt**, nikoli Giffenův paradox.

**Rozdíl mechanismů.**

- **Giffenův statek** je z definice **inferiorní statek** se silným důchodovým efektem (typicky levná základní potravina chudých — Marshallův příklad se zemědělskými dělníky, kteří víc pracovali při zdražení obilí). Mechanismus je **ekonomický** (rozpočtový) — zdražení statku stáhne reálný důchod tak, že chudák si nemůže dovolit lepší alternativu a koupí ještě víc levné brambory. Detail v [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]].
- **Veblenův efekt** je **psychologický/sociologický**. Spotřebitel kupuje drahý statek pro signální hodnotu (status). Růst ceny zvyšuje vnímanou kvalitu a žádanost.

Parfémy jsou **luxusní statek** ($E_I > 1$), nikoli inferiorní. Také není pravda, že by vyšší cena snižovala reálný důchod chudých kupujících tak, že by museli kupovat více parfémů namísto jiných — to nedává ekonomický smysl.

### Doplňující úvahy

Pokud původní nízká cena nezvýšila prodeje, mohlo to být tím, že:

1. **Špatná promotion** — zboží není vnímáno jako luxusní, marketing nedělá svou práci. Cena je signál kvality, příliš nízká cena dává **negativní signál**.
2. **Krátké období** — značka ještě není etablovaná, dlouhodobé efekty ještě nenastaly. Firma by měla urychlit etablaci značky pomocí intenzivního marketingu, distribuční politiky a budování image.
3. **Přejaté koeficienty** — koeficienty příjmové elasticity z USA neplatí v ČR. Nizozemský trh má jinou strukturu preferencí než americký.

> [!tip] Postup ověření Veblena vs. Giffena v praxi
> 1. Zjistěte $E_I$ statku — pokud $> 1$ (luxus), je to spíše Veblen.
> 2. Zjistěte $E_I$ statku — pokud $< 0$ (inferiorní), je to možný Giffen.
> 3. Zjistěte profil zákazníků — bohatí signalizující status = Veblen; chudí s úzkým rozpočtem = potenciální Giffen.
> 4. Změřte cenovou elasticitu při různých cenách. Veblen efekt obvykle končí při velmi vysokých cenách (saturace statusu); Giffen mizí, když se statek stane dostupným.

---

## Související wiki stránky

- [[mikk|Mikroekonomie 2]] — kurzová stránka.
- [[mikk-utility-preference|Užitková funkce a preference]] — odvození poptávky z preferencí.
- [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]] — Slutskyho rozklad, Giffen vs. Veblen.
- [[mikk-marshall-hicks-poptavka|Marshallova vs. Hicksova poptávka]] — kompenzovaná elasticita.
- [[mikk-monopol-pokrocily|Monopol (pokročilé)]] — Lernerův index $L = -1/E_D$, pricing.
- [[mikk-cenova-diskriminace|Cenová diskriminace]] — segmentace dle elasticity.
- [[mikk-trzni-rovnovaha-dynamika|Tržní rovnováha a její dynamika]] — daňový dopad podle $E_S/E_D$.
- [[mikk-odhad-poptavky|Odhad poptávky]] — empirické metody, ekonometrie.
- [[elasticita|Elasticita (ImeK primer)]] — bázový kurz Matematická ekonomie.
- [[mikk-vzorce-prehled|Přehled vzorců MikK]] — souhrnný cheatsheet.

## Klíčové vzorce — souhrn

| Veličina               | Vzorec                                                       |
|------------------------|--------------------------------------------------------------|
| Cenová elasticita poptávky (bod) | $E_D = \dfrac{P}{Q}\cdot\dfrac{dQ}{dP}$               |
| Cenová elasticita poptávky (oblouk) | $E_D^{\,arc} = \dfrac{(Q_2-Q_1)/(Q_1+Q_2)}{(P_2-P_1)/(P_1+P_2)}$ |
| Geometrická interpretace | $\lvert E_D\rvert = \overline{AC}/\overline{AE}$           |
| Konstantní elasticita  | $P = A\,Q^a \;\Rightarrow\; E_D = 1/a$                       |
| Cenová elasticita nabídky | $E_S = \dfrac{P}{Q}\cdot\dfrac{dQ_S}{dP}$                 |
| Tržní potenciál (max)  | $\max MP \;\Leftrightarrow\; E_D = -1$                       |
| Vztah $MR$ a $E_D$     | $MR = P\,(1 + 1/E_D)$                                        |
| Lernerův index         | $L = (P-MC)/P = -1/E_D$                                      |
| Křížová elasticita     | $E_{XY} = \dfrac{\%\,\Delta Q_X}{\%\,\Delta P_Y}$            |
| Důchodová elasticita   | $E_I = \dfrac{\%\,\Delta Q_X}{\%\,\Delta I}$                 |
| Daňový dopad           | $\dfrac{\text{daň spotřebitele}}{\text{daň výrobce}} = \dfrac{E_S}{\lvert E_D\rvert}$ |
