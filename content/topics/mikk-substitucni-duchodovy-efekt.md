---
title: "Cenový rozklad: substituční a důchodový efekt"
course: mikk
type: topic
tags: [mikk, mikroekonomie, slutsky, hicks, giffen, pcc, icc, engel]
sources: [raw/mikk/Prednaska 1. a 2. blok.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Cenový rozklad: substituční a důchodový efekt

> [!abstract] TL;DR
> Když se změní cena statku, spotřebitel reaguje dvěma souběžnými důvody: relativní cena se posunula (**substituční efekt**, SE) a reálná kupní síla důchodu se posunula (**důchodový efekt**, IE). Součet obou je **cenový (celkový) efekt**. Substituční efekt je vždy záporný — proti směru změny ceny. Důchodový efekt je záporný u normálních statků, kladný u podřadných. Když u podřadného statku kladný IE převáží záporný SE, dostáváme **Giffenův paradox**: cena roste a poptávka roste s ní. **Hicksův rozklad** drží spotřebitele na původní indiferenční křivce (zachovává užitek), **Slutského rozklad** mu drží dosažitelnost původního koše (zachovává reálné množství). Z trajektorie optima při změně ceny vzniká **PCC** (cenová spotřební křivka, zdroj individuální poptávky), z trajektorie při změně důchodu vzniká **ICC** (důchodová spotřební křivka), a z ICC se přímo odvozuje **Engelova křivka** $X^*(I)$.

Tato stránka navazuje na [[mikk-rovnovaha-spotrebitele|rovnováhu spotřebitele]] a [[mikk-utility-preference|teorii užitku a preferencí]]. Cenový rozklad je páteří celé mikroekonomické analýzy poptávky — bez něj nelze pochopit ani [[mikk-marshall-hicks-poptavka|rozdíl mezi Marshallovou a Hicksovou poptávkou]], ani [[mikk-elasticita-poptavky|elasticity]], ani daňovou incidenci.

---

## 1. Cenový (celkový) efekt = substituční + důchodový

Předpoklady úlohy: spotřebitel volí mezi statky $X$ a $Y$ při daných cenách $P_X, P_Y$ a peněžním důchodu $I$. Optimum splňuje rozpočtové omezení $P_X X + P_Y Y = I$ a tečnost indiferenční křivky a rozpočtové přímky:
$$\text{MRS}_{XY} = \frac{MU_X}{MU_Y} = \frac{P_X}{P_Y}.$$

Nyní změňme cenu jednoho statku, např. $P_X$ klesne na $P_X'$ při zachování $P_Y$ a $I$. Spotřebitel přechází z původního optima $E_0$ do nového optima $E_2$. Změna spotřebovaného množství $X$ je **cenový (celkový) efekt**:
$$\Delta X^{\text{cen}} = X(E_2) - X(E_0).$$

Tento celkový pohyb lze rozložit na dvě části:

- **Substituční efekt (SE)** — kolik z $\Delta X^{\text{cen}}$ je způsobeno samotnou změnou *relativních* cen, tj. tím, že $X$ je teď oproti $Y$ levnější (resp. dražší). Při čistě relativní změně cen by spotřebitel přesunul část výdajů ze zdraženého statku k tomu zlevněnému, i kdyby celková kupní síla zůstala konstantní.
- **Důchodový efekt (IE)** — kolik z $\Delta X^{\text{cen}}$ je způsobeno tím, že po zlevnění $X$ má spotřebitel za stejné peníze efektivně víc než dřív (vzrostla *reálná* kupní síla, i když nominální $I$ se nezměnilo).

Symbolicky:
$$\Delta X^{\text{cen}} = \underbrace{\Delta X^{\text{SE}}}_{\text{relativní cena}} + \underbrace{\Delta X^{\text{IE}}}_{\text{reálný důchod}}.$$

> [!info] Proč to vůbec rozkládat?
> Čtyři hlavní důvody: (1) Konstrukce **cenové spotřební křivky** a tím i tržní poptávky. (2) Vyčíslení, do jaké míry spotřebitel přechází k *substitutům* — to je SE. (3) Vyčíslení, jak změna ceny mění *celkovou* spotřebu daného statku — to je úloha IE. (4) Konstrukce **důchodové spotřební křivky** a Engelových křivek pro predikci poptávky při změnách příjmu.

## 2. Substituční efekt je vždy záporný

Slovo „záporný" zde znamená *proti směru změny ceny* — pokud cena roste, SE snižuje poptávané množství; pokud cena klesá, SE zvyšuje poptávané množství. Důvod je čistě geometrický: indiferenční křivky jsou konvexní (klesající MRS), takže při změně sklonu rozpočtové přímky se tečna posouvá podél IC ve směru zlevňujícího se statku.

Formálně, pro Hicksovu kompenzovanou poptávku $X^H(P_X, P_Y, U_0)$ platí:
$$\frac{\partial X^H}{\partial P_X} \le 0.$$

Tato nerovnost je zákonem (důsledek konkávní výdajové funkce, viz [[mikk-marshall-hicks-poptavka|Marshallova vs. Hicksova poptávka]]).

> [!tip] Intuice
> Když $P_X$ klesne, ale „odečteme" spotřebiteli takovou částku, aby zůstal stejně bohatý jako předtím (Hicksovsky stejně užitkový, Slutsky-stejně schopný koupit původní koš), pak jediným důvodem ke změně koše je to, že $X$ je *relativně* levnější. A spotřebitel reaguje předvídatelně: nakoupí víc $X$ a méně $Y$.

## 3. Důchodový efekt — normální vs. podřadné zboží

Po izolaci SE zbývá doplnit zpět právě tu kupní sílu, kterou jsme spotřebiteli „odebrali". To je důchodový efekt. Jeho znaménko závisí na typu statku:

- **Normální zboží** — s rostoucím důchodem roste poptávané množství, $\partial X^M/\partial I > 0$. Pokles $P_X$ zvýší reálný důchod, takže poptávka po $X$ ještě dál vzroste. IE proto působí *stejným směrem* jako SE → zesiluje cenový efekt.
- **Podřadné (inferiorní) zboží** — s rostoucím důchodem poptávané množství *klesá*, $\partial X^M/\partial I < 0$. Pokles $P_X$ zvýší reálný důchod, ale spotřebitel ho použije k posunu k „lepším" statkům, takže poptávka po $X$ se sníží. IE působí *proti* SE → oslabuje cenový efekt.

> [!warning] Pozor na konvenci znamének
> V některých učebnicích se „kladný IE" rozumí stejným směrem jako SE; jinde se IE definuje jako $\Delta X^{\text{IE}}$ a jeho znaménko se odvíjí od toho, zda $X$ klesá nebo roste. V této stránce držíme konvenci přednášky: pro normální zboží jdou SE i IE *stejným* směrem (oba zvyšují $X$ při poklesu $P_X$); pro podřadné zboží jdou *proti* sobě (SE zvyšuje, IE snižuje).

| Typ zboží | znaménko $\partial X^M/\partial I$ | znaménko SE | znaménko IE | výsledný cenový efekt |
|---|---|---|---|---|
| normální | $> 0$ | proti $\Delta P$ | proti $\Delta P$ | vždy klesající D |
| podřadné, ne-Giffen | $< 0$ | proti $\Delta P$ | po směru $\Delta P$ | klesající D, ale plošší |
| Giffen | $\ll 0$ a velký podíl výdajů | proti $\Delta P$ | po směru $\Delta P$, $|IE| > |SE|$ | rostoucí D! |

## 4. Geometrie rozkladu — body $E_0, E_1, E_2$

![[mikk-slutsky-hicks-rozklad.jpeg|Slutsky vs. Hicksův rozklad cenového efektu na substituční (SE) a důchodový efekt (IE)]]

V grafu indiferenčních křivek uvažujme zlevnění $X$ (ze sklonu $-P_X/P_Y$ na $-P_X'/P_Y$):

- **Bod $E_0$** — původní optimum na rozpočtové přímce $L$, na indiferenční křivce $U_0$. Spotřebovává množství $Q$ statku $X$.
- **Bod $E_2$** — nové optimum na nové rozpočtové přímce $L'$ (s mírnějším sklonem, protože $X$ zlevnilo), na vyšší indiferenční křivce $U_1$. Spotřebovává $S$ statku $X$.
- **Bod $E_1$** — pomocný „kompenzovaný" bod. Leží na pomocné rozpočtové přímce $L^\wedge$, která má **stejný sklon jako $L'$** (tj. nové relativní ceny), ale je posunutá tak, aby spotřebitel zůstal stejně bohatý jako v $E_0$. Spotřebovává $R$ statku $X$.

V interval $E_0 \to E_1 \to E_2$:

- $QR =$ posun z $E_0$ do $E_1$ = **substituční efekt**;
- $RS =$ posun z $E_1$ do $E_2$ = **důchodový efekt**;
- $QS =$ posun z $E_0$ do $E_2$ = **cenový efekt** = $QR + RS$.

Rozdíl mezi Hicksovým a Slutského rozkladem spočívá *jen* v tom, jak je definováno „stejně bohatý jako předtím" — neboli kde přesně leží pomocná přímka $L^\wedge$ a kde leží $E_1$.

## 5. Hicksova separace — zachování užitku

> [!example] Hicksova konstrukce
> Pomocná rozpočtová přímka $L^\wedge_H$ je **paralelní s novou rozpočtovou přímkou $L'$** (sklon $-P_X'/P_Y$) a **tečná k původní indiferenční křivce $U_0$**. Bod $E_1^H$ je tečným bodem.

Hicks definuje „stejně bohatého spotřebitele" tak, že má **stejný užitek** jako v původním optimu. Substituční efekt je proto čistě pohyb po $U_0$, jen s novými relativními cenami:

$$X^H(E_1^H) = \arg\min \{ P_X' X + P_Y Y : U(X,Y) = U_0 \}.$$

Substituční efekt v Hicksově pojetí je:
$$\Delta X^{\text{SE,H}} = X^H(E_1^H) - X(E_0) = \left.\frac{\partial X^H}{\partial P_X}\right|_{U=U_0} \cdot \Delta P_X.$$

> [!tip] Hicks v jedné větě
> „Sebrat spotřebiteli takový peněžní obnos, aby přesně dorovnal zlevnění $X$ z hlediska jeho užitku — pak ho nechat se přeoptimalizovat."

Hicksova separace je *teoreticky čistší*: drží konstantní *užitek*, což je hlavní pojmová proměnná teorie spotřebitele. Pro analytické úlohy (Slutského rovnice, dualita s výdajovou funkcí) je nepostradatelná.

## 6. Slutského separace — zachování koše

> [!example] Slutského konstrukce
> Pomocná rozpočtová přímka $L^\wedge_S$ je **paralelní s novou rozpočtovou přímkou $L'$** (sklon $-P_X'/P_Y$) a **prochází původním optimem $E_0$**. Bod $E_1^S$ je nové optimum na této přímce — leží na *vyšší* IC než $U_0$.

Slutsky definuje „stejně bohatého spotřebitele" tak, že má **stále k dispozici původní spotřební koš** $E_0$. Při zlevnění $X$ ale původní koš leží *uvnitř* nové rozpočtové množiny (na pomocné přímce $L^\wedge_S$ je to její koncový bod), takže se spotřebitel může pohnout na vyšší IC.

Důsledek: Slutského substituční efekt je *větší* (v absolutní hodnotě) než Hicksův, protože $E_1^S$ leží na vyšší IC než $E_1^H$:
$$|\Delta X^{\text{SE,S}}| \ge |\Delta X^{\text{SE,H}}|.$$

> [!tip] Slutsky v jedné větě
> „Sebrat spotřebiteli takový peněžní obnos, aby si stále mohl koupit přesně to, co kupoval předtím — pak ho nechat se přeoptimalizovat."

Slutského separace je *empiricky operativnější*: spotřební koš $E_0$ je přímo pozorovatelný (z dat o domácnostech), zatímco užitek $U_0$ je latentní. Statistici a empirici proto dávají Slutského rozkladu přednost. Pro infinitesimální změny ceny se oba rozklady shodují (limita $\Delta P_X \to 0$).

## 7. Slutského rovnice

Centrální identita celé teorie spojuje pozorovatelnou Marshallovu (tržní) poptávku $X^M(I, P_X, P_Y)$ s Hicksovou kompenzovanou poptávkou $X^H(U_0, P_X, P_Y)$:

$$\boxed{\;\frac{\partial X^M}{\partial P_X} \;=\; \underbrace{\frac{\partial X^H}{\partial P_X}}_{\text{SE (Hicks)}} \;-\; \underbrace{X \cdot \frac{\partial X^M}{\partial I}}_{\text{IE}}\;}$$

Levá strana je *cenový* (celkový) efekt — to, co skutečně pozorujeme na trhu. Pravá strana je rozklad: první člen je substituční efekt podle Hicksova pojetí (vždy nekladný), druhý je důchodový efekt vážený stávající spotřebou $X$.

> [!note] Odvození ve dvou krocích
> 1. Z **duality** výdajové a nepřímé užitkové funkce platí $X^M(I^*, P_X, P_Y) = X^H(U_0, P_X, P_Y)$ podél optima, kde $I^* = E(U_0, P_X, P_Y)$.
> 2. Derivováním obou stran podle $P_X$ a využitím **Shephardova lemmatu** $\partial E/\partial P_X = X^H$ získáme přesně boxovou identitu výše. Detail viz [[mikk-marshall-hicks-poptavka|Marshallova vs. Hicksova poptávka]].

Praktické důsledky Slutského rovnice:

- Pro normální zboží ($\partial X^M/\partial I > 0$) jsou oba členy záporné → Marshallova poptávka klesá v $P_X$.
- Pro podřadné ($\partial X^M/\partial I < 0$) je druhý člen kladný — když je dost velký (statek tvoří velký podíl výdajů, $X$ velké), může převážit nad záporným SE a dostat $\partial X^M/\partial P_X > 0$ → **Giffenův paradox**.

## 8. Srovnání Hicks vs. Slutsky

| kritérium | Hicks | Slutsky |
|---|---|---|
| co se zachovává | užitek $U_0$ | koš $(X_0, Y_0)$ |
| pomocná IC | původní $U_0$ | vyšší než $U_0$ |
| pomocná rozpočtová přímka | tečná k $U_0$, sklon nový | prochází $E_0$, sklon nový |
| velikost SE | menší | větší |
| pozorovatelnost | latentní (užitek) | přímá (koš z dat) |
| výhoda | čisté pojmově, dualita | empirie, indexy cen |
| typické použití | teoretická analýza, Slutského identita | aplikovaná ekonomie, CPI |
| limita $\Delta P \to 0$ | shodují se | shodují se |

Doporučení: pro odvození a důkazy používáme Hicksův rozklad; pro empirickou aproximaci z reálných dat a pro výpočty přes Laspeyresovy/Paascheho indexy používáme Slutského.

## 9. Cenový efekt pro normální zboží

Pro normální zboží jdou SE i IE stejným směrem. Pokud $P_X$ klesne:

- $SE: \;\downarrow P_X \to \uparrow X$ (substituce z $Y$ k levnějšímu $X$);
- $IE: \;\downarrow P_X \to \uparrow I_{\text{real}} \to \uparrow X$ (vyšší kupní síla, X normální).

Oba efekty zvyšují $X$, takže **Marshallova poptávka po normálním zboží je vždy klesající** v $P_X$. Graficky to odpovídá třem bodům $E_0, E_1, E_2$, všem posunutým vpravo, kde $QS = QR + RS > 0$ pro pokles ceny.

## 10. Cenový efekt pro podřadné zboží

Pro podřadné (inferiorní, ne ovšem Giffenovo) zboží jdou SE a IE *proti sobě*:

- $SE: \;\downarrow P_X \to \uparrow X$;
- $IE: \;\downarrow P_X \to \uparrow I_{\text{real}} \to \downarrow X$ (X podřadné).

Tuto situaci lze popsat slovy: „substituční a důchodový efekt se *přetahují*". Výsledný cenový efekt je *součet* dvou opačně orientovaných sil:

- Pokud $|SE| > |IE|$ — typické pro mírně podřadné statky — D křivka stále klesá, ale je *plošší* než pro normální zboží.
- Pokud $|SE| < |IE|$ — typické pro statky tvořící velkou část rozpočtu chudých domácností bez substitutů — vzniká **Giffen**.

## 11. Giffenův paradox

> [!warning] Definice
> **Giffenovo zboží** je takové podřadné zboží, u nějž **kladný důchodový efekt převáží nad záporným substitučním**, takže s **poklesem ceny poptávané množství klesá** a s **růstem ceny roste**. Marshallova poptávka po Giffenově zboží je *rostoucí* v ceně.

Mechanismus:

1. $X$ je silně podřadné — s rostoucím důchodem ho spotřebitel rád nahrazuje lepšími statky.
2. $X$ tvoří **značnou část** spotřebitelových výdajů — pokles $P_X$ způsobí velký nárůst reálného důchodu.
3. $X$ je **základní životní potřeba** — nelze ji jednoduše substituovat ničím jiným.
4. Žádné blízké substituty neexistují → SE je malý.

Pak: zlevnění $X$ → velký nárůst $I_{\text{real}}$ → spotřebitel si za uvolněné peníze koupí *jiné, lepší* statky a $X$ omezí. Záporný (silně) IE > záporný (slabě) SE → poptávané množství $X$ klesá.

> [!example] Klasické historické příklady
> - **Brambory v Irsku během hladomoru 1845–1849.** Brambory tvořily většinu kalorického příjmu chudé populace. Když cena brambor v důsledku úrody-i-poškození rostla, chudá rodina nemohla nahradit brambory masem (na to nebyly peníze) a místo toho omezila i ty malé výdaje na maso — a kupovala *víc* brambor, ne méně. Empiricky kontroverzní; klasickou fenomenologii popsal Robert Giffen.
> - **Rýže a chléb v některých chudých regionech Asie a Číny** (studie Jensen & Miller, Hunan a Gansu, kolem 2007).
> - Stručně: „Při zdražení zboží Y poptávka po něm vzrostla."

> [!tip] Vztah ke Slutského rovnici
> Giffen $\iff \partial X^M/\partial P_X > 0 \iff -X \cdot \partial X^M/\partial I > -\partial X^H/\partial P_X = |SE|$. Druhá podmínka rozepíše: $X$ velké (hlavní výdajová položka), $\partial X^M/\partial I$ silně záporné (silně podřadné), $|SE|$ malé (málo substitutů).

> [!warning] Každý Giffen je podřadný, ne každé podřadné zboží je Giffen.
> Podmínka „podřadný" je *nutná*, ale ne dostatečná. Většina podřadných statků (např. rohlíky pro středostavovskou rodinu) má příliš malý podíl na rozpočtu, takže IE je nedostatečně silný k převažení nad SE.

## 12. Cenová spotřební křivka (PCC)

> [!info] Definice
> **Cenová spotřební křivka (Price Consumption Curve, PCC)** je trajektorie spotřebitelových optim $E_0, E_1, E_2, \dots$ při různých hodnotách $P_X$, zatímco $P_Y$ a $I$ jsou konstantní.

Jinak řečeno: pro každou hodnotu $P_X$ máme rozpočtovou přímku, na ní tečné optimum, a body všech těchto optim spojené v rovině $(X, Y)$ tvoří PCC. Z PCC se přímo odvozuje individuální Marshallova poptávková křivka $X^M(P_X)$ — projekcí každého bodu PCC do roviny $(X, P_X)$.

### 12.1 Tvar PCC a elasticita poptávky

Vztah mezi sklonem PCC a [[mikk-elasticita-poptavky|cenovou elasticitou poptávky]]: výdaje na $X$ jsou $P_X \cdot X$. Pohybem podél PCC se výdaje na $Y$ mění opačně k výdajům na $X$ (kvůli rozpočtovému omezení). Když cena $X$ klesne:

- **Pružná poptávka ($|E_X^P| > 1$)** — výdaje na $X$ rostou (procentní pokles ceny vyvolá větší procentní růst poptávaného množství). Spotřebitel utrácí *víc* za $X$ a *míň* za $Y$ → bod se na PCC posune *dolů* (méně $Y$). PCC klesá.
- **Jednotková elasticita ($|E_X^P| = 1$)** — výdaje na $X$ se nemění, takže ani výdaje na $Y$ se nemění → PCC je *vodorovná*.
- **Nepružná poptávka ($|E_X^P| < 1$)** — výdaje na $X$ klesají, výdaje na $Y$ rostou → PCC roste *vpravo nahoru*.

### 12.2 PCC pro Giffenovo zboží

Pro Giffenovo zboží má PCC *netypický* tvar: při poklesu $P_X$ se optimum posune *vlevo* (méně $X$), nikoli vpravo. PCC tedy ohýbá zpět, a odpovídající projekce do $(X, P_X)$ je rostoucí — to je rostoucí Marshallova poptávka po Giffenovi.

## 13. Důchodová spotřební křivka (ICC)

> [!info] Definice
> **Důchodová spotřební křivka (Income Consumption Curve, ICC)** je trajektorie spotřebitelových optim při různých hodnotách peněžního důchodu $I$, zatímco $P_X, P_Y$ jsou konstantní (a nemění se preference, ceteris paribus).

Při růstu $I$ se rozpočtová přímka *paralelně* posouvá vpravo nahoru, sklon zůstává stejný. Optima se posouvají po IC vyšších tříd, a jejich spojnice je ICC.

### 13.1 Tvar ICC podle typu zboží

Rozlišujeme tři typické tvary:

- **$X$ i $Y$ normální** — ICC stoupá vpravo nahoru, zhruba pod úhlem 45° (přesně 45° pro homotetické preference jako Cobb-Douglas).
- **$X$ podřadné, $Y$ normální** — ICC se po jisté úrovni důchodu *odklání vlevo* (klesá $X$, roste $Y$). Spotřebitel s vyšším příjmem omezuje podřadný $X$.
- **$Y$ podřadné, $X$ normální** — ICC se po jisté úrovni důchodu *odklání dolů* (roste $X$, klesá $Y$).

Statek nemůže být podřadný v *celém* rozsahu důchodů — pro $I \to 0$ musí být každý spotřebovávaný statek normální (jinak by jeho spotřeba byla z definice nulová). Statek je tedy obvykle normální v *nízkých* příjmech a stává se podřadným až nad jistou úrovní.

### 13.2 Vliv změny ceny na ICC

Pokles $P_X$ změní *sklon* všech rozpočtových přímek a tedy přesune i ICC. Po zlevnění $X$ se každé optimum při daném $I$ posune vpravo (více $X$), takže celá ICC se posune vpravo. To je ekvivalentní pohybu podél PCC pro každou hodnotu důchodu.

## 14. Engelovy křivky

> [!info] Definice
> **Engelova křivka** statku $X$ je funkce $X^*(I)$, vyjadřující optimální spotřebu $X$ jako funkci důchodu při fixních cenách. Geometricky se Engelova křivka *kreslí v rovině $(X, I)$* a získává se přímo projekcí ICC.

### 14.1 Konstrukce z ICC

Postup:

1. Pro každou hodnotu $I$ najdi optimum na ICC, odečti $X^*(I)$.
2. V rovině $(X, I)$ vynes bod $(X^*(I), I)$.
3. Spojení těchto bodů je Engelova křivka.

### 14.2 Tvary Engelových křivek

Typické tvary:

- **Normální zboží** — Engelova křivka je rostoucí, $\partial X^*/\partial I > 0$.
  - **Nezbytný statek** — roste, ale konkávně (mezní sklon klesá s důchodem).
  - **Luxusní statek** — roste konvexně (mezní sklon roste s důchodem; podíl výdajů na $X$ roste s $I$).
- **Podřadné zboží** — Engelova křivka má **zlom v $I_0$**: pod $I_0$ je rostoucí (statek je při nízkých příjmech normální), nad $I_0$ klesá (statek se stává podřadným).
- **Souhrnná Engelova křivka** — agregace přes všechny statky a domácnosti, používá se při empirických studiích spotřeby.

> [!note] Vztah k důchodové elasticitě
> Důchodová elasticita poptávky $E_X^I = (\partial X^*/\partial I)(I/X)$ je sklon Engelovy křivky vážený poměrem $I/X$. Klasifikace:
> - $E_X^I < 0$ → podřadné;
> - $0 < E_X^I < 1$ → nezbytné (normální);
> - $E_X^I > 1$ → luxusní.

> [!tip] Engelův zákon
> Empirické pravidlo (Ernst Engel, 1857): podíl výdajů na potraviny klesá s rostoucím příjmem. Potraviny mají Engelovu křivku konkávní (nezbytný statek). To je dnes základní fakt empirické ekonomie.

## 15. Aplikace v praxi

### 15.1 Daňová politika a daňová incidence

Když stát uvalí spotřební daň na statek $X$ (např. cigarety), $P_X$ pro spotřebitele roste. Cenový efekt rozhodne, jak moc poptávka klesne — tedy kolik státu vybere a jak moc je daň regresivní:

- Statek s nepružnou D (nízká SE, nízký podíl) → vysoký výnos, malý dopad na spotřebu.
- Statek s pružnou D → nízký výnos (spotřebitelé přejdou k substitutům).
- Pro chudé domácnosti, kde $X$ tvoří velký podíl rozpočtu, je IE silný a daň regresivní (více ji pociťují).

### 15.2 Sociální dávky a rozpočtová politika

Změna důchodu $\Delta I$ přesouvá spotřebitele po ICC. Z Engelových křivek lze odhadnout, do čeho přesně poteče případné navýšení sociálních dávek: u domácností pod prahem chudoby do potravin a bydlení (nezbytné statky), u středních příjmů do volnočasových služeb (luxusní statky).

### 15.3 Marketingová segmentace

Identifikace luxusního vs. nezbytného vs. podřadného zboží (přes Engelovu křivku) určuje cílovou skupinu. Luxusní auta rostou s příjmem konvexně → cílit na vysokopříjmové segmenty. Discountní řetězce tržou na podřadných statcích → cílit na pokles příjmů, recese.

### 15.4 Analýza šoků (energie, potraviny)

Energetické krize (zdražení zemního plynu) pro nízkopříjmové domácnosti aktivují silný IE u jiných statků: musí omezit spotřebu „luxusních" položek, aby udrželi zaplatitelný plyn. Empiricky pozorovatelné jako pokles spotřeby restaurací, dovolených apod. — všechno přes Slutského rovnici.

## 16. Příklad — Cobb-Douglasovy preference

> [!example] Zadání
> $U(X,Y) = X^{0,5} Y^{0,5}$, $I = 100$, $P_Y = 1$, $P_X$ klesne z $2$ na $1$. Najdi cenový efekt a jeho rozklad podle Slutského.

### 16.1 Marshallova poptávka

Pro Cobb-Douglas $U = X^\alpha Y^{1-\alpha}$ je Marshallova poptávka:
$$X^M(I, P_X, P_Y) = \frac{\alpha I}{P_X}, \quad Y^M = \frac{(1-\alpha)I}{P_Y}.$$

Pro $\alpha = 0{,}5$, $I = 100$:
$$X^M_0 = \frac{0{,}5 \cdot 100}{2} = 25, \quad Y^M_0 = \frac{0{,}5 \cdot 100}{1} = 50.$$
Po zlevnění $P_X = 1$:
$$X^M_1 = \frac{0{,}5 \cdot 100}{1} = 50, \quad Y^M_1 = \frac{0{,}5 \cdot 100}{1} = 50.$$

**Cenový efekt:** $\Delta X^{\text{cen}} = 50 - 25 = 25$.

### 16.2 Slutského rozklad

Pomocný „Slutského" důchod $I^S$ je takový, aby si spotřebitel za nové ceny mohl koupit původní koš $(25, 50)$:
$$I^S = P_X' \cdot 25 + P_Y \cdot 50 = 1 \cdot 25 + 1 \cdot 50 = 75.$$

Slutského pomocná Marshallova poptávka při $I = 75$, $P_X = 1$:
$$X^S = \frac{0{,}5 \cdot 75}{1} = 37{,}5.$$

**Substituční efekt (Slutsky):** $\Delta X^{\text{SE,S}} = 37{,}5 - 25 = 12{,}5$.

**Důchodový efekt (Slutsky):** $\Delta X^{\text{IE,S}} = 50 - 37{,}5 = 12{,}5$.

Kontrola: $12{,}5 + 12{,}5 = 25 = \Delta X^{\text{cen}}$. Sedí.

### 16.3 Hicksův rozklad

Pro Cobb-Douglas je nepřímá užitková funkce:
$$U_0 = (X^M_0)^{0{,}5} (Y^M_0)^{0{,}5} = 25^{0{,}5} \cdot 50^{0{,}5} = \sqrt{1250} \approx 35{,}36.$$

Hicksova kompenzovaná poptávka pro Cobb-Douglas:
$$X^H = U_0 \left(\frac{(1-\alpha) P_X}{\alpha P_Y}\right)^{-(1-\alpha)} = U_0 \left(\frac{P_Y}{P_X}\right)^{0{,}5}.$$

Při $P_X = 1, P_Y = 1$:
$$X^H = 35{,}36 \cdot 1 = 35{,}36.$$

**Substituční efekt (Hicks):** $\Delta X^{\text{SE,H}} = 35{,}36 - 25 \approx 10{,}36$.

**Důchodový efekt (Hicks):** $\Delta X^{\text{IE,H}} = 50 - 35{,}36 \approx 14{,}64$.

Pozorování: $|\Delta X^{\text{SE,S}}| = 12{,}5 > |\Delta X^{\text{SE,H}}| \approx 10{,}36$ — Slutského SE je větší než Hicksův SE, jak teorie předpovídá.

### 16.4 Kontrola Slutského rovnice

Pro Cobb-Douglas:
$$\frac{\partial X^M}{\partial P_X} = -\frac{\alpha I}{P_X^2}, \quad \frac{\partial X^M}{\partial I} = \frac{\alpha}{P_X}.$$

V bodě $E_0$ ($P_X = 2$, $I = 100$):
$$\frac{\partial X^M}{\partial P_X} = -\frac{0{,}5 \cdot 100}{4} = -12{,}5, \quad X \cdot \frac{\partial X^M}{\partial I} = 25 \cdot \frac{0{,}5}{2} = 6{,}25.$$

Tedy SE musí být $\partial X^M/\partial P_X + X \cdot \partial X^M/\partial I = -12{,}5 + 6{,}25 = -6{,}25$. Pro infinitesimální změny tedy SE/$\Delta P = -6{,}25$, a IE/$\Delta P = -6{,}25$. Pro velkou změnu $\Delta P_X = -1$ aproximace dává SE $\approx 6{,}25$, IE $\approx 6{,}25$ — což je mezi Hicksovým a Slutského diskrétním rozkladem výše (jak má být — pro infinitesimální změnu se obě metody shodují).

## 17. Numerické příklady ze zkoušek

V archivu zkouškových variant najdeme řešené příklady na cenový rozklad. Konkrétně:

- **Varianta W** — klasický Slutského rozklad pro Cobb-Douglasovy preference podobné výše uvedenému.
- **Varianta H** — úloha s Giffenovým zbožím: dáno extrémně podřadné $X$ a velký podíl rozpočtu, požaduje se vyšetřit znaménko cenového efektu.

Detailní řešení viz [[mikk-vzorove-zkousky|Vzorové zkoušky]] a souhrn vzorců [[mikk-vzorce-prehled|Přehled vzorců MikK]].

## 17a. Substituty a komplementy přes SE a IE

Cenový rozklad lze rozšířit na **křížové** efekty — tj. změnu ceny statku $Y$ na poptávku po statku $X$. Klasifikace dvojic statků jako *substituty* nebo *komplementy* závisí na poměru SE a IE pro křížový efekt:

$$\frac{\partial X^M}{\partial P_Y} = \underbrace{\frac{\partial X^H}{\partial P_Y}}_{\text{SE křížový}} - \underbrace{Y \cdot \frac{\partial X^M}{\partial I}}_{\text{IE křížový}}.$$

### 17a.1 Hicksovi substituty a komplementy

Hicksovsky se dvojice $(X, Y)$ klasifikuje znaménkem *kompenzovaného* křížového efektu:
- **Hicksovi substituty:** $\partial X^H/\partial P_Y > 0$ (zdražení $Y$ → spotřebitel přechází k $X$).
- **Hicksovi komplementy:** $\partial X^H/\partial P_Y < 0$ (zdražení $Y$ → spotřeba $X$ klesá, „chodí spolu").

Tato klasifikace je *symetrická*: $\partial X^H/\partial P_Y = \partial Y^H/\partial P_X$ (Slutského symetrie, plyne z konkávní výdajové funkce).

### 17a.2 Hrubé (Marshallovy) substituty a komplementy

V tržně pozorovatelné poptávce klasifikujeme znaménkem $\partial X^M/\partial P_Y$:
- **Hrubé substituty:** $\partial X^M/\partial P_Y > 0$.
- **Hrubé komplementy:** $\partial X^M/\partial P_Y < 0$.

Tato klasifikace *není* symetrická — záleží na velikostech $Y$ a $X$ a důchodových efektech. Konkrétně:

- **Komplementy** ($X$ a $Y$ se konzumují společně, např. káva a cukr): $SE: \downarrow P_Y \to \uparrow X$ (převažující komplementarita posune k $X$), $IE: \downarrow P_Y \to \uparrow I_{\text{real}} \to \uparrow X$ (oba kladně), výsledek: $IE > SE$, hrubě komplementy.
- **Substituty** ($X$ a $Y$ se nahrazují, např. káva a čaj): $SE: \downarrow P_Y \to \downarrow X$ (přechod k $Y$), $IE: \downarrow P_Y \to \uparrow I_{\text{real}} \to \uparrow X$ (kladně), výsledek: $SE > IE$, hrubě substituty.

> [!tip] Praktický význam
> Při daňové analýze se rozhoduje: zdaníme-li $Y$, jak se to odrazí na poptávce po $X$? Pro substituty (káva–čaj) kávovna získá zákazníky, když stát zdaní čaj. Pro komplementy (auta–benzin) prodejci aut tratí, když stát zdaní benzin.

## 17b. Výdajová funkce a její derivace

**Výdajová funkce** $E(U_0, P_X, P_Y) = \min\{P_X X + P_Y Y : U(X,Y) \ge U_0\}$ je peněžní obnos potřebný k dosažení užitku $U_0$ při daných cenách. Vlastnosti:

- **rostoucí v užitku** $U_0$;
- **neklesající v cenách** (zdražení statku zvýší minimální výdaje);
- **rostoucí, pokud roste alespoň jedna cena**;
- **konkávní v cenách** — geometricky to znamená, že parciální derivace $\partial^2 E/\partial P_X^2 \le 0$, což je matematickým jádrem zákona klesající Hicksovy poptávky;
- **homogenní stupně 1 v cenách** — $E(U_0, \lambda P_X, \lambda P_Y) = \lambda E(U_0, P_X, P_Y)$.

> [!note] Shephardovo lemma
> Parciální derivace výdajové funkce podle ceny statku je Hicksova poptávka po tomto statku:
> $$\frac{\partial E(U_0, P_X, P_Y)}{\partial P_X} = X^H(U_0, P_X, P_Y).$$
> Důsledek: druhá derivace $\partial^2 E/\partial P_X^2 = \partial X^H/\partial P_X \le 0$ (z konkávity $E$ v cenách). To je formální důkaz, že **Hicksova poptávka je vždy klesající** v ceně daného statku.

### 17b.1 Vztah maximalizace užitku a minimalizace výdajů

Dvě duální úlohy:

| | Primární (max užitek) | Duální (min výdaje) |
|---|---|---|
| úloha | $\max U(X,Y)$ s.t. $P_X X + P_Y Y = I$ | $\min P_X X + P_Y Y$ s.t. $U(X,Y) = U_0$ |
| řešení | Marshallova poptávka $X^M(I, P_X, P_Y)$ | Hicksova poptávka $X^H(U_0, P_X, P_Y)$ |
| optimum | nepřímá užitková funkce $V(I, P_X, P_Y)$ | výdajová funkce $E(U_0, P_X, P_Y)$ |

**Dualita:** $V(E(U_0, P_X, P_Y), P_X, P_Y) = U_0$ a $E(V(I, P_X, P_Y), P_X, P_Y) = I$. Tj. obě funkce jsou navzájem inverzní v užitkové dimenzi.

**Substituce:** $X^M(E(U_0, P_X, P_Y), P_X, P_Y) = X^H(U_0, P_X, P_Y)$. Tj. když do Marshallovy poptávky dosadíme přesně tolik důchodu, abychom dosáhli užitku $U_0$, dostaneme Hicksovu poptávku.

Z této identity přímo plyne **Slutského rovnice** (derivace obou stran podle $P_X$).

## 17c. Rozklad pro velkou změnu ceny — pozor na cestu

Rozklad přes SE a IE jsme dosud psali pro *konečnou* změnu $\Delta P_X$. Pro infinitesimální změnu se obě metody (Hicks i Slutsky) shodují s parciálními derivacemi. Pro velkou diskrétní změnu ale rozklad závisí na *cestě*:

- **Hicks** = projekce na pomocnou IC $U_0$ (jedna a táž IC pro libovolnou velikost $\Delta P_X$);
- **Slutsky** = posun rozpočtové přímky o pevný offset (původní koš dosažitelný i v novém režimu);
- pro velké $\Delta P_X$: $|SE_S| > |SE_H|$, $|IE_S| < |IE_H|$.

Důsledek pro praxi: empirické indexy spotřebitelské inflace (CPI, Laspeyres, Paasche) jsou Slutského typu — počítají kompenzaci jako „kolik bych musel mít, abych si pořídil původní koš za nové ceny". Skutečná Hicksova kompenzace by byla menší (protože spotřebitel se může adaptovat substitucí), takže Laspeyresův index *nadhodnocuje* skutečnou inflaci. To je tzv. *substitution bias* indexů.

## 17d. Detailní příklad — Giffenův paradox krok po kroku

> [!example] Zadání
> Chudý spotřebitel má $I = 60$ Kč týdně. Spotřebovává brambory ($X$, $P_X = 4$ Kč/kg) a maso ($Y$, $P_Y = 20$ Kč/kg). Kvůli silné podřadnosti brambor a velkému podílu výdajů (spotřebovává 10 kg brambor) předpokládáme Giffenovo chování.

**Výchozí stav:** $X_0 = 10$, $Y_0 = (60 - 4 \cdot 10)/20 = 1$. Tj. 10 kg brambor a 1 kg masa za 60 Kč. Brambory tvoří $40/60 \approx 67\,\%$ výdajů.

**Šok:** $P_X$ klesne z 4 na 3 Kč/kg.

**Slutského kompenzace:** aby si stále mohl koupit původní koš, potřebuje $I^S = 3 \cdot 10 + 20 \cdot 1 = 50$ Kč. „Sebrali jsme mu" 10 Kč z 60.

**Pomocné optimum:** při $I^S = 50$ a nových cenách. Pokud je $X$ silně podřadné, spotřebitel s nižším důchodem ale levnějším X *zvýší* spotřebu brambor — řekněme na $X^S = 12$, takže $Y^S = (50 - 36)/20 = 0{,}7$.

**Slutského SE:** $\Delta X^{\text{SE}} = 12 - 10 = +2$ kg (kladný, jak má SE u poklesu ceny být).

**Vrátíme důchod:** spotřebitel má teď $I = 60$ při $P_X = 3$. Protože $X$ je silně podřadné, dodatečných 10 Kč ho odvede *od* brambor k masu: může si koupit $X_2 = 9$, $Y_2 = (60 - 27)/20 = 1{,}65$.

**Slutského IE:** $\Delta X^{\text{IE}} = 9 - 12 = -3$ kg (záporný, podřadné zboží).

**Cenový efekt:** $\Delta X^{\text{cen}} = 9 - 10 = -1$ kg.

Kontrola: $SE + IE = 2 + (-3) = -1 = \Delta X^{\text{cen}}$. Sedí.

Cena brambor klesla, ale spotřeba brambor *taky* klesla — protože uvolněné peníze stačily na víc masa. To je Giffen.

> [!warning] Klíčové podmínky
> 1. $X$ je *silně* podřadné — IE je velký a záporný.
> 2. $X$ tvoří velký podíl rozpočtu — pokles $P_X$ uvolní hodně reálné kupní síly.
> 3. SE je malý — spotřebitel nemá blízké substituty pro $X$.

## 17e. Detailní příklad — konstrukce PCC, ICC, Engelovy křivky

> [!example] Zadání
> Cobb-Douglas $U = X^{1/3} Y^{2/3}$, $P_Y = 1$. Sestrojíme PCC, ICC a Engelovu křivku.

### Marshallova poptávka

$$X^M = \frac{(1/3) I}{P_X}, \quad Y^M = \frac{(2/3) I}{P_Y} = \frac{2I}{3}.$$

### PCC — měníme $P_X$, fixujeme $I = 60$

Pro různé $P_X \in \{1, 2, 3, 6\}$:

| $P_X$ | $X$ | $Y$ |
|---|---|---|
| 1 | 20 | 40 |
| 2 | 10 | 40 |
| 3 | 6{,}67 | 40 |
| 6 | 3{,}33 | 40 |

**Pozorování:** $Y$ je konstantní (= $2I/3 = 40$). PCC je v rovině $(X, Y)$ vodorovná přímka $Y = 40$. Důvod: pro Cobb-Douglas je *jednotková* cenová elasticita poptávky po $X$, takže výdaje na $X$ jsou konstantní $(1/3) I = 20$, a výdaje na $Y$ jsou doplňkem.

**Marshallova poptávka po $X$** (projekce do $(X, P_X)$): $X = 20/P_X$ — klasická hyperbola.

### ICC — měníme $I$, fixujeme $P_X = 2, P_Y = 1$

| $I$ | $X$ | $Y$ |
|---|---|---|
| 30 | 5 | 20 |
| 60 | 10 | 40 |
| 90 | 15 | 60 |
| 120 | 20 | 80 |

**Pozorování:** ICC je přímka procházející počátkem se sklonem $Y/X = 4$ (přesně $Y/X = (2/3)/((1/3)/P_X) \cdot P_X/P_Y = 2 P_X / P_Y = 4$). Pro Cobb-Douglas je ICC vždy lineární s konstantním sklonem — to je důsledek **homotetičnosti** preferencí.

### Engelova křivka pro $X$

Z $X^M = I/(3 P_X) = I/6$ při $P_X = 2$:

| $I$ | $X$ |
|---|---|
| 0 | 0 |
| 60 | 10 |
| 120 | 20 |

**Pozorování:** Engelova křivka je přímka $X = I/6$, lineární a rostoucí. Důchodová elasticita $E_X^I = 1$ — Cobb-Douglasovy preference popisují *zboží s jednotkovou důchodovou elasticitou*. Žádný luxus, žádné nezbytné, žádné podřadné — zlatá střední cesta. To je důvod, proč Cobb-Douglas slouží jen jako didaktický základ; reálná data vyžadují bohatší užitkové funkce (Stone-Geary, CES, kvázi-lineární).

## 17f. Historický kontext

> [!note] Historie konceptu
> Rozklad cenového efektu vznikal postupně mezi koncem 19. a polovinou 20. století:
> - **Eugen Slutsky (1915)** — italský článek „Sulla teoria del bilancio del consumatore" v *Giornale degli Economisti*. Slutsky odvodil základní rovnici i koncept zachování koše. Práce zůstala dlouho neznámá, protože vyšla v italštině v době první světové války.
> - **John R. Hicks a R. G. D. Allen (1934)** — *Economica*, „A Reconsideration of the Theory of Value". Hicks a Allen nezávisle objevili obdobu Slutského rozkladu, ale s pojetím zachovaného užitku místo zachovaného koše. Hicksův přístup se stal dominantním v anglosaské mikroekonomii.
> - **Robert Giffen** (paradox pojmenován po něm) — anglický statistik, popisoval anomální chování poptávky po chlebu chudých dělníků v 19. století. Sám o sobě paradox nikdy formálně nepojmenoval; přiřazení udělal Alfred Marshall ve své *Principles of Economics* (1895).
> - **Paul A. Samuelson (1947)** — *Foundations of Economic Analysis*. Sjednotil Slutského a Hicksův přístup pod „theory of revealed preference" a ukázal, že obě dekompozice se shodují v limitě infinitesimálních změn.
> - **Jensen & Miller (2008)** — *American Economic Review*, „Giffen Behavior and Subsistence Consumption". První moderní empirický důkaz Giffenova chování (rýže ve venkovských oblastech Číny).

## 17g. Limitní případy a rohové řešení

### Perfektní substituty

Pokud $U(X, Y) = aX + bY$ (lineární užitek, perfektní substituty), spotřebitel nakupuje *jen jeden* statek — ten s vyšším poměrem $MU/P$:
- Pokud $a/P_X > b/P_Y$: $X = I/P_X$, $Y = 0$.
- Pokud $a/P_X < b/P_Y$: $X = 0$, $Y = I/P_Y$.

V tomto případě **substituční efekt skokově dominuje**: malé zlevnění $X$ (přesné překročení prahu) přepne celou spotřebu z $Y$ na $X$. IE je definován jen v rohu a má interpretaci „dopad na spotřebu kvantitativní veličiny, kterou už nakupujeme".

### Perfektní komplementy

$U(X, Y) = \min(aX, bY)$ — Leontiefův užitek. Spotřebitel kupuje vždy v poměru $X:Y = b:a$, takže $aX = bY$. Důsledek: **substituční efekt je nulový** (žádná substituce při změně relativních cen — proporcionální nákup je dán technologií, ne preferencemi). Veškerý cenový efekt je důchodový. Slutského rovnice degeneruje na $\partial X^M/\partial P_X = -X \cdot \partial X^M/\partial I$.

### Kvázi-lineární užitek

$U(X, Y) = v(X) + Y$. Marshallova poptávka po $X$ nezávisí na důchodu (pokud není rohová): $v'(X) = P_X/P_Y$. Důsledek: **důchodový efekt na $X$ je nulový** (kromě extrémně nízkých důchodů). Veškerý cenový efekt je substituční. Slutského rovnice se zjednoduší: $\partial X^M/\partial P_X = \partial X^H/\partial P_X$. Tato vlastnost je důvod, proč se kvázi-lineární užitek používá v *teorii průmyslových organizací* a *welfare ekonomii* — vyhneme se komplikacím s důchodovými efekty.

## 17h. SE a IE pro spotřebitele s pracovní nabídkou

Cenový rozklad se *přirozeně* přenáší na pracovní nabídku, kde je „cenou" mzda $w$ a „statkem" volný čas $L$. Spotřebitel volí mezi spotřebou $C$ a volným časem $L$ při omezení $C = w(T - L) + V$ (kde $T$ je dispozice času, $V$ jsou nepracovní příjmy).

Růst mzdy $w$ rozkládáme:
- **SE**: volný čas zdražil → spotřebitel snižuje volný čas (víc pracuje). Vždy $-$ k volnému času, $+$ k práci.
- **IE**: vzrostl reálný důchod (volný čas je obvykle normální statek) → spotřebitel chce *víc* volného času, méně pracovat.

Pro nízké mzdy SE > IE → křivka nabídky práce roste. Pro vysoké mzdy IE > SE → křivka „ohýbá zpět" (backward-bending labor supply). Tento jev je další verze Giffena, jen pro pracovní nabídku, a detailněji se s ním pracuje v rámci modelů spotřebitele s časovou volbou.

## 17i. SE a IE v intertemporální volbě

Stejný rozklad funguje pro volbu mezi *současnou* a *budoucí* spotřebou ($C_1, C_2$) při úrokové míře $r$. Růst $r$:
- **SE**: budoucí spotřeba je „levnější" (vysoká cena současné) → spotřebitel přesouvá do $C_2$ (víc šetří).
- **IE pro střadatele**: vyšší výnos z úspor → bohatší → chce víc obojího → IE proti SE u $C_2$, ve směru SE u $C_1$ (pokud je střadatel).
- **IE pro dlužníka**: vyšší úroky → chudší → chce méně obojího.

Tento rozklad je jádrem moderní teorie *consumption smoothing* a *Eulerovy rovnice* v makroekonomii.

## 18. Souvislosti a další čtení

- **Předchozí téma:** [[mikk-utility-preference|Užitek a preference]] (axiomy, IC, MRS) → [[mikk-rovnovaha-spotrebitele|Rovnováha spotřebitele]] (tečnost MRS = $P_X/P_Y$).
- **Návazné téma:** [[mikk-marshall-hicks-poptavka|Marshallova vs. Hicksova poptávka]] — formálně rozvíjí Slutského rovnici, dualitu, Shephardovo lemma.
- **Aplikace:** [[mikk-elasticita-poptavky|Elasticity poptávky]] — sklon PCC vs. cenová elasticita; Engelova křivka vs. důchodová elasticita.
- **Tržní agregace:** [[mikk-trzni-rovnovaha-dynamika|Tržní rovnováha a dynamika]] — agregace individuálních poptávek na tržní křivku, Engelovy křivky pro celou populaci.
- **Křížový kontext:** [[poptavka-nabidka|Poptávka/nabídka (ImeK)]] — matematicko-ekonomické zachycení v ImeK.
- **Hub kurzu:** [[mikk|Mikroekonomie 2]].

## 19. Časté chyby a varování

> [!warning] Časté chyby ve zkoušce
> 1. **Záměna SE a IE pro podřadné zboží.** SE je *vždy* záporný (proti směru ceny). IE u podřadného zboží působí *po* směru ceny. Ne naopak.
> 2. **„Giffen = luxus."** *Ne!* Giffen je *podřadný* statek se silným IE. Luxus má naopak vysokou *kladnou* důchodovou elasticitu, žádný paradox to není.
> 3. **Pomocná Slutského přímka prochází *novým* bodem.** Ne. Prochází *původním* bodem $E_0$, ale má *nový* sklon.
> 4. **Hicksova rozpočtová přímka má *původní* sklon.** Ne. Má *nový* sklon (jako $L'$), ale je posunutá tak, aby byla tečnou původní IC.
> 5. **PCC = poptávková křivka.** PCC žije v rovině $(X, Y)$, poptávková křivka v rovině $(X, P_X)$. Poptávková křivka se *odvozuje* z PCC, ale není to totéž.
> 6. **„Engelova křivka klesá → podřadné zboží."** Pouze v té části, kde klesá. Statek může být v nízkých příjmech normální a v středních se stát podřadným (zlomená Engelova křivka).
> 7. **Slutského rovnice — znaménko druhého členu.** $-X \cdot \partial X^M/\partial I$. Mínus před výrazem často účastníci zapomínají, vyjde jim opačné znaménko.

> [!note] Konvence
> V této stránce držíme: SE i IE jsou *změny množství $X$*, ne změny ceny. „Záporný SE" znamená, že *směr* změny $X$ je opačný ke směru změny $P_X$. Jiné učebnice někdy parametrizují SE jako derivaci a píší $\partial X^H/\partial P_X \le 0$ — což je totéž tvrzení.

---

## Shrnutí klíčových identit

$$\boxed{\;\Delta X^{\text{cen}} = \Delta X^{\text{SE}} + \Delta X^{\text{IE}}\;}$$

$$\boxed{\;\frac{\partial X^M}{\partial P_X} = \frac{\partial X^H}{\partial P_X} - X \cdot \frac{\partial X^M}{\partial I}\;}$$

$$\boxed{\;\frac{\partial X^H}{\partial P_X} \le 0 \quad \text{(SE vždy nekladný)}\;}$$

$$\boxed{\;\text{Giffen} \iff \frac{\partial X^M}{\partial P_X} > 0 \iff X \cdot \left|\frac{\partial X^M}{\partial I}\right| > \left|\frac{\partial X^H}{\partial P_X}\right| \text{ a } X \text{ podřadné}\;}$$

PCC: trajektorie optim při $\Delta P_X$, ceny $P_Y$ a důchod $I$ konstantní → individuální poptávka.

ICC: trajektorie optim při $\Delta I$, ceny $P_X, P_Y$ konstantní → Engelova křivka.

Engel: $X^*(I)$ při fixních cenách → klasifikace luxus / nezbytné / podřadné podle sklonu.
