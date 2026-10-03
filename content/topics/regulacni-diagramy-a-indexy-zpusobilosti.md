---
title: "Regulační diagramy a indexy způsobilosti"
course: mask
type: topic
tags: [mask, regulacni-diagramy, indexy-zpusobilosti, qcc, statistika, r]
sources: [raw/mask/06 regulační diagramy.pdf, raw/mask/07 indexy způsobilosti.pdf, raw/mask/návod 06 a 07.pdf, raw/mask/příklady 06 a 07.pdf]
created: 2026-10-02
updated: 2026-10-02
---

# Regulační diagramy a indexy způsobilosti

> [!tldr] V kostce
> - Regulační diagram zobrazuje vývoj variability procesu v čase a dává signál, že na proces začala působit vymezitelná příčina: bod mimo akční meze UCL a LCL.
> - Regulace měřením (spojitá veličina s normálním rozdělením): diagramy $(\bar{x}, R)$, $(\bar{x}, s)$ a $(x_i, R_{kl,i})$.
> - Regulace srovnáváním (diskrétní veličina): počet neshod $c$ (konstantní rozsah) a $u$ (nekonstantní rozsah), počet neshodných produktů $np$ (konstantní rozsah) a jejich podíl $p$ (nekonstantní rozsah).
> - Podskupiny s vymezitelnou příčinou se po jejím odstranění z výpočtu vyřadí a meze se přepočítají, dokud jsou všechny body uvnitř mezí.
> - Indexy způsobilosti $C_p$, $C_{pk}$, $C_{pm}$, $C_{pmk}$ posuzují, zda statisticky zvládnutý proces vyhovuje tolerančním mezím; $C_{pk}$ navíc zohledňuje vychýlení střední hodnoty.
> - V R diagramy i indexy počítá balíček `qcc`.

## Statistická regulace procesu

Tradiční zabezpečování jakosti kontroluje výrobky až po jejich vyrobení, což je neekonomické. **Statistická regulace procesu** je preventivní nástroj řízení jakosti: analyzuje chování výrobního procesu, umožňuje včas odhalit odchylky od normy a zasáhnout tak, aby proces zůstal dlouhodobě na požadované a stabilní úrovni — ve **statisticky zvládnutém stavu**.

Teorie regulace vychází z **variability** procesu, kterou způsobují dva druhy příčin:

| | Náhodné příčiny | Vymezitelné příčiny |
|---|---|---|
| Povaha | široká skupina neidentifikovatelných vlivů, každý přispívá k variabilitě malou měrou | vlivy, které za běžných podmínek na proces nepůsobí; vyvolají nepřirozené kolísání údajů |
| Stav procesu | ustálený, jakost výstupů je předvídatelná, není nutné zasahovat — statisticky zvládnutý | jakost výstupů není předvídatelná, je nutné zasáhnout — proces není statisticky zvládnutý |
| Příklady | psychický stav pracovníka, chvění stroje, teplota ovzduší | změna materiálu, nezaškolená obsluha |

Vymezitelné příčiny jsou **sporadické** (vznikají náhle, změny trvají krátce) nebo **přetrvávající** (trvají stále nebo se mění).

![[mask-ilu-pricin-variability.png|Dva stroje vedle regulačních diagramů: při náhodných příčinách kolísají body kolem střední přímky uvnitř mezí UCL a LCL, při vymezitelné příčině, například opotřebeném nástroji, bod vybočí nad UCL a je nutný zásah]]

Regulace probíhá ve třech fázích:

1. **Fáze přípravná** — stanoví se sledované znaky jakosti (rozměr, hmotnost, počet vad…), délka časového intervalu mezi měřeními, **logická podskupina** (skupina měření, v níž se předpokládá působení pouze náhodných příčin), typ regulačního diagramu a místa kontroly v procesu.
2. **Fáze zabezpečování statistické zvládnutosti** — pomocí regulačních diagramů se identifikují vymezitelné příčiny a odstraní se jejich působení.
3. **Fáze analýzy a zabezpečení způsobilosti** — zkoumá se, zda statisticky zvládnutý proces vyhovuje požadavkům zákazníka; k tomu slouží indexy způsobilosti (níže).

## Princip regulačního diagramu

**Regulační diagram** je grafický prostředek pro zobrazení vývoje variability procesu v čase. Popisuje statistickou zvládnutelnost procesu a dává signál, že na proces začala působit vymezitelná příčina; na jeho základě se do procesu zasáhne s cílem příčinu odstranit.

- **CL** — střední přímka, odpovídá požadované (referenční) hodnotě použité charakteristiky,
- **UCL** — horní akční regulační mez,
- **LCL** — dolní akční regulační mez.

Akční meze vymezují pásmo působení pouze náhodných příčin variability.

![[mask-rd-schema.png|Schéma regulačního diagramu: hodnoty testového kritéria v logických podskupinách kolísají kolem střední přímky CL uvnitř pásma mezi horní a dolní akční regulační mezí UCL a LCL]]

**Interpretace:** jsou-li všechny body uvnitř akčních mezí, je proces statisticky zvládnutý (nepůsobí žádná vymezitelná příčina). Je-li některý bod mimo meze, lze usuzovat, že proces není ve statisticky zvládnutém stavu; je třeba identifikovat vymezitelnou příčinu a přijmout opatření k jejímu odstranění.

Podle charakteru regulované veličiny se diagramy dělí na diagramy pro **regulaci měřením** (regulovaná veličina je spojitá náhodná veličina) a pro **regulaci srovnáváním** (diskrétní náhodná veličina).

Postup při konstrukci regulačního diagramu:

1. volba regulované veličiny,
2. sběr a záznam dat,
3. ověření požadovaných předpokladů o datech,
4. volba rozsahu logických podskupin,
5. volba vhodného regulačního diagramu,
6. výpočet hodnot zvoleného testového kritéria pro jednotlivé výběry,
7. ověření a zajištění statistické zvládnutosti procesu,
8. ověření způsobilosti procesu,
9. vlastní regulace procesu.

## Regulace měřením

Diagramy pro regulaci měřením se používají, když je regulovaná veličina měřitelná. Požaduje se, aby:

- jednotlivá měření byla vzájemně nezávislá,
- regulovaná veličina byla spojitá náhodná veličina s normálním rozdělením se střední hodnotou $\mu$ a směrodatnou odchylkou $\sigma$ — tyto dva parametry charakterizují statistickou stabilitu procesu; $\mu$ je hodnota, na niž je proces nastaven, $\sigma$ charakterizuje jeho přesnost.

Jsou-li předpoklady splněny, volí se diagramy, které současně sledují stabilitu polohy i stabilitu rozptylu: $(\bar{x}, R)$, $(\bar{x}, s)$ a $(x_i, R_{kl,i})$. Výsledkem jsou vždy dva diagramy.

### Diagram $(\bar{x}, R)$

Regulované veličiny jsou výběrové průměry $\bar{x}_i$ a výběrová rozpětí $R_i$ v logických podskupinách:

$$\bar{x}_i = \frac{1}{n}\sum_{j=1}^n x_{ij}, \qquad R_i = \max_j x_{ij} - \min_j x_{ij}.$$

Podmínky použití: regulovaná veličina je měřitelná a má normální rozdělení, jednotlivá měření jsou nezávislá, každá logická podskupina má stejný rozsah aspoň dvou měření. Má-li každá podskupina aspoň 4 měření, lze diagram pro výběrový průměr použít i pro data, která nepocházejí z normálního rozdělení.

Data se zapisují do tabulky: řádek $i = 1, \dots, k$ je logická podskupina v pořadí, v jakém byla získána, sloupce obsahují $n$ naměřených hodnot a poslední dva sloupce $\bar{x}_i$ a $R_i$. Pro sestrojení diagramu je potřeba aspoň 20 podskupin. Nejprve se určí diagram $R$, potom diagram $\bar{x}$ — u obou střední přímka a akční meze. V R se diagramy konstruují funkcí `qcc()`.

> [!example] Příklad: kontrola rozměru dílu ve 20 logických podskupinách
> Naměřená data znaku jakosti $X$ byla získána ve 20 logických podskupinách po 4 měřeních ($k=20$, $n=4$); znak je měřitelný a má normální rozdělení. Sestrojte regulační diagram $(\bar{x}, R)$.

| $i$ | $x_{i1}$ | $x_{i2}$ | $x_{i3}$ | $x_{i4}$ |
|---|---|---|---|---|
| 1 | 106 | 98 | 101 | 101 |
| 2 | 95 | 94 | 108 | 92 |
| 3 | 122 | 105 | 103 | 133 |
| 4 | 113 | 71 | 128 | 135 |
| 5 | 101 | 92 | 103 | 92 |
| 6 | 98 | 103 | 97 | 99 |
| … | … | … | … | … |
| 19 | 128 | 133 | 120 | 125 |
| 20 | 98 | 103 | 97 | 99 |

Pro každou podskupinu se dopočítá výběrový průměr $\bar{x}_i$ a rozpětí $R_i$:

| $i$ | $\bar{x}_i$ | $R_i$ |
|---|---|---|
| 1 | 101,50 | 8 |
| 2 | 97,25 | 16 |
| 3 | 115,75 | 30 |
| 4 | 111,75 | 64 |
| 5 | 97,00 | 11 |
| 6 | 99,25 | 6 |
| … | … | … |
| 19 | 126,50 | 13 |
| 20 | 99,25 | 6 |

Nejprve se posoudí diagram $R$ na všech 20 podskupinách: $CL(R)=15{,}8$, $UCL(R)=36{,}06$, $LCL(R)=0$. Rozpětí čtvrté podskupiny ($R_4=64$) mez překračuje; po potvrzení vymezitelné příčiny se podskupina 4 z výpočtu vyřadí a meze se přepočítají — $CL(R)=13{,}26$, $UCL(R)=30{,}27$, $LCL(R)=0$. Diagram rozpětí je teď zvládnutý, lze tedy posoudit diagram $\bar{x}$.

Diagram $\bar{x}$ bez čtvrté podskupiny dává $CL(\bar{x})=102{,}01$, $UCL(\bar{x})=111{,}68$, $LCL(\bar{x})=92{,}34$. Mez teď překračují průměry podskupin 3 a 19. Po potvrzení vymezitelné příčiny se vyřadí obě najednou a meze diagramu $R$ se přepočítají bez podskupin 3, 4 a 19: $CL(R)=12{,}29$, $UCL(R)=28{,}06$, $LCL(R)=0$ — žádná z 17 zbývajících podskupin mez nepřekračuje.

Konečný diagram $\bar{x}$ na stejných 17 podskupinách má $CL(\bar{x})=99{,}76$, $UCL(\bar{x})=108{,}73$, $LCL(\bar{x})=90{,}80$ — všechny výběrové průměry leží uvnitř mezí, proces je zvládnutý. Protože bylo vyřazeno několik podskupin, je vhodné měření doplnit tak, aby se pracovalo s počtem podskupin mezi 20 a 25.

![[mask-rd-priklad1-meze.png|Příklad 1: pásma mezi LCL a UCL se střední přímkou pro diagram R (všech 20 podskupin, bez podskupiny 4, bez podskupin 3, 4 a 19) a diagram x̄ (bez podskupiny 4, bez podskupin 3, 4 a 19); červeně body mimo meze R₄ = 64, x̄₃ a x̄₁₉]]

V R se diagramy sestrojí funkcí `qcc()` z balíčku `qcc`. Data jsou tabulka, v níž řádek odpovídá logické podskupině a sloupce jednotlivým měřením:

```r
library(qcc)
data <- read.table("3_2.txt", header = TRUE)
qcc(data, type = "R")      # diagram R
qcc(data, type = "xbar")   # diagram x̄
```

Funkce vykreslí diagram se střední přímkou a akčními mezemi a body mimo meze zvýrazní. Podskupina s potvrzenou vymezitelnou příčinou se vyřadí z dat (například `data[-4, ]`) a diagram se sestrojí znovu.

### Diagram $(\bar{x}, s)$

Regulované veličiny jsou výběrové průměry $\bar{x}_i$ a výběrové směrodatné odchylky $s_i$ v logických podskupinách. Podmínky použití jsou stejné jako u $(\bar{x}, R)$, logické podskupiny ale sestávají z většího počtu měření. Data se zapisují do obdobné tabulky.

```r
data <- read.table("3_2.txt", header = TRUE)
qcc(data, type = "S")      # diagram s
qcc(data, type = "xbar")   # diagram x̄
```

### Diagram $(x_i, R_{kl,i})$

Používá se za stejných podmínek jako $(\bar{x}, R)$, ale v každé logické podskupině se provede jen jedno měření — například proto, že náklady na kontrolu jsou vysoké nebo kontrola trvá dlouho. Charakteristikou rozptylu je pak **klouzavé rozpětí**:

$$R_{kl,i} = |x_i - x_{i-1}|, \quad i = 2, 3, \dots, k, \qquad \bar{R}_{kl} = \frac{1}{k-1}\sum_{i=2}^k R_{kl,i}.$$

Regulované veličiny jsou hodnoty $x_i$ a $R_{kl,i}$; nejdříve se určí střední přímka a meze diagramu $R_{kl,i}$, potom diagramu $x_i$. Data jsou jeden vektor naměřených hodnot:

```r
data <- read.table("3_3.txt", header = TRUE)
qcc(data[, 1], type = "xbar.one")
```

## Regulace srovnáváním

Diagramy pro regulaci srovnáváním se používají, sledují-li se počty neshodných produktů nebo počty neshod na produktech — regulovaná veličina je diskrétní náhodná veličina.

| Sleduje se | Konstantní rozsah podskupin | Nekonstantní rozsah podskupin |
|---|---|---|
| počet neshod na produktech (např. vady na stejných tabulích skla) | $c$ | $u$ |
| počet neshodných produktů ve výběru (např. neshodné kusy ze série na výrobní lince) | $np$ | $p$ |

### Diagram $c$

Regulovanou veličinou $c_i$ je počet neshod na produktech v $i$-té logické podskupině, $i = 1, \dots, k$; v každé podskupině je stejný počet $n$ produktů. Počet neshod má Poissonovo rozdělení, pokud může být počet neshod na produktu teoreticky neohraničený a pravděpodobnost více než jedné neshody v určitém místě produktu je zanedbatelná.

> [!example] Příklad: bodové vady na pásech látky
> Při tkaní látek se zjišťuje počet bodových vad na pásech dlouhých 100 metrů. Pro 20 pásů v pořadí, v jakém byly vybrány, jsou dány počty vad $c_i$. Sestrojte regulační diagram $c$.

```r
c_i <- c(7, 1, 2, 5, 0, 6, 2, 0, 4, 4, 6, 3, 3, 3, 1, 6, 3, 1, 5, 6)

q_c <- qcc(c_i, type = "c")
summary(q_c)
```

```text
Call:
qcc(data = c_i, type = "c")

c chart for c_i 

Summary of group statistics:
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   0.00    1.75    3.00    3.40    5.25    7.00 

Group sample size:  1
Number of groups:  20
Center of group statistics:  3.4
Standard deviation:  1.843909 

Control limits:
 LCL      UCL
   0 8.931727
```

Průměrný počet vad na pás je $CL = \bar{c} = 3{,}4$, horní mez $UCL = 8{,}93$ a dolní mez $LCL = 0$. Žádný pás meze nepřekračuje — proces je zvládnutý.

![[mask-rd-priklad2-c.png|Diagram c s počtem vad na 20 pásech látky, střední přímkou 3,4 a horní mezí 8,9]]

### Diagram $u$

Regulovanou veličinou $u_i = c_i/n_i$ je průměrný počet neshod přepočítaný na jeden produkt z logické podskupiny; rozsah podskupin $n_i$ není konstantní, a proto se bod od bodu mění i meze.

Za `sizes` se dosadí vektor rozsahů jednotlivých logických podskupin, resp. rozměr jejich jednotek:

```r
data <- read.table("3_4.txt", header = TRUE)   # počty suků a rozměry prken
qcc(data[, 1], type = "u", sizes = data[, 2])
```

### Diagram $np$

Regulovanou veličinou je počet neshodných produktů (ne neshod) v logické podskupině. Podmínky použití: rozsahy podskupin jsou stejně velké a velké (alespoň 50 produktů). Počet neshodných produktů má pak přibližně binomické rozdělení se střední hodnotou $np$, kde $p$ je pravděpodobnost, že vyrobený produkt je neshodný.

Pro konstantní rozsah $n$:

```r
data <- read.table("3_7.txt", header = TRUE)   # počty vadných tabletů v sériích po 100 kusech
qcc(data[, 1], type = "np", sizes = 100)
```

### Diagram $p$

Regulovanou veličinou je počet neshodných produktů v logické podskupině přepočtený na jednotku, $p_i = np_i/n_i$; rozsahy podskupin nemusí být konstantní.

Za `sizes` se dosadí vektor rozsahů logických podskupin:

```r
data <- read.table("3_6.txt", header = TRUE)   # počty vadných tabletů a rozsahy sérií
qcc(data[, 1], type = "p", sizes = data[, 2])
```

## Indexy způsobilosti

Zatímco regulační diagram posuzuje stabilitu procesu v čase, index způsobilosti posuzuje, zda se zvládnutý proces svou přirozenou variabilitou vejde do tolerančních mezí zadaných specifikací — dolní meze $LSL$ a horní meze $USL$. Způsobilost se zkoumá až pro proces, který je podle regulačních diagramů statisticky zvládnutý (třetí fáze regulace).

### $C_p$ — index způsobilosti

Podíl mezi délkou tolerančního intervalu a délkou intervalu, ve kterém by za normálního rozdělení mělo ležet skoro všech 99,73 % hodnot znaku, tedy $6\sigma$:

$$C_p = \frac{USL - LSL}{6\sigma}.$$

$C_p$ srovnává jen délky, nevšímá si, kde uprostřed tolerance proces leží — centrovaný i silně vychýlený proces se stejným $\sigma$ mají stejné $C_p$.

Doplňkové charakteristiky využití tolerančního intervalu:

- **míra využití tolerančního intervalu**: $\dfrac{100}{C_p}\,\%$ — na kolik procent je toleranční interval využíván sledovaným znakem,
- **robustnost procesu**: rezerva, kterou máme v tolerančních mezích, než index $C_p$ nabyde hodnotu 1 — rovná se menší hodnotě z výrazů $USL-(\mu+3\sigma)$ a $(\mu-3\sigma)-LSL$,
- **podíl zmetků**: $P_z = 2\Phi(-3C_p)$, kde $\Phi$ je distribuční funkce normovaného normálního rozdělení.

### $C_{pk}$ — index způsobilosti s ohledem na vychýlení

Bere v úvahu, že proces nemusí být centrovaný na střed tolerance; počítá se samostatně vzdálenost k horní a dolní mezi a horší z obou se stane indexem:

$$C_{pk} = \min\left(\frac{USL-\mu}{3\sigma},\ \frac{\mu-LSL}{3\sigma}\right).$$

Vyjde-li některý z obou podílů záporný, položí se roven nule; to nastane, když střední hodnota $\mu$ leží mimo toleranční interval, a proces pak není pod statistickou kontrolou. U centrovaného procesu jsou oba podíly stejné a $C_{pk} = C_p$; čím víc je proces vychýlený, tím víc je $C_{pk}$ menší než $C_p$.

### $C_{pm}$ a $C_{pmk}$ — indexy vztažené k cíli

Pokud má proces zadaný cílový střed $T$ (ne nutně střed tolerance), nahradí se $\sigma$ odmocninou ze střední čtvercové odchylky od cíle $\tau = \sqrt{\sigma^2+(\mu-T)^2}$, která trestá i vychýlení od $T$:

$$C_{pm} = \frac{USL-LSL}{6\tau}, \qquad C_{pmk} = \min\left(\frac{USL-\mu}{3\tau},\ \frac{\mu-LSL}{3\tau}\right).$$

### Interpretace

| Hodnota $C_p$ | Způsobilost procesu |
|---|---|
| $C_p < 1$ | dosahovaná přesnost je menší než předepsaná — proces je nezpůsobilý |
| $C_p = 1$ | dosahovaná přesnost je rovna předepsané — proces je způsobilý, ale sebemenší zvětšení $\sigma$ jej posune na nezpůsobilý |
| $C_p > 1$ | dosahovaná přesnost je větší než předepsaná — proces je způsobilý |

U indexu $C_{pk}$ se v praxi požaduje víc než jen hodnota nad 1: s rozvojem technologií roste nárok na rezervu, a běžně se dnes vyžaduje hodnota alespoň $1{,}5$.

![[mask-rd-cp-panely.png|Tři procesy se stejným tolerančním intervalem a rostoucím σ, s indexem Cp postupně nad, rovno a pod 1 — šířka 6σ v porovnání s tolerančním intervalem]]

![[mask-rd-cpk-off-centre.png|Vychýlený proces s vyznačenými LSL, USL, μ a mezemi μ±3σ: Cp počítá s celou tolerancí, Cpk jen s bližší, kratší vzdáleností]]

### Výpočet v R

Indexy způsobilosti počítá `process.capability()` z výstupu regulačního diagramu `q`; `spec.limits` jsou toleranční meze $LSL$ a $USL$, `target` cílová hodnota $T$. Pro velikost výrobku v mm s tolerančními mezemi 100 a 110 mm a cílovou hodnotou 105 mm:

```r
library(qcc)
data <- read.table("3_8.txt", header = TRUE)
x <- as.matrix(data)
q <- qcc(x, type = "xbar")
process.capability(q, spec.limits = c(100, 110), target = 105, std.dev = sd(x))
```

Výpis obsahuje řádky `Cp`, `Cp_l`, `Cp_u`, `Cp_k` a `Cpm` s hodnotou indexu a 95% intervalem spolehlivosti. `Cp_l` a `Cp_u` jsou dílčí poměry k dolní a horní mezi, jejich minimum je $C_{pk}$. Index $C_{pmk}$ a doplňkové charakteristiky se dopočítají ze vzorců výše:

```r
mu <- mean(x); sigma <- sd(x)
LSL <- 100; USL <- 110; T <- 105
tau <- sqrt(sigma^2 + (mu - T)^2)
Cp <- (USL - LSL) / (6 * sigma)
Cpmk <- min((USL - mu) / (3 * tau), (mu - LSL) / (3 * tau))
miravyuziti <- 100 / Cp
robustnost <- min(USL - (mu + 3 * sigma), (mu - 3 * sigma) - LSL)
Pz <- 2 * pnorm(-3 * Cp)
```

## Časté chyby

- Počítat indexy způsobilosti pro proces, který není statisticky zvládnutý — způsobilost se zkoumá až ve třetí fázi regulace.
- Posuzovat jen $C_p$ u vychýleného procesu — $C_p$ polohu střední hodnoty nezohledňuje, vychýlení zachytí až $C_{pk}$.
- Zaměnit diagram $c$ s diagramem $u$ nebo diagram $np$ s diagramem $p$ — při nekonstantním rozsahu podskupin se volí $u$, resp. $p$, a do `sizes` se zadává vektor rozsahů.
- Posuzovat diagram $\bar{x}$ dřív než diagram rozpětí — nejprve se určí a stabilizuje diagram $R$ (resp. $s$), potom diagram $\bar{x}$.
- Vyřadit podskupinu jen podle polohy bodu — vyřazuje se až po zjištění a odstranění vymezitelné příčiny.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[popisna-statistika]]
- [[nahodne-veliciny-a-rozdeleni]]
- [[testovani-hypotez]]
- [[regresni-a-korelacni-analyza]]
- [[kontingencni-tabulky]]
- [[mask-r-tahak|Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.

MONTGOMERY, D. C. *Introduction to Statistical Quality Control*. 6. vyd. John Wiley & Sons, 2005.

ČSN ISO 8258. *Shewhartovy regulační diagramy*. Praha: Český normalizační institut, 1994.

KUPKA, K. *Statistické řízení jakosti*. Pardubice: TriloByte, 1997.
