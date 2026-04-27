---
title: "MikK — Kompletní přehled vzorců"
course: mikk
type: output
tags: [mikk, mikroekonomie, vzorce, prehled, reference]
sources: [raw/mikk/Prednaska 1. a 2. blok.pdf, raw/mikk/mik2K prednaska 3 blok 2026.pdf, raw/mikk/Mikro KS prednaska 5 2026.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# MikK — Kompletní přehled vzorců

> [!abstract] TL;DR
> Referenční přehled **všech klíčových vzorců** kurzu [[mikk|Mikroekonomie 2]] od teorie spotřebitele přes elasticity, monopol, cenovou diskriminaci, oligopolní modely až po behavioristické a manažerské teorie firmy a ekonomiku rizika. Pro každý vzorec uvádíme **původ** (odkud se bere, z čeho se odvozuje), **intuici** (co znamená ekonomicky) a **odkaz** na příslušnou topic stránku, kde najdeš úplné odvození a příklady.

## 1. Spotřebitel — užitek (kardinální vs. ordinální)

**Základní téma:** [[mikk-utility-preference|Užitek a preference spotřebitele]]

### Kardinální užitek — celkový a mezní

$$TU = U(X, Y, \dots)$$

**Původ:** axiom kardinální teorie — užitek je měřitelný v utilech (Jevons, Walras, Marshall, konec 19. stol.). Spotřebitel má užitkovou funkci $U: \mathbb{R}^n_+ \to \mathbb{R}$, která každé spotřební koši přiřadí číslo.

**Intuice:** „Kolik mi spotřební koš dává štěstí." Kardinální verze předpokládá, že rozdíly užitku mají smysl ($U(A) - U(B) = 5$ utilů); ordinální říká, že smysl má jen pořadí.

### Mezní užitek (Marginal Utility)

$$MU_X = \frac{\partial U}{\partial X}$$

**Původ:** parciální derivace užitkové funkce podle množství statku $X$. V diskrétní podobě $MU_X = \Delta U / \Delta X$ při změně $\Delta X = 1$.

**Intuice:** „O kolik mi vzroste užitek, když koupím o jednu jednotku $X$ navíc." Zákon klesajícího mezního užitku (Gossenův 1. zákon): $\partial MU_X / \partial X < 0$, tj. $\partial^2 U / \partial X^2 < 0$ — každá další jednotka přidá méně.

### Rovnováha spotřebitele kardinálně (Gossenův 2. zákon)

$$\frac{MU_X}{P_X} = \frac{MU_Y}{P_Y} = \dots = \frac{MU_n}{P_n} = \lambda$$

**Původ:** podmínka prvního řádu maximalizace užitku při rozpočtovém omezení $\sum P_i X_i = I$. Gossen (1854) ji formuloval jako zákon vyrovnaných mezních užitků.

**Intuice:** „Poslední koruna utracená za každý statek mi musí přinést stejný mezní užitek." Kdyby $MU_X / P_X > MU_Y / P_Y$, vyplatí se přesunout výdaj z $Y$ na $X$. Stínová cena $\lambda$ je mezní užitek příjmu (utility per koruna).

### Mezní míra substituce (MRS) ordinálně

$$MRS_C = -\frac{dY}{dX}\bigg|_{U = U_0} = \frac{MU_X}{MU_Y}$$

**Původ:** sklon indiferenční křivky $U(X, Y) = U_0$. Z totálního diferenciálu $dU = MU_X \, dX + MU_Y \, dY = 0$ plyne $dY/dX = -MU_X / MU_Y$. Záporné znaménko se vykompenzuje a definujeme $MRS_C > 0$.

**Intuice:** „Kolika jednotek $Y$ se musím vzdát, abych získal jednotku $X$ a zůstal stejně spokojen." Klesající MRS = konvexní indiferenční křivky = preferují se diverzifikované koše.

### Cobb-Douglasova užitková funkce

$$U(X, Y) = X^a \cdot Y^b, \qquad a, b > 0$$

**Původ:** Cobb-Douglas (1928) původně pro produkční funkci, později aplikován i na užitek. Multiplikativní forma s mocninnými exponenty.

**Intuice:** Statky $X, Y$ jsou částečně substituty (oba se musejí konzumovat — užitek je nulový, pokud chybí jeden). Exponenty $a, b$ vyjadřují **váhu** statků v preferencích.

### MRS pro Cobb-Douglas

$$MRS_C = \frac{MU_X}{MU_Y} = \frac{a X^{a-1} Y^b}{b X^a Y^{b-1}} = \frac{a Y}{b X}$$

**Původ:** dosazení $MU_X = a X^{a-1} Y^b$ a $MU_Y = b X^a Y^{b-1}$ do definice MRS.

**Intuice:** MRS závisí jen na poměru $Y/X$ a vahách $a/b$ — homogennost stupně 0 v $(X, Y)$. Pokud $X$ je hodně a $Y$ málo, hodnota dalšího kusu $Y$ je relativně vysoká.

---

## 2. Optimalizace spotřebitele

**Základní téma:** [[mikk-rovnovaha-spotrebitele|Rovnováha spotřebitele]]

### Rozpočtové omezení

$$P_X \cdot X + P_Y \cdot Y = I$$

**Původ:** definice — celkový výdaj se rovná příjmu. V intervalovém tvaru $P_X X + P_Y Y \le I$, ale v rovnováze platí rovnost (spotřebitel utratí celý příjem, předpoklad nenasycenosti).

**Intuice:** Přímka v rovině $(X, Y)$ se sklonem $-P_X / P_Y$ a průsečíky $I/P_X$ (na ose $X$) a $I/P_Y$ (na ose $Y$).

### Lagrangián spotřebitelovy úlohy

$$L(X, Y, \lambda) = U(X, Y) + \lambda \cdot (I - P_X X - P_Y Y)$$

**Původ:** standardní metoda Lagrangeových multiplikátorů pro vázanou optimalizaci $\max U$ při omezení $P_X X + P_Y Y = I$.

**Intuice:** Bez omezení by spotřebitel chtěl koupit nekonečno; multiplikátor $\lambda$ vynucuje rozpočet. Hodnota $\lambda^*$ v optimu = mezní užitek koruny příjmu.

### Podmínky prvního řádu (FOC)

$$\frac{\partial L}{\partial X} = MU_X - \lambda P_X = 0$$
$$\frac{\partial L}{\partial Y} = MU_Y - \lambda P_Y = 0$$
$$\frac{\partial L}{\partial \lambda} = I - P_X X - P_Y Y = 0$$

**Původ:** FOC Lagrangeovy úlohy.

**Intuice:** Z prvních dvou: $\lambda = MU_X / P_X = MU_Y / P_Y$ (Gossenův 2. zákon, viz sekce 1). Třetí podmínka říká, že rozpočet musí být vyčerpán.

### Podmínka tečnosti (ordinálně)

$$MRS_C = \frac{MU_X}{MU_Y} = \frac{P_X}{P_Y}$$

**Původ:** poměr dvou prvních FOC.

**Intuice:** „Sklon indiferenční křivky = sklon rozpočtové přímky." Optimum spotřebitele leží v bodě, kde se nejvyšší dosažitelná indiferenční křivka **dotýká** rozpočtové přímky.

### Stínová cena (interpretace $\lambda$)

$$\lambda^* = \frac{\partial U^*}{\partial I} = \frac{MU_X}{P_X} = \frac{MU_Y}{P_Y}$$

**Původ:** věta o obálce (envelope theorem) aplikovaná na maximální užitkovou funkci $U^*(P_X, P_Y, I)$.

**Intuice:** „O kolik vzroste užitek, když mi přidají jednu korunu příjmu" — mezní užitek peněz. V rovnováze stejný napříč všemi statky.

---

## 3. Marshallova vs. Hicksova poptávka — dualita

**Základní téma:** [[mikk-marshall-hicks-poptavka|Marshallova vs. Hicksova poptávka]]

### Marshallova (necompensated, ordinary) poptávka

$$X^M = X^M(P_X, P_Y, I)$$

**Původ:** řešení primární úlohy $\max U(X, Y)$ s.t. $P_X X + P_Y Y = I$.

**Intuice:** „Jaké množství statku $X$ koupím při cenách $P_X, P_Y$ a příjmu $I$." Zachycuje kombinaci substitučního a důchodového efektu při změně ceny.

### Hicksova (compensated) poptávka

$$X^H = X^H(P_X, P_Y, U_0)$$

**Původ:** řešení duální úlohy $\min E = P_X X + P_Y Y$ s.t. $U(X, Y) = U_0$.

**Intuice:** „Jaké množství $X$ koupím, kdybych měl vždy zachovat užitek $U_0$." Zachycuje **pouze substituční efekt** — důchodový je „odkompenzován" tím, že se mění příjem tak, aby užitek zůstal stejný.

### Nepřímá užitková funkce

$$V(P_X, P_Y, I) = \max_{X, Y} \{ U(X, Y) : P_X X + P_Y Y \le I \}$$

**Původ:** maximální dosažitelný užitek jako funkce parametrů úlohy.

**Intuice:** „Kolik užitku mi přinese rozpočet $I$ při cenách $(P_X, P_Y)$." Klesá v cenách, roste v příjmu, je homogenní stupně 0 (zdvojnásobení všech cen i příjmu nic nezmění).

### Výdajová funkce

$$E(P_X, P_Y, U_0) = \min_{X, Y} \{ P_X X + P_Y Y : U(X, Y) \ge U_0 \}$$

**Původ:** minimální výdaj nutný k dosažení užitku $U_0$ při cenách $(P_X, P_Y)$.

**Intuice:** „Kolik korun musím utratit, abych si zachoval životní standard $U_0$." Roste v cenách, roste v $U_0$, je homogenní stupně 1 v cenách (zdvojnásobení cen zdvojnásobí výdaj).

### Shephardovo lemma

$$\frac{\partial E(P_X, P_Y, U_0)}{\partial P_X} = X^H(P_X, P_Y, U_0)$$

**Původ:** věta o obálce aplikovaná na $E$ — derivace minimální výdajové funkce podle ceny dává odpovídající Hicksovu poptávku.

**Intuice:** „Když cena $P_X$ vzroste o malou jednotku, výdaj se zvýší přibližně o $X^H$ (kolik kusů jsem teď kupoval)." Hicksova poptávka je tedy cenovou „derivací" výdajové funkce.

### Royova identita

$$X^M(P_X, P_Y, I) = -\frac{\partial V / \partial P_X}{\partial V / \partial I}$$

**Původ:** věta o obálce aplikovaná na nepřímou užitkovou funkci.

**Intuice:** „Marshallova poptávka se dá spočítat z $V$ bez explicitního řešení FOC." Tato identita ukazuje hlubokou symetrii primární a duální úlohy.

### Slutského rovnice

$$\frac{\partial X^M}{\partial P_X} = \underbrace{\frac{\partial X^H}{\partial P_X}}_{\text{substituční efekt} \le 0} \; - \; \underbrace{X^M \cdot \frac{\partial X^M}{\partial I}}_{\text{důchodový efekt}}$$

**Původ:** Eugen Slutsky (1915), z totálního diferenciálu identity $X^H(P_X, P_Y, U_0) = X^M(P_X, P_Y, E(P_X, P_Y, U_0))$.

**Intuice:** „Změna Marshallovy poptávky při změně ceny = substituční efekt (čistá substituce při zachování užitku) + důchodový efekt (změna reálné kupní síly)." Pro normální statky jsou oba efekty záporné, pro Giffenovy statky důchodový převažuje a celkový efekt je kladný.

### Vztah Marshall–Hicks v optimu

$$X^M(P_X, P_Y, I) = X^H(P_X, P_Y, V(P_X, P_Y, I))$$
$$X^H(P_X, P_Y, U_0) = X^M(P_X, P_Y, E(P_X, P_Y, U_0))$$

**Původ:** identity z duality.

**Intuice:** „V optimu se obě poptávky shodují — liší se jen tím, co je proměnná: Marshall fixuje $I$, Hicks fixuje $U_0$." Viz [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]].

---

## 4. Elasticity (4 typy + speciální)

**Základní téma:** [[mikk-elasticita-poptavky|Elasticita poptávky]]

### Cenová elasticita poptávky (bodová)

$$E_D = -\frac{P}{Q} \cdot \frac{dQ}{dP}$$

**Původ:** definice procentní citlivosti množství na změnu ceny: $E_D = \% \Delta Q / \% \Delta P = (\Delta Q / Q) / (\Delta P / P)$. V limitě se diferencemi nahradíme derivací.

**Intuice:** „O kolik procent klesne poptávané množství, když cena vzroste o 1 %." Záporné znaménko poptávky kompenzujeme `−`, takže $E_D > 0$.

**Klasifikace:**
- $E_D > 1$ — elastická poptávka (luxusní zboží, mnoho substitutů)
- $E_D = 1$ — jednotkově elastická (max tržního potenciálu)
- $0 < E_D < 1$ — neelastická (potraviny, léky)
- $E_D = 0$ — dokonale neelastická (insulin pro diabetika)
- $E_D = \infty$ — dokonale elastická (homogenní statek v dokonalé konkurenci)

### Oblouková elasticita (mid-point)

$$E_D = -\frac{(Q_2 - Q_1) / (Q_2 + Q_1)}{(P_2 - P_1) / (P_2 + P_1)} = -\frac{\Delta Q}{\Delta P} \cdot \frac{P_1 + P_2}{Q_1 + Q_2}$$

**Původ:** úprava bodové definice pro **diskrétní** změny cen — místo bodu $(P, Q)$ použijeme **střed** intervalu, čímž je výsledek symetrický (nezávisí na směru změny).

**Intuice:** Když nemáme spojitou poptávkovou funkci, ale jen dva body $(P_1, Q_1)$ a $(P_2, Q_2)$, počítáme oblouk. Použití středu odstraňuje paradox „elasticita vzhůru ≠ elasticita dolů".

### Geometrická elasticita

$$E_D = \frac{AC}{EC}$$

**Původ:** z geometrie — pro lineární poptávku $P = aQ + b$ ($a < 0$) v bodě $E$ je $AC$ vzdálenost od $E$ k průsečíku s osou $Q$ a $EC$ vzdálenost od $E$ k průsečíku s osou $P$.

**Intuice:** Na lineární poptávkové křivce klesá elasticita zhora dolů: nahoře $E_D \to \infty$, uprostřed $E_D = 1$ (max tržního potenciálu), dole $E_D \to 0$. Geometrická konstrukce dává okamžitou hodnotu.

### Konstantní elasticita (mocninná poptávka)

$$P = A \cdot Q^a \quad \Leftrightarrow \quad Q = (P/A)^{1/a}$$

$$E_D = -\frac{1}{a}$$

**Původ:** pro $P = A Q^a$ je $dQ/dP = (1/a)(P/A)^{1/a - 1} \cdot 1/A$, dosazením do $E_D = -(P/Q)(dQ/dP)$ vyjde $E_D = -1/a$ (konstantní).

**Intuice:** Funkce typu $P = A Q^a$ má **stejnou elasticitu ve všech bodech** — proto se používá v ekonometrii (logaritmováním vznikne lineární regrese: $\ln P = \ln A + a \ln Q$).

**Příklad ze cvičení:** $P = 66 Q^{-1/3} \Rightarrow E_D = -1/(-1/3) = 3$.

### Cenová elasticita nabídky

$$E_S = \frac{P}{Q} \cdot \frac{dQ}{dP}$$

**Původ:** analogicky k poptávce, ale bez záporného znaménka (nabídka je rostoucí v ceně).

**Intuice:** „O kolik procent vzroste nabízené množství, když cena vzroste o 1 %." V krátkém období je nabídka méně elastická (nelze rychle zvýšit kapacitu) než v dlouhém.

### Křížová elasticita

$$E_{XY} = \frac{\partial Q_X / Q_X}{\partial P_Y / P_Y} = \frac{\partial Q_X}{\partial P_Y} \cdot \frac{P_Y}{Q_X}$$

**Původ:** analogicky, ale derivujeme poptávku po $X$ podle ceny **jiného** statku $Y$.

**Klasifikace:**
- $E_{XY} > 0$ — **substituty** (káva a čaj: zdraží káva, lidé kupují víc čaje)
- $E_{XY} < 0$ — **komplementy** (auto a benzin: zdraží benzin, klesá poptávka po autech)
- $E_{XY} = 0$ — nezávislé statky

**Intuice:** Diagnostika konkurenčních a doplňkových vztahů na trhu.

### Příjmová (důchodová) elasticita

$$E_I = \frac{\partial Q / Q}{\partial I / I} = \frac{\partial Q}{\partial I} \cdot \frac{I}{Q}$$

**Původ:** definice citlivosti poptávky na změnu příjmu (nominálního důchodu).

**Klasifikace:**
- $E_I > 1$ — **luxusní zboží** (auta, dovolená, šperky)
- $0 < E_I < 1$ — **nezbytné zboží** (potraviny, oblečení)
- $E_I < 0$ — **podřadné zboží** (chleba, brambory v bohaté domácnosti)
- $E_I = 0$ — neutrální (sůl)

**Intuice:** Engelovy křivky zachycují, jak se mění výdaje na statek s rostoucím příjmem.

---

## 5. Tržní potenciál

**Základní téma:** [[mikk-elasticita-poptavky|Elasticita a tržní potenciál]]

### Definice tržního potenciálu

$$MP(P) = TR(P) = P \cdot Q(P)$$

**Původ:** definice celkové tržby jako funkce ceny (s dosazenou poptávkou $Q = D(P)$).

**Intuice:** Při jaké ceně inkasujeme nejvyšší tržbu? Záleží na elasticitě.

### Maximalizace tržního potenciálu

$$\frac{dMP}{dP} = Q + P \cdot \frac{dQ}{dP} = 0 \quad \Rightarrow \quad E_D = 1$$

**Původ:** FOC pro $\max P \cdot Q(P)$ — vyjde z toho, že max tržby = jednotkově elastický bod poptávky.

**Intuice:** „Když je $E_D > 1$, snížením ceny získáš víc, než ztratíš (zvyš prodej). Když $E_D < 1$, zvyšením ceny získáš víc, než ztratíš (zvyš cenu). Optimum: $E_D = 1$."

### Vzorec přes elasticitu

$$\frac{dMP}{dP} = Q \cdot (1 - E_D)$$

**Původ:** úpravou předchozího vzorce ($Q + P \cdot dQ/dP = Q + Q \cdot (P/Q)(dQ/dP) = Q(1 + (-E_D)) = Q(1-E_D)$).

**Intuice:** Znaménko derivace tržby = znaménko $(1 - E_D)$. V neelastické oblasti tržba roste s cenou, v elastické klesá.

---

## 6. Monopol

**Základní téma:** [[mikk-monopol-pokrocily|Pokročilý monopol]]

### Mezní příjem monopolu

$$MR = \frac{dTR}{dQ} = P + Q \cdot \frac{dP}{dQ}$$

**Původ:** derivace celkové tržby $TR = P(Q) \cdot Q$ podle množství. Druhý člen $Q \cdot dP/dQ < 0$ vyjadřuje, že monopolista musí snižovat cenu, aby prodal víc.

**Intuice:** „Mezní příjem je vždy pod cenou (krom dokonalé konkurence, kde $dP/dQ = 0$)." Pro lineární poptávku $P = a - bQ$: $MR = a - 2bQ$ (dvojnásobný sklon).

### Markup vzorec přes elasticitu

$$\frac{P - MC}{P} = \frac{1}{E_D}$$

**Původ:** podmínka $MR = MC$, kde $MR = P(1 - 1/E_D)$. Po úpravě.

**Intuice:** „Procentuální přirážka nad mezními náklady = 1/elasticita." Čím elastičtější poptávka (víc substitutů), tím menší marže. V dokonalé konkurenci $E_D \to \infty \Rightarrow P = MC$.

### Lernerův index tržní síly

$$L = \frac{P - MC}{P} = \frac{1}{E_D}$$

**Původ:** Abba P. Lerner (1934) — měřítko síly tržního dominanta. Hodnoty $0 \le L \le 1$.

**Intuice:** $L = 0$ → dokonalá konkurence, $L \to 1$ → silný monopol.

### Optimální cena monopolisty

$$P^* = \frac{MC}{1 - 1/E_D} = MC \cdot \frac{E_D}{E_D - 1}$$

**Původ:** úprava markup vzorce.

**Intuice:** Cena je **markup** mezních nákladů, faktor $E_D / (E_D - 1)$ je vždy $> 1$ pro $E_D > 1$.

### Mrtvá ztráta (Deadweight Loss, DWL)

$$DWL = \frac{1}{2} (P^M - P^C)(Q^C - Q^M)$$

**Původ:** plocha trojúhelníka mezi monopolním ($P^M, Q^M$) a konkurenčním ($P^C, Q^C$) bodem.

**Intuice:** Přebytek, který se ztratil tím, že monopol nevyrobí $Q^C$. Reprezentuje neefektivní alokaci zdrojů.

**Příklad:** $P^M = 55$, $Q^M = 9$, $P^C = 10$, $Q^C = 18$. $DWL = 0{,}5 \cdot (55 - 10) \cdot (18 - 9) = 0{,}5 \cdot 45 \cdot 9 = 202{,}5$.

### Monopol s více závody

$$MC_1(Q_1) = MC_2(Q_2) = \dots = MC_T = MR(Q_T)$$

**Původ:** FOC úlohy $\max \pi = TR(Q_1 + \dots + Q_n) - C_1(Q_1) - \dots - C_n(Q_n)$.

**Intuice:** „Vyrábí v každém závodě tolik, aby mezní náklady byly stejné." Kdyby ne, přesune produkci z dražšího závodu do levnějšího. Výsledný **horizontální součet** $MC_T(Q)$ se rovná $MR$.

---

## 7. Cenová diskriminace

**Základní téma:** [[mikk-cenova-diskriminace|Cenová diskriminace]]

### 1. stupeň (perfektní)

**Princip:** Cena = WTP každého zákazníka. Monopolista zachytí **celý spotřebitelský přebytek**.

$$\pi = \int_0^{Q^*} [P(q) - MC(q)] \, dq$$

**Intuice:** Teoreticky maximální zisk; v praxi nemožné (vyžaduje znalost preferencí každého zákazníka). Aukce, individualizovaná cena u zubaře.

### 2. stupeň (blokové cenování / quantity discounts)

**Princip:** Různé ceny za různá množství; spotřebitel si volí blok sám (samosegmentace).

**Intuice:** Mobilní tarify (1 GB za 200 Kč, 5 GB za 600 Kč), elektřina (první kWh dražší, další levnější).

### 3. stupeň (segmentace trhu)

$$MR_1(Q_1) = MR_2(Q_2) = \dots = MR_n(Q_n) = MC$$

**Původ:** FOC úlohy $\max \pi = \sum_i TR_i(Q_i) - C(Q)$, kde $Q = \sum Q_i$.

**Intuice:** „Na každém trhu vyrovnám mezní příjem s mezními náklady." Trh s elastickější poptávkou dostane **nižší** cenu.

### Vztah cen na 2 trzích

$$\frac{P_1}{P_2} = \frac{1 - 1/E_2}{1 - 1/E_1}$$

**Původ:** z $MR_i = P_i (1 - 1/E_i) = MC$ pro oba trhy.

**Intuice:** Trh s vyšší elasticitou má nižší cenu. Pokud $E_1 > E_2$, pak $P_1 < P_2$. Příklad: studentské slevy (studenti elastičtější), ekonomická vs. business class v letadle.

### Plně řešený příklad (Block 5, Příklad 1)

Monopolista s $TC = Q^2 + 10Q$ na 2 trzích:
- Trh 1: $P_1 = 76 - 2Q_1 \Rightarrow MR_1 = 76 - 4Q_1$
- Trh 2: $P_2 = 124 - 2Q_2 \Rightarrow MR_2 = 124 - 4Q_2$

$MC = 2Q + 10$, $Q = Q_1 + Q_2$.

Z $MR_1 = MC$: $76 - 4Q_1 = 2(Q_1 + Q_2) + 10 \Rightarrow 6Q_1 + 2Q_2 = 66$
Z $MR_2 = MC$: $124 - 4Q_2 = 2(Q_1 + Q_2) + 10 \Rightarrow 2Q_1 + 6Q_2 = 114$

Řešení: $Q_1 = 8$, $Q_2 = 7$, ceny $P_1 = 60$, $P_2 = 110$.

---

## 8. Two-Part Tariff a Bundling

**Základní téma:** [[mikk-bundling-two-part-tariff|Bundling a Two-Part Tariff]]

### Two-Part Tariff (dvousložková tarifa)

$$\pi = (P - MC) \cdot Q \cdot n + (T - T_0) \cdot n$$

**Původ:** Spotřebitel platí **fixní poplatek** $T$ (vstupné, předplatné) plus **variabilní cenu** $P$ za jednotku. $T_0$ je nutné minimum aby se vůbec zúčastnil.

**Intuice:** Disneyland (vstupné + jízdenky), mobilní tarif (paušál + minutovka), kávovary (stroj + kapsle). Optimum: $P = MC$ a $T = CS$ (zachytíme celý přebytek přes fixní složku).

### Bundling (balíčkování)

**Princip:** Monopolista nabízí balíček zboží $A + B$ za pevnou cenu, místo aby je prodával zvlášť.

**Vzorec optimální ceny balíčku** (čistý bundling, 2 zákazníci):

$$P_{balíček} \le \min_i (WTP_i^A + WTP_i^B)$$

**Původ:** Aby všichni zákazníci kupili, musí cena balíčku být menší nebo rovna nejnižší celkové ochotě platit.

**Intuice:** Bundling funguje, když preference jsou **negativně korelované** — někdo si víc cení $A$, jiný $B$, ale součty jsou podobné. Microsoft Office (Word + Excel + PowerPoint), Spotify Family.

### Plně řešený příklad (Block 5, Příklad 3, Hotel U Pepy Flinty)

3 skupiny zákazníků × 2 služby (ubytování + wellness):
- Manažeři: WTP $200 + 100 = 300$
- Páry: WTP $150 + 200 = 350$
- Studenti: WTP $100 + 50 = 150$

Cena balíčku $P = 310$ — koupí všichni kromě studentů.

Zisk: $2 \cdot 50 \text{ skupin} \cdot (310 - 60 \text{ MC}) = 100 \cdot 250 = 25\,000$. (V přednášce výsledek $13\,800$ při jiných parametrech — viz [[mikk-vzorove-zkousky]].)

---

## 9. Monopson

**Základní téma:** [[mikk-monopson-mzdova-diskriminace|Monopson na trhu práce]]

### Mzdová křivka monopsonu

$$S_L: W = f(L), \qquad \frac{dW}{dL} > 0$$

**Původ:** Monopson je **jediný kupující** práce — musí zvyšovat mzdu, chce-li najmout víc lidí (rostoucí nabídková křivka).

**Intuice:** „Aby monopson získal o jednoho zaměstnance navíc, musí zvýšit mzdu — a to **všem**, ne jen tomu novému."

### Mezní výdaj na práci (Marginal Cost of Labor)

$$MCL = \frac{d(W \cdot L)}{dL} = W + L \cdot \frac{dW}{dL} > W$$

**Původ:** derivace celkových výdajů na práci $TC_L = W \cdot L$ podle $L$. Druhý člen $L \cdot dW/dL$ vyjadřuje, že zvýšení mzdy se týká i všech předchozích zaměstnanců.

**Intuice:** $MCL$ vždy nad $S_L$ (analog vztahu $MR < P$ u monopolu). Pro lineární $W = a + bL$: $MCL = a + 2bL$.

### Optimum monopsonu

$$MCL = MRPL$$

**Původ:** FOC úlohy $\max \pi = TR - W \cdot L$, kde $TR = P \cdot Q(L)$ a $MRPL = P \cdot MP_L$ (mezní příjem z práce).

**Intuice:** „Najímej, dokud mezní výdaj na práci nedosáhne mezního příjmu z práce." Optimální $L^*$ je tam, kde se kříží $MCL$ a $MRPL$.

### Mzda a renta v rovnováze

$$W^* = f(L^*) \quad \text{(z mzdové křivky } S_L\text{)}$$

$$\text{Monopsoní renta} = L^* \cdot (MRPL - W^*)$$

**Původ:** Monopson platí mzdu z $S_L$ při optimálním $L^*$, přičemž $W^* < MRPL$.

**Intuice:** „Monopson platí míň, než by zaplatil konkurenční trh." Rozdíl mezi $MRPL$ a $W^*$ je **monopsoní renta** — výsada plynoucí z tržní moci. V USA byly příklady moneconlpsonu textilní města 19. století, dnes velké korporace v menších městech.

---

## 10. Cournotův model

**Základní téma:** [[mikk-oligopol-cournot-stackelberg|Cournotův a Stackelbergův oligopol]]

### Předpoklady (lineární verze)

- Tržní poptávka: $P = a - b Q$, kde $Q = Q_1 + Q_2$
- 2 firmy s identickými mezními náklady $MC = 0$ (zjednodušení)
- Firmy si **současně** volí množství $Q_1, Q_2$

### Reakční funkce firmy 1

$$Q_1 = \frac{a}{2b} - \frac{Q_2}{2}$$

**Původ:** Firma 1 maximalizuje $\pi_1 = (a - b(Q_1 + Q_2)) Q_1$. FOC: $\partial \pi_1 / \partial Q_1 = a - 2bQ_1 - bQ_2 = 0 \Rightarrow Q_1 = (a - bQ_2)/(2b) = a/(2b) - Q_2/2$.

**Intuice:** „Co udělám, když si myslím, že soupeř vyrobí $Q_2$." Funkce klesá v $Q_2$ — když soupeř víc, já míň.

### Cournotova rovnováha (Nash)

$$Q_1^C = Q_2^C = \frac{a}{3b}, \qquad Q^C = \frac{2a}{3b}, \qquad P^C = \frac{a}{3}$$

$$\pi_1^C = \pi_2^C = \frac{a^2}{9b}$$

**Původ:** Symetrické řešení soustavy reakčních funkcí. $Q_1 = a/(2b) - Q_1/2 \Rightarrow Q_1 = a/(3b)$.

**Intuice:** „Stabilní bod, kde každá firma reaguje optimálně na soupeřovu strategii." Antoine Augustin Cournot (1838) — první analýza oligopolu.

---

## 11. Stackelbergův model

**Základní téma:** [[mikk-oligopol-cournot-stackelberg|Cournotův a Stackelbergův oligopol]]

### Předpoklady

- Tržní poptávka $P = a - b Q$, $MC = 0$.
- Firma 1 = **lider** (volí $Q_1$ jako první).
- Firma 2 = **follower** (vidí $Q_1$ a reaguje).

### Follower (firma 2)

Reaguje podle Cournotovy reakční funkce:

$$Q_2 = \frac{a}{2b} - \frac{Q_1}{2}$$

### Lider (firma 1)

Vědomí že $Q_2$ závisí na $Q_1$, dosadí to do své zisk-funkce:

$$\pi_1 = (a - b(Q_1 + Q_2(Q_1))) Q_1 = \left( a - b\left(Q_1 + \frac{a}{2b} - \frac{Q_1}{2}\right) \right) Q_1 = \left(\frac{a}{2} - \frac{bQ_1}{2}\right) Q_1$$

FOC: $\partial \pi_1 / \partial Q_1 = a/2 - b Q_1 = 0 \Rightarrow Q_1 = a/(2b)$.

### Stackelbergova rovnováha

$$Q_1^S = \frac{a}{2b}, \qquad Q_2^S = \frac{a}{4b}, \qquad Q^S = \frac{3a}{4b}, \qquad P^S = \frac{a}{4}$$

$$\pi_1^S = \frac{a^2}{8b}, \qquad \pi_2^S = \frac{a^2}{16b}$$

**Intuice:** „Lider využívá své první-tahové výhody (first-mover advantage). Vyrobí víc než v Cournotově modelu, follower je nucen produkovat méně. Liderův zisk je 2× větší než Cournotův, followerův poloviční."

**Heinrich von Stackelberg (1934)** — model dominantní firmy.

---

## 12. Bertrandův model

**Základní téma:** [[mikk-oligopol-bertrand-cenova-konkurence|Bertrandův oligopol]]

### Předpoklady (homogenní zboží)

- 2 firmy si **současně** volí cenu (ne množství).
- Spotřebitelé kupují u levnější firmy. Při shodě cen každá dostane polovinu trhu.
- $MC_1 = MC_2 = c$ (identické).

### Bertrandova rovnováha

$$P_1 = P_2 = MC, \qquad \pi_1 = \pi_2 = 0$$

**Původ:** Joseph Bertrand (1883). Argument: pokud by $P_1 > MC$, firma 2 ji podseče o haléř a získá celý trh. Stejně tak firma 1. Jediný stabilní bod: $P_1 = P_2 = MC$, kde už podsekávat nelze (záporný zisk).

**Intuice:** **Bertrandův paradox** — pouhé 2 firmy stačí na konkurenční výsledek. V realitě paradox neplatí, protože:
- Zboží není homogenní (diferenciace)
- Kapacitní omezení (Edgeworth)
- Opakované hry (možnost koluze)
- Vyhledávací náklady spotřebitelů

---

## 13. Sdílený monopol (koluze)

**Základní téma:** [[mikk-oligopol-cenovy-vudce-kartel|Cenový vůdce a kartel]]

### Princip

2 firmy se domluví, jakoby byly **jeden monopol**. Maximalizují společný zisk a dělí ho mezi sebe.

### Optimum koluze

$$Q^K = \frac{a}{2b}, \qquad P^K = \frac{a}{2}, \qquad \sum \pi^K = \frac{a^2}{4b}$$

Při dělení 50:50: $Q_1^K = Q_2^K = a/(4b)$, $\pi_i^K = a^2/(8b)$.

**Původ:** $\max \pi = (a - bQ)Q \Rightarrow Q^* = a/(2b)$ (standardní monopol).

**Intuice:** „Společný zisk je největší, ale je to **nestabilní** rovnováha — každá firma má motivaci podvádět (zvýšit svou produkci nad $a/(4b)$, dokud druhá drží slovo)."

### Stabilita koluze

Koluze vyžaduje:
- Detekci podvádění (kontrola)
- Trestání podvádějící firmy (grim trigger, tit-for-tat)
- Nízkou diskontní sazbu (budoucí zisky musí převažovat nad krátkodobým podvodným ziskem)

V opakované hře s nekonečným horizontem může být koluze **subgame-perfect Nashovou rovnováhou** (folk theorem).

---

## 14. Zlatá srovnávací tabulka 4 modelů

Pro lineární poptávku $P = a - bQ$ a $MC = 0$:

| Model | $Q_1$ | $Q_2$ | $Q$ celkem | $P$ | $\pi_1$ | $\pi_2$ | $\sum \pi$ |
|-------|-------|-------|-----------|-----|---------|---------|-----------|
| Sdílený monopol (koluze) | $\frac{a}{4b}$ | $\frac{a}{4b}$ | $\frac{a}{2b}$ | $\frac{a}{2}$ | $\frac{a^2}{8b}$ | $\frac{a^2}{8b}$ | $\frac{a^2}{4b}$ |
| Cournot | $\frac{a}{3b}$ | $\frac{a}{3b}$ | $\frac{2a}{3b}$ | $\frac{a}{3}$ | $\frac{a^2}{9b}$ | $\frac{a^2}{9b}$ | $\frac{2a^2}{9b}$ |
| Stackelberg | $\frac{a}{2b}$ | $\frac{a}{4b}$ | $\frac{3a}{4b}$ | $\frac{a}{4}$ | $\frac{a^2}{8b}$ | $\frac{a^2}{16b}$ | $\frac{3a^2}{16b}$ |
| Bertrand | $\frac{a}{2b}$ | $\frac{a}{2b}$ | $\frac{a}{b}$ | $0$ | $0$ | $0$ | $0$ |

**Pořadí podle:**
- **Celkového zisku odvětví:** koluze ($a^2/4b$) > Cournot ($2a^2/9b$) > Stackelberg ($3a^2/16b$) > Bertrand ($0$).
- **Spotřebitelského přebytku:** Bertrand > Stackelberg > Cournot > koluze.
- **Stability:** Cournot, Stackelberg, Bertrand jsou Nashovy rovnováhy; koluze není (motivace k podvádění).

Detailní rozbor v [[mikk-srovnani-modelu-oligopolu|MikK — Srovnání oligopolních modelů]].

---

## 15. Monopolistická konkurence

**Základní téma:** [[mikk-monopolisticka-konkurence|Monopolistická konkurence]]

### Měření koncentrace trhu

#### CR4 (four-firm concentration ratio)

$$CR_4 = s_1 + s_2 + s_3 + s_4$$

kde $s_i = Q_i / Q$ je tržní podíl $i$-té firmy.

**Klasifikace:**
- $CR_4 < 40\,\%$ — konkurenční trh
- $40\,\% \le CR_4 < 70\,\%$ — středně koncentrovaný
- $CR_4 \ge 70\,\%$ — silně koncentrovaný (oligopol)

#### Herfindahl-Hirschmanův index (HHI)

$$HHI = \sum_{i=1}^n s_i^2$$

kde $s_i$ je tržní podíl v procentech (0–100).

**Klasifikace** (US DOJ Guidelines):
- $HHI < 1\,000$ — konkurenční trh
- $1\,000 \le HHI < 1\,800$ — středně koncentrovaný
- $HHI \ge 1\,800$ — silně koncentrovaný

**Intuice:** HHI dává **větší váhu velkým firmám** (kvadrát). Plně konkurenční trh: $HHI \to 0$. Monopol: $HHI = 10\,000$.

### Chamberlinova rovnováha LR (long run)

$$LAC(Q^*) = AR(Q^*) = P^*$$

**Původ:** V dlouhém období do trhu vstupují další firmy s diferencovaným zbožím, dokud nezmizí ekonomický zisk. Bod tečnosti $LAC$ a poptávkové křivky $AR$.

**Intuice:** „V dlouhém období každá firma má **0 ekonomický zisk** (jako v dokonalé konkurenci), ale $P > MC$ (jako v monopolu) — neefektivnost s diferenciací." Edward Chamberlin (1933).

---

## 16. Behavioristické modely firmy

**Základní téma:** [[mikk-behavioristicke-modely-firmy|Behavioristické modely firmy]]

### Simon — aspirační úroveň (satisficing)

**Princip:** Firma nemaximalizuje, ale **stačí** dosáhnout aspirační úrovně zisku $\pi^*$. Když $\pi \ge \pi^*$, hledání končí. Když $\pi < \pi^*$, hledá se dál.

**Vzorec dynamiky aspirace:**

$$\pi^*_{t+1} = \alpha \cdot \pi_t + (1 - \alpha) \cdot \pi^*_t, \quad \alpha \in [0, 1]$$

**Původ:** Herbert A. Simon (1955), Nobelova cena 1978. Bounded rationality — kognitivní omezení vedou k satisficing místo optimalizace.

**Intuice:** „Lidé hledají dost dobré řešení, ne nejlepší." Když firma zisk překračuje, aspirace stoupá; když je nedosahuje, aspirace klesá.

### Cyert-March — koalice s 5 oblastmi cílů

**Princip:** Firma = koalice zájmových skupin (vlastníci, manažeři, zaměstnanci, dodavatelé). Každá má své **side payments**. Cíle:

1. **Cíl výroby** (production goal)
2. **Cíl zásob** (inventory goal)
3. **Cíl prodeje** (sales goal)
4. **Cíl tržního podílu** (market share goal)
5. **Cíl zisku** (profit goal)

**Původ:** Richard Cyert & James March (1963), „A Behavioral Theory of the Firm."

**Intuice:** „Konflikty mezi cíli se řeší **sekvenčně** (nejdřív výroba, pak prodej, pak tržní podíl, pak zisk), ne simultánně. Firma uplatňuje **organizační slack** — drží rezervy, aby přežila výkyvy."

### Doyle — 8 cílů a zóny tolerance

**Princip:** Manažeři sledují 8 cílů (zisk, růst, tržní podíl, riziko, dividendy, sociální cíle, profesní status, osobní cíle). Pro každý je **zóna tolerance** $[L_i, U_i]$.

**Optimum:** dosáhnout každý cíl v jeho zóně, aniž by se některý dramaticky překročil/podlézl.

**Intuice:** „Místo jedné optimalizační rovnice — hledání **proveditelného bodu** v 8-rozměrném prostoru."

---

## 17. Manažerské modely firmy

**Základní téma:** [[mikk-alternativni-cile-firmy|Alternativní cíle firmy]]

### Baumol — maximalizace tržeb (sales revenue maximization)

$$\max TR = P \cdot Q$$

**Omezení:** $\pi \ge \pi_{\min}$ (minimální zisk pro vlastníky).

**FOC:** $\frac{dTR}{dQ} = MR = 0 \quad \Leftrightarrow \quad E_D = 1$

**Původ:** William Baumol (1959). Manažeři mají platy závislé na velikosti firmy, ne na zisku, takže preferují růst tržeb.

**Intuice:** „Baumolova firma vyrábí víc a prodává levněji než zisk-maximalizující monopol." Optimum leží v jednotkově elastickém bodě poptávky (max tržního potenciálu).

### Williamson — maximalizace užitku manažera

$$U_{man} = U(S, M, ID)$$

kde:
- $S$ = staff expenditures (počet podřízených)
- $M$ = managerial emoluments (luxusní auto, kanceláře)
- $ID$ = discretionary investment (investiční volnost)

**Omezení:** $\pi \ge \pi_{\min}$.

**Původ:** Oliver Williamson (1964), Nobelova cena 2009. Rozšiřuje principal-agent problém na manažera.

**Intuice:** „Manažer maximalizuje **vlastní benefity**, které pramení z velikosti firmy a kontroly nad penězi." Vede k inflaci stafu, luxusu a riskantním investicím.

### Ward — zaměstnanecká firma (labor-managed firm)

$$\max y = \frac{TR - FC}{L}$$

kde $y$ = příjem na zaměstnance.

**FOC:** $P \cdot MP_L = y \quad \Leftrightarrow \quad VMP_L = y$

**Původ:** Benjamin Ward (1958), model jugoslávské družstevní firmy.

**Intuice:** „Family firma maximalizuje **příjem na hlavu**, ne celkový zisk." Důsledky:
- **Klesá** zaměstnanost při růstu cen (paradoxně — chce méně zaměstnanců, aby každý dostal víc)
- Nestabilní reakce na šoky
- Underinvestment problem (nikdo nechce dlouhodobé investice)

---

## 18. Riziko a pojištění

**Základní téma:** [[mikk-riziko-nejistota-spotrebitele|Riziko a nejistota]]

### Očekávaný užitek (Expected Utility)

$$EU(L) = \sum_{i=1}^n p_i \cdot u(x_i)$$

kde $L = \{(x_1, p_1), \dots, (x_n, p_n)\}$ je loterie (výsledky $x_i$ s pravděpodobnostmi $p_i$).

**Původ:** Daniel Bernoulli (1738, paradox St. Petěrburku), formalizace von Neumann & Morgenstern (1944).

**Intuice:** „Spotřebitel hodnotí loterii ne podle očekávané **hodnoty** $E(L) = \sum p_i x_i$, ale podle očekávaného **užitku** $E(u(L))$." Klesající mezní užitek peněz vede k averzi k riziku.

### Klasifikace postojů k riziku

- **Risk averse** (averzní): $u'' < 0$ (konkávní), $u(E(L)) > E(u(L))$
- **Risk neutral** (neutrální): $u$ lineární, $u(E(L)) = E(u(L))$
- **Risk loving** (vyhledávající): $u'' > 0$ (konvexní), $u(E(L)) < E(u(L))$

### Jistotní ekvivalent (Certainty Equivalent)

$$u(CE) = E(u(L)) \quad \Rightarrow \quad CE = u^{-1}(E(u(L)))$$

**Intuice:** „Jistá částka, která mi přinese stejný užitek jako daná loterie." Pro risk-averse spotřebitele $CE < E(L)$.

### Riziková prémie

$$RP = E(L) - CE$$

**Původ:** rozdíl mezi očekávanou hodnotou loterie a jistotním ekvivalentem.

**Intuice:** „Kolik bych zaplatil, abych se loterie zbavil." Kladná pro risk-averse, nulová pro neutrálního, záporná pro risk-loving.

### Fair (actuarially fair) premium

$$\pi_F = p \cdot L$$

kde $p$ = pravděpodobnost ztráty, $L$ = velikost ztráty.

**Původ:** definice — pojistné se rovná očekávané ztrátě (pojišťovna ani nevydělává, ani neprodělává).

**Intuice:** „Risk-averse spotřebitel se za fair premium plně pojistí." V realitě pojišťovny účtují vyšší premium ($\pi > p L$) kvůli administrativním nákladům a marži; risk-averse spotřebitel se může pojistit i za vyšší premium, dokud zachovává očekávaný užitek.

### Plné pojištění (full insurance)

Pro risk-averse spotřebitele s fair premium:

$$x = W - \pi_F = W - pL \quad \text{(jisté bohatství)}$$

**Intuice:** „S plným pojištěním je bohatství v každém stavu světa stejné." Risk-averse spotřebitel vždy preferuje jisté bohatství před loterií se stejnou očekávanou hodnotou.

---

## Souhrnný přehled — frekvence vzorců na zkoušce

Z analýzy 14 zkouškových termínů (viz [[mikk-vzorove-zkousky|MikK — Vzorové zkoušky]]) vyplývá toto pořadí důležitosti:

| Téma | Frekvence (z 14) | Klíčový vzorec |
|------|------------------|---------------|
| Elasticita poptávky (4 typy) | 14/14 | $E_D = -(P/Q)(dQ/dP)$ |
| Optimum spotřebitele (Lagrange) | 13/14 | $MRS = P_X/P_Y$ |
| Monopol (markup, DWL) | 12/14 | $L = 1/E_D$, $DWL = 0{,}5(P^M-P^C)(Q^C-Q^M)$ |
| Cournot/Stackelberg | 11/14 | tabulka v sekci 14 |
| Cenová diskriminace 3. stupně | 10/14 | $MR_1 = MR_2 = MC$ |
| Bertrand | 7/14 | $P = MC$ |
| Marshall vs. Hicks | 6/14 | Slutsky |
| Two-Part Tariff / Bundling | 5/14 | $\pi = (P-MC)Q + T$ |
| Monopson | 4/14 | $MCL = MRPL$ |
| Behavioristické modely | 3/14 | (kvalitativní) |
| Manažerské modely (Baumol, Williamson, Ward) | 3/14 | $MR = 0$ (Baumol), $VMP_L = y$ (Ward) |
| Riziko a pojištění | 2/14 | $RP = E(L) - CE$ |

---

## Související stránky

- [[mikk|Mikroekonomie 2 (MikK)]] — kurzová stránka
- [[mikk-vzorove-zkousky|MikK — Vzorové zkoušky a Předtermíny]] — všech 14 termínů s řešeními
- [[mikk-srovnani-modelu-oligopolu|MikK — Srovnání oligopolních modelů]] — detailní rozbor 4 modelů

### Topic stránky podle sekcí

- Sekce 1, 2: [[mikk-utility-preference|Užitek a preference]], [[mikk-rovnovaha-spotrebitele|Rovnováha spotřebitele]]
- Sekce 3: [[mikk-marshall-hicks-poptavka|Marshall vs. Hicks]], [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]]
- Sekce 4, 5: [[mikk-elasticita-poptavky|Elasticita poptávky]], [[mikk-odhad-poptavky|Odhad poptávky]]
- Sekce 6, 7: [[mikk-monopol-pokrocily|Pokročilý monopol]], [[mikk-cenova-diskriminace|Cenová diskriminace]]
- Sekce 8: [[mikk-bundling-two-part-tariff|Bundling a Two-Part Tariff]]
- Sekce 9: [[mikk-monopson-mzdova-diskriminace|Monopson a mzdová diskriminace]]
- Sekce 10–14: [[mikk-oligopol-cournot-stackelberg|Cournot/Stackelberg]], [[mikk-oligopol-bertrand-cenova-konkurence|Bertrand]], [[mikk-oligopol-cenovy-vudce-kartel|Cenový vůdce a kartel]], [[mikk-oligopol-zalomena-poptavka|Zalomená poptávka]], [[mikk-vezno-dilema-teorie-her|Vězňovo dilema]]
- Sekce 15: [[mikk-monopolisticka-konkurence|Monopolistická konkurence]]
- Sekce 16, 17: [[mikk-behavioristicke-modely-firmy|Behavioristické modely]], [[mikk-alternativni-cile-firmy|Alternativní cíle firmy]], [[mikk-zamestnanecka-firma-ward|Zaměstnanecká firma (Ward)]]
- Sekce 18: [[mikk-riziko-nejistota-spotrebitele|Riziko a nejistota]]
- Doplňkově: [[mikk-trzni-rovnovaha-dynamika|Tržní rovnováha a dynamika]], [[mikk-prirozeny-monopol-regulace|Přirozený monopol]]

