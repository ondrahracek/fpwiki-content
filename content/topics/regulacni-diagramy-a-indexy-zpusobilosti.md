---
title: "Regulační diagramy a indexy způsobilosti"
course: mask
type: topic
tags: [mask, regulacni-diagramy, indexy-zpusobilosti, qcc, statistika, r]
sources: ["raw/mask/images_we_have_rights_to/Regulační diagramy_ Měření a srovnávání.png", "raw/mask/06 regulační diagramy.pdf", "raw/mask/06 regulační diagramy přednáška.pdf", "raw/mask/07 indexy způsobilosti - Moodle 2026-11-06.pdf", "raw/mask/návod 06 a 07.pdf", "raw/mask/příklady 06 a 07.pdf", "raw/mask/regulace a indexy způsobilosti příklady.pdf", "raw/mask/6_1.txt", "raw/mask/6_2.txt", "raw/mask/6_3.txt", "raw/mask/6_4.txt", "raw/mask/6_5.txt", "raw/mask/6_6.txt"]
created: 2026-10-02
updated: 2026-11-06
---

# Regulační diagramy a indexy způsobilosti

> [!tldr] V kostce
> - Regulační diagram sleduje, jak se výroba mění v čase.
> - Bod mimo meze upozorňuje na změnu, jejíž příčinu potřebujeme vyšetřit.
> - Typ diagramu vybíráme podle toho, zda měříme rozměry, počítáme vady, nebo počítáme vadné kusy.
> - Způsobilost posuzujeme až u stabilní výroby. Ukazuje, zda její výsledky vyhovují tolerancím zákazníka.

## Statistická regulace procesu

Rozměry vyrobených dílů nejsou při každém měření stejné. Samotná kontrola hotových výrobků odhalí nevyhovující kusy až poté, co vzniknou. **Statistická regulace procesu** sleduje průběžná měření a pomáhá rozpoznat změnu, na kterou je třeba reagovat. Cílem je předvídatelné kolísání procesu, označované jako **statisticky zvládnutý stav**.

Rozdíly mezi výsledky měření se nazývají **variabilita**. Část kolísání patří k běžnému chodu výroby, například vlivem chvění stroje nebo teploty ovzduší. Jiné kolísání může vyvolat konkrétní změna, například jiný materiál. Podle toho rozlišujeme dva druhy příčin:

| | Náhodné příčiny | Vymezitelné příčiny |
|---|---|---|
| Povaha | mnoho drobných vlivů, jejichž jednotlivé příspěvky nelze rozlišit | konkrétní vlivy, které vyvolají kolísání odlišné od běžného chodu procesu |
| Stav procesu | ustálený, jakost výstupů je předvídatelná, není nutné zasahovat — statisticky zvládnutý | jakost výstupů není předvídatelná, je nutné zasáhnout — proces není statisticky zvládnutý |
| Příklady | psychický stav pracovníka, chvění stroje, teplota ovzduší | změna materiálu, nezaškolená obsluha |

Vymezitelné příčiny mohou působit krátce a náhle; pak se označují jako **sporadické**. **Přetrvávající** příčiny působí dlouhodobě, přičemž se jejich vliv může měnit.

![[mask-ilu-pricin-variability.png|Dva stroje vedle regulačních diagramů: při náhodných příčinách kolísají body kolem střední přímky uvnitř mezí UCL a LCL, při vymezitelné příčině, například opotřebeném nástroji, bod vybočí nad UCL a je nutný zásah]]

Před měřením se určí, co se bude sledovat a které výsledky patří k sobě. Například rozměry dílů odebraných za srovnatelných podmínek tvoří **logickou podskupinu**. Uvnitř takové skupiny předpokládáme jen běžné náhodné kolísání. Rozdíly mezi postupně odebíranými skupinami pak mohou upozornit na změnu výroby.

Regulace probíhá ve třech fázích:

1. **Fáze přípravná** — zvolí se sledovaný rozměr, hmotnost nebo počet vad, místa kontroly a interval mezi odběry. Určí se také složení logických podskupin a vhodný typ diagramu.
2. **Fáze zabezpečování statistické zvládnutosti** — hledají se příčiny signálů v diagramu a odstraňují se potvrzené vymezitelné příčiny.
3. **Fáze analýzy a zabezpečení způsobilosti** — u stabilního procesu se posoudí, zda výrobky splňují požadavky zákazníka. K tomu slouží indexy způsobilosti.

## Princip regulačního diagramu

**Regulační diagram** zachovává časové pořadí měření. Každý bod představuje například průměr rozměrů z jedné podskupiny nebo počet vad v jedné sérii. Z polohy bodů vůči střední přímce a regulačním mezím se posuzuje, zda se proces změnil natolik, že je třeba hledat konkrétní příčinu.

- **CL** — střední přímka, referenční úroveň sledované charakteristiky,
- **UCL** — horní akční regulační mez,
- **LCL** — dolní akční regulační mez.

Akční meze vymezují pásmo očekávaného náhodného kolísání. Nejsou to zákazníkovy požadavky na rozměr výrobku; ty vyjadřují toleranční meze.

![[mask-rd-schema.png|Schéma regulačního diagramu: hodnoty testového kritéria v logických podskupinách kolísají kolem střední přímky CL uvnitř pásma mezi horní a dolní akční regulační mezí UCL a LCL]]

Bod mimo akční meze je **signálem statistické nezvládnutosti**. Jeho čas a příslušná podskupina pomáhají určit, kde hledat změnu procesu. Samotný bod ještě neříká, co ji způsobilo. Kromě překročení mezí se sledují i nenáhodná uspořádání, například dlouhá řada bodů na jedné straně střední přímky. Body uvnitř mezí tedy samy o sobě nezaručují stabilitu.

![[mask-rd-volba-diagramu.png|Volba regulačního diagramu podle měřených hodnot, počtu neshod nebo počtu neshodných produktů a rozsahu podskupin]]

Zkratka LP v obrázku znamená logickou podskupinu. Při větším počtu měření v podskupině se místo rozpětí obvykle sleduje směrodatná odchylka. Rozdělení na menší a větší podskupiny u dvojic $(\bar{x},R)$ a $(\bar{x},s)$ je orientační, ne ostrá hranice použitelnosti.

Při **regulaci měřením** se zapisují naměřené hodnoty, například délky výrobků. Jde o spojitou náhodnou veličinu. Při **regulaci srovnáváním** se počítají vady nebo vadné kusy; taková veličina je diskrétní.

Konstrukce diagramu navazuje na plán odběru. Nejprve se připraví data a ověří jejich předpoklady, poté se vypočítají meze a vyšetří případné signály:

1. zvolit sledovanou veličinu,
2. shromáždit a zaznamenat data v časovém pořadí,
3. ověřit požadované předpoklady o datech,
4. určit počet měření v logických podskupinách,
5. vybrat vhodný regulační diagram,
6. vypočítat hodnotu sledované charakteristiky pro každou podskupinu,
7. posoudit stabilitu procesu a odstranit potvrzené vymezitelné příčiny,
8. u stabilního procesu ověřit způsobilost,
9. používat diagram k průběžnému sledování procesu.

## Regulace měřením

Při sledování délky nebo hmotnosti potřebujeme rozlišit dvě změny: posun obvyklé hodnoty a zvětšení rozdílů mezi výrobky. Diagramy pro regulaci měřením proto sledují obojí. Jejich použití vyžaduje:

- vzájemnou nezávislost jednotlivých měření,
- spojitou veličinu s normálním rozdělením, jehož střední hodnota $\mu$ vyjadřuje nastavení procesu a směrodatná odchylka $\sigma$ rozptýlení výrobků kolem této hodnoty.

Stabilita procesu znamená, že se v čase nemění ani $\mu$, ani $\sigma$.

Dvojice $(\bar{x}, R)$, $(\bar{x}, s)$ a $(x_i, R_{kl,i})$ vždy obsahují dva diagramy. Jeden sleduje polohu měření, druhý jejich rozptýlení. Stabilní průměr totiž může skrývat rostoucí rozdíly mezi jednotlivými výrobky.

### Diagram $(\bar{x}, R)$

Z měření v každé podskupině se spočítá průměr $\bar{x}_i$ a rozpětí $R_i$. Průměr popisuje obvyklou úroveň rozměru, rozpětí rozdíl mezi největším a nejmenším naměřeným rozměrem:

$$
\bar{x}_i = \frac{1}{n}\sum_{j=1}^n x_{ij}, \qquad R_i = \max_j x_{ij} - \min_j x_{ij}.
$$

Každá podskupina musí obsahovat stejný počet alespoň dvou nezávislých měření veličiny s normálním rozdělením. Při větším počtu měření je diagram průměrů méně citlivý na odchylky od normality. Samotná čtyři měření však pro libovolné rozdělení normální aproximaci nezaručují.

V tabulce patří na jeden řádek všechna měření z téhož odběru. Řádek $i = 1, \dots, k$ tak představuje jednu podskupinu a zachovává pořadí odběrů. Vedle $n$ naměřených hodnot se dopočítají $\bar{x}_i$ a $R_i$. Pro sestrojení diagramu je potřeba aspoň 20 podskupin. Nejprve se posuzuje diagram $R$: mění-li se rozptýlení měření, nelze spoléhat ani na meze diagramu $\bar{x}$. V R obě části počítá funkce `qcc()`.

> [!example] Příklad: kontrola rozměru dílu ve 20 logických podskupinách
> Rozměr dílu $X$ byl měřen ve 20 podskupinách po 4 měřeních ($k=20$, $n=4$). Předpokládáme nezávislá měření a normální rozdělení rozměru. Sestrojte regulační diagram $(\bar{x}, R)$.

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

Z rozměrů na každém řádku vznikne výběrový průměr $\bar{x}_i$ a rozpětí $R_i$. Tyto dvojice hodnot se pak vynášejí do diagramů:

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

V této ukázce sledujeme také přepočet mezí po vyřazení podskupin. Každý takový krok je podmíněn tím, že se příčina příslušného signálu skutečně zjistí a odstraní. Diagram sám tuto podmínku nedokládá.

Pro všech 20 podskupin má diagram $R$ meze $CL(R)=15{,}8$, $UCL(R)=36{,}06$, $LCL(R)=0$. Ve čtvrté podskupině je rozdíl mezi krajními rozměry příliš velký: $R_4=64$ překračuje horní mez. Pokud se potvrdí a odstraní vymezitelná příčina, podskupina 4 se vyřadí a meze se přepočítají na $CL(R)=13{,}26$, $UCL(R)=30{,}27$, $LCL(R)=0$. Zbývající rozpětí už meze nepřekračují a lze přejít k diagramu $\bar{x}$.

Diagram $\bar{x}$ bez čtvrté podskupiny má $CL(\bar{x})=102{,}01$, $UCL(\bar{x})=111{,}68$, $LCL(\bar{x})=92{,}34$. Horní mez překračují průměry podskupin 3 a 19. Pokud se i u nich příčina potvrdí a odstraní, vyřadí se obě najednou. Diagram $R$ bez podskupin 3, 4 a 19 pak dává $CL(R)=12{,}29$, $UCL(R)=28{,}06$, $LCL(R)=0$. Žádné ze 17 zbývajících rozpětí tyto meze nepřekračuje.

Pro stejných 17 podskupin vycházejí v diagramu $\bar{x}$ hodnoty $CL(\bar{x})=99{,}76$, $UCL(\bar{x})=108{,}73$, $LCL(\bar{x})=90{,}80$. Všechny průměry leží uvnitř mezí. V této podmíněné variantě tedy další překročení nenastává. Po vyřazení několika podskupin je vhodné měření doplnit na počet mezi 20 a 25.

![[mask-rd-priklad1-meze.png|Příklad 1: pásma mezi LCL a UCL se střední přímkou pro diagram R (všech 20 podskupin, bez podskupiny 4, bez podskupin 3, 4 a 19) a diagram x̄ (bez podskupiny 4, bez podskupin 3, 4 a 19); červeně body mimo meze R₄ = 64, x̄₃ a x̄₁₉]]

Předchozí příklad pracoval s 20 podskupinami. Následující úloha má jiných 25 podskupin; i u nich se zachovává časové pořadí.

### Úloha 1: délky výrobků ve 25 podskupinách

Při každém odběru byly změřeny čtyři délky výrobků. V R tvoří délky z jednoho odběru jeden řádek tabulky `data1`; sloupce obsahují jednotlivá měření. Sestrojte dvojice diagramů $(\bar{x},R)$ a $(\bar{x},s)$. Nejprve sledujte rozdíly mezi výrobky uvnitř podskupin, potom změny jejich průměrné délky.

Nejprve zadáme naměřené délky. Balíček `qcc` pak z téže tabulky vytvoří oba diagramy.

```r
library(qcc)
data1 <- matrix(c(
  110, 105, 107, 110,
  100, 103, 105, 105,
  106, 111, 106, 104,
  108, 106, 105, 104,
  115, 108, 105, 104,
  99, 109, 110, 110,
  100, 100, 108, 109,
  105, 105, 100, 108,
  106, 105, 102, 100,
  107, 105, 102, 102,
  100, 110, 100, 100,
  102, 100, 99, 96,
  102, 99, 110, 100,
  110, 99, 111, 107,
  110, 106, 105, 107,
  98, 108, 106, 106,
  105, 103, 105, 108,
  107, 105, 106, 105,
  108, 104, 110, 105,
  107, 104, 101, 104,
  105, 105, 103, 104,
  104, 109, 109, 105,
  100, 110, 110, 108,
  102, 100, 100, 110,
  110, 100, 98, 110
), ncol = 4, byrow = TRUE)
colnames(data1) <- c("x1", "x2", "x3", "x4")
```

```r
q_R <- qcc(data1, type = "R")
q_xR <- qcc(data1, type = "xbar")
```

Rozdíly mezi délkami uvnitř podskupin meze nepřekračují. V diagramu průměrů však podskupina 12 leží pod dolní mezí a pravidlo pro řady označuje také podskupinu 13. Průměrná délka tedy vykazuje signál změny a proces nelze považovat za statisticky zvládnutý. Příčinu je třeba vyšetřit; do té doby zůstává ve výpočtu všech 25 podskupin.

![[mask-rd-6-1-xbar-r.png|Délky výrobků ve 25 podskupinách: diagram R bez překročení mezí a diagram průměrů s podskupinou 12 pod LCL]]

### Diagram $(\bar{x}, s)$

V této dvojici se z každé podskupiny opět spočítají průměry $\bar{x}_i$, ale rozptýlení měření popisují výběrové směrodatné odchylky $s_i$. Předpoklady zůstávají stejné jako u $(\bar{x}, R)$. Diagram se používá pro větší podskupiny; uspořádání měření v tabulce se nemění.

U délek z `data1` nejprve posoudíme směrodatné odchylky jednotlivých podskupin. Aby na tento diagram správně navazoval diagram průměrů, převezme stejný odhad $\sigma$ z diagramu $s$. V R se předá přes `std.dev`; samotné `qcc(..., type = "xbar")` by odhadlo variabilitu z rozpětí.

```r
q_S <- qcc(data1, type = "S")
q_xS <- qcc(data1, type = "xbar", std.dev = q_S$std.dev)
```

Směrodatné odchylky v diagramu $s$ meze nepřekračují. Diagram průměrů ale znovu označuje podskupinu 12. Jiný způsob měření rozptýlení tak vede ke stejnému závěru o změně průměrné délky.

Přepočet bez podskupiny 12 by připadal v úvahu až po zjištění a odstranění její vymezitelné příčiny. V R by se použilo `data1[-12, ]` a znovu by se posoudily oba diagramy. Tuto podmíněnou variantu rozvíjí příklad indexů způsobilosti níže.


### Diagram $(x_i, R_{kl,i})$

Když je kontrola drahá nebo trvá dlouho, může při každém odběru vzniknout jen jedno měření. Z jediné hodnoty nelze spočítat rozpětí uvnitř podskupiny. Místo něj se použije rozdíl sousedních měření, tedy **klouzavé rozpětí**. Předpoklady jsou stejné jako u $(\bar{x}, R)$:

$$
R_{kl,i} = |x_i - x_{i-1}|, \quad i = 2, 3, \dots, k, \qquad \bar{R}_{kl} = \frac{1}{k-1}\sum_{i=2}^k R_{kl,i}.
$$

Sledují se jednotlivá měření $x_i$ a jejich klouzavá rozpětí $R_{kl,i}$. Nejdříve se posoudí diagram $R_{kl,i}$, potom diagram $x_i$. Do R se délky zadávají jako jediná posloupnost hodnot, tedy vektor, v původním pořadí.

#### Úloha 2: jednotlivě měřené délky

Máme 20 postupně naměřených délek výrobků. Každý odběr obsahuje jen jeden výrobek. Pro výpočet klouzavých rozpětí spojí příkaz `cbind()` sousední délky do řádků tabulky `dvojice`; tyto dvojice pouze porovnávají sousední odběry.

```r
data2 <- c(504, 496, 510, 506, 497, 494, 501, 499, 495, 503, 504, 495, 502, 505, 496, 501, 497, 493, 500, 496)
dvojice <- cbind(head(data2, -1), tail(data2, -1))
```

```r
q_MR <- qcc(dvojice, type = "R")
q_I <- qcc(data2, type = "xbar.one")
```

Jednotlivé délky ani rozdíly sousedních délek nepřekračují akční meze. Také pravidlo pro řady zůstává bez signálu. Použité diagramy tedy neukázaly statistickou nezvládnutost procesu.


## Regulace srovnáváním

Při kontrole lze počítat buď jednotlivé vady, nebo vadné výrobky. Na jedné desce může být více suků, takže přibývají vady. Vadný tablet se naopak do počtu vadných kusů započte jen jednou, i kdyby měl více závad. Odborně jde o **neshody** a **neshodné produkty**. Pro volbu diagramu záleží také na tom, zda má každý odběr stejný rozsah, například stejnou plochu nebo stejný počet kontrolovaných kusů.

| Sleduje se | Konstantní rozsah podskupin | Nekonstantní rozsah podskupin |
|---|---|---|
| počet neshod na produktech (např. vady na stejných tabulích skla) | $c$ | $u$ |
| počet neshodných produktů ve výběru (např. neshodné kusy ze série na výrobní lince) | $np$ | $p$ |

### Diagram $c$

Pokud se při každé kontrole prohlédne stejné množství výrobků nebo stejně velká plocha, lze přímo porovnávat počty vad. Počet neshod $c_i$ v $i$-té podskupině, $i = 1, \dots, k$, pak sleduje diagram se stejnými mezemi. Každá podskupina obsahuje stejný počet $n$ produktů. Používá se Poissonovo rozdělení: počet možných vad není shora omezen a pravděpodobnost více vad v témže místě je zanedbatelná.

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

Střední přímka $CL = \bar{c} = 3{,}4$ udává průměrný počet vad na pás. Meze jsou $UCL = 8{,}93$ a $LCL = 0$. Žádný pás nemá počet vad mimo toto pásmo, takže překročení mezí změnu procesu nesignalizuje.

![[mask-rd-priklad2-c.png|Diagram c s počtem vad na 20 pásech látky, střední přímkou 3,4 a horní mezí 8,9]]

#### Úloha 4: vady na magnetických páskách

U 24 stejně dlouhých magnetických pásek sledujeme počet vad. Jedna páska může mít více vad, proto volíme diagram $c$.

```r
vady4 <- c(14, 18, 5, 7, 11, 24, 17, 13, 12, 15, 18, 11, 7, 18, 12, 8, 5, 9, 14, 13, 16, 15, 17, 13)
q_c4 <- qcc(vady4, type = "c")
```

Šestá páska má 24 vad a překračuje horní mez. Její počet vad vybočuje z očekávaného kolísání a je třeba hledat příčinu. K vyřazení pásky z výpočtu mezí by bylo nutné příčinu zjistit a odstranit.

![[mask-rd-6-4-c.png|Počty vad na 24 stejně dlouhých magnetických páskách; šestá páska s 24 vadami překračuje UCL]]

### Diagram $u$

U různě velkých desek by samotný počet vad nebyl dobře srovnatelný: na větší ploše je více příležitostí k výskytu vady. Proto se počítá počet vad na jednotku plochy nebo na jeden produkt, $u_i = c_i/n_i$. Rozsah kontroly $n_i$ se mezi podskupinami mění, a proto má každý bod také vlastní regulační meze.

#### Úloha 3: suky na deskách o různé ploše

Na 22 deskách byly spočítány suky a změřeny plochy v m². Sloupec `x` obsahuje počty suků a `rozsah3` příslušné plochy. Diagram porovnává počet suků na m². Funkce `qcc()` tento přepočet provede sama: dostane počty suků a přes `sizes` plochy desek.

```r
data3 <- data.frame(
  x = c(2, 3, 6, 4, 1, 0, 2, 3, 5, 4, 3, 5, 3, 1, 3, 4, 2, 1, 0, 4, 4, 2),
  rozsah3 = c(5.1, 4.8, 3.7, 6.2, 5.4, 2.8, 4.5, 5.3, 4.2, 5.2, 5.4, 5.6, 4.7, 5.3, 5.6, 4.4, 5.6, 6.1, 5.7, 6.1, 5.2, 4.9)
)
q_u <- qcc(data3$x, type = "u", sizes = data3$rozsah3)
```

Menší deska má širší meze pro počet suků přepočtený na plochu. Meze proto nejsou vodorovné a každý bod se porovnává s mezemi pro svou desku. Žádný bod je nepřekračuje a ani pravidlo pro řady nedává signál.

![[mask-rd-6-3-u.png|Počty suků na m² u 22 desek; proměnlivé horní meze odpovídají různým plochám desek]]


### Diagram $np$

Při kontrole stejně velkých sérií se může přímo sledovat počet vadných kusů. Každý výrobek se hodnotí jako vyhovující, nebo neshodný. Podskupiny musí být stejně velké a obsahovat alespoň 50 produktů. Při nezávislosti výsledků a stejné pravděpodobnosti neshody má počet neshodných produktů binomické rozdělení se střední hodnotou $np$. Symbol $p$ znamená pravděpodobnost, že výrobek bude neshodný.

#### Úloha 6: vadné tablety v sériích po 100 kusech

Ve 24 sériích se stejným rozsahem 100 tabletů sledujeme počet vadných kusů `pv6`. Každý tablet se započte nejvýše jednou.

```r
pv6 <- c(0, 2, 1, 0, 3, 0, 2, 5, 0, 6, 1, 2, 1, 3, 4, 1, 1, 1, 0, 7, 0, 2, 3, 0)
q_np <- qcc(pv6, type = "np", sizes = 100)
```

Série 10 a 20 obsahují 6 a 7 vadných tabletů a překračují horní mez. Diagram tak signalizuje nestabilitu procesu. Pokud by se pro obě série potvrdila a odstranila vymezitelná příčina, přepočet by vycházel z `pv6[-c(10, 20)]`.

![[mask-rd-6-6-np.png|Počty vadných tabletů ve 24 sériích po 100 kusech; série 10 a 20 překračují horní mez]]


### Diagram $p$

U různě velkých sérií se porovnává podíl vadných výrobků. Počet vadných kusů se vydělí počtem všech zkontrolovaných kusů v sérii, $p_i = np_i/n_i$. Každý výrobek se započítává nejvýše jednou; velikosti sérií se mohou lišit.

#### Úloha 5: podíl vadných tabletů při různých rozsazích sérií

V této úloze se velikost kontrolovaných sérií mění. Stejný počet vadných tabletů proto nemusí znamenat stejný podíl vadných kusů. Diagram $np$ nahradíme diagramem $p$ s proměnlivými mezemi. Počty vadných tabletů jsou ve sloupci `pv5`, počty kontrolovaných tabletů v `rozsah5`. Funkce `qcc()` dostane oba sloupce a podíly spočítá sama.

```r
data5 <- data.frame(
  podskupina = 1:24,
  pv5 = c(0, 2, 1, 0, 3, 0, 2, 5, 0, 6, 1, 2, 1, 3, 4, 1, 1, 1, 0, 7, 0, 2, 3, 0),
  rozsah5 = c(100, 150, 100, 100, 150, 50, 100, 200, 100, 200, 100, 100, 150, 150, 150, 100, 100, 100, 100, 200, 150, 150, 100, 150)
)
q_p <- qcc(data5$pv5, type = "p", sizes = data5$rozsah5)
```

Střední přímka odpovídá podílu vadných tabletů ze všech zkontrolovaných kusů dohromady. Větší série tak mají při výpočtu větší váhu; nejde o prostý průměr podílů jednotlivých sérií. Všechny podíly leží uvnitř svých mezí a ani pravidlo pro řady neukazuje statistickou nezvládnutost.

![[mask-rd-6-5-p.png|Podíly vadných tabletů ve 24 různě velkých sériích s proměnlivými horními regulačními mezemi]]


## Indexy způsobilosti

Výroba může být stabilní, a přesto vyrábět příliš rozdílné rozměry. Regulační diagram posuzuje, zda se chování procesu v čase mění. **Indexy způsobilosti** pak u stabilního procesu porovnávají rozptýlení rozměrů s požadavkem zákazníka: dolní toleranční mezí $LSL$ a horní toleranční mezí $USL$. Toto posouzení tedy navazuje až na ověření statistické zvládnutosti.

### $C_p$ — index způsobilosti

Nejprve porovnáme šířku přípustného rozmezí s šířkou přirozeného kolísání procesu. Při normálním rozdělení obsahuje pásmo o šířce $6\sigma$ kolem střední hodnoty přibližně 99,73 % hodnot. Poměr obou šířek vyjadřuje index:

$$
C_p = \frac{USL - LSL}{6\sigma}.
$$

$C_p$ porovnává pouze šířky. Nezohledňuje, zda běžné rozměry leží uprostřed tolerance, nebo blízko jejího okraje. Procesy se stejným $\sigma$ proto mají stejné $C_p$, i když se liší svou polohou.

Vedle indexu lze popsat, kolik tolerance proces zabírá, jakou má rezervu a jaký podíl zmetků vychází z normálního modelu:

- **Míra využití tolerančního intervalu**: $\dfrac{100}{C_p}\,\%$ udává šířku přirozeného kolísání jako procento šířky tolerance.
- **Robustnost procesu**: rezerva k bližší toleranční mezi. Na rozdíl od indexu $C_p$ zohledňuje také polohu procesu. Vypočítá se jako menší z hodnot $USL-(\mu+3\sigma)$ a $(\mu-3\sigma)-LSL$. Kladná rezerva znamená, že se přirozené rozmezí hodnot do tolerancí vejde; záporná, že je přesahuje.
- **Podíl zmetků při normálním rozdělení a centrování na střed tolerance**: $P_z = 2\Phi(-3C_p)$, kde $\Phi$ je distribuční funkce normovaného normálního rozdělení.

### $C_{pk}$ — index způsobilosti s ohledem na vychýlení

Pokud průměrný rozměr neleží uprostřed tolerance, k jednomu okraji zbývá méně místa než k druhému. Index proto porovná vzdálenosti od střední hodnoty k oběma mezím s kolísáním procesu a vybere horší výsledek:

$$
C_{pk} = \min\left(\frac{USL-\mu}{3\sigma},\ \frac{\mu-LSL}{3\sigma}\right).
$$

Jestliže střední hodnota $\mu$ leží dokonce mimo toleranci, vyjde jeden podíl záporný. Záporný je pak i $C_{pk}$; jeho hodnotu ponecháváme, nenahrazujeme ji nulou. Vyjadřuje nepříznivou polohu rozměrů vůči toleranci, nikoli změnu procesu v čase. U procesu nastaveného na střed tolerance platí $C_{pk} = C_p$. S rostoucím vychýlením je $C_{pk}$ menší než $C_p$.

### $C_{pm}$ a $C_{pmk}$ — indexy vztažené k cíli

Někdy je kromě tolerancí zadán i požadovaný rozměr $T$, který nemusí ležet uprostřed tolerance. Odchylka od tohoto cíle se zahrne do rozptýlení: místo $\sigma$ se použije $\tau = \sqrt{\sigma^2+(\mu-T)^2}$. Čím více se střední hodnota vzdálí od $T$, tím větší je tento jmenovatel a tím menší jsou indexy:

$$
C_{pm} = \frac{USL-LSL}{6\tau}.
$$

$$
C_{pmk} = \min\left(\frac{USL-\mu}{3\tau},\ \frac{\mu-LSL}{3\tau}\right).
$$

### Interpretace

| Hodnota $C_p$ | Porovnání šířek $6\sigma$ a tolerance |
|---|---|
| $C_p < 1$ | přirozená šířka procesu je větší než tolerance |
| $C_p = 1$ | přirozená šířka procesu se rovná toleranci; pro centrovaný proces není rezerva |
| $C_p > 1$ | přirozená šířka procesu je menší než tolerance; způsobilost ještě závisí na poloze procesu |

Toto porovnání má význam pro statisticky zvládnutý proces s vhodným modelem rozdělení. Hodnota $C_p>1$ říká, že tolerance je širší než přirozené kolísání. Stále však záleží na tom, kde uvnitř tolerance proces leží.

Požadovanou hodnotu indexu určuje specifikace zákazníka. Hodnota 1 je hranicí porovnávaných šířek; přísnější požadavek může být například $1{,}33$, $1{,}5$ nebo $2$.

![[mask-rd-cp-panely.png|Tři procesy se stejným tolerančním intervalem a rostoucím σ, s indexem Cp postupně nad, rovno a pod 1 — šířka 6σ v porovnání s tolerančním intervalem]]

![[mask-rd-cpk-off-centre.png|Vychýlený proces s vyznačenými LSL, USL, μ a mezemi μ±3σ: Cp počítá s celou tolerancí, Cpk jen s bližší, kratší vzdáleností]]

### Úloha 7: výpočet v R pro délky výrobků

Vraťme se k původním 25 podskupinám délek v `data1`. Dolní tolerance je 100 mm, horní tolerance 110 mm a cílová délka 105 mm. Diagram průměrů u těchto dat ukázal nestabilitu, takže z nich nelze posoudit způsobilost procesu. Následující výpočet ukazuje dosazení do vzorců; používá všechna původní měření.

Funkce `process.capability()` navazuje na vypočtený regulační diagram. Zde jí zadáme směrodatnou odchylku všech 100 naměřených délek. Příkaz `as.numeric(data1)` vezme délky ze všech řádků tabulky do jedné posloupnosti a `sd(as.numeric(data1))` z nich spočítá směrodatnou odchylku. Ta se může lišit od odhadu založeného na rozdílech uvnitř podskupin, který používá regulační diagram.

```r
sigma <- sd(as.numeric(data1))
process.capability(q_xR, spec.limits = c(100, 110),
                   target = 105, std.dev = sigma)
```

```text

Process Capability Analysis

Call:
process.capability(object = q_xR, spec.limits = c(100, 110),     target = 105, std.dev = sigma)

Number of obs = 100          Target = 105
       Center = 105             LSL = 100
       StdDev = 3.831           USL = 110

Capability indices:

       Value    2.5%   97.5%
Cp    0.4350  0.3745  0.4955
Cp_l  0.4342  0.3595  0.5089
Cp_u  0.4359  0.3611  0.5108
Cp_k  0.4342  0.3451  0.5232
Cpm   0.4350  0.3748  0.4952

Exp<LSL 9.6%	 Obs<LSL 7%
Exp>USL 9.5%	 Obs>USL 3%
```

Ve výstupu jsou `Cp_l` a `Cp_u` indexy pro dolní a horní toleranci. Jejich minimum `Cp_k` odpovídá $C_{pk}$. Hodnoty ostatních charakteristik získáme dosazením do vzorců uvedených výše:

| Charakteristika | Hodnota |
|---|---:|
| $\mu$ | 104,990000 mm |
| $s$ | 3,831014 mm |
| $C_p$ | 0,435046 |
| $C_{pk}$ | 0,434176 |
| $C_{pm}$ | 0,435044 |
| $C_{pmk}$ | 0,434174 |
| míra využití tolerance | 229,860827 % |
| rezerva k bližší mezi | −6,503041 mm |
| $P_z$ | 0,191848 |

Průměr 104,99 mm je téměř shodný s cílem, ale směrodatná odchylka je přibližně 3,831 mm. Šířka $6s$ je větší než tolerance, takže vychází $C_p\doteq0{,}435$ a $C_{pk}\doteq0{,}434$. Problémem tohoto souboru délek je tedy především jejich velké rozptýlení. Záporná rezerva přibližně −6,503 mm znamená, že pásmo $\bar{x}\pm3s$ přesahuje toleranci. Hodnota $P_z\doteq0{,}1918$ vychází z normálního modelu s těmito parametry. Protože proces není stabilní, nelze ji použít jako spolehlivou předpověď podílu vadných výrobků. Výpočet sčítá pravděpodobnosti pod dolní a nad horní tolerancí zvlášť; vztah $2\Phi(-3C_p)$ předpokládá přesné centrování.

### Podmíněný přepočet po odstranění vymezitelné příčiny

Nyní posoudíme odlišnou, podmíněnou variantu: u podskupiny 12 by se musela skutečně zjistit a odstranit vymezitelná příčina. Teprve to by odůvodnilo její vyřazení. Pro zbývajících 24 podskupin se znovu sestaví diagram rozpětí i průměrů. Pokud neukážou nestabilitu a je splněn předpoklad normality, lze přejít k hodnocení způsobilosti.

```r
data1_24 <- data1[-12, ]
qR_24 <- qcc(data1_24, type = "R")
qx_24 <- qcc(data1_24, type = "xbar")
```

Diagramy v podmíněné variantě neukazují bod mimo meze ani signál pravidla pro řady. Pro 96 zbývajících měření použijeme výběrovou směrodatnou odchylku všech hodnot:

```r
sigma24 <- sd(as.numeric(data1_24))
```

Nejprve posoudíme původní tolerance 100–110 mm:

```r
process.capability(qx_24, spec.limits = c(100, 110),
                   target = 105, std.dev = sigma24)
```

```text

Process Capability Analysis

Call:
process.capability(object = qx_24, spec.limits = c(100, 110),     target = 105, std.dev = sigma24)

Number of obs = 96           Target = 105
       Center = 105.2           LSL = 100
       StdDev = 3.695           USL = 110

Capability indices:

       Value    2.5%   97.5%
Cp    0.4511  0.3870  0.5150
Cp_l  0.4717  0.3924  0.5511
Cp_u  0.4304  0.3544  0.5064
Cp_k  0.4304  0.3399  0.5209
Cpm   0.4502  0.3865  0.5138

Exp<LSL 7.8%	 Obs<LSL 5.2%
Exp>USL 9.8%	 Obs>USL 3.1%
```

Potom stejná měření porovnáme se širšími tolerancemi 92–118 mm:

```r
process.capability(qx_24, spec.limits = c(92, 118),
                   target = 105, std.dev = sigma24)
```

```text

Process Capability Analysis

Call:
process.capability(object = qx_24, spec.limits = c(92, 118),     target = 105, std.dev = sigma24)

Number of obs = 96           Target = 105
       Center = 105.2           LSL = 92
       StdDev = 3.695           USL = 118

Capability indices:

      Value    2.5%  97.5%
Cp    1.173  1.0062  1.339
Cp_l  1.193  1.0404  1.346
Cp_u  1.152  1.0037  1.301
Cp_k  1.152  0.9752  1.329
Cpm   1.171  1.0048  1.336

Exp<LSL 0.017%	 Obs<LSL 0%
Exp>USL 0.027%	 Obs>USL 0%
```

V podmíněné variantě už oba diagramy zůstávají bez překročení mezí i bez signálu pravidla pro řady. Obsahuje 96 měření s průměrem přibližně 105,229 mm a směrodatnou odchylkou 3,695 mm. Indexy pro tolerance 100–110 mm však stále leží pod 1. **Stabilní proces nemusí být způsobilý:** jeho šířka $6s$ je přibližně 22,17 mm a do tolerance široké 10 mm se nevejde.

Při širší toleranci 92–118 mm dává stejných 96 měření indexy $C_p\doteq1{,}173$ a $C_{pk}\doteq1{,}152$. Překračují hraniční jedničku, protože se změnil požadavek, s nímž rozměry porovnáváme. Výroba se tím nezlepšila a pro původní toleranci 100–110 mm zůstává závěr nepříznivý. Tyto hodnoty zároveň nedosahují přísnějšího požadavku 1,33.

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
