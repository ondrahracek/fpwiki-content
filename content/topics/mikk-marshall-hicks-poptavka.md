---
title: "Marshallova a Hicksova poptávka, dualita"
course: mikk
type: topic
tags: [mikk, mikroekonomie, marshall, hicks, dualita, slutsky, shephard]
sources: [raw/mikk/Numerický vztah mezi Marshall a Hicks demand.pdf, raw/mikk/Prednaska 1. a 2. blok.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Marshallova a Hicksova poptávka, dualita

> [!abstract] TL;DR
> V mikroekonomii rozlišujeme **dva typy poptávky**:
> - **Marshallova (necompenzovaná) poptávka** $X^M(P_X, P_Y, I)$ — funkce cen a důchodu, plyne z **maximalizace užitku** při rozpočtovém omezení. Zahrnuje současně substituční i důchodový efekt.
> - **Hicksova (kompenzovaná) poptávka** $X^H(P_X, P_Y, U_0)$ — funkce cen a referenčního užitku, plyne z **minimalizace výdajů** při zachování užitku. Zachycuje pouze **substituční efekt**.
>
> Obě úlohy jsou navzájem **duální** a vedou ke stejnému optimálnímu koši. Dvojici spojuje **Slutského rovnice**, **Shephardovo lemma** a **Royova identita**. Detailní numerický výpočet pro $U=\sqrt{XY}$ je v kapitole 12.

Tato stránka se vrací k jednomu z nejhlubších výsledků teorie spotřebitele — **dualitě** mezi maximalizací užitku a minimalizací výdajů — a propojuje formální aparát ([[lagrangeova-metoda|Lagrange (ImeK)]], [[uzitecnost|Užitečnost (ImeK)]], [[optimalizace-spotrebitele|Optimalizace spotřebitele (ImeK)]]) s aplikační rovinou kurzu [[mikk|Mikroekonomie 2]]. Navazuje na stránky [[mikk-utility-preference]], [[mikk-rovnovaha-spotrebitele]] a zejména na [[mikk-substitucni-duchodovy-efekt]], kde už jsme rozdíl mezi Slutsky a Hicks dekompozicí probrali geometricky.

---

## 1. Motivace duálního přístupu

Spotřebitel řeší v zásadě **jednu** rozhodovací situaci, ale matematicky ji můžeme formulovat **dvěma ekvivalentními způsoby**.

### 1.1 Primární úloha — maximalizace užitku

$$\max_{X, Y} U(X, Y) \quad \text{za podmínky}\quad P_X X + P_Y Y \le I$$

Otázka: *„Při daných cenách a důchodu — jaký nejvyšší užitek dosáhnu?"*

Řešením jsou **Marshallovy poptávky** $X^M, Y^M$ jako funkce $(P_X, P_Y, I)$.

### 1.2 Duální úloha — minimalizace výdajů

$$\min_{X, Y} E = P_X X + P_Y Y \quad \text{za podmínky}\quad U(X, Y) \ge U_0$$

Otázka: *„Při daných cenách — kolik nejméně musím utratit, abych dosáhl předem daného užitku $U_0$?"*

Řešením jsou **Hicksovy poptávky** $X^H, Y^H$ jako funkce $(P_X, P_Y, U_0)$.

### 1.3 Dualita

![[mikk-marshall-hicks-dualita.jpeg|Dualita primární (Marshall, max U) a duální (Hicks, min výdajů) úlohy spotřebitele — stejný bod E]]

> [!important] Klíčový princip duality
> Pokud spotřebitel maximalizuje užitek pro důchod $I$ a dosáhne užitku $U^* = V(P_X, P_Y, I)$, pak **stejný optimální koš** by získal i z duální úlohy minimalizace výdajů s cílovým užitkem $U_0 = U^*$ — výsledné výdaje budou přesně $I$.
>
> Stejný bod tečnosti rozpočtové přímky a indiferenční křivky je geometrickým řešením **obou** úloh — liší se jen tím, *která veličina je dána a která hledaná*.

Geometrická intuice: ten samý bod tečnosti $\text{IC}(U_0)$ a rozpočtové přímky $P_X X + P_Y Y = I$ je optimem v obou formulacích. Primární úloha **„fixuje rozpočet"** a hledá nejvyšší IC; duální **„fixuje IC"** a hledá nejnižší rozpočtovou přímku.

---

## 2. Marshallova poptávka

> [!note] Definice — Marshallova poptávka
> $$X^M = X^M(P_X, P_Y, I)$$
> Optimální množství statku $X$ jako funkce **cen** $P_X, P_Y$ a **důchodu** $I$. Plyne z primární úlohy maximalizace užitku přes [[lagrangeova-metoda|Lagrangeovu metodu]].

### 2.1 Vlastnosti

- Geometricky: bod **tečnosti** rozpočtové přímky a indiferenční křivky.
- Zachycuje **necompenzovanou reakci** spotřebitele na změnu ceny — zahrnuje současně substituční (SE) i důchodový (IE) efekt.
- **Homogenní stupně 0** v cenách a důchodu: $X^M(\lambda P_X, \lambda P_Y, \lambda I) = X^M(P_X, P_Y, I)$ — proporcionální změna všech cen a důchodu poptávku nezmění (žádná peněžní iluze).
- Splňuje **Walrasův zákon**: $P_X X^M + P_Y Y^M = I$ (rozpočet se vyčerpá při monotónních preferencích).

### 2.2 Souvislost s rovnovážnou podmínkou

V optimu platí již známá rovnost mezních veličin (viz [[mikk-rovnovaha-spotrebitele]]):

$$\frac{MU_X}{MU_Y} = \frac{P_X}{P_Y} \quad\Leftrightarrow\quad MRS = \frac{P_X}{P_Y}$$

Spolu s rozpočtem dává **dvě rovnice** pro **dvě neznámé** $X^M, Y^M$.

---

## 3. Hicksova poptávka

> [!note] Definice — Hicksova poptávka
> $$X^H = X^H(P_X, P_Y, U_0)$$
> Optimální množství statku $X$ jako funkce **cen** $P_X, P_Y$ a **referenčního užitku** $U_0$. Plyne z duální úlohy minimalizace výdajů.

### 3.1 Vlastnosti

- Spotřebitel je „kompenzován" tak, aby zůstal na **stejné indiferenční křivce** $\text{IC}(U_0)$ — i po změně ceny.
- Zachycuje proto **pouze substituční efekt** (Hicksův typ — zachování užitku, ne původního koše; viz [[mikk-substitucni-duchodovy-efekt]]).
- **Nerostoucí v ceně daného statku**: $\partial X^H/\partial P_X \le 0$ vždy (zákon poptávky platí pro Hicksovu poptávku **bez výjimek**, žádné Giffenovo zboží).
- **Homogenní stupně 0** v cenách: $X^H(\lambda P_X, \lambda P_Y, U_0) = X^H(P_X, P_Y, U_0)$.

### 3.2 Proč je Hicksova poptávka klíčová pro welfare

Protože odmítá důchodový efekt, **Hicksova poptávka je nástrojem pro přesné měření změn blahobytu**: kompenzační variace (CV) i ekvivalentní variace (EV) se počítají z plochy pod Hicksovou křivkou, nikoli pod Marshallovou. Marshallův spotřebitelský přebytek je jen aproximací.

---

## 4. Nepřímá užitková funkce $V(P_X, P_Y, I)$

> [!note] Definice
> $$V(P_X, P_Y, I) = \max_{X, Y} \{U(X, Y) : P_X X + P_Y Y \le I\} = U\bigl(X^M(P_X,P_Y,I),\, Y^M(P_X,P_Y,I)\bigr)$$
> Maximální užitek dosažitelný při daných cenách a důchodu — užitek **vyjádřený nepřímo** přes ceny a rozpočet.

### Vlastnosti

| Vlastnost | Význam |
|-----------|--------|
| **Rostoucí v $I$** | Vyšší důchod ⟶ vyšší užitek. |
| **Neklesající (záporně) v cenách** | Růst ceny snižuje (nebo nemění) maximální dosažitelný užitek: $\partial V/\partial P_i \le 0$. |
| **Homogenní stupně 0** | $V(\lambda P_X, \lambda P_Y, \lambda I) = V(P_X, P_Y, I)$. |
| **Kvazi-konvexní v cenách** | Sady $\{P : V(P, I) \le \bar V\}$ jsou konvexní. |

---

## 5. Výdajová funkce $E(P_X, P_Y, U_0)$

Výdajová funkce je centrálním pojmem duální teorie. Definice:

> [!quote] Výdajová funkce
> Minimum výdajů potřebných k dosažení užitku $U_0$ při cenách $P_X, P_Y$:
> $$E(P_X, P_Y, U_0) = \min_{X,Y}\{P_X X + P_Y Y : U(X,Y) \ge U_0\}$$
> **Vlastnosti:** rostoucí s užitkem, neklesající s cenami a rostoucí při růstu nejméně jedné ceny, **konkávní v cenách**. Parciální derivace podle cen jsou Hicksovy funkce poptávky.

### 5.1 Detailní vlastnosti

| Vlastnost | Důsledek |
|-----------|----------|
| **Rostoucí v $U_0$** | Vyšší cílový užitek ⟶ vyšší minimální výdaje. |
| **Neklesající v každé ceně** | Růst kterékoli ceny nemůže snížit minimální výdaje. |
| **Striktně rostoucí, pokud je $X^H, Y^H > 0$** | Pokud spotřebitel daný statek opravdu spotřebovává, nezáporné množství poptávané vede ke striktnímu růstu $E$ při růstu ceny. |
| **Konkávní v cenách** | Při růstu ceny se spotřebitel **přesouvá** k levnějším alternativám, což zmírňuje růst výdajů (proto konkávní, nikoli lineární). |
| **Homogenní stupně 1 v cenách** | $E(\lambda P_X, \lambda P_Y, U_0) = \lambda E(P_X, P_Y, U_0)$ — zdvojnásobení všech cen zdvojnásobí výdaje. |

> [!tip] Geometrická intuice konkávnosti $E$ v cenách
> Kdyby spotřebitel nereagoval na změnu ceny (konstantní koš), výdaje by rostly **lineárně** s cenou. Skutečnost, že může substituovat k levnějšímu zboží, znamená, že výdaje rostou **pomaleji než lineárně** ⟶ funkce je konkávní.

---

## 6. Inverze mezi $V$ a $E$

> [!important] Inverzní vztah
> Nepřímá užitková funkce a výdajová funkce jsou navzájem **inverzní** v argumentech $(I, U_0)$:
> $$V(P_X, P_Y, E(P_X, P_Y, U_0)) = U_0$$
> $$E(P_X, P_Y, V(P_X, P_Y, I)) = I$$

První rovnost říká: *„Když dostanu právě tolik peněz, kolik je minimální výdaj na užitek $U_0$, dosáhnu maximálně užitku $U_0$."* Druhá je její zrcadlový obraz.

Tato inverze je **technický nástroj** k získání výdajové funkce z nepřímé užitkové (a naopak) — viz numerický příklad v kapitole 12.

---

## 7. Shephardovo lemma

> [!important] Shephardovo lemma
> Parciální derivace výdajové funkce podle ceny statku $i$ rovná se Hicksově poptávce po statku $i$:
> $$h_X(P_X, P_Y, U_0) = \frac{\partial E(P_X, P_Y, U_0)}{\partial P_X}, \qquad h_Y(P_X, P_Y, U_0) = \frac{\partial E(P_X, P_Y, U_0)}{\partial P_Y}$$

### Intuice

Pokud cena $P_X$ vzroste o malé $\Delta P_X$, výdaje vzrostou (v 1. řádu) přesně o $X^H \cdot \Delta P_X$ — protože v optimu spotřebitel reaguje na změnu ceny **bez prvořádové ztráty užitku** (envelopový teorém). Jednoduše: *„marginální zdražení dopadá přesně na poptávané množství."*

### Důkaz (skica)

Z Lagrangiánu duální úlohy $\mathcal L = P_X X + P_Y Y - \mu(U(X,Y) - U_0)$ plyne podmínka prvního řádu $P_X = \mu \cdot MU_X$ a v optimu

$$\frac{\partial E}{\partial P_X} = X^H + P_X \frac{\partial X^H}{\partial P_X} + P_Y \frac{\partial Y^H}{\partial P_X} - \mu\Bigl(MU_X \frac{\partial X^H}{\partial P_X} + MU_Y \frac{\partial Y^H}{\partial P_X}\Bigr)$$

Po dosazení podmínek 1. řádu se vnitřní členy ruší a zbude $\partial E/\partial P_X = X^H$.

---

## 8. Royova identita

> [!important] Royova identita
> Marshallovu poptávku lze získat z nepřímé užitkové funkce vztahem:
> $$X^M(P_X, P_Y, I) = -\frac{\partial V/\partial P_X}{\partial V/\partial I}, \qquad Y^M = -\frac{\partial V/\partial P_Y}{\partial V/\partial I}$$

### Odvození

Aplikujeme implicitní funkci na identitu $V(P_X, P_Y, E(P_X, P_Y, U_0)) = U_0$. Derivováním podle $P_X$:

$$\frac{\partial V}{\partial P_X} + \frac{\partial V}{\partial I}\cdot\frac{\partial E}{\partial P_X} = 0$$

A protože dle Shephardova lemmatu $\partial E/\partial P_X = X^H = X^M$ (v bodě, kde $I = E(P, U_0)$), dostáváme

$$X^M = -\frac{\partial V/\partial P_X}{\partial V/\partial I}.$$

> [!tip] Praktický význam
> Royova identita je **„opačnou stranou Shephardova lemmatu"**: Shephard získává Hicksovu poptávku ze $E$, Roy získává Marshallovu poptávku z $V$. Společně uzavírají duální čtyřúhelník $\bigl(X^M, X^H, V, E\bigr)$.

---

## 9. Slutského rovnice

> [!important] Slutského rovnice — duální verze
> $$\frac{\partial X^M}{\partial P_X} = \underbrace{\frac{\partial X^H}{\partial P_X}}_{\text{čistý SE (Hicks)}} - \underbrace{X^M\frac{\partial X^M}{\partial I}}_{\text{IE}}$$

### Význam

Změna **Marshallovy poptávky** (kterou pozorujeme v reálných datech) při změně ceny $P_X$ se rozkládá na:
1. **Substituční efekt** podle Hickse — pohyb po stejné IC, $\partial X^H/\partial P_X \le 0$.
2. **Důchodový efekt** — vážený mírou citlivosti poptávky na důchod $\partial X^M/\partial I$ a samotnou poptávkou $X^M$ (která reprezentuje „kupní sílu na statku $X$").

Pro **normální zboží** ($\partial X^M/\partial I > 0$) jdou oba efekty stejným směrem (pokles ceny ⟶ růst poptávky). Pro **inferiorní zboží** mohou jít proti sobě a v krajním případě (Giffenovo zboží) může důchodový efekt převážit substituční.

> [!example] Vazba na geometrii Hickse vs. Slutsky
> Substituční efekt v Slutského rovnici je **Hicksův** — zachovává **užitek**. Slutsky alternativní rozklad zachovává **původní koš** (real bundle) — viz detail v [[mikk-substitucni-duchodovy-efekt]]. V infinitezimálních změnách jsou oba pohledy ekvivalentní; v diskrétních se liší.

---

## 10. Srovnávací schéma duálního čtyřúhelníku

```
         Maximalizace užitku                     Minimalizace výdajů
       ┌──────────────────────┐               ┌──────────────────────┐
       │  max U(X,Y) za       │               │  min E = PxX + PyY   │
       │  PxX + PyY ≤ I       │               │  za U(X,Y) ≥ U0      │
       └──────────────────────┘               └──────────────────────┘
                  │                                       │
                  ▼ (Lagrange)                            ▼ (Lagrange)
          ┌───────────────┐                       ┌───────────────┐
          │  Marshall     │                       │  Hicks        │
          │  X^M(P,I)     │  ◄── Slutsky ───►     │  X^H(P,U0)    │
          └───────────────┘                       └───────────────┘
                  │                                       │
                  ▼ (dosadit)                             ▼ (sečíst)
          ┌───────────────┐                       ┌───────────────┐
          │  Nepřímá V    │   ◄── Inverze ───►    │  Výdajová E   │
          │  V(P, I)      │                       │  E(P, U0)     │
          └───────────────┘                       └───────────────┘
                  │                                       │
                  └── Roy: X^M = -(∂V/∂P)/(∂V/∂I)         │
                                                          │
                       Shephard: X^H = ∂E/∂P ─────────────┘
```

Tento diagram ukazuje **čtyři klíčové funkce** ($X^M, X^H, V, E$) propojené čtyřmi vztahy: dualitou, inverzí, Shephardem a Royem. Slutského rovnice pak svazuje derivace $X^M$ a $X^H$.

---

## 11. Vlastnosti — souhrnná tabulka

| Funkce | Argumenty | Klíčová vlastnost | Znaménko |
|--------|-----------|-------------------|----------|
| Marshallova $X^M$ | $(P_X, P_Y, I)$ | Homogenní st. 0 | $\partial X^M/\partial P_X \lessgtr 0$ (Giffen!) |
| Hicksova $X^H$ | $(P_X, P_Y, U_0)$ | Homogenní st. 0 | $\partial X^H/\partial P_X \le 0$ (vždy) |
| Nepřímá užitková $V$ | $(P_X, P_Y, I)$ | Homogenní st. 0; kvazikonvexní v cenách | $\partial V/\partial I > 0,\ \partial V/\partial P_i \le 0$ |
| Výdajová $E$ | $(P_X, P_Y, U_0)$ | Homogenní st. 1 v cenách; **konkávní v cenách** | $\partial E/\partial U_0 > 0,\ \partial E/\partial P_i \ge 0$ |

---

## 12. Detailní příklad: $U = \sqrt{XY}$

> [!example] Klíčový příklad z přepisu
> Tento výpočet pochází z ručně zpracovaného listu pro Cobb-Douglasovy preference. Jde o Cobb-Douglasovy preference se symetrickými exponenty $\alpha = \beta = 0{,}5$.

Užitková funkce:
$$U(X, Y) = \sqrt{XY} = X^{0{,}5}\, Y^{0{,}5}$$

Rozpočtové omezení (značíme $B$ místo $I$, jak v ručním zápisu):
$$B = P_X X + P_Y Y$$

### 12.1 Krok 1 — Marshallova poptávka přes Lagrange

Lagrangián:
$$\mathcal{L} = X^{0{,}5}\, Y^{0{,}5} + \lambda\bigl(B - P_X X - P_Y Y\bigr)$$

Parciální derivace (podmínky 1. řádu):
$$\frac{\partial \mathcal{L}}{\partial X} = 0{,}5\, X^{-0{,}5}\, Y^{0{,}5} - P_X \lambda = 0 \;\Rightarrow\; \lambda = \frac{0{,}5\, Y^{0{,}5}}{X^{0{,}5}\, P_X}$$

$$\frac{\partial \mathcal{L}}{\partial Y} = 0{,}5\, X^{0{,}5}\, Y^{-0{,}5} - P_Y \lambda = 0 \;\Rightarrow\; \lambda = \frac{0{,}5\, X^{0{,}5}}{Y^{0{,}5}\, P_Y}$$

Rovnost obou výrazů $\lambda$:
$$\frac{0{,}5\, Y^{0{,}5}}{X^{0{,}5}\, P_X} = \frac{0{,}5\, X^{0{,}5}}{Y^{0{,}5}\, P_Y} \;\Rightarrow\; Y \cdot P_Y = X \cdot P_X$$

Tedy spotřebitel utratí **stejně peněz** za obě statky (charakteristika Cobb-Douglas s rovnými exponenty).

Z rozpočtu $B = P_X X + P_Y Y$ a $P_X X = P_Y Y$:
$$B = 2 P_X X = 2 P_Y Y$$

> [!success] Marshallovy poptávky pro $U = \sqrt{XY}$
> $$\boxed{X^M = \frac{B}{2 P_X}, \qquad Y^M = \frac{B}{2 P_Y}}$$

### 12.2 Krok 2 — Nepřímá užitková funkce $V(P_X, P_Y, B)$

Dosadíme Marshallovy poptávky zpět do užitkové funkce:
$$V = U(X^M, Y^M) = \sqrt{X^M\, Y^M} = \sqrt{\frac{B}{2 P_X} \cdot \frac{B}{2 P_Y}} = \frac{B}{2\sqrt{P_X\, P_Y}}$$

> [!success] Nepřímá užitková funkce
> $$\boxed{V(P_X, P_Y, B) = \frac{B}{2\sqrt{P_X\, P_Y}}}$$

### 12.3 Krok 3 — Výdajová funkce $E(P_X, P_Y, U_0)$

Inverze nepřímé užitkové funkce vůči $B$. Z $U_0 = B/(2\sqrt{P_X P_Y})$ řešíme pro $B$:

$$B = 2\sqrt{P_X\, P_Y}\cdot U_0$$

> [!success] Výdajová funkce
> $$\boxed{E(P_X, P_Y, U_0) = 2\sqrt{P_X\, P_Y}\cdot U_0}$$

### 12.4 Krok 4 — Hicksova poptávka přes Shephardovo lemma

Aplikujeme $h_X = \partial E/\partial P_X$. Přepišeme:
$$E = 2\, P_X^{0{,}5}\, P_Y^{0{,}5}\, U_0$$

Derivujeme podle $P_X$:
$$h_X = \frac{\partial E}{\partial P_X} = 2 \cdot 0{,}5\, P_X^{-0{,}5}\, P_Y^{0{,}5}\, U_0 = P_X^{-0{,}5}\, P_Y^{0{,}5}\, U_0$$

A symetricky pro $P_Y$:
$$h_Y = \frac{\partial E}{\partial P_Y} = P_X^{0{,}5}\, P_Y^{-0{,}5}\, U_0$$

> [!success] Hicksovy poptávky pro $U = \sqrt{XY}$
> $$\boxed{h_X = \sqrt{\frac{P_Y}{P_X}}\cdot U_0, \qquad h_Y = \sqrt{\frac{P_X}{P_Y}}\cdot U_0}$$

---

## 13. Souhrnná tabulka pro $U = \sqrt{XY}$

| Funkce | Výraz |
|--------|-------|
| Marshall $X^M(P_X, P_Y, B)$ | $X^M = \dfrac{B}{2\, P_X}$ |
| Marshall $Y^M(P_X, P_Y, B)$ | $Y^M = \dfrac{B}{2\, P_Y}$ |
| Nepřímá užitková $V(P_X, P_Y, B)$ | $V = \dfrac{B}{2\sqrt{P_X\, P_Y}}$ |
| Výdajová $E(P_X, P_Y, U_0)$ | $E = 2\sqrt{P_X\, P_Y}\cdot U_0$ |
| Hicks $h_X(P_X, P_Y, U_0)$ | $h_X = \sqrt{P_Y/P_X}\cdot U_0$ |
| Hicks $h_Y(P_X, P_Y, U_0)$ | $h_Y = \sqrt{P_X/P_Y}\cdot U_0$ |

> [!tip] Konzistentnost
> Když do Hicksovy poptávky $h_X = \sqrt{P_Y/P_X}\cdot U_0$ dosadíme $U_0 = V = B/(2\sqrt{P_X P_Y})$, dostaneme $h_X = \sqrt{P_Y/P_X}\cdot B/(2\sqrt{P_X P_Y}) = B/(2 P_X) = X^M$. **Marshallova a Hicksova poptávka splývají v bodě, kde $I = E(P, U_0)$.**

---

## 14. Geometrické srovnání obou poptávkových křivek

V cenovém prostoru ($P_X$ na ose $x$, množství $X$ na ose $y$) zakreslíme obě křivky:

- **Marshallova** křivka $X^M(P_X)$ — průchozí danou kombinací (cena, množství) — obvykle **plošší**, protože pokles ceny zvyšuje reálný důchod a posouvá poptávku doprava (zahrnuje IE).
- **Hicksova** křivka $X^H(P_X)$ pro pevný $U_0$ — **strmější** pro normální zboží, protože odráží jen substituční efekt.
- Obě křivky se **protnou v jednom bodě** — tom, kde počáteční cena dává Marshallově poptávce právě užitek $U_0$.

> [!info] Pro inferiorní zboží
> Pro inferiorní zboží jde IE proti SE, takže **Marshallova křivka může být strmější než Hicksova** (a v krajním případě, u Giffenova zboží, kladně skloněná).

> [!info] Pro $U = \sqrt{XY}$ (Cobb-Douglas)
> Cobb-Douglas je **homotetický** typ preferencí: Marshallova poptávka po $X$ je $X^M = B/(2P_X)$ — hyperbola v cenovém prostoru, **nezávislá na $P_Y$**. Hicksova poptávka $h_X = \sqrt{P_Y/P_X}\cdot U_0$ má naopak na $P_Y$ závislost. Tato vlastnost je specifická pro Cobb-Douglas.

---

## 15. Aplikace

### 15.1 Welfare analysis — měření užitkové změny

> [!important] Tři míry změny blahobytu
> 1. **Marshallův spotřebitelský přebytek** ($\Delta CS$) — plocha pod **Marshallovou** křivkou. Pohodlná, ale **nepřesná** míra (záměna SE a IE).
> 2. **Kompenzační variace** ($CV$) — plocha pod **Hicksovou** křivkou s $U_0 =$ původní užitek. *„Kolik bych musel spotřebiteli vzít po zlevnění, aby zůstal stejně šťastný?"*
> 3. **Ekvivalentní variace** ($EV$) — plocha pod **Hicksovou** křivkou s $U_0 =$ nový užitek. *„Kolik bych musel spotřebiteli dát před zlevněním, aby dosáhl stejně vysokého užitku jako po zlevnění?"*
>
> Pořadí pro normální zboží při poklesu ceny: $EV \ge \Delta CS \ge CV$.

Formálně:
$$CV = E(P^1, U^0) - E(P^0, U^0), \qquad EV = E(P^1, U^1) - E(P^0, U^1)$$

### 15.2 Daňová ekonomika

Daň + transfer **není** užitkově neutrální. Daň zdanění statku $X$ posunuje spotřebitele z optima (substituční efekt), takže i když mu transfer kompenzuje **rozpočet**, neudrží se na původní indiferenční křivce. Tato „mrtvá ztráta" (deadweight loss) se měří přes Hicksovu poptávku.

### 15.3 Cost-of-living index

- **Laspeyresův index** používá fixní koš (ten Marshallovský z období 0) — **nadhodnocuje** růst životních nákladů (nepočítá se substitucí).
- **Paaschyo index** používá fixní koš z období 1 — **podhodnocuje** růst nákladů.
- **Idealizovaný Hicksův index** $E(P^1, U_0) / E(P^0, U_0)$ je „pravým" měřítkem životních nákladů, ale vyžaduje znalost preferencí.

---

## 16. Numerický příklad — Slutského dekompozice

> [!example] Plný výpočet pro $U = \sqrt{XY}$
> **Zadání:** $I = 100$, $P_Y = 1$, počáteční $P_X = 2$, nová $P_X = 1$. Spočtěte SE a IE pro statek $X$.

### 16.1 Marshallova reakce (celkový efekt)

Marshallova poptávka při $I = 100$, $P_X = 2$:
$$X^M_0 = \frac{100}{2 \cdot 2} = 25$$

Po poklesu ceny na $P_X = 1$:
$$X^M_1 = \frac{100}{2 \cdot 1} = 50$$

**Celkový efekt (TE)**:
$$\Delta X^M = X^M_1 - X^M_0 = 50 - 25 = 25$$

### 16.2 Referenční užitek $U_0$

V počátečním optimu $X = 25, Y = 50$:
$$U_0 = \sqrt{25 \cdot 50} = \sqrt{1250} \approx 35{,}36$$

(Konzistentní s nepřímou užitkovou: $V = 100/(2\sqrt{2 \cdot 1}) = 100/(2\sqrt 2) \approx 35{,}36$.)

### 16.3 Hicksova reakce (substituční efekt)

Hicksova poptávka při počáteční ceně $P_X = 2$:
$$X^H_0 = \sqrt{\frac{1}{2}}\cdot 35{,}36 \approx 0{,}7071 \cdot 35{,}36 \approx 25$$

(Splývá s $X^M_0 = 25$, jak musí — viz pozn. konzistentnosti v kap. 13.)

Po poklesu na $P_X = 1$, **při zachování užitku $U_0$**:
$$X^H_1 = \sqrt{\frac{1}{1}}\cdot 35{,}36 \approx 35{,}36$$

**Substituční efekt (SE)**:
$$\Delta X^H = X^H_1 - X^H_0 \approx 35{,}36 - 25 = 10{,}36$$

### 16.4 Důchodový efekt

$$IE = \Delta X^M - SE \approx 25 - 10{,}36 = 14{,}64$$

> [!success] Souhrn dekompozice
> | Efekt | Změna v $X$ |
> |-------|-------------|
> | Celkový (TE, Marshall) | $+25{,}00$ |
> | Substituční (SE, Hicks) | $+10{,}36$ |
> | Důchodový (IE) | $+14{,}64$ |
>
> Pro Cobb-Douglas s $\alpha = 0{,}5$ je IE relativně **silný** — odpovídá zhruba 60 % celkového efektu. Důvodem je vysoká důchodová elasticita (jednotková) a velký relativní výdaj na statek $X$.

---

## 17. Vazba na Slutsky vs. Hicks separaci

Slutského rovnice využívá **Hicksovu** definici substitučního efektu (zachování užitku). Existuje ale alternativní **Slutského** definice — zachování **původního koše** (spotřebitel po změně ceny dostane tolik kompenzace, aby si mohl koupit *stejný* koš jako předtím, ne aby byl *stejně spokojen*).

| Hledisko | Hicks | Slutsky |
|----------|-------|---------|
| Co se zachovává? | Užitek $U_0$ | Původní koš $(X_0, Y_0)$ |
| Kompenzace | $E(P^1, U_0) - I$ | $P^1 \cdot (X_0, Y_0) - I$ |
| Pozorovatelnost | Nepřímá (vyžaduje preference) | Přímá (jen ceny a množství) |
| Použití | Welfare analysis (CV, EV) | Aproximace v datech, indexy |

V infinitezimálních změnách jsou oba pohledy **ekvivalentní**, v diskrétních se liší. Detailní geometrický rozbor obou typů (s grafickou konstrukcí pomocí Hicksovy zlomené přímky) je v [[mikk-substitucni-duchodovy-efekt]].

---

## 18. Aplikační otázky ze zkoušky

V přijímacích a předtermínových testech se objevují úlohy:

- **Varianta s `expenditure function`** — odvození výdajové funkce ze zadané užitkové, výpočet $E(P^1, U_0)$ pro vyhodnocení CV.
- **Varianta s `Hicks/Marshall`** — porovnání plochy pod oběma křivkami, výpočet $\Delta CS$ vs. $CV$.

Vzorová řešení a širší přehled zkouškových úloh: [[mikk-vzorove-zkousky]]. Kompaktní přehled vzorců: [[mikk-vzorce-prehled]].

> [!tip] Strategie u zkoušky
> Pokud máte **Cobb-Douglas** preference $U = X^\alpha Y^\beta$, můžete začít rovnou z hotových vzorců:
> $$X^M = \frac{\alpha}{\alpha + \beta}\cdot \frac{I}{P_X}, \quad Y^M = \frac{\beta}{\alpha + \beta}\cdot \frac{I}{P_Y}$$
> a odtud postupně $V$, $E$, $h_X, h_Y$. Pro $\alpha = \beta = 0{,}5$ to dává přesně formule z kapitoly 13.

---

## 19. Souvislosti a další čtení

- [[mikk|Mikroekonomie 2]] — kurzový rozcestník
- [[mikk-utility-preference]] — teorie užitku, preference, MRS
- [[mikk-rovnovaha-spotrebitele]] — primární optimalizace, podmínky 1. řádu
- [[mikk-substitucni-duchodovy-efekt]] — Slutsky vs. Hicks geometricky
- [[mikk-elasticita-poptavky]] — citlivost poptávky, vazba na Slutského rovnici
- [[mikk-vzorce-prehled]] — kompaktní přehled vzorců kurzu
- [[mikk-vzorove-zkousky]] — řešené zkouškové úlohy
- [[lagrangeova-metoda|Lagrange (ImeK)]] — matematický aparát pro vázanou optimalizaci
- [[uzitecnost|Užitečnost (ImeK)]] — pojem užitku v matematické ekonomii
- [[optimalizace-spotrebitele|Optimalizace spotřebitele (ImeK)]] — paralelní výklad v kurzu Matematická ekonomie

---

> [!note] Zdroje
> Tato stránka kombinuje učebnicovou definici výdajové funkce a duálního schématu s ručním přepisem numerického příkladu pro $U = \sqrt{XY}$ — kompletní výpočet všech čtyř funkcí ($X^M, V, E, h_X$).
