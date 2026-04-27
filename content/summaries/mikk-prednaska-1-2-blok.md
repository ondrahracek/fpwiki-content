---
title: "MikK — Úvod, poptávka, spotřebitel, monopol"
course: mikk
type: summary
tags: [mikk, mikroekonomie, prednaska, spotrebitel, elasticita]
sources: [raw/mikk/Prednaska 1. a 2. blok.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# MikK — Úvod, poptávka, spotřebitel, monopol

> [!abstract] TL;DR
> Vstupní oblouk kurzu [[mikk|Mikroekonomie 2]] pokrývá organizační záležitosti, matematický aparát (lineární a kvadratické funkce, [[lagrangeova-metoda|Lagrange]]), úvod do nabídky a poptávky, **cenovou, křížovou a příjmovou elasticitu poptávky**, metody **odhadu poptávky**, dynamiku tržní rovnováhy (cobweb), **kardinální a ordinální teorii užitku**, indiferenční křivky, **rozpočtové omezení**, **substituční a důchodový efekt** podle Hickse i Slutského, výstavbu poptávkové křivky (PCC, ICC, Engel) a **dualitu Marshall ↔ Hicks**.

## Hlavní obsah

### Matematické základy

Před úvodem do mikroekonomické analýzy si Luňáček shrnuje:

- **Lineární funkce** $y = ax + b$ — interpretace sklonu, posunu.
- **Parabolické (kvadratické) funkce** $y = ax^2 + bx + c$ — vrchol, konvexita.
- **Optimum funkce jedné proměnné**: $y'(x^*) = 0$, $y''(x^*) < 0$ (maximum).
- **Vázaná optimalizace ([[lagrangeova-metoda|Lagrangeova metoda]]):** maximalizace $f(x,y)$ při $g(x,y) = 0$ vede k Lagrangiánu $\mathcal{L} = f - \lambda g$, podmínky $\partial\mathcal{L}/\partial x = \partial\mathcal{L}/\partial y = \partial\mathcal{L}/\partial \lambda = 0$.

### Veblenův a Bandwagon efekt

- **Veblenův efekt** — vyšší cena → vyšší poptávané množství u luxusního zboží (snobský motiv). Příklady: kosmetika Dr. Středa, šampaňské Perrier-Jouët.
- **Bandwagon efekt** — poptávka roste s tím, jak roste počet ostatních konzumentů (módní zboží).

### [[mikk-elasticita-poptavky|Cenová elasticita poptávky]]

> [!info] Vzorec
> $$E_D = \dfrac{\Delta Q / Q}{\Delta P / P} = \dfrac{dQ}{dP} \cdot \dfrac{P}{Q}$$

Kategorie:

| Hodnota $\lvert E_D \rvert$ | Kategorie | Reakce TR na pokles ceny |
|---|---|---|
| $> 1$ | elastická | TR roste |
| $= 1$ | jednotková | TR nemění se |
| $< 1$ | neelastická | TR klesá |
| $= 0$ | dokonale neelastická | — |
| $\to \infty$ | dokonale elastická | — |

**Geometrická interpretace:** na lineární poptávce $E_D$ není konstantní — od $\infty$ v ose $P$ klesá k $0$ v ose $Q$, $\lvert E_D \rvert = 1$ ve středu úsečky.

**Determinanty:** počet substitutů, podíl výdajů na rozpočtu, krátké vs. dlouhé období (dlouhé období → vyšší elasticita), nezbytnost zboží, návyk.

### Křížová a příjmová elasticita

- **Křížová** $E_{XY} = \dfrac{\partial Q_X / Q_X}{\partial P_Y / P_Y}$:
  - $E_{XY} > 0$ → **substituty** (káva ↔ čaj),
  - $E_{XY} < 0$ → **komplementy** (auto ↔ benzin),
  - $E_{XY} = 0$ → nezávislé zboží.
- **Příjmová** $E_I = \dfrac{\partial Q / Q}{\partial I / I}$:
  - $E_I > 1$ → **luxusní** zboží,
  - $0 < E_I < 1$ → **normální nezbytné** zboží,
  - $E_I < 0$ → **inferiorní** zboží.

### [[mikk-odhad-poptavky|Odhad poptávky]]

Metody:

1. **Dotazníkový průzkum spotřebitelů** — přímé otázky na ochotu kupovat za různé ceny.
2. **Pozorování chování spotřebitelů** — sledování v reálných nákupních situacích.
3. **Tržní experiment (market testing)** — testování ceny v omezené geografické oblasti.
4. **Statistická regrese** — ekonometrický odhad $Q = a + bP + cI + dP_S + \dots + \varepsilon$.
5. **Dekompozice časové řady** — trend, sezónnost, cyklus, nahodilost.
6. **Delphi metoda** — opakovaná konzultace expertů.

### Tržní rovnováha a cobweb

- **Statická rovnováha:** $Q^D(P^*) = Q^S(P^*)$.
- **Cobweb model (pavučinový):** dynamika v případě, že nabídka reaguje s časovým zpožděním (zemědělství). Stabilita závisí na sklonu nabídky a poptávky:
  - $\lvert$ sklon S $\rvert > \lvert$ sklon D $\rvert$ → konvergence k rovnováze,
  - opačný případ → divergence.
- Příklad: historie cen mědi (cyklický pohyb).

### Kardinální vs. ordinální užitek

- **Kardinální:** užitek měřitelný v utilech. **Mezní užitek (MU)** klesá s množstvím (1. Gossenův zákon). Optimum: $\dfrac{MU_X}{P_X} = \dfrac{MU_Y}{P_Y}$ (2. Gossenův zákon).
- **Ordinální:** užitek je seřazen, ne měřen. Pracuje s [[mikk-utility-preference|indiferenčními křivkami]] a **MRS** (mezní míra substituce):

> [!tip] MRS
> $$MRS_{XY} = -\dfrac{dY}{dX}\bigg|_{U=\text{const}} = \dfrac{MU_X}{MU_Y}$$

**Speciální tvary preferencí:**

- Dokonalé substituty: $U = aX + bY$, IC jsou přímky, $MRS = a/b$ konstantní.
- Dokonalé komplementy: $U = \min(aX, bY)$, IC jsou L-tvar.
- Neutrální zboží: $U = U(X)$ (Y nezáleží), IC jsou vodorovné (resp. svislé).
- Nežádoucí zboží: $\partial U/\partial Y < 0$, IC mají kladný sklon.

### Rozpočtové omezení

$$P_X \cdot X + P_Y \cdot Y = I$$

- **Vnitřní řešení:** tečnost IC a budget line, $MRS = P_X/P_Y$.
- **Rohové řešení:** spotřebitel utrácí celý důchod jen za jedno zboží (typicky pro dokonalé substituty s nestejným poměrem cen).

### [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]]

Pokles ceny $P_X$ se rozkládá na:

- **Substituční efekt (SE):** vždy proti pohybu ceny ($P_X \downarrow \Rightarrow X \uparrow$).
- **Důchodový efekt (IE):** pro normální zboží ve směru SE; pro inferiorní zboží proti SE; pro **Giffenovo zboží** IE převažuje SE → poptávka má kladný sklon.

Křivky odvozené z IC analýzy:

- **PCC (price-consumption curve)** → klasická poptávková křivka.
- **ICC (income-consumption curve)** → **Engelova křivka** (Q jako funkce důchodu).

### [[mikk-marshall-hicks-poptavka|Hicks vs. Slutsky]]

- **Hicksův přístup:** kompenzace držena na původní úrovni **užitku**.
- **Slutského přístup:** kompenzace držena na původní **kupní síle** (tj. původní koš spotřeby je dosažitelný).
- **Dualita Marshall ↔ Hicks:**
  - **Marshallova (nekompenzovaná) poptávka** $X^M(P_X, P_Y, I) = \arg\max U(X,Y)$ s.t. budget,
  - **Hicksova (kompenzovaná) poptávka** $X^H(P_X, P_Y, U) = \arg\min$ výdajů s.t. $U(X,Y) = U$,
  - **Výdajová funkce** $E(P_X, P_Y, U) = \min P_X X + P_Y Y$ s.t. $U(X,Y) = U$.

## Klíčové vzorce (souhrn)

| Vzorec | Význam |
|---|---|
| $E_D = \dfrac{dQ}{dP} \cdot \dfrac{P}{Q}$ | bodová cenová elasticita |
| $E_{XY} = \dfrac{\partial Q_X}{\partial P_Y} \cdot \dfrac{P_Y}{Q_X}$ | křížová elasticita |
| $E_I = \dfrac{\partial Q}{\partial I} \cdot \dfrac{I}{Q}$ | příjmová elasticita |
| $\dfrac{MU_X}{P_X} = \dfrac{MU_Y}{P_Y}$ | 2. Gossenův zákon (rovnováha) |
| $MRS = \dfrac{MU_X}{MU_Y} = \dfrac{P_X}{P_Y}$ | optimum spotřebitele |
| $P_X X + P_Y Y = I$ | rozpočtové omezení |
| $\Delta X = SE + IE$ | rozklad efektu změny ceny |

## Související stránky

- [[mikk-elasticita-poptavky|Elasticita poptávky]]
- [[mikk-utility-preference|Užitek a preference]]
- [[mikk-rovnovaha-spotrebitele|Rovnováha spotřebitele]]
- [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]]
- [[mikk-marshall-hicks-poptavka|Marshall vs. Hicksova poptávka]]
- [[mikk-trzni-rovnovaha-dynamika|Tržní rovnováha a cobweb]]
- [[mikk-odhad-poptavky|Odhad poptávky]]
- [[mikk|Mikroekonomie 2]] — kurzová stránka.
