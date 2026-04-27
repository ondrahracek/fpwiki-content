---
title: "ImeK — Příprava ke zkoušce: kompletní řešení 8 zadání"
course: imek
type: output
tags: [imek, zkouska, priprava, mikroekonomie, makroekonomie]
sources: [raw/imek/ImeK_Zadani-zkousky_final.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# ImeK — Příprava ke zkoušce: kompletní řešení 8 zadání

> [!abstract] TL;DR
> Plná řešení **všech 8 zkouškových zadání** (každé 4 úlohy, dohromady 32 úloh) z předmětu [[imek|Matematická ekonomie]]. Pro každou úlohu: zadání, klíčová myšlenka, postup, dílčí výpočty, výsledek a odkaz na příslušnou topic stránku. Stránka slouží jako **závěrečný materiál ke studiu** — předpokládá, že už máš prostudované jednotlivé téma a chceš si je upevnit přímo na zkouškových úlohách.

## Struktura zadání

Každé zadání má 4 úlohy s pevnou strukturou bodování:

| Úloha | Body | Charakter |
|---|---|---|
| Q1 | 10 b | **Kvalitativní rozhodování** — která z 5 funkcí může být TR, AC, nabídka, úspory, … |
| Q2 | 20 b | **Definice + interpretace** mezní veličiny (MPK, MRTS, MRCS, EPA) |
| Q3 | 30 b | **Optimalizace** — max užitečnosti, min výdajů, max produkce, max zisku, rovnováha trhu |
| Q4 | 40 b | **Komplexní úloha** — model C-I, IS-LM, cenová diskriminace, vícefaktorová poptávka, MR/MC firmy |

> [!warning] Pozor na aproximace
> Úlohy s diferenciálem (ΔY, Δr, ΔMC při změně parametru) používají **lineární aproximaci**. Ta je přesná jen pro **malé změny**. Pokud se parametr změní o 50 % nebo víc (např. *a* z 0,2 na 0,4), aproximace se může lišit od přesné hodnoty o 10–30 %. V řešení vždy spočítáme **obě hodnoty** a porovnáme.

> [!info] Pozorování o opakování
> Z analýzy 8 zadání vyplývá, že některé úlohy se **opakují** (často beze změny):
> - **Z1/Q4 ≈ Z6/Q4** (model C-I; (a)–(d) totožné, liší se jen perturbace v (e))
> - **Z3/Q3 = Z5/Q3** (produkce Q = −0,2L³ + 12L²)
> - **Z3/Q4 = Z4/Q4** (IS-LM s identickými parametry)
> - **Z3/Q1 = Z5/Q1** (5 funkcí AC)
> - **Z2/Q3 = Z8/Q3** (min výdajů, U = Q₁^¼·Q₂^½, U*=10)
> - **Z7/Q4 = Z8/Q4** (kašmírové ponožky, vícefaktorová poptávka)
>
> Týž matematický postup tedy zvládne víc úloh.

---

# Zadání 1

## Z1/Q1 [10 b] — Které funkce mohou být TR(Q)?

**Zadání:** Rozhodněte, které z funkcí mohou být funkcí celkového příjmu TR = TR(Q):
(a) TR = 200Q − 10Q²; (b) TR = Q(50 − Q²); (c) TR = 20Q + Q²; (d) TR = 1000 − 2Q²; (e) TR = 10Q − Q².

**Klíč k úloze:** Funkce TR musí splnit **dvě podmínky**:

1. **TR(0) = 0** — při nulovém prodeji nulový příjem (TR = P·Q).
2. **P = TR/Q je klesající** v Q (zákon klesající poptávky — TR pochází z poptávky).

Ekvivalentně: pokud TR = aQ² + bQ (kvadratická), pak parabola musí mít a < 0 a procházet počátkem.

Viz [[prijem-naklady-zisk|Příjem, náklady, zisk]] (vzorec 3.1).

### Rozbor

| | Funkce | TR(0) | P = TR/Q | Verdikt |
|---|---|---|---|---|
| (a) | 200Q − 10Q² | = 0 ✓ | 200 − 10Q (klesá) ✓ | **ANO** |
| (b) | Q(50 − Q²) = 50Q − Q³ | = 0 ✓ | 50 − Q² (klesá pro Q > 0) ✓ | **ANO** |
| (c) | 20Q + Q² | = 0 ✓ | 20 + Q (**roste!**) ✗ | **NE** |
| (d) | 1000 − 2Q² | = **1000** ✗ | — | **NE** |
| (e) | 10Q − Q² | = 0 ✓ | 10 − Q (klesá) ✓ | **ANO** |

**Zdůvodnění (c):** P = 20 + Q je rostoucí poptávka, což porušuje zákon klesající poptávky.

**Zdůvodnění (d):** Při Q = 0 je TR = 1000 ≠ 0 — když nic neprodáme, nemůžeme mít kladný příjem.

> [!tip] Rychlý filtr
> Stačí ověřit **kvadratický tvar TR = aQ² + bQ** (žádný absolutní člen, a < 0, b > 0). Funkce, které nemají tuto strukturu nebo mají kladný absolutní člen, vypadnou.

---

## Z1/Q2 [20 b] — Mezní produkt kapitálu MPK

**Zadání:** Definujte MPK(L,K) a interpretujte MPK(10,100) = 5. Může nabývat záporných hodnot? Pokud ano, interpretujte MPK(20,80) = −5.

### Definice

$$MP_K = \frac{\partial Q}{\partial K}$$

Parciální derivace produkční funkce $Q = Q(L,K)$ podle kapitálu (při fixní práci). Viz [[produkce|Produkce — produkční funkce, Cobb-Douglas, MRTS]] (vzorec 5.2).

### Interpretace MPK(10,100) = 5

Při zaměstnání **L = 10 pracovníků** a **K = 100 jednotek kapitálu** se produkce přibližně **zvýší o 5 jednotek**, jestliže se kapitál zvýší o 1 jednotku (z 100 na 101) — práce zůstává konstantní.

Slovně: „další stroj (či jednotka kapitálu) přidá v daném bodě cca 5 jednotek produkce."

### Záporné hodnoty?

**ANO**, matematicky možné. Ekonomicky vzácné, ale objevuje se v případech **přebytku kapitálu** vůči práci — zákon klesajících výnosů přejde do záporu.

### Interpretace MPK(20,80) = −5

Při L=20 a K=80 by **další jednotka kapitálu snížila produkci o ~5 jednotek**. Ekonomicky: kapitálu je *tolik*, že další jednotka je kontraproduktivní (např. další stroj, na který nemáme operátora; přeplnění výrobní haly; obsluha rostoucí kapitálové základny zatěžuje stávající práci). Indikuje **překročení optimálního poměru K/L** — firmě by se vyplatilo kapitál spíše snížit nebo přidat pracovníky.

> [!info] Klíčový kontrast
> MPK = +5 → kapitál v optimální zóně, přidávání pomáhá.
> MPK = −5 → kapitál v zóně přesycení, přidávání škodí. Takový bod je za maximem produkce v daném směru.

---

## Z1/Q3 [30 b] — Maximalizace užitečnosti

**Zadání:** $U = U(Q_1, Q_2) = Q_1^{1/2} \cdot Q_2^{1/2}$, $P_1 = 5$, $P_2 = 10$, důchod $Y = 500$. Určete $Q_1, Q_2$ maximalizující užitečnost.

**Klíč:** Lagrangeova metoda → podmínka **MRCS = P₁/P₂** + rozpočtové omezení. Viz [[optimalizace-spotrebitele|Optimalizace spotřebitele]] (vzorec 6.13–6.14).

### Krok 1: MRCS

$$MU_1 = \tfrac{1}{2} Q_1^{-1/2} Q_2^{1/2}, \qquad MU_2 = \tfrac{1}{2} Q_1^{1/2} Q_2^{-1/2}$$

$$\boxed{\; MRCS = \frac{MU_1}{MU_2} = \frac{Q_2}{Q_1} \;}$$

### Krok 2: Podmínka optimality

$$\frac{Q_2}{Q_1} = \frac{P_1}{P_2} = \frac{5}{10} = \frac{1}{2} \quad\Longrightarrow\quad Q_2 = \tfrac{1}{2} Q_1$$

### Krok 3: Rozpočtové omezení

$$5 Q_1 + 10 Q_2 = 500 \;\xRightarrow{Q_2 = Q_1/2}\; 5Q_1 + 10 \cdot \tfrac{Q_1}{2} = 10 Q_1 = 500$$

### Výsledek

$$\boxed{\; Q_1^* = 50, \quad Q_2^* = 25, \quad U^* = \sqrt{50 \cdot 25} = \sqrt{1250} \approx 35{,}36 \;}$$

> [!tip] Cobb-Douglas zkratka
> Pro $U = Q_1^a Q_2^b$ s ryzí Cobb-Douglas (zde $a = b = 1/2$, symetrický případ) platí:
> $$Q_1^* = \frac{a}{a+b} \cdot \frac{Y}{P_1}, \qquad Q_2^* = \frac{b}{a+b} \cdot \frac{Y}{P_2}$$
> Pro náš případ: $Q_1^* = \tfrac{1}{2} \cdot \tfrac{500}{5} = 50$, $Q_2^* = \tfrac{1}{2} \cdot \tfrac{500}{10} = 25$. Stejný výsledek bez Lagrange.

---

## Z1/Q4 [40 b] — Model C-I

**Zadání:** Y = C + I, C = aY + b. Najděte (a) redukovaný tvar pro Y; (b) multiplikátory + znaménka; (c) Y^E pro a = 0,2; b = 100; I = 1000; (d) ΔY ≈ při ΔI = 100; (e) ΔY ≈ při da = 0,2; db = 3; dI = 10.

**Klíč:** Viz [[narodni-duchod|Národní důchod]] (vzorce 7.6–7.7) a [[imek-vzorce-prehled#13. Makroekonomie — národní důchod|sekce 13 přehledu vzorců]].

### (a) Redukovaný tvar

$$Y = aY + b + I \;\Longrightarrow\; Y(1-a) = b + I \;\Longrightarrow\; \boxed{Y^E = \frac{b + I}{1 - a}}$$

### (b) Multiplikátory

$$\frac{\partial Y^E}{\partial a} = \frac{b + I}{(1-a)^2} > 0, \qquad \frac{\partial Y^E}{\partial b} = \frac{1}{1-a} > 0, \qquad \frac{\partial Y^E}{\partial I} = \frac{1}{1-a} > 0$$

Při běžných předpokladech 0 < a < 1, b > 0, I > 0 jsou **všechny multiplikátory kladné** — růst libovolného z parametrů zvyšuje rovnovážný důchod.

### (c) Rovnovážný důchod

$$Y^E = \frac{100 + 1000}{1 - 0{,}2} = \frac{1100}{0{,}8} = \boxed{1375}$$

### (d) ΔI = 100

**Aproximace (diferenciál):**
$$\Delta Y \approx \frac{\partial Y^E}{\partial I} \cdot \Delta I = \frac{1}{0{,}8} \cdot 100 = 125$$

**Přesně:**
$$Y^E_{\text{nový}} = \frac{100 + 1100}{0{,}8} = 1500 \;\Longrightarrow\; \Delta Y = 1500 - 1375 = 125$$

> [!info] Proč jsou hodnoty stejné?
> Y^E je **lineární v I** (multiplikátor 1/(1−a) nezávisí na I). Pro lineární funkce jsou diferenciál a přesná změna identické. Stejně to bude pro změny **jen** v I nebo **jen** v b.

### (e) Současné změny da = 0,2; db = 3; dI = 10

**Aproximace:**
$$\Delta Y \approx \underbrace{\frac{1100}{0{,}64}}_{=1718{,}75} \cdot 0{,}2 + \underbrace{\frac{1}{0{,}8}}_{=1{,}25} \cdot 3 + \underbrace{\frac{1}{0{,}8}}_{=1{,}25} \cdot 10$$
$$= 343{,}75 + 3{,}75 + 12{,}5 = \boxed{360}$$

**Přesně** (a → 0,4; b → 103; I → 1010):
$$Y^E_{\text{nový}} = \frac{103 + 1010}{1 - 0{,}4} = \frac{1113}{0{,}6} = 1855 \;\Longrightarrow\; \Delta Y = 480$$

> [!warning] Velká chyba aproximace!
> Aproximace 360 vs. přesných 480 — chyba **25 %**. Důvod: změna $da = 0{,}2$ znamená, že *a* se **zdvojnásobuje** (z 0,2 na 0,4). Lineární aproximace funguje jen pro malé perturbace; tady už máme „velkou změnu", a $Y^E$ je vůči *a* silně nelineární (přes $(1-a)^2$ ve jmenovateli).
>
> **Poučení:** v zadání takto velké perturbace si všimni a uveď, že aproximace je orientační. Ke zkoušce odevzdáš obě hodnoty.

---

# Zadání 2

## Z2/Q1 [10 b] — Které funkce mohou být nabídka?

**Zadání:** Rozhodněte, které z funkcí mohou být funkcí nabídky:
(a) P = 100 + 0,2Q²; (b) Q = 50 + 0,5P; (c) P = −80 + 2Q; (d) P = 500 − 2Q; (e) Q = 0,5P − 200.

**Klíč:** Funkce nabídky musí být **rostoucí** v ceně (zákon rostoucí nabídky). Viz [[poptavka-nabidka|Poptávka, nabídka a tržní rovnováha]].

### Test: kladná derivace

| | Funkce | Derivace | Verdikt |
|---|---|---|---|
| (a) | P = 100 + 0,2Q² | dP/dQ = 0,4Q ≥ 0 | **ANO** |
| (b) | Q = 50 + 0,5P | dQ/dP = 0,5 > 0 | **ANO** |
| (c) | P = −80 + 2Q | dP/dQ = 2 > 0 | **ANO** |
| (d) | P = 500 − 2Q | dP/dQ = −2 < 0 | **NE** (klesá!) |
| (e) | Q = 0,5P − 200 | dQ/dP = 0,5 > 0 | **ANO** |

**Zdůvodnění (d):** P klesá s Q — to není zákon nabídky, ale spíš poptávky.

**Poznámka k omezením:**
- (b) má smysl pro Q ≥ 50 (alternativně P = 2Q − 100 → P ≥ 0 ⟺ Q ≥ 50).
- (c) má smysl pro Q ≥ 40 (P = −80 + 2Q ≥ 0 ⟺ Q ≥ 40).
- (e) má smysl pro P ≥ 400 (Q ≥ 0).

Tato omezení nezruší platnost — připustí se s reálným cenovým rozpětím.

---

## Z2/Q2 [20 b] — Křížová cenová elasticita poptávky $E_{P_A}$

**Zadání:** Definujte $E_{P_A}$ a interpretujte $E_{P_A} = 0{,}5$.

### Definice

Pro vícefaktorovou poptávku $Q = D(P, P_A, Y)$:

$$\boxed{\; E_{P_A} = \frac{P_A}{Q} \cdot \frac{\partial Q}{\partial P_A} \;}$$

Viz [[elasticita|Elasticita poptávky a nabídky]] (vzorec 4.19).

### Interpretace $E_{P_A} = 0{,}5$

**Vzroste-li cena alternativního zboží $P_A$ o 1 %, poptávané množství základního zboží Q se zvýší přibližně o 0,5 %** (ceteris paribus).

**Charakter zboží:** $E_{P_A} > 0$ → zboží jsou **substituty** (zdražení alternativy přesouvá poptávku na základní zboží).

> [!info] Příklad
> Máslo a margarín: zdraží-li se margarín, lidé kupují víc másla → $E_{P_A} > 0$.
> Auto a benzín (komplementy): zdraží-li se benzín, lidé kupují méně aut → $E_{P_A} < 0$.

---

## Z2/Q3 [30 b] — Minimalizace výdajů

**Zadání:** $U = Q_1^{1/4} \cdot Q_2^{1/2}$, $U^* = 10$, $P_1 = 5$, $P_2 = 4$. Určete $Q_1, Q_2$ minimalizující výdaje.

**Klíč:** **Duální úloha** — Lagrange s vazbou $U(Q_1,Q_2) = U^*$ a minimalizujeme $E = P_1 Q_1 + P_2 Q_2$. V optimu opět **MRCS = P₁/P₂**. Viz [[optimalizace-spotrebitele#Duální úloha — minimalizace výdajů|sekce duální úlohy]].

### Krok 1: MRCS

$$MU_1 = \tfrac{1}{4} Q_1^{-3/4} Q_2^{1/2}, \qquad MU_2 = \tfrac{1}{2} Q_1^{1/4} Q_2^{-1/2}$$

$$MRCS = \frac{MU_1}{MU_2} = \frac{1/4}{1/2} \cdot Q_1^{-1} \cdot Q_2 = \frac{Q_2}{2 Q_1}$$

### Krok 2: Podmínka optimality

$$\frac{Q_2}{2 Q_1} = \frac{5}{4} \;\Longrightarrow\; Q_2 = \tfrac{5}{2} Q_1$$

### Krok 3: Vazba užitečnosti

$$Q_1^{1/4} \cdot \left(\tfrac{5}{2} Q_1\right)^{1/2} = 10$$

$$Q_1^{1/4} \cdot \sqrt{\tfrac{5}{2}} \cdot Q_1^{1/2} = Q_1^{3/4} \cdot \sqrt{\tfrac{5}{2}} = 10$$

$$Q_1^{3/4} = \frac{10}{\sqrt{5/2}} = 10\sqrt{\tfrac{2}{5}} = 2\sqrt{10}$$

$$Q_1 = (2\sqrt{10})^{4/3} = 2^{4/3} \cdot 10^{2/3} = 4 \cdot 5^{2/3}$$

### Výsledek (přesně)

$$\boxed{\; Q_1^* = 4 \cdot 5^{2/3} \approx 11{,}696, \quad Q_2^* = 10 \cdot 5^{2/3} \approx 29{,}240 \;}$$

$$\boxed{\; E^* = 5 \cdot Q_1^* + 4 \cdot Q_2^* = 60 \cdot 5^{2/3} \approx 175{,}44 \;}$$

**Ověření vazby:** $Q_1^{*\,1/4} \cdot Q_2^{*\,1/2} = 11{,}696^{0{,}25} \cdot 29{,}240^{0{,}5} \approx 1{,}849 \cdot 5{,}408 \approx 10{,}00$ ✓

> [!tip] Proč tahle úloha vyšla nehezky?
> Exponenty $1/4$ a $1/2$ nesoudí (součet 3/4, ne 1) → Cobb-Douglas se neredukuje na ryzí tvar a výsledek obsahuje $5^{2/3}$. Pro $U = Q_1^{1/2} Q_2^{1/2}$ (Z1/Q3) to vyšlo na celá čísla 50 a 25.

---

## Z2/Q4 [40 b] — Cenová diskriminace

**Zadání:** $P_1 = 300 - Q_1$ (domácí), $P_2 = 200 - 0{,}5 Q_2$ (zahraniční), $TC = 5000 + 100Q$, $Q = Q_1 + Q_2$. Stanovte ceny pro max zisku (a) s diskriminací; (b) bez diskriminace; (c) porovnejte.

**Klíč:** **MR_i = MC pro každý segment** při diskriminaci; **MR(Q) = MC** pro tržní poptávku bez diskriminace. Viz [[prijem-naklady-zisk|Příjem, náklady, zisk]] (Příklad 3.25 — totožná úloha v knize Mezník).

### (a) S cenovou diskriminací

**Mezní příjmy a mezní náklady:**
$$MR_1 = 300 - 2 Q_1, \quad MR_2 = 200 - Q_2, \quad MC = 100$$

**Trh 1:** $300 - 2 Q_1 = 100 \;\Longrightarrow\; Q_1 = 100, \; P_1 = 200$
**Trh 2:** $200 - Q_2 = 100 \;\Longrightarrow\; Q_2 = 100, \; P_2 = 150$

**Zisk:**
$$Q = 200, \; TR = 200 \cdot 100 + 150 \cdot 100 = 35\,000, \; TC = 5000 + 100 \cdot 200 = 25\,000$$

$$\boxed{\; PR^{(a)} = 35\,000 - 25\,000 = 10\,000 \;}$$

### (b) Bez cenové diskriminace

**Tržní poptávka** (jediná cena P pro oba segmenty). Z inverzí:
$$Q_1 = 300 - P, \qquad Q_2 = \frac{200 - P}{0{,}5} = 400 - 2P$$

Pro P ≤ 200 (jinak Q₂ = 0):
$$Q = Q_1 + Q_2 = 700 - 3P \;\Longrightarrow\; P = \frac{700 - Q}{3}$$

**Mezní příjem:**
$$TR = P \cdot Q = \frac{700 Q - Q^2}{3}, \quad MR = \frac{700 - 2Q}{3}$$

**MR = MC:** $\frac{700 - 2Q}{3} = 100 \;\Longrightarrow\; 700 - 2Q = 300 \;\Longrightarrow\; Q = 200$

$$P = \frac{500}{3} \approx 166{,}67$$

**Zisk:**
$$TR = \tfrac{500}{3} \cdot 200 = \tfrac{100\,000}{3} \approx 33\,333{,}33; \quad TC = 25\,000$$

$$\boxed{\; PR^{(b)} = \tfrac{25\,000}{3} \approx 8\,333{,}33 \;}$$

### (c) Porovnání

$$\Delta PR = PR^{(a)} - PR^{(b)} = 10\,000 - 8\,333{,}33 = \boxed{1\,666{,}67}$$

**Cenová diskriminace přináší firmě o 1 666,67 vyšší zisk.** Důvod: v (a) může firma zachytit přebytek spotřebitele zvlášť na každém trhu — na elastičtějším trhu (zahraniční, sklon −0,5) dá nižší cenu, na neelastičtějším (domácí, sklon −1) vyšší. Bez diskriminace je nucena dát „kompromisní" cenu, která je na žádném trhu optimální.

> [!info] Klíčové pravidlo cenové diskriminace
> Při diskriminaci vyrovnává firma **MR** napříč trhy (každý trh dostane své $MR_i = MC$). Firma vyrovnává mezní zisk plynoucí z každého trhu, ne ceny. Cena bývá **vyšší tam, kde je poptávka méně elastická**.

---

# Zadání 3

## Z3/Q1 [10 b] — Které funkce mohou být AC(Q)?

**Zadání:** (a) AC = 100/Q + 0,1Q; (b) AC = 50/Q − 0,1; (c) AC = −1000/Q + Q; (d) AC = −1000/Q − 2Q; (e) AC = 200/Q + 0,5 + 0,001Q.

**Klíč:** Průměrné náklady musí splnit **AC > 0 pro všechna Q > 0** (jinak by TC = AC·Q bylo záporné, což nemá smysl). Viz [[prijem-naklady-zisk#Náklady firmy|sekce Náklady firmy]].

### Rozbor

| | Funkce | Test | Verdikt |
|---|---|---|---|
| (a) | 100/Q + 0,1Q | TC = 100 + 0,1Q² > 0; FC = 100; vždy >0 ✓ | **ANO** |
| (b) | 50/Q − 0,1 | pro $Q \to \infty$: AC → −0,1 < 0 ✗ | **NE** |
| (c) | −1000/Q + Q | pro Q = 1: AC = −999 < 0 ✗ | **NE** |
| (d) | −1000/Q − 2Q | vždy záporné ✗ | **NE** |
| (e) | 200/Q + 0,5 + 0,001Q | TC = 200 + 0,5Q + 0,001Q² > 0; FC = 200 ✓ | **ANO** |

**Numerické ověření (b):** AC(1000) = 50/1000 − 0,1 = 0,05 − 0,1 = −0,05 < 0. Skutečně nesplňuje.

> [!tip] Filtr
> Standardní AC vychází z TC = FC + aQ + bQ² + cQ³ → AC = FC/Q + a + bQ + cQ². Členy s **kladnou** mocninou Q i konstanta musí být nezáporné (jinak AC pro velká Q půjde do mínusu). Záporné koeficienty u −1000/Q jsou červený praporek.

---

## Z3/Q2 [20 b] — MRCS(L,K) — vlastně MRCS(Q₁,Q₂)

**Zadání:** Definujte mezní míru komoditní substituce MRCS a interpretujte MRCS(100,200) = 5.

> [!warning] Pozor na pojmenování
> Symbol $L, K$ je v zadání nezvyklý pro MRCS — typicky se MRCS používá pro **užitečnost** (Q₁, Q₂), zatímco MRTS pro **produkci** (L, K). Pravděpodobně jde o překlep v zadání; obsahově se ptá na MRCS(Q₁, Q₂).

### Definice

$$\boxed{\; MRCS = \frac{MU_1}{MU_2} = \frac{\partial U / \partial Q_1}{\partial U / \partial Q_2} \;}$$

Viz [[uzitecnost|Užitečnost]] (vzorec 6.9).

### Interpretace MRCS(100,200) = 5

Na svazku $(Q_1 = 100, Q_2 = 200)$ je spotřebitel ochoten **obětovat 5 jednotek $Q_2$ za získání 1 jednotky $Q_1$ navíc**, aby zachoval stejnou užitečnost (zůstal na téže indiferenční křivce).

Geometricky: **sklon indiferenční křivky** v daném bodě je $-MRCS = -5$.

> [!info] Intuice
> MRCS odpovídá na otázku „kolik **vzdám** druhého zboží za jednu jednotku prvního?"
> Vysoké MRCS = první zboží subjektivně vzácné, ochotně se zbavuju druhého za něj.
> Nízké MRCS = první zboží mám už dost, druhého se zbavím nerad.

---

## Z3/Q3 [30 b] — Maximalizace produkce a produktivity

**Zadání:** $Q = -0{,}2 L^3 + 12 L^2$. (a) Max produktivity práce + odpovídající produkce na pracovníka. (b) Ověření principu max $AP_L$. (c) Max produkce + maximum.

**Klíč:** Viz [[produkce|Produkce]] (sekce „Princip maximalizace průměrného produktu práce", úloha 5.5 v knize).

### (a) Max produktivity práce ($AP_L$)

$$AP_L = \frac{Q}{L} = -0{,}2 L^2 + 12 L$$

$$AP_L' = -0{,}4 L + 12 = 0 \;\Longrightarrow\; L = 30$$

$AP_L'' = -0{,}4 < 0$ → maximum.

$$AP_L(30) = -0{,}2 \cdot 900 + 12 \cdot 30 = -180 + 360 = 180$$

$$\boxed{\; L = 30 \text{ pracovníků}, \; AP_L(30) = 180 \text{ jednotek/pracovníka} \;}$$

### (b) Ověření principu MP_L = AP_L v max AP_L

$$MP_L = Q'(L) = -0{,}6 L^2 + 24 L$$

$$MP_L(30) = -0{,}6 \cdot 900 + 24 \cdot 30 = -540 + 720 = 180 = AP_L(30) \;\checkmark$$

**Princip platí:** v bodě maxima průměrného produktu práce se mezní produkt rovná průměrnému.

### (c) Max produkce

$$Q'(L) = -0{,}6 L^2 + 24 L = L(-0{,}6 L + 24) = 0 \;\Longrightarrow\; L = 0 \text{ nebo } L = 40$$

$Q''(40) = -1{,}2 \cdot 40 + 24 = -24 < 0$ → maximum.

$$Q(40) = -0{,}2 \cdot 64\,000 + 12 \cdot 1\,600 = -12\,800 + 19\,200 = 6\,400$$

$$\boxed{\; L = 40 \text{ pracovníků}, \; Q_{\max} = 6\,400 \text{ jednotek} \;}$$

> [!info] Pozor — dvě různá maxima
> **Max produktivity** ($L = 30$) ≠ **max produkce** ($L = 40$). Mezi $L = 30$ a $L = 40$ produkce stále **roste** (přidávat pracovníky se vyplatí), ale klesá průměrný produkt na pracovníka (MP_L < AP_L). Po $L = 40$ je produkce na vrcholu a další pracovníci by ji už snižovali (MP_L < 0).

---

## Z3/Q4 [40 b] — IS-LM analýza

**Zadání:** Y = mr + n (IS), Y = pr + q (LM); m = −50, n = 2000, p = 200, q = 1000.
(a) Redukovaný tvar pro r. (b) Multiplikátory. (c) Vypočtěte $Y^E, r^E$. (d) Δr ≈ při dp = −20, dm = +10; porovnejte s přesným.

**Klíč:** Viz [[is-lm|IS-LM analýza]].

### (a) Redukovaný tvar

Z $mr + n = pr + q$:

$$\boxed{\; r^E = \frac{q - n}{m - p} \;}$$

(Obecně: $Y^E = m \cdot r^E + n = \frac{mq - np}{m - p}$.)

### (b) Multiplikátory pro r

$$\frac{\partial r}{\partial m} = -\frac{q - n}{(m-p)^2}, \qquad \frac{\partial r}{\partial n} = -\frac{1}{m-p}, \qquad \frac{\partial r}{\partial p} = \frac{q - n}{(m-p)^2}, \qquad \frac{\partial r}{\partial q} = \frac{1}{m-p}$$

### (c) Rovnovážné hodnoty

$$r^E = \frac{1000 - 2000}{-50 - 200} = \frac{-1000}{-250} = \boxed{4}$$

$$Y^E = -50 \cdot 4 + 2000 = -200 + 2000 = \boxed{1800}$$

**Kontrola přes LM:** $200 \cdot 4 + 1000 = 1800$ ✓

### (d) Změna při dp = −20, dm = +10

**Multiplikátory v hladině (c):** $(m - p)^2 = (-250)^2 = 62\,500$

$$\frac{\partial r}{\partial m} = -\frac{-1000}{62\,500} = 0{,}016, \qquad \frac{\partial r}{\partial p} = \frac{-1000}{62\,500} = -0{,}016$$

**Aproximace:**
$$\Delta r \approx 0{,}016 \cdot 10 + (-0{,}016) \cdot (-20) = 0{,}16 + 0{,}32 = \boxed{0{,}48}$$

**Přesně** (m₁ = −40, p₁ = 180):
$$r^E_{\text{nový}} = \frac{1000 - 2000}{-40 - 180} = \frac{-1000}{-220} = \frac{50}{11} \approx 4{,}5455$$

$$\Delta r_{\text{přesné}} = 4{,}5455 - 4 = 0{,}5455$$

**Porovnání:** aproximace 0,48 vs. přesných 0,5455 → chyba ~12 %. Důvod: změny dp = −20 a dm = +10 jsou poměrně malé proti $|m - p| = 250$ (cca 4–8 %), ale druhá derivace přes $(m-p)^2$ stále působí. Pro čistě informativní odhad směru a řádu změny je aproximace dobrá.

---

# Zadání 4

## Z4/Q1 [10 b] — Páry funkcí poptávky ve dvoukomoditním trhu

**Zadání:** Pro 5 dvojic funkcí (Q₁, Q₂) rozhodněte, zda jde o poptávku, a v kladném případě určete typ vztahu (substituty/komplementy).

**Klíč:** Pro $Q_i = a_i + b_i P_1 + c_i P_2$ musí platit:
- **a₁, a₂ > 0** (kladné množství při nulových cenách);
- **b₁, c₂ < 0** (vlastní cenové koeficienty — zákon klesající poptávky);
- **substituty:** c₁ > 0, b₂ > 0;
- **komplementy:** c₁ < 0, b₂ < 0.

Viz [[poptavka-nabidka#Vícekomoditní (dvoukomoditní) trh|Dvoukomoditní trh]] (vzorec 2.6).

### Rozbor

| | Funkce | a₁,a₂ | b₁,c₂ (vlastní) | c₁,b₂ (zkřížené) | Verdikt |
|---|---|---|---|---|---|
| (a) | Q₁ = 10 − 2P₁ + P₂; Q₂ = 5 + 2P₁ − 2P₂ | 10, 5 ✓ | −2, −2 ✓ | +1, +2 → **substituty** | **ANO – substituty** |
| (b) | Q₁ = 3 − P₁ − P₂; Q₂ = 4 + P₁ + P₂ | 3, 4 ✓ | −1, **+1** ✗ | — | **NE** |
| (c) | Q₁ = 6 − P₁ − P₂; Q₂ = 7 − P₁ − P₂ | 6, 7 ✓ | −1, −1 ✓ | −1, −1 → **komplementy** | **ANO – komplementy** |
| (d) | Q₁ = −8 − P₁ + P₂; Q₂ = 2 + P₁ − P₂ | **−8** ✗ | — | — | **NE** |
| (e) | Q₁ = 3 + P₁ + 4P₂; Q₂ = 3 + 5P₁ + P₂ | 3, 3 ✓ | **+1, +1** ✗ | — | **NE** |

**Zdůvodnění (b):** $\partial Q_2 / \partial P_2 = +1 > 0$ — Q₂ roste s vlastní cenou, porušuje zákon klesající poptávky.

**Zdůvodnění (d):** Při $P_1 = P_2 = 0$ je $Q_1 = -8 < 0$ — záporné množství.

**Zdůvodnění (e):** Obě vlastní cenové derivace jsou kladné (Q₁ roste s P₁, Q₂ s P₂) — obě porušují zákon klesající poptávky.

---

## Z4/Q2 [20 b] — MRCS interpretace

**Zadání identické s Z3/Q2** — viz výše. Definice $MRCS = MU_1/MU_2$, interpretace MRCS(100,200) = 5: spotřebitel ochotně obětuje 5 jednotek $Q_2$ za 1 jednotku $Q_1$ navíc při zachované užitečnosti.

---

## Z4/Q3 [30 b] — Firma s dvěma zbožími v dokonalé konkurenci

**Zadání:** $TC = 2 Q_1^2 + Q_1 Q_2 + 2 Q_2^2$; ceny $P_1^*, P_2^*$ pevně dány. (a) Funkce $Q_1(P_1, P_2), Q_2(P_1, P_2)$ pro max zisk. (b) Pro $P_1^* = 12, P_2^* = 18$ vypočtěte zisk.

**Klíč:** V dokonalé konkurenci $TR = P_1 Q_1 + P_2 Q_2$. Maximalizace zisku $PR = TR - TC$ přes obě množství: nutné podmínky $\partial PR / \partial Q_1 = 0$, $\partial PR / \partial Q_2 = 0$. Viz [[funkce-vice-promennych|Funkce více proměnných]] a [[prijem-naklady-zisk]].

### (a) Optimální množství

$$PR = P_1 Q_1 + P_2 Q_2 - (2 Q_1^2 + Q_1 Q_2 + 2 Q_2^2)$$

**Nutné podmínky:**
$$\frac{\partial PR}{\partial Q_1} = P_1 - 4 Q_1 - Q_2 = 0 \;\Longrightarrow\; 4 Q_1 + Q_2 = P_1$$

$$\frac{\partial PR}{\partial Q_2} = P_2 - Q_1 - 4 Q_2 = 0 \;\Longrightarrow\; Q_1 + 4 Q_2 = P_2$$

**Determinant soustavy:** $4 \cdot 4 - 1 \cdot 1 = 15$

$$\boxed{\; Q_1 = \frac{4 P_1 - P_2}{15}, \qquad Q_2 = \frac{4 P_2 - P_1}{15} \;}$$

**Postačující podmínky** (Hessián):
$$H_{11} = -4 < 0, \quad H_{22} = -4, \quad H_{12} = -1, \quad \det H = 16 - 1 = 15 > 0 \;\Longrightarrow\; \text{maximum}$$

### (b) Pro $P_1^* = 12, P_2^* = 18$

$$Q_1^* = \frac{48 - 18}{15} = \frac{30}{15} = 2, \qquad Q_2^* = \frac{72 - 12}{15} = \frac{60}{15} = 4$$

$$PR^* = 12 \cdot 2 + 18 \cdot 4 - (2 \cdot 4 + 2 \cdot 4 + 2 \cdot 16) = 24 + 72 - 48 = \boxed{48}$$

> [!info] Proč $4 Q_1 + Q_2 = P_1$?
> Levou stranu lze číst jako „mezní náklady na $Q_1$" — $\partial TC / \partial Q_1 = 4 Q_1 + Q_2$. V dokonalé konkurenci je MR_i = P_i. Podmínka $MR_i = MC_i$ (princip max zisku) na obou trzích dá výše uvedenou soustavu.

---

## Z4/Q4 [40 b] — IS-LM (totožné se Z3/Q4)

Stejné parametry, stejný postup, stejné výsledky:

$$r^E = 4, \quad Y^E = 1800, \quad \Delta r \approx 0{,}48 \text{ (přesně 0,5455)}$$

**Viz Z3/Q4 výše.**

---

# Zadání 5

## Z5/Q1 [10 b] — AC funkce (totožné se Z3/Q1)

(a) ANO; (b) NE; (c) NE; (d) NE; (e) ANO. **Viz Z3/Q1.**

---

## Z5/Q2 [20 b] — MRTS(L,K)

**Zadání:** Definujte mezní míru technické substituce a interpretujte MRTS(10,100) = 15.

### Definice

$$\boxed{\; MRTS = \frac{MP_L}{MP_K} = \frac{\partial Q / \partial L}{\partial Q / \partial K} \;}$$

Viz [[produkce|Produkce]] (vzorec 5.14).

### Interpretace MRTS(10,100) = 15

Na hladině $(L = 10, K = 100)$ lze **1 jednotku práce nahradit přibližně 15 jednotkami kapitálu** se zachovanou produkcí (pohyb po izokvantě).

Ekvivalentně: poklesne-li práce o 1 pracovníka, musíme pro udržení produkce přidat **~15 jednotek kapitálu**.

Geometricky: **sklon izokvanty** v daném bodě je $-MRTS = -15$.

> [!info] MRTS vs. MRCS
> Stejný matematický koncept jako MRCS u užitečnosti — **podíl mezních veličin = sklon vrstevnice**. MRCS pro indiferenční křivky (užitečnost), MRTS pro izokvanty (produkce).

---

## Z5/Q3 [30 b] — Max produkce (totožné se Z3/Q3)

(a) $L = 30, AP_L = 180$; (b) MP_L(30) = 180 = AP_L(30) ✓; (c) $L = 40, Q_{\max} = 6\,400$.

**Viz Z3/Q3.**

---

## Z5/Q4 [40 b] — Firma s pevnými MC a lineárním MR

**Zadání:** $MC = 20$, $FC = 120$, $MR = 100 - 20Q$.
(a) TR a poptávka. (b) TC. (c) Max TR + maximum. (d) Body zvratu. (e) Max zisku + maximum. (f) Náčrt.

**Klíč:** Integrace MR a MC + standardní úkony [[prijem-naklady-zisk]].

### (a) TR a D(Q)

$$TR = \int MR \, dQ = \int (100 - 20Q) \, dQ = 100Q - 10Q^2 \quad \text{(konstanta = 0, neboť } TR(0) = 0)$$

$$P = D(Q) = \frac{TR}{Q} = \boxed{100 - 10 Q}$$

### (b) TC

$$TC = \int MC \, dQ + FC = 20 Q + 120$$

### (c) Max TR

$MR = 0$: $100 - 20Q = 0 \Rightarrow Q_1 = 5$

$$TR_{\max} = 100 \cdot 5 - 10 \cdot 25 = \boxed{250}$$

### (d) Body zvratu (PR = 0)

$$PR = TR - TC = 100Q - 10Q^2 - 20Q - 120 = -10 Q^2 + 80 Q - 120$$

$$PR = 0 \;\Longleftrightarrow\; Q^2 - 8Q + 12 = 0 \;\Longrightarrow\; Q = \frac{8 \pm 4}{2}$$

$$\boxed{\; Q_A = 2, \quad Q_B = 6 \;}$$

### (e) Max zisku

$MR = MC$: $100 - 20Q = 20 \Rightarrow Q_2 = 4$

$$PR(4) = -10 \cdot 16 + 80 \cdot 4 - 120 = -160 + 320 - 120 = \boxed{40}$$

### (f) Náčrt

Klíčové body, které by měly být v grafu:

| Křivka | Tvar | Klíčové body |
|---|---|---|
| TR(Q) | parabola obrácená dolů | kořeny $Q = 0, 10$; vrchol $(5, 250)$ |
| TC(Q) | rostoucí přímka | průsečík s osou: $(0, 120)$; sklon 20 |
| PR(Q) | parabola obrácená dolů | kořeny $Q = 2, 6$ (body zvratu); vrchol $(4, 40)$ |
| MR(Q) | klesající přímka | průsečík s osou: $(0, 100)$; sklon −20; protíná osu $Q$ v bodě $Q = 5$ |
| MC(Q) | konstanta | vodorovná přímka v $P = 20$ |
| D(Q) | klesající přímka | sklon −10 (poloviční oproti MR) |

**Vyznačit:** $Q_1 = 5$ (max TR — tam, kde MR protíná osu Q); $Q_A = 2, Q_B = 6$ (body zvratu — TR = TC); $Q_2 = 4$ (max zisku — průsečík MR a MC).

> [!info] Geometrický vztah
> $Q_2 = 4$ leží **mezi** $Q_A = 2$ a $Q_B = 6$ — uvnitř ziskového intervalu, blízko jeho středu (přesně středem: $(2+6)/2 = 4$, neboť PR je kvadratická parabola). Maximum TR ($Q_1 = 5$) leží **vpravo** od max zisku — protože tam už náklady rostou rychleji než příjem.

---

# Zadání 6

## Z6/Q1 [10 b] — TR funkce

**Zadání:** (a) TR = 100 − 3Q; (b) TR = 12Q − Q²; (c) TR = 1000 − Q²; (d) TR = Q(100 − 2Q²); (e) TR = 10Q + Q².

**Klíč:** Stejný jako Z1/Q1 — TR(0) = 0 a P klesající.

| | Funkce | TR(0) | P | Verdikt |
|---|---|---|---|---|
| (a) | 100 − 3Q | = **100** ✗ | — | **NE** |
| (b) | 12Q − Q² | = 0 ✓ | 12 − Q (klesá) ✓ | **ANO** |
| (c) | 1000 − Q² | = **1000** ✗ | — | **NE** |
| (d) | Q(100 − 2Q²) = 100Q − 2Q³ | = 0 ✓ | 100 − 2Q² (klesá pro Q>0) ✓ | **ANO** |
| (e) | 10Q + Q² | = 0 ✓ | 10 + Q (**roste**) ✗ | **NE** |

---

## Z6/Q2 [20 b] — MPK(20,900) = 15

**Definice** (jako Z1/Q2): $MP_K = \partial Q / \partial K$.

**Interpretace:** Na hladině $L = 20$ pracovníků, $K = 900$ jednotek kapitálu se produkce přibližně **zvýší o 15 jednotek**, jestliže se kapitál zvýší o 1 jednotku (z 900 na 901), při neměnné práci. Další jednotka kapitálu přidá v daném bodě ~15 jednotek produkce.

---

## Z6/Q3 [30 b] — Mezní náklady $MC = 50 - 10Q + Q^2$, FC = 10

**Zadání:** (a) Stanovte TC a rychlost změny TC při Q = 20. (b) Min MC. (c) ΔMC při Q: 20→30, porovnejte s přesným.

### (a) TC a rychlost při Q = 20

$$TC = \int MC \, dQ + FC = \int (50 - 10Q + Q^2) \, dQ + 10 = 50Q - 5Q^2 + \frac{Q^3}{3} + 10$$

**Rychlost změny TC** = mezní náklady = MC(Q):
$$TC'(20) = MC(20) = 50 - 200 + 400 = \boxed{250}$$

Při produkci 20 jednotek se celkové náklady mění **rychlostí 250 peněžních jednotek na další jednotku produkce**.

(Pro úplnost: $TC(20) = 1000 - 2000 + 8000/3 + 10 \approx 1\,676{,}67$.)

### (b) Min MC

$$MC' = -10 + 2Q = 0 \;\Longrightarrow\; Q^* = 5$$

$MC''(5) = 2 > 0$ → minimum.

$$MC(5) = 50 - 50 + 25 = \boxed{25}$$

### (c) ΔMC při Q: 20 → 30

**Aproximace (diferenciál):**
$$\Delta MC \approx MC'(Q) \cdot \Delta Q = (-10 + 2 \cdot 20) \cdot 10 = 30 \cdot 10 = 300$$

**Přesně:**
$$MC(30) = 50 - 300 + 900 = 650; \quad MC(20) = 250$$
$$\Delta MC_{\text{přesné}} = 650 - 250 = 400$$

**Porovnání:** aproximace 300 vs. přesných 400 → **chyba 25 %**. Důvod: $\Delta Q = 10$ je velký krok, MC je kvadratická (nelineární), takže lineární aproximace systematicky podhodnocuje (druhá derivace je kladná).

> [!warning] Diferenciál v kvadratické funkci
> Pro funkci $f(Q) = aQ^2 + bQ + c$ platí: $f(Q + \Delta) - f(Q) = (2aQ + b) \Delta + a \Delta^2$.
> Lineární aproximace zachytí jen první člen ($f'(Q) \cdot \Delta = (2aQ + b) \Delta$), zatímco kvadratický člen $a \Delta^2$ vypadne.
> Zde: $a = 1$, $\Delta = 10$ → vynechaný člen $1 \cdot 100 = 100$, což přesně odpovídá rozdílu (400 − 300 = 100). ✓

---

## Z6/Q4 [40 b] — Model C-I (jako Z1/Q4 s odlišným (e))

**(a)–(d) totožné se Z1/Q4:**
- $Y^E = (b + I)/(1 - a)$
- ∂Y/∂a > 0, ∂Y/∂b > 0, ∂Y/∂I > 0
- (c) $Y^E = 1375$
- (d) ΔI = 100 → ΔY = 125 (přesné = přibližné, lineární v I)

### (e) da = −0,1; db = 2; dI = 10

**Aproximace** (multiplikátory v hladině (c) jako u Z1/Q4):
$$\Delta Y \approx 1718{,}75 \cdot (-0{,}1) + 1{,}25 \cdot 2 + 1{,}25 \cdot 10$$
$$= -171{,}875 + 2{,}5 + 12{,}5 = \boxed{-156{,}875}$$

**Přesně** (a → 0,1; b → 102; I → 1010):
$$Y^E_{\text{nový}} = \frac{102 + 1010}{1 - 0{,}1} = \frac{1112}{0{,}9} \approx 1\,235{,}56$$
$$\Delta Y_{\text{přesné}} = 1\,235{,}56 - 1375 \approx -139{,}44$$

**Porovnání:** aproximace −156,875 vs. přesných −139,44 → chyba ~12 %. Změna $da = -0{,}1$ je menší než v Z1/Q4 (tam $da = +0{,}2$), proto i chyba aproximace je menší.

> [!info] Srovnání Z1/Q4(e) a Z6/Q4(e)
> | Změna | da | Aproximace | Přesné | Chyba |
> |---|---|---|---|---|
> | Z1/Q4(e) | +0,2 | 360 | 480 | 25 % |
> | Z6/Q4(e) | −0,1 | −156,9 | −139,4 | 12 % |
>
> Větší $|da|$ → větší chyba lineárního přibližení.

---

# Zadání 7

## Z7/Q1 [10 b] — Funkce úspor

**Zadání:** (a) S = 0,3Y − 50; (b) S = 2,5Y − 20; (c) S = 0,3Y + 50; (d) S = −0,3Y − 150; (e) S = 0,03Y − 100.

**Klíč:** Lineární model úspor je $S = (1 - a)Y - b$ kde 0 < a < 1, b > 0. Tedy:
- **MPS = 1 − a ∈ (0, 1)** (sklon kladný, ale menší než 1);
- **autonomní úspory $S(0) = -b < 0$** (záporné, neboť b > 0).

Viz [[narodni-duchod#Spotřeba a úspory|Spotřeba a úspory]] (vzorec 7.4).

### Rozbor

| | Funkce | MPS | S(0) | Verdikt |
|---|---|---|---|---|
| (a) | 0,3Y − 50 | 0,3 ∈ (0,1) ✓ | −50 < 0 ✓ | **ANO** |
| (b) | 2,5Y − 20 | **2,5 > 1** ✗ | — | **NE** |
| (c) | 0,3Y + 50 | 0,3 ✓ | **+50 > 0** ✗ | **NE** |
| (d) | −0,3Y − 150 | **−0,3 < 0** ✗ | — | **NE** |
| (e) | 0,03Y − 100 | 0,03 ∈ (0,1) ✓ | −100 < 0 ✓ | **ANO** |

**Zdůvodnění (b):** MPS = 2,5 by znamenalo MPC = 1 − 2,5 = −1,5 — záporná spotřeba na další korunu důchodu, ekonomicky nesmysl.

**Zdůvodnění (c):** Kladné autonomní úspory implikují $b < 0$, tj. autonomní spotřeba C(0) = b < 0 — také nesmysl.

**Zdůvodnění (d):** Záporné MPS znamená, že s růstem důchodu úspory klesají — porušuje princip „úspory rostou s důchodem".

> [!tip] Filtr v 5 sekundách
> 1. Sklon (koeficient u Y) musí být v intervalu (0, 1).
> 2. Absolutní člen musí být záporný (= autonomní úspory < 0).
> Pokud něco z toho neplatí, není to standardní funkce úspor.

---

## Z7/Q2 [20 b] — MRCS (zadání píše MRTS, ale formulace je MRCS)

**Definice + interpretace** stejné jako Z3/Q2.

**Vzorec:** $MRCS = MU_1/MU_2$.

**MRCS(100,200) = 5:** spotřebitel je ochoten obětovat 5 jednotek $Q_2$ za 1 jednotku $Q_1$ navíc se zachovanou užitečností.

> [!warning] Pozor na formulaci úlohy
> Zadání uvádí „mezní míru technické substituce MRCS" — kombinace pojmu *technické substituce* (MRTS, produkce) a symbolu *MRCS* (komoditní substituce, užitečnost). Pokud by byla otázka **MRTS(L,K) = 5**, znamenalo by to: 1 jednotku práce lze nahradit 5 jednotkami kapitálu se zachovanou produkcí. Ostatní obsah úlohy se kryje.

---

## Z7/Q3 [30 b] — Tržní rovnováha s nelineární nabídkou

**Zadání:** $D(Q) = 18 - 2Q$, $S(Q) = 3 + Q^2$.
(a) $Q^E$ + náčrt; (b) elasticita poptávky při $P = 10$; (c) $Q^*$ pro max TR; (d) přebytek spotřebitele a výrobce při rovnovážném množství.

### (a) Rovnovážné množství

$$18 - 2Q = 3 + Q^2 \;\Longrightarrow\; Q^2 + 2Q - 15 = 0$$

$$Q = \frac{-2 \pm \sqrt{4 + 60}}{2} = \frac{-2 \pm 8}{2} \;\Longrightarrow\; Q = 3 \text{ nebo } Q = -5$$

$$\boxed{\; Q^E = 3, \quad P^E = 18 - 6 = 12 \;}$$

**Náčrt:** D je klesající přímka z (0, 18) do (9, 0); S je rostoucí parabola z (0, 3); průsečík v $E[3, 12]$.

### (b) Elasticita poptávky při P = 10

Inverze: $Q = (18 - P)/2 = 9 - P/2$, $\frac{dQ}{dP} = -\frac{1}{2}$. Při $P = 10$: $Q = 4$.

$$E = -\frac{P}{Q} \cdot \frac{dQ}{dP} = -\frac{10}{4} \cdot \left(-\tfrac{1}{2}\right) = \boxed{1{,}25}$$

**Klasifikace:** $E > 1$ → **elastická poptávka**. Snížení ceny zvýší celkový příjem.

### (c) Max TR

$$TR = P \cdot Q = (18 - 2Q) Q = 18Q - 2 Q^2$$

$$MR = 18 - 4Q = 0 \;\Longrightarrow\; Q^* = 4{,}5$$

$$TR_{\max} = 18 \cdot 4{,}5 - 2 \cdot 20{,}25 = 81 - 40{,}5 = \boxed{40{,}5}$$

### (d) Přebytky při $Q^E = 3, P^E = 12$

**Přebytek spotřebitele:**
$$CS = \int_0^3 (18 - 2Q) \, dQ - 12 \cdot 3 = \left[18Q - Q^2\right]_0^3 - 36 = (54 - 9) - 36 = \boxed{9}$$

**Přebytek výrobce:**
$$PS = 12 \cdot 3 - \int_0^3 (3 + Q^2) \, dQ = 36 - \left[3Q + \frac{Q^3}{3}\right]_0^3 = 36 - (9 + 9) = \boxed{18}$$

**Geometricky:**
- CS = plocha mezi křivkou $D(Q)$ (klesající přímka shora) a vodorovnou linií $P = 12$ na intervalu $[0, 3]$.
- PS = plocha mezi vodorovnou linií $P = 12$ (shora) a křivkou $S(Q)$ (rostoucí parabola zdola) na intervalu $[0, 3]$.

Celkový blahobyt $W = CS + PS = 27$ — čistý přínos trhu pro obě strany dohromady.

---

## Z7/Q4 [40 b] — Vícefaktorová poptávka po kašmírových ponožkách

**Zadání:** $Q = 1000 - 400P + 200 P_A + 0{,}5 Y$ (Q = páry kašmírových; P = cena kašmír; $P_A$ = cena vlna; Y = důchod).
$P = 10, P_A = 5, Y = 20\,000$.
(a) Q. (b) E_P, E_PA, E_Y + charakter. (c) Substitut/komplement, normální/podřadné. (d) ΔQ % při ΔP% = +1, ΔPA% = −3, ΔY% = +20.

**Klíč:** Vícefaktorové elasticity ([[elasticita#Vícefaktorový model|vzorce 4.18–4.20]]) + procentní aproximace (4.21).

### (a) Q na hladině

$$Q = 1000 - 400 \cdot 10 + 200 \cdot 5 + 0{,}5 \cdot 20\,000 = 1000 - 4000 + 1000 + 10\,000 = \boxed{8\,000}$$

### (b) Elasticity

**Cenová:**
$$\frac{\partial Q}{\partial P} = -400, \quad E_P = -\frac{P}{Q} \cdot \frac{\partial Q}{\partial P} = -\frac{10}{8000} \cdot (-400) = \frac{4000}{8000} = \boxed{0{,}5}$$

→ **neelastická** (0 < E_P < 1).

**Křížově-cenová:**
$$\frac{\partial Q}{\partial P_A} = +200, \quad E_{P_A} = \frac{P_A}{Q} \cdot \frac{\partial Q}{\partial P_A} = \frac{5}{8000} \cdot 200 = \boxed{0{,}125}$$

**Důchodová:**
$$\frac{\partial Q}{\partial Y} = +0{,}5, \quad E_Y = \frac{Y}{Q} \cdot \frac{\partial Q}{\partial Y} = \frac{20\,000}{8000} \cdot 0{,}5 = \boxed{1{,}25}$$

### (c) Charakterizace

- $E_{P_A} = 0{,}125 > 0$ → vlna je **substitut** kašmíru (zdraží-li se vlněné ponožky, lidé kupují víc kašmírových).
- $E_Y = 1{,}25 > 0$ → kašmír je **normální zboží**. Navíc $E_Y > 1$ → **luxusní zboží** (s růstem důchodu roste spotřeba rychleji než důchod).

### (d) ΔQ % při současných změnách

Vzorec: $\Delta Q\% \approx -E_P \cdot \Delta P\% + E_{P_A} \cdot \Delta P_A\% + E_Y \cdot \Delta Y\%$

$$\Delta Q\% \approx -0{,}5 \cdot 1 + 0{,}125 \cdot (-3) + 1{,}25 \cdot 20$$
$$= -0{,}5 - 0{,}375 + 25 = \boxed{+24{,}125 \%}$$

**Interpretace:** dominuje **důchodový efekt** — 20 % růst důchodu krát luxusní elasticita 1,25 = 25 procentních bodů růstu Q. Cenové efekty (zdražení kašmíru, zlevnění vlny) sotva tlumí o necelé procento.

---

# Zadání 8

## Z8/Q1 [10 b] — Funkce úspor

**Zadání:** (a) S = 0,2Y − 50; (b) S = 50 − 0,3Y; (c) S = 1,2Y − 10; (d) S = 0,4Y − 10; (e) S = 100 + 0,4Y.

**Stejná pravidla** jako Z7/Q1.

| | Funkce | MPS | S(0) | Verdikt |
|---|---|---|---|---|
| (a) | 0,2Y − 50 | 0,2 ∈ (0,1) ✓ | −50 < 0 ✓ | **ANO** |
| (b) | −0,3Y + 50 | **−0,3** ✗ | — | **NE** |
| (c) | 1,2Y − 10 | **1,2 > 1** ✗ | — | **NE** |
| (d) | 0,4Y − 10 | 0,4 ✓ | −10 < 0 ✓ | **ANO** |
| (e) | 0,4Y + 100 | 0,4 ✓ | **+100 > 0** ✗ | **NE** |

---

## Z8/Q2 [20 b] — MRTS(10,100) = 15

**Identické se Z5/Q2.** $MRTS = MP_L/MP_K$. MRTS(10,100) = 15 znamená, že 1 jednotku práce lze nahradit ~15 jednotkami kapitálu se zachovanou produkcí.

---

## Z8/Q3 [30 b] — Min výdajů (totožné se Z2/Q3)

$$Q_1^* = 4 \cdot 5^{2/3} \approx 11{,}696, \quad Q_2^* = 10 \cdot 5^{2/3} \approx 29{,}240, \quad E^* = 60 \cdot 5^{2/3} \approx 175{,}44$$

**Viz Z2/Q3.**

---

## Z8/Q4 [40 b] — Kašmírové ponožky (totožné se Z7/Q4)

$Q = 8\,000$; $E_P = 0{,}5$ (neelastická); $E_{P_A} = 0{,}125$ (substitut); $E_Y = 1{,}25$ (normální/luxusní); $\Delta Q\% \approx +24{,}125 \%$.

**Viz Z7/Q4.**

---

# Závěrečné shrnutí pro studium

## Mapa úloh × topiky

| Zadání | Q1 | Q2 | Q3 | Q4 |
|---|---|---|---|---|
| 1 | TR | MPK | max U | C-I |
| 2 | nabídka | E_PA | min E | cenová diskriminace |
| 3 | AC | MRCS | max produkce | IS-LM |
| 4 | páry poptávky | MRCS | max zisku 2 zboží | IS-LM (= Z3) |
| 5 | AC (= Z3) | MRTS | max produkce (= Z3) | TR/TC firmy |
| 6 | TR | MPK | mezní náklady | C-I (≈ Z1) |
| 7 | úspory | MRCS | rovnováha trhu | vícefaktorová |
| 8 | úspory | MRTS | min E (= Z2) | vícefaktorová (= Z7) |

## Klíčové vzorce, které musíš znát

1. **TR = P·Q, MR = TR'(Q), MC = TC'(Q)** — derivace celkových veličin (viz [[derivace]]).
2. **AC = MC v min AC; AVC = MC v min AVC; MR = MC v max zisku** — tři optimalizační principy firmy.
3. **MRCS = MU₁/MU₂ = P₁/P₂** v optimu spotřebitele; **MRTS = MP_L/MP_K** sklon izokvanty.
4. **Y^E = (b + I)/(1 − a)** — model C-I; **Keynesův multiplikátor** $\partial Y / \partial I = 1/(1-a)$.
5. **r^E = (q − n)/(m − p)** — IS-LM po dosazení.
6. **Δf ≈ f'(x) Δx** (jedna proměnná) nebo **df = ∑(∂f/∂xᵢ) dxᵢ** (více proměnných) — diferenciál.
7. **E = −(P/Q)·(dQ/dP)** — cenová elasticita; vícefaktorové analogicky pro $E_{P_A}, E_Y$.
8. **CS = ∫₀^Q D dQ − P Q;  PS = P Q − ∫₀^Q S dQ** — přebytky.

## Kdy je aproximace přesná a kdy ne

- **Přesná** = aproximace pro **lineární** funkce (např. $Y^E = (b+I)/(1-a)$ je lineární v $b$ a $I$ — tedy diferenciál pro samotné $\Delta b$ nebo $\Delta I$ je přesný).
- **Přibližná** = aproximace pro **nelineární** funkce nebo **velké** perturbace. Příklady chyb v tomto materiálu:
  - Z1/Q4(e): $da = 0{,}2$ → chyba 25 %
  - Z3/Q4(d): $dp = -20, dm = 10$ → chyba 12 %
  - Z6/Q3(c): $dQ = 10$ pro kvadratické MC → chyba 25 %
  - Z6/Q4(e): $da = -0{,}1$ → chyba 12 %

> [!tip] Heuristika pro zkoušku
> Když relativní změna parametru přesahuje **5–10 %**, očekávej, že lineární aproximace **podhodnotí nebo nadhodnotí** přesný výsledek. V odpovědi vždy uveď obě hodnoty a krátce komentuj.

## Postup řešení dle typu úlohy

> [!tip] Q1 (10 b) — kvalitativní rozhodování
> 1. Vyber **2–3 podmínky**, které funkce daného typu musí splnit.
> 2. Pro každou variantu odpověz „ano/ne" a stručně **zdůvodni** (dosazením do podmínky).

> [!tip] Q2 (20 b) — definice + interpretace
> 1. **Vzorec** definice (parciální derivace).
> 2. **Slovní interpretace** numerické hodnoty: „při hladině X přidání 1 jednotky Y změní Z přibližně o ...".
> 3. Případně **znaménko / typ vztahu** (substitut/komplement, normální/podřadné, optimální/přesycený).

> [!tip] Q3 (30 b) — optimalizace
> 1. **Identifikuj typ:** max U / min E / max produkce / max zisku (i 2-zbožového) / rovnováha trhu.
> 2. **Lagrange** (pro vázanou) nebo **přímá derivace = 0** (volná).
> 3. **Vyřeš soustavu** (typicky 2 rovnice).
> 4. **Dopočítej** výsledné veličiny (užitečnost, výdaje, produkce, zisk, přebytky).

> [!tip] Q4 (40 b) — komplexní makroekonomický nebo strategický model
> 1. **Sestav rovnice** ze zadání (rovnováha + funkce spotřeby/investic / poptávka + náklady / IS + LM).
> 2. **Řeš soustavu** → redukovaný tvar.
> 3. **Dosaď čísla** → rovnovážné hodnoty.
> 4. **Multiplikátory** = parciální derivace redukovaného tvaru.
> 5. **Aproximace změn** přes diferenciál; **porovnej s přesným** výsledkem.

---

## Navigace

- **Kompletní přehled vzorců:** [[imek-vzorce-prehled|ImeK — kompletní přehled vzorců]]
- **Kurz:** [[imek|Matematická ekonomie (ImeK)]]
- **Souhrny přednášek:** [[imek-blok-01|Kalkul a mikroekonomie]], [[imek-blok-02|Elasticita a produkce]], [[imek-blok-03|Užitečnost a národní důchod]]
- **Mikroekonomie:** [[poptavka-nabidka|Poptávka a nabídka]], [[prijem-naklady-zisk|Příjem, náklady, zisk]], [[elasticita|Elasticita]], [[produkce|Produkce]], [[uzitecnost|Užitečnost]], [[optimalizace-spotrebitele|Optimalizace spotřebitele]], [[prebytek-spotrebitele-vyrobce|Přebytky]]
- **Makroekonomie:** [[narodni-duchod|Národní důchod]], [[is-lm|IS-LM analýza]]
- **Matematický aparát:** [[derivace|Derivace]], [[integral|Integrál]], [[funkce-vice-promennych|Funkce více proměnných]], [[lagrangeova-metoda|Lagrangeova metoda]]
