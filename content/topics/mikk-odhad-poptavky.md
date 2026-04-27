---
title: "Odhad a predikce poptávky"
course: mikk
type: topic
tags: [mikk, mikroekonomie, odhad-poptavky, delphi, dekompozice]
sources: [raw/mikk/Prednaska 1. a 2. blok.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Odhad a predikce poptávky

## TL;DR

Odhad poptávky a predikce poptávky jsou dvě **různé úlohy**: odhad kvantifikuje
**existující** poptávkovou funkci na základě historických dat (typicky regresní
analýzou), zatímco predikce extrapoluje **budoucí** poptávku s využitím
trendových a sezónních složek. Tržní potenciál $MP = P \cdot Q$ je jejich
přirozeným důsledkem a je **maximální tam, kde je cenová elasticita poptávky
rovna jedné** — viz [[mikk-elasticita-poptavky|cenová elasticita]].

Ekonometrický postup pracuje s vícefaktorovou poptávkovou funkcí
$Q_d = f(P_o, P_c, P_s, Y_d, T, A_o, A_c, A_s, I, C, E)$ ve třech standardních
funkčních formách: **lineární**, **exponenciální** (multiplikativní)
a **logaritmická**. V exponenciální a logaritmické formě jsou odhadované
parametry rovnou interpretovatelné jako elasticity, což je jejich praktická
přednost.

Pro predikci se nejčastěji používá **dekompozice časové řady**
$X_t = T_t + S_t + I_t$ (trend + sezóna + náhodná složka). Doplňkové metody
zahrnují **Delphi** (iterativní anonymní expertní dotazování), **market
testing** (Sales Wave, Simulated Store, Test Marketing) a **Sales Force
Opinion**. Volba metody závisí na typu produktu, dostupnosti dat a charakteru
trhu.

> [!note] Distinkce odhad vs. predikce
> - **Odhad (estimation)** odpovídá na otázku „**jaká poptávka je**?" —
>   kvantifikuje parametry stávající poptávkové funkce.
> - **Predikce (forecasting)** odpovídá na otázku „**jaká poptávka bude**?"
>   — extrapoluje budoucí hodnoty.
>
> Tyto úlohy mají **odlišné metody**, **odlišné předpoklady** i **odlišné
> zdroje chyb**, a je nutné je v praxi rozlišovat.

## 1. Tržní potenciál

### Kotlerova definice

Tržní potenciál ($MP$, *market potential*) je dle Kotlera (s. 261)
**maximální objem prodeje** — měřený ve fyzických nebo peněžních jednotkách —
který může být dosažen na určitém trhu v určitém čase, při dané úrovni
marketingového úsilí a při daných podmínkách prostředí.

Klíčová formální vazba: tržní potenciál je funkcí poptávky, která je sama
funkcí ceny:

$$MP = f(D) = f(D(P)) = P \cdot Q$$

Tržní potenciál tedy **závisí na ceně** a v důsledku se mění spolu s tím,
jak se firma pohybuje po poptávkové křivce.

### Maximalizace tržního potenciálu

Vzhledem k tomu, že $MP = P \cdot Q$ a poptávka má klesající průběh, existuje
**vnitřní optimum**: snížení ceny zvyšuje prodané množství, ale snižuje
jednotkovou tržbu, a naopak. Maximum nastává tam, kde se obě tendence
vyrovnají — tedy kde:

$$E_D = 1$$

Tato podmínka odráží známý vztah z teorie celkových tržeb:

- $E_D > 1$ (pružná poptávka) — pokles ceny zvyšuje $TR = P \cdot Q$.
- $E_D < 1$ (nepružná poptávka) — růst ceny zvyšuje $TR$.
- $E_D = 1$ (jednotková elasticita) — $TR$ je v lokálním maximu.

> [!tip] Praktický důsledek
> Firma odhadující tržní potenciál **musí znát elasticitu** (alespoň
> v okolí současné ceny). Bez ní nelze rozhodnout, zda zvyšovat nebo
> snižovat cenu. Detail v [[mikk-elasticita-poptavky|cenové elasticitě
> poptávky]].

### Vyjádření MP

MP se v praxi vyjadřuje:

- **Ve fyzických jednotkách** — kolik kusů (litrů, kWh) maximálně lze prodat.
- **V peněžních jednotkách** — celkové tržby, $P \cdot Q$.

Obě podoby jsou ekvivalentní pouze v daném bodě poptávkové křivky;
maximum peněžního MP nemusí ležet v bodě maxima fyzického MP.

## 2. Empirické průzkumy poptávky

### Demonstrace — jogurty výrobců A, B, C

Reálný marketingový průzkum tří výrobců mléčných výrobků (Bílek 2001, FP VUT
Brno, cca 200 respondentů) na poptávku po bílém jogurtu při různých cenách:

| Cena (Kč) | 9{,}75 | 10{,}25 | 10{,}75 | 11{,}25 | 11{,}75 | 12{,}25 | 12{,}75 | 13{,}25 | 13{,}75 |
|---|---|---|---|---|---|---|---|---|---|
| Množství (ks) | 175 | 185 | 195 | 190 | 175 | 140 | 130 | 100 | 95 |
| Bodová elasticita | — | $-1{,}1$ | $-1{,}1$ | $0{,}6$ | $1{,}9$ | $5{,}3$ | $1{,}9$ | $6{,}8$ | $1{,}4$ |

Pozorování:

- V dolním pásmu cen (9{,}75–10{,}75 Kč) je poptávka **anomální**:
  s rostoucí cenou roste i poptávané množství. Záporná „elasticita" znamená,
  že průzkum zachytil oblast, kde se uplatňuje [[mikk-utility-preference|jiný
  motiv]] než cena (kvalita, vnímané postavení produktu).
- Od 11{,}75 Kč výše roste elasticita strmě — typický **vysoce pružný
  segment**.
- V krajním bodě (13{,}25 Kč) je elasticita $E_D = 6{,}8$ — pokles prodejů
  na 100 ks dokládá výrazný odliv zákazníků k substitutu.

> [!warning] Limit dotazníkového průzkumu
> Respondent uvádí, **kolik by koupil** — ale skutečnou volbu provede až
> v obchodě. Sklon k nadhodnocení (deklarace ≠ realizace) je častý zdroj
> systematické chyby empirických průzkumů.

## 3. Anomálie poptávkové křivky

Reálná poptávková křivka se ne vždy chová jako ideální klesající funkce.
Tři důležité anomální případy:

### Vertikální poptávka

- $E_D = 0$ — poptávané množství se s cenou prakticky nemění.
- Typické statky: **bydlení**, **sůl**, **léky bez náhrady**.
- Tabulkové hodnoty (Gwartney et al. 2005): $E_D \approx 0{,}1$ pro sůl,
  $0{,}01$ pro bydlení v krátkém období.

### Horizontální poptávka

- $E_D = \infty$ — sebemenší zvýšení ceny vede k nulovému prodeji.
- Vzniká na **dokonale konkurenčním trhu** s perfektními substituty:
  jakmile firma nasadí cenu nad tržní rovnováhu, zákazníci přejdou
  k substitutu.

### Protnutí osy X

Otázka „**může poptávka protnout osu X**?" — tj. existuje konečná cena,
při které je poptávané množství nulové i pro spotřebitele s libovolně
vysokým rozpočtem? Ano:

- Pro většinu nepostradatelných statků **ne** — poptávka asymptoticky
  klesá k nule.
- Pro substituovatelné statky **ano** — existuje **rezervační cena**,
  nad níž žádný spotřebitel statek nekoupí (přejde k substitutu).

## 4. Strategie firmy a pružnost nabídky

Pružnost nabídky firmy je úzce svázaná s její **strategií**:

| Strategie | Pružnost nabídky | Důvod |
|---|---|---|
| Cost Leadership | nízká | optimalizace na úzkou produktovou škálu, vysoké fixní náklady, low-cost technologie |
| Diferenciace | střední | příležitost reagovat na premium segmenty |
| Flexibilita / Niche | vysoká | nevyužité kapacity, modulární výroba, snadno dostupné zdroje |

Vysoká pružnost nabídky je dosažitelná pokud:

- Jsou snadno dostupné výrobní zdroje a distribuční kanály.
- Firma má **nevyužité kapacity**.
- Zboží lze vyrábět **na sklad**.
- **Fixní náklady** nejsou vysoké.

> [!info] Trade-off
> Pružnost je užitečná v období růstu poptávky, ale **drahá** v období
> stagnace (nevyužité kapacity = sunk cost). Strategie Cost Leadership
> proto pružnost obvykle obětuje ve prospěch nákladové efektivity.

## 5. Ekonometrické metody — obecná forma

### Vícefaktorová poptávková funkce

Obecný tvar jakékoliv poptávkové funkce zahrnuje **jedenáct typických
faktorů**:

$$Q_d = f(P_o, P_c, P_s, Y_d, T, A_o, A_c, A_s, I, C, E)$$

| Symbol | Význam |
|---|---|
| $P_o$ | vlastní cena (own price) |
| $P_c$ | cena komplementu |
| $P_s$ | cena substitutu |
| $Y_d$ | disponibilní příjem (disposable income) |
| $T$ | preference / vkus (taste) |
| $A_o$ | reklama vlastní (own advertising) |
| $A_c$ | reklama komplementu |
| $A_s$ | reklama substitutu |
| $I$ | imageové faktory |
| $C$ | klima / sezónní podmínky |
| $E$ | očekávání (expectations) |

V praxi se modeluje obvykle **podmnožina** — nelze odhadovat efekt všech
faktorů z omezeného vzorku dat (princip parsimony).

### Tři standardní funkční formy

**Lineární forma** — nejjednodušší, koeficienty jsou marginální dopady:

$$Q_d = a + b_1 P_o + b_2 P_c + b_3 P_s + b_4 Y_d + b_5 T + \ldots$$

**Exponenciální forma** (multiplikativní, log-log model) — koeficienty jsou
**přímo elasticity**:

$$Q_d = P_o^{a} \cdot P_c^{b} \cdot P_s^{c} \cdot Y_d^{d} \cdot T^{e} \cdot A_o^{f} \cdot A_c^{g} \cdot A_s^{h} \cdot I^{i} \cdot C^{j} \cdot E^{k}$$

**Logaritmická forma** — linearizovaná verze exponenciální, přímo
odhadovatelná OLS regresí:

$$\log Q_d = a \log P_o + b \log P_c + c \log P_s + d \log Y_d + e \log T + \ldots$$

> [!tip] Volba formy
> Pro praktickou interpretaci je **logaritmická forma** nejvýhodnější:
> každý koeficient je elasticita příslušného faktoru. To výrazně
> usnadňuje srovnání s tabulkovými hodnotami (Baye, Gwartney) a vstupy
> do strategického rozhodování.

### Ekonometrický postup

![[mikk-regrese-odhad-poptavky.jpeg|OLS odhad poptávkové funkce — bodový diagram s regresní přímkou P̂ = a − b·Q, reziduály a 95 % interval spolehlivosti]]

1. **Sběr dat** — historické dvojice $(P_t, Q_t)$ a hodnoty ostatních
   regresorů.
2. **Volba funkce** — na základě teorie a tvaru bodového grafu.
3. **Odhad parametrů** — typicky OLS (ordinary least squares).
4. **Diagnostika** — koeficient determinace $R^2$, $t$-testy, F-test,
   reziduální analýza.
5. **Interpretace** — elasticity, marginální dopady, význam dummy
   proměnných.

## 6. Příklad — poptávka po zemním plynu Hong-Kong

### Specifikace modelu

Klasický příklad ekonometrického odhadu poptávkové funkce:

$$\text{QUANTITY} = b_0 + b_1 \cdot \text{PRICE} + b_2 \cdot \text{INCOME} + b_3 \cdot \text{LPGPRICE} + b_4 \cdot \text{CLPPRICE} + b_5 \cdot \text{DUMMY}$$

| Proměnná | Význam |
|---|---|
| PRICE | cena zemního plynu (TownGas) |
| INCOME | hrubý domácí důchod |
| LPGPRICE | cena LPG (substitut — propan-butan) |
| CLPPRICE | cena elektřiny (substitut) |
| DUMMY | $0$ před 1982, $1$ po 1982 (efekt bezpečnostní zprávy z roku 1981) |

### Výsledky

| Parametr | Odhad | Význam |
|---|---|---|
| PRICE | $-0{,}263$ | vlastní cenová elasticita (málo pružná poptávka) |
| INCOME | $+1{,}531^{**}$ | důchodová elasticita — luxusní statek |
| LPGPRICE | $+0{,}059$ | substituční vazba na LPG, slabá |
| CLPPRICE | $-0{,}053$ | nezamítnutá komplementarita s elektřinou (slabě záporná) |
| DUMMY | $+0{,}363^{**}$ | bezpečnostní zpráva zvýšila poptávku |

$R^2 = 0{,}993$ — model vysvětluje 99{,}3 % variability poptávaného množství.

> [!note] Interpretace dummy proměnné
> Po 1981 (Safety report) se v Hong-Kongu zvýšila důvěra v zemní plyn
> jako bezpečnou domácí energii. Skoková změna vnímání je v modelu
> zachycena jako konstantní posun křivky o $+0{,}363$ — typický
> use-case dummy proměnné pro **regulační šok**.

## 7. Statistické problémy ekonometrické aplikace

### Multikolinearita

- **Definice:** vstupní proměnné jsou silně vzájemně korelovány.
- **Důsledek:** parametry jsou nestabilní — malá změna dat vyvolá velkou
  změnu odhadu. Jednotlivé $t$-testy mohou nevyjít jako významné, přestože
  model jako celek (F-test) vychází významně.
- **Příklad:** v Hong-Kong modelu jsou LPGPRICE a CLPPRICE typicky
  korelované — obě sledují inflaci energií.
- **Řešení:** redukce proměnných, ridge regression, principal components.

### Heteroskedasticita

- **Definice:** rozptyl reziduí $\sigma^2_t$ se mění v čase / napříč
  pozorováními.
- **Důsledek:** OLS odhady zůstávají nestranné, ale **neefektivní** —
  standardní chyby jsou nesprávně odhadnuty, $t$-testy jsou nespolehlivé.
- **Řešení:** WLS (weighted least squares), robustní standardní chyby
  (White / HC).

### Autokorelace

- **Definice:** sousední rezidua jsou korelovaná, $\text{cov}(\varepsilon_t,
  \varepsilon_{t-1}) \neq 0$.
- **Časté u časových řad** — pokud nezahrneme všechny dynamické faktory,
  jejich efekt se „propisuje" do reziduí.
- **Detekce:** Durbin-Watson statistika.
- **Řešení:** lag operátory, ARIMA modely, Cochrane-Orcutt.

> [!warning] „Nelze modelovat vše!"
> Klíčová zásada: **každý další regresor zatíží model**. Princip
> parsimony žádá najít nejmenší množinu proměnných, která zachytí
> systematickou variabilitu. Nadměrná specifikace vede k overfittingu
> a multikolinearitě.

### Problém identifikace

Z pozorování trhu známe pouze **rovnovážné body** — průsečíky poptávky
a nabídky. Bez doplňkových informací nelze oddělit, zda pohyb je důsledkem
posunu poptávky $D$, nebo posunu nabídky $S$.

> "**THIS IS WHAT WE THINK WE SEE**" — pozorovaná data jsou rovnováhy
> $(P^*, Q^*)$, nikoliv samotná poptávková křivka.

Řešení: **instrumentální proměnné** — proměnná korelovaná s nabídkou,
ale nezávislá na poptávce, umožňuje izolovat poptávkový efekt.

## 8. Známé hodnoty elasticit (Baye et al. 1992)

Tabulka empiricky odhadnutých elasticit (USA, 1992):

| Produktová kategorie | Vlastní cenová $E_D$ | Reklamní $E_A$ | Důchodová $E_I$ |
|---|---|---|---|
| Transport | $-0{,}559$ | $-0{,}027$ | $1{,}787$ |
| Food | $-0{,}672$ | $-0{,}016$ | $0{,}843$ |
| Alcohol & Tobacco | $-0{,}261$ | $-0{,}051$ | $1{,}220$ |
| Recreation | $-1{,}094$ | $0{,}078$ | $1{,}067$ |
| Clothing | $-0{,}889$ | $0{,}013$ | $1{,}024$ |
| Household & Personal Care | $-0{,}629$ | $-0{,}023$ | $0{,}086$ |

Interpretace:

- **Transport, Food, Alcohol** — nepružná poptávka (|$E_D$| < 1) —
  zvýšení ceny zvyšuje tržby.
- **Recreation, Clothing** — pružná poptávka — citlivost spotřebitele
  na cenu, riziko poklesu tržeb při zdražení.
- **Recreation** je jedinou kategorií s pozitivní reklamní elasticitou
  vyšší než marginální — reklama zde přináší přidanou hodnotu.
- **Transport a Recreation** jsou typické luxusní kategorie ($E_I > 1$):
  s růstem příjmů domácností rostou výdaje na ně rychleji než příjem.

> [!info] Použitelnost odhadu elasticit
> Pro široké marketingové využití se obecné elasticity nehodí — čím
> přesněji je definován trh a produkt, tím přesnější odhad. Hlavní
> aplikace tabulkových hodnot:
> - **Daňová ekonomika** — Ramseyho pravidlo zdanění: zdaňuj nepružná
>   zboží.
> - **Veřejné finance** — odhad výnosu spotřební daně, viz
>   [[zdaneni-trhu|zdanění trhu]].
> - **Marketing** — citlivost na cenu, vliv substitutů a komplementů.

## 9. Predikce — extrapolace a dekompozice

### Nejjednodušší metoda — extrapolace trendu

Předpokládáme, že trend posledních období bude pokračovat. Vyhladíme křivku
prodejů (lineárně, exponenciálně) a prodloužíme za poslední pozorování.

**Předpoklad:** stabilní prostředí, žádné strukturální změny.

**Riziko:** v období krize / inflace / regulace dává systematicky špatné
předpovědi.

### Dekompozice časové řady

Aditivní model dekompozice:

$$X_t = T_t + S_t + I_t$$

| Komponenta | Význam |
|---|---|
| $X_t$ | pozorovaná hodnota prodejů v čase $t$ |
| $T_t$ | trendová složka — dlouhodobý směr (regresní funkce) |
| $S_t$ | sezónní složka — pravidelné periodické výkyvy |
| $I_t$ | nepravidelná (irreguární) složka — náhodný šum |

V multiplikativním tvaru: $X_t = T_t \cdot S_t \cdot I_t$ (vhodnější pro
data s rostoucí amplitudou výkyvů).

### Postup dekompozice

1. **Odhad trendu $T_t$.** Regresní analýza s časem na ose $x$ a prodeji
   jako závislá proměnná. Volba funkce:
   - **Lineární** $T_t = \alpha + \beta t$ — pro stabilní růst.
   - **Exponenciální** $T_t = \alpha e^{\beta t}$ — pro fáze růstu
     v životním cyklu výrobku.
   - **Logistická** — pro saturaci trhu.
2. **Výpočet $T_t$ pro každé období** (interpolace + extrapolace).
3. **Reziduum:** pro každé $t$ spočítej:
   $$X_t - T_t = S_t + I_t$$
   tj. odchylku pozorování od trendu.
4. **Determinace sezónnosti.** Klasifikuj rezidua podle období (roční
   čtvrtletí, školní rok, daňové období atd.).
5. **Průměrování.** Pro každé „období" spočítej průměr reziduí — to je
   odhad sezónní složky $\hat{S}$ pro dané období. Náhodná složka $I_t$
   se v průměrování vykrátí.
6. **Predikce.** Pro budoucí čas $t^*$:
   $$\hat{X}_{t^*} = T_{t^*} + \hat{S}_{\text{period}(t^*)}$$

### Příklad — výkup mléka 2009–2010

| Období | Q (mil. l) | P (Kč/l) |
|---|---|---|
| I/2009 | 568 836 | 6{,}82 |
| II/2009 | 599 998 | 6{,}24 |
| III/2009 | 579 263 | 6{,}07 |
| IV/2009 | 543 573 | 6{,}32 |
| I/2010 | 552 691 | 6{,}92 |

Z dat lze odhadnout:

- **Lineární trend ceny:** $P_t = -7 \cdot 10^{-6} \cdot Q + 10{,}733$,
  $R^2 = 0{,}198$ — slabý (cena nezáleží primárně na množství v jednom
  roce).
- **Polynomický trend $3.$ stupně:** $R^2 = 0{,}9549$ — výrazně lepší,
  ale **přefitovaný** (5 bodů, 4 parametry — přesnost je iluzorní).

> [!warning] Přefitování
> Vysoké $R^2$ pro polynom vyššího stupně neznamená dobrou predikci —
> typický příklad **overfittingu**. Pro predikci je vhodnější jednoduchý
> trend s vyšší robustností.

### Slabé stránky dekompozice

- **Předpoklad:** hlavním faktorem ovlivňujícím poptávku je **čas** —
  vše ostatní zanedbatelné. To je v praxi často **silně nereálný
  předpoklad**.
- **Krize / nestabilita:** model se rozpadá právě tam, kde je predikce
  nejdůležitější.
- **Sofistikovanější metody** (ARIMA, GARCH, state-space modely)
  poskytují jen marginálně lepší přesnost — **nákladově neefektivní**
  pro běžnou praxi.

> [!info] Praktická volba
> Pro plánování prodejů spotřebního zboží s ročním cyklem je dekompozice
> obvykle **dostatečně přesná a velmi levná** — proto v praxi dominuje.
> ARIMA má smysl tam, kde **přesnost přímo ovlivňuje rozhodnutí**
> (zásobování supermarketu, plánování energetiky).

## 10. Evaluace predikce — 6 kritérií

| Kritérium | Otázka |
|---|---|
| **Objektivita** | Pokud změníme data či osobu provádějící predikci, jsou výsledky stejné? |
| **Validita** | Jak moc se predikované hodnoty odlišují od skutečných? Zachycuje předpověď všechny známé parametry? |
| **Spolehlivost** | Vezmeme-li rozdílné výchozí body, zůstávají výsledky přibližně stejné? |
| **Přesnost** | Jak blízké jsou prognózy skutečným číslům za známá období? Jsou odchylky přijatelné? |
| **Důvěra** | Existuje vysoká pravděpodobnost, že výsledky lze reálně využít? |
| **Citlivost** | Pokud použijeme metodu pro různé typy dat, jak moc se změní výsledky? |

Tato kritéria jsou **vzájemně závislá** — vysoká objektivita + spolehlivost
posiluje důvěru, ale může jít na úkor citlivosti (model je „příliš
konzervativní").

## 11. Měření přesnosti predikce

Definujme chybu predikce $e_t = X_t - \hat{X}_t$.

### Průměrná chyba (Mean Error, ME)

$$\text{ME} = \frac{1}{n} \sum_{t=1}^{n} e_t$$

> [!warning] Pozor na střídání znamének
> Kladné a záporné chyby se v součtu **vykrátí**. Predikce systematicky
> chybující o $+10$ a $-10$ jednotek získá ME = 0 — jakoby byla bezchybná!
> ME měří **bias**, ne přesnost.

### Průměrná absolutní chyba (Mean Absolute Error, MAE)

$$\text{MAE} = \frac{1}{n} \sum_{t=1}^{n} |e_t|$$

Robustní k znaménku, ale nezvýrazňuje velké chyby.

### Průměrná kvadratická chyba (Mean Squared Error, MSE)

$$\text{MSE} = \frac{1}{n} \sum_{t=1}^{n} e_t^2$$

**Větší váha velkých chyb** — preferovaná tam, kde jednotlivé velké
chyby mají závažné důsledky (zásobování, kapacitní plánování).

### Směrodatná odchylka (Root Mean Squared Error, RMSE)

$$\text{RMSE} = \sqrt{\text{MSE}} = \sqrt{\frac{1}{n} \sum_{t=1}^{n} e_t^2}$$

Hodnota je **ve stejných jednotkách jako data** (kusy, Kč) — nejvýhodnější
pro reportování.

| Metrika | Bias? | Velké chyby | Jednotky |
|---|---|---|---|
| ME | ano | nezvýraznění | data |
| MAE | ne | nezvýraznění | data |
| MSE | ne | zvýraznění | data² |
| RMSE | ne | zvýraznění | data |

## 12. Ostatní metody predikce

### Barometric forecasting (vedoucí indikátory)

Poptávka je přímo ovlivněna **známým parametrem**, který lze pozorovat
nebo přesně vypočítat **dříve**:

| Vedoucí indikátor | Predikovaná poptávka |
|---|---|
| Mezinárodní telefonní hovory | Objem mezinárodního obchodu |
| Počet narozených dětí | Poptávka po dětském oblečení, jeslích, školkách |
| Příjmy státního rozpočtu | Investice do infrastruktury |
| Počet nově registrovaných firem | Poptávka po komerčních prostorech |

Výhodné, pokud vedoucí indikátor předbíhá poptávku **o známý lag**.

### Průzkumy trhu

Použitelné, pokud:

- **Náklady na identifikaci zákazníka jsou přijatelné**.
- **Zákazníci poskytují reálné informace** a chtějí je poskytovat.
- **Zákazníci realizují své záměry** — nejde jen o sny.

Nejlepší použitelnost:

- Produkty, kde **se nákup plánuje dopředu** (auto, dovolená, byt).
- Produkty s **malou a přesně definovanou skupinou zákazníků** (B2B
  speciální stroje).
- **Úplně nový produkt**, kde nejsou data z minulosti.

> [!example] Dotazník pro identifikaci poptávky po banánech
> | Cena (Kč/kg) | Kolik byste koupil(a)? |
> |---|---|
> | 120 | … |
> | 100 | … |
> | 80 | … |
> | 60 | … |
> | 40 | … |
>
> Z odpovědí 200+ respondentů sestavíme agregovanou poptávkovou křivku
> a odhadneme bodové elasticity.

### Sales Force Opinion

Využití **prodejní síly** (obchodních zástupců) jako zdroj predikce.

Výhody:

- Úzká vazba na zákazníka — zachycuje **subtilní signály**.
- Šíře informací: nejen objem prodeje, ale i **nové kategorie zákazníků**,
  tlak na technologické změny, makroekonomické signály.

Nevýhody:

- **Morální hazard** — pokud jsou prodejci hodnoceni dle plnění plánu,
  systematicky **podhodnocují** odhady (aby snadněji přeplnili plán).
- **Regionální zkreslení** — prodejce vidí svůj region, ne celkový trh.

### Expert Opinion + Delphi metoda

**Expert Opinion:** dotazování průmyslových analytiků, konzultantů,
členů obchodních komor.

**Riziko: groupthink** — pokud experti diskutují společně, dominantní
osobnost ovlivní ostatní a skupinová odpověď bude méně přesná než
průměr individuálních odpovědí.

**Delphi metoda** řeší groupthink:

> *"Delphi je metoda pro vytvoření skupinového komunikačního procesu tak,
> že je proces efektivní v ponechání skupiny jednotlivců jakožto celku
> řešícího komplexní problém. Je využita zpětná vazba, skupinový názor,
> revize názorů, určitá anonymita."*

**Postup Delphi:**

1. **Formulace otázky** — jasně definovaný problém s číselnou odpovědí.
2. **První kolo** — každý expert **anonymně** poskytne odhad.
3. **Sumarizace** — facilitátor zveřejní distribuci odpovědí (medián,
   kvartily) **bez identifikace** autorů.
4. **Druhé kolo** — experti vidí distribuci a mohou revidovat svůj odhad.
   Pokud revize výrazně mění mínění, **zdůvodňují**.
5. **Iterace** — typicky 2–4 kola, dokud se distribuce nestabilizuje.
6. **Konečný odhad** — medián posledního kola.

**Výhody:**

- **Anonymita** eliminuje groupthink a vliv autority.
- **Iterace** umožňuje konvergenci k informovanému konsenzu.
- **Strukturovaná zpětná vazba** dává prostor minoritním názorům.

**Existují příznivci i odpůrci** — kritici argumentují, že anonymita
brání skutečné argumentační diskusi a že konsensus může být **zdánlivý**.

### Test Marketing

**Sales Wave Research**

- Vybere se vzorek zákazníků.
- Sleduje se **rychlost opakovaného nákupu** (re-purchase rate).
- Vliv změny **obalu**, **složení**, **vztahu ke komplementům
  a substitutům**.

**Simulated Store Techniques**

- Podobné Sales Wave, ale s důrazem na **účinnost reklamy**.
- Zákazníci dostanou peníze a pohybují se v simulovaném obchodě s pultem
  produktů.
- Měří se míra konverze reklama → nákup.

**Test Marketing — „vyrob a prodej!"**

- Produkt se uvede do prodeje na **omezeném lokálním trhu** (1 město /
  region).
- Po definovaném období (3–12 měsíců) se vyhodnotí výsledky.
- Pokud jsou pozitivní → národní rozvinutí.
- Pokud negativní → zastavení projektu, **úspora vs. plné uvedení**.

**Riziko Test Marketingu:** konkurence vidí test a může reagovat
**dříve**, než firma stihne plné uvedení (obranný cenový tah,
souběžný launch).

## 13. Volba metody dle situace

| Typ produktu / trhu | Doporučená metoda |
|---|---|
| **A.** Průmyslový produkt s omezeným trhem | **Expert Opinion** (B) — málo zákazníků, expert je zná individuálně |
| **B.** Spotřebitelský trh s dostatkem dat z minulých prodejů | **Extrapolace trendů** (A) — dekompozice časové řady |
| **C.** Nový produkt s plánovanou dlouhou životností (nikoliv spotřební zboží) | **Market Testing** (C) — postupné uvedení s měřením |
| **D.** Technologicky vyspělý produkt na globálním trhu | **Průzkum trhu** (D) — Delphi expertů z různých regionů |

Mapování:

- $1 \rightarrow B$ (Expert Opinion)
- $2 \rightarrow A$ (Extrapolace)
- $3 \rightarrow C$ (Market Testing)
- $4 \rightarrow D$ (Průzkum trhu)

> [!tip] Kombinace metod
> V praxi se metody **kombinují**: extrapolace dává základní scénář,
> Delphi koriguje na strukturální změny, market testing validuje
> na reálných zákaznících. Konečná predikce je **vážený průměr**
> s váhami dle důvěry.

## 14. Aplikace odhadu poptávky

### Daňová ekonomika a veřejný sektor

- **Ramseyho pravidlo zdanění** — daňové zatížení by mělo být
  inverzně úměrné cenové elasticitě poptávky. Zdanění nepružných
  statků (alkohol, tabák, benzín) maximalizuje výnos s minimálním
  efektem na kvantitu — viz [[zdaneni-trhu|zdanění trhu]].
- **Predikce daňových výnosů** — dekompozice historických příjmů
  + makroekonomický scénář.
- **Kapacitní plánování** veřejných služeb — školky, doprava,
  zdravotnictví.

### Marketing

- **Cenová politika** — odhad elasticity → cenová optimalizace
  (maximum tržeb tam, kde $E_D = 1$).
- **Segmentace** — různé segmenty mají různé elasticity → diferencované
  ceny (verzování, slevové programy).
- **Reklama** — odhad reklamní elasticity rozhoduje o výši rozpočtu na
  marketing.
- **Substituty a komplementy** — křížová elasticita mapuje konkurenci
  a komplementární prodej (cross-selling).

### Strategické rozhodování firmy

- **Plánování kapacit** — predikce poptávky určuje investice do
  výrobních kapacit.
- **Životní cyklus produktu** — fáze introduction / growth / maturity
  / decline mají odlišné poptávkové dynamiky.
- **Vstup na nový trh** — Delphi + market testing minimalizují riziko
  selhání.

## 15. Souvislosti

- [[mikk|Mikroekonomie 2]] — kurzová stránka
- [[mikk-elasticita-poptavky|Cenová elasticita poptávky]] — vstup do
  výpočtu tržního potenciálu a klíčový parametr ekonometrického modelu.
- [[mikk-utility-preference|Užitečnost a preference]] — mikroekonomické
  základy poptávkové funkce.
- [[mikk-rovnovaha-spotrebitele|Rovnováha spotřebitele]] — ze
  spotřebitelské optimalizace plyne tvar poptávkové funkce, kterou pak
  empiricky odhadujeme.
- [[mikk-trzni-rovnovaha-dynamika|Tržní rovnováha a její dynamika]] —
  komparativní statika a problémy identifikace ($D$ vs. $S$ z rovnovážných dat).
- [[mikk-monopolisticka-konkurence|Monopolistická konkurence]] —
  odhad poptávky pro firmu s diferencovaným produktem.
- [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]] —
  teoretický základ pro tvar poptávkové křivky.
- [[mikk-vzorce-prehled|Přehled vzorců MikK]] — referenční seznam.
- [[mikk-vzorove-zkousky|Vzorové zkoušky a Předtermíny]] — Předtermín B
  (ekonometrické metody odhadu poptávky).
- [[poptavka-nabidka|Poptávka a nabídka (ImeK)]] — komplementární
  matematické pojetí poptávkové funkce.
- [[predikce|Predikce v ekonomickém modelování]] — obecné metody
  predikce, soft computing alternativy.
- [[zdaneni-trhu|Zdanění trhu]] — aplikace elasticit v daňové ekonomice.

## Zdroje

- Bílek, L.: Analýza pružnosti poptávky. Brno, 2001, FP VUT v Brně,
  písemná práce doktorandského studia (data jogurty A, B, C).
- Baye et al. 1992 — tabulka elasticit dle produktové kategorie.
- Gwartney, J. D., Stroup, R. L., Macpherson, D., Sobel, R. S.:
  Economics: Private and Public Choice. South-Western, 11. vydání, 2005.
- Kotler, P.: definice tržního potenciálu.
