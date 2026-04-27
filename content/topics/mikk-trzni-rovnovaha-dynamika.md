---
title: "Tržní rovnováha a její dynamika"
course: mikk
type: topic
tags: [mikk, mikroekonomie, rovnovaha, cobweb, bandwagon, veblen]
sources: [raw/mikk/Prednaska 1. a 2. blok.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Tržní rovnováha a její dynamika

> [!abstract] TL;DR
> **Tržní rovnováha** je stav, ve kterém se nabízené množství rovná poptávanému množství při určité ceně $P_E$, takže poptávka je plně uspokojena, zboží nepřebývá a ceny jsou stálé. V čase se rovnováha **nemusí ustálit triviálně** — Cobweb model ukazuje, že podle vztahu sklonů $D$ a $S$ může cena oscilací **konvergovat**, **trvale oscilovat**, nebo **divergovat** (trh se rozpadá). Vedle ceny působí na obě strany trhu **necenové determinanty** (důchody, technologie, regulace, klima, preference, očekávání), které křivky **posouvají** a tím mění samotnou rovnovážnou polohu. K tomu přistupují **anomálie poptávky** — Veblenův efekt (vyšší cena → vyšší poptávka kvůli signalizaci bohatství) a Bandwagon efekt (poptávka kvůli tomu, že poptávají ostatní) — které lokálně deformují tvar poptávkové křivky a komplikují prognózování.

## 1. Tři atributy rovnováhy

Rovnováha trhu se v teorii definuje **třemi současně platnými znaky**:

1. **Poptávka je plně uspokojena.** Při ceně $P_E$ není žádný spotřebitel, který by chtěl nakoupit a nemohl. Zboží je trvale dostatek pro všechny ochotné platit cenu $P_E$.
2. **Co se nabízí, se také spotřebuje.** Žádný producent nemá neprodané zásoby vznikající z přebytku nabídky — produkce odpovídá realizovanému prodeji.
3. **Ceny jsou stálé.** Neexistuje vnitřní tlak na pohyb ceny ani směrem nahoru (přebytek poptávky), ani směrem dolů (přebytek nabídky).

> [!info] Geometricky
> Bod rovnováhy je průsečíkem křivky poptávky $D$ a křivky nabídky $S$ v rovině $P \times Q$:
> $$Q_D(P_E) = Q_S(P_E) = Q_E$$
> Při $P > P_E$ vzniká **přebytek nabídky** (zásoby tlačí cenu dolů). Při $P < P_E$ vzniká **přebytek poptávky** (nedostatek tlačí cenu nahoru). Tržní mechanismus konverguje k $P_E$.

Tyto tři atributy jsou **idealizací**. V praxi se ptáme, zda jsou některé reálné trhy v rovnováze — bytový trh, trh zdravotní péče či vzdělání mají často **trvalé převisy** jedné strany (fronty na bydlení, čekací doby na lékaře), takže atribut č. 1 nebo č. 2 není naplněn.

> [!note] Proč některé trhy v rovnováze nejsou
> - **Regulace cen.** Pokud stát stanoví cenový strop pod $P_E$ (regulované nájmy), poptávka trvale převyšuje nabídku — vznikají fronty, šedá ekonomika, příplatky pod stolem.
> - **Rigidita mezd a cen.** Pracovní trh nereaguje pružně, zaměstnavatelé nesnižují nominální mzdy ani v recesi (efekt psychologie pracovníků a kolektivních smluv) — vzniká nezaměstnanost.
> - **Asymetrie informací.** U pojištění a zdravotní péče spotřebitel nedokáže ohodnotit kvalitu, takže cena nereaguje hladce na kvalitu.
> - **Veřejné statky a externality.** U statků s pozitivními či negativními externalitami (obrana, vzdělání, znečištění) tržní rovnováha existuje, ale není **společensky efektivní**.
> 
> Ekonom proto rozlišuje **rovnováhu** (matematický stav $Q_D = Q_S$) a **efektivnost** (rovnováha bez deformací externalit a regulací).

## 2. Tvar nabídkové křivky

V základním schématu kreslíme nabídku jako rostoucí lineární funkci $S$. Tento ideál ovšem stojí za to konfrontovat s alternativou $S^*$ — **která je realističtější?**

| typ | tvar | interpretace |
|-----|------|--------------|
| $S$ — lineární | rovnoměrně rostoucí | každá další jednotka má o stejnou částku vyšší mezní náklad |
| $S^*$ — zalomená / strmá | plochá pro nízké $Q$, **prudce roste** u kapacitního stropu | producent má volnou kapacitu, kterou nasazuje za stabilní cenu, ale po jejím vyčerpání náklady prudce rostou |

V řadě reálných odvětví (energetika, výrobní linky, zemědělství s pevnou plochou půdy) je $S^*$ vystihující lépe — proto se v dalším výkladu používá obecná rostoucí křivka, jejíž **lokální sklon** kolem rovnováhy určuje dynamiku přizpůsobení (viz Cobweb).

> [!example] Energetický trh
> Ve špičkovém zatížení sítě (chladná lednová večera v 18:00) se postupně zapojují elektrárny od nejlevnější k nejdražší: jaderné a vodní → uhelné → plynové → špičkové plynové turbíny. Křivka nabídky je proto **schodovitá s prudkým náběhem** v posledních procentech kapacity. Když poptávka v ledové vlně narazí na strmou část $S^*$, **velkoobchodní cena elektřiny vyletí o stovky procent** během několika hodin — přesně to, co popisuje topic [[zdaneni-trhu|Zdanění trhu]] u trhů s nízkou krátkodobou elasticitou nabídky.

Symetricky platí, že tvar **poptávkové křivky** není automaticky lineární. Vedle sebe lze postavit:

- **Zboží, bez něhož se nelze obejít** (potraviny, léky, voda) — strmá poptávka, nízká elasticita; spotřebitel nakoupí téměř totéž množství i při velkém zdražení.
- **Zboží, bez něhož se lze obejít** (luxus, zájmy, restaurace) — plochá poptávka, vysoká elasticita; spotřebitel snadno omezí spotřebu při zdražení.

Tím se otevírá zajímavá otázka: **může poptávka protnout osu X?** Jinými slovy: existuje cena, při které poptávka klesne na nulu? Pro zboží, které lze nahradit, ano — existuje **cena rezervace**, nad níž spotřebitel raději přejde k substitutu. Pro nezbytnosti bez substitutu (voda, kyslík) poptávka nikdy nedopadne na nulu, protože i při astronomických cenách je nutné si nějaké minimum koupit (modeluje se asymptotou).

## 3. Cobweb model — dynamika nastolení rovnováhy

![[mikk-cobweb-3pripady.jpeg|Cobweb model ve třech režimech — stabilní spirála, nestabilní spirála a uzavřený cyklus]]

V základním statickém modelu předpokládáme, že obě strany trhu reagují na cenu **okamžitě**. To je ale často nereálné — typický příklad je zemědělství:

> [!example] Zemědělský cyklus
> Farmář se v dubnu rozhoduje, kolik zasadit, podle **současné** ceny komodity. Sklizeň ale přijde až v září. Pokud byla v dubnu cena vysoká, zasadí všichni farmáři hodně a v září je trh přesycen — cena padne. Příští duben sází farmáři málo, takže v září vznikne nedostatek a cena vyletí. **Cyklus se opakuje.**

### 3.1 Předpoklady modelu

- **Spotřebitelé** reagují na cenu okamžitě: $Q_D^t = D(P_t)$.
- **Producenti** reagují s **jednoperiodovým zpožděním**: $Q_S^t = S(P_{t-1})$.
- Trh se v každém období vyčistí — to, co je vyrobeno, se prodá za cenu, která vyrovná aktuální nabídku s aktuální poptávkou: $Q_S^t = Q_D^t$.

### 3.2 Tři scénáře

Podle vztahu **absolutních hodnot** sklonů poptávky $|D'|$ a nabídky $|S'|$ rozlišujeme tři případy:

**A) Konvergence — stabilní cobweb**

$$|S'| > |D'| \quad \Longleftrightarrow \quad \text{nabídka je strmější než poptávka}$$

Cenové výchylky se v každém kole zmenšují a posloupnost $\{P_t\}$ konverguje k $P_E$. Trajektorie v rovině $P \times Q$ tvoří dovnitř se stahující spirálu — odtud anglický název *cobweb* (pavoučí síť).

**B) Trvalá oscilace — mezní případ**

$$|S'| = |D'|$$

Cena se periodicky střídá mezi dvěma hodnotami $P_a, P_b$ a nikdy se neustálí. Stejně tak množství. V čistě teoretickém modelu nekonečně dlouho.

**C) Divergence — rozpad trhu**

$$|S'| < |D'| \quad \Longleftrightarrow \quad \text{poptávka je strmější než nabídka}$$

Výchylky se v každém kole **zvětšují**, posloupnost $\{P_t\}$ uniká od $P_E$. Trh přestává fungovat — cena buď padne pod nulu (nesmyslná hodnota), nebo vyletí do astronomické výše a producenti či spotřebitelé z trhu vystoupí.

> [!tip] Intuice
> Klíčem je, **kdo silněji reaguje** na cenovou změnu. Pokud producenti reagují na cenovou výchylku méně razantně než spotřebitelé (strmější $S$), výchylka v dalším kole oslabí. Pokud reagují razantněji (plošší $S$ než $D$), přestřelí a výchylka zesílí.

### 3.3 Reálné cykly

- **Vepřový cyklus** (3–4 roky) — klasický příklad ve světové ekonomické literatuře. Cena vepřového kolísá v cyklech odpovídajících reprodukčnímu času prasete.
- **Cyklus na trhu IT specialistů** — vlna zájmu o obor → masivní studium → o 4–5 let později přebytek absolventů → pokles platů → pokles zájmu → nedostatek → růst platů. Iterace.
- **Trh komerčních nemovitostí** — výstavba kanceláří se rozhoduje na základě aktuálních nájmů, dostavba trvá 3–5 let, vznikají přestřelení projekty.
- **Lodní doprava (kontejnerové sazby).** Stavba nové kontejnerové lodi trvá 2–3 roky. V boomu zadají rejdaři masivní objednávky, které dorazí ve chvíli, kdy už cyklus skončil — flotila přebývá, sazby padají na náklady.

### 3.4 Útěk z modelu — racionální očekávání

Cobweb model předpokládá, že producenti naivně extrapolují **současnou cenu** do budoucna. Reálný producent ale ví, že trh cykluje, a může své rozhodnutí upravit. Pokročilejší modely (**racionální očekávání**, Muth 1961) proto formulují:

$$Q_S^t = S(\mathbb{E}[P_t \mid \text{informace v } t-1])$$

Pokud producenti odhad ceny **zlepšují** (sledují celý trh, ne jen vlastní zkušenost), Cobweb cyklus **slábne** nebo zaniká. Empiricky: zemědělské trhy s rozvinutými **futures burzami** mají méně výrazné cykly než trhy bez termínového obchodování — futures cena slouží jako kolektivní racionální odhad budoucí spot ceny.

## 4. Jiná interpretace rovnováhy — posuny v čase

Alternativní pohled: **rovnováha se v čase přemisťuje**. Křivky $D$ a $S$ se postupně posouvají (technologický pokrok, růst populace, změny preferencí) a sledem rovnovážných bodů $(P_1, Q_1), (P_2, Q_2), \dots$ vzniká **trajektorie**:

$$D_1 \cap S_1 \to (P_1, Q_1)$$
$$D_2 \cap S_2 \to (P_2, Q_2)$$
$$D_3 \cap S_3 \to (P_3, Q_3)$$

Pozorovaná data o ceně a množství v čase tedy **nejsou body jedné křivky**, ale stopa posouvajících se rovnováh. Tento problém **identifikace** je centrální při empirickém odhadu poptávkové funkce — nelze prostě regresí proložit body $(P_t, Q_t)$ a tvrdit, že je to poptávka.

## 5. Tři otázky o rovnováze

Před každou aplikací je vhodné položit si tři klasické otázky:

1. **Existuje rovnováha?** Ne každý zadaný pár křivek se vůbec protne v ekonomicky smysluplné oblasti $P, Q \geq 0$. Existuje varianta, kdy **trh nebude fungovat** — minimální cena, za kterou je producent ochoten nabídnout, je vyšší než maximální cena, za kterou je kdokoli ochoten poptat. Trh neexistuje.
2. **Je rovnováha jedinečná?** U netradičních tvarů křivek (Veblenův efekt → poptávka má rostoucí úsek; zalomená nabídka) může existovat **více průsečíků**. Některé jsou stabilní, jiné nestabilní.
3. **Je rovnováha stabilní?** Tedy: pokud se trh ocitne mimo $P_E$, vrátí se? Stabilita souvisí přímo s Cobweb podmínkou — záleží na poměru sklonů $D$ a $S$ v okolí rovnováhy.

## 6. Spotřeba a cena mědi 1880–1998

Historický graf spotřeby a ceny mědi za více než století dává **tři lekce** pro práci s časovými řadami:

1. **Reálná vs. nominální cena.** Nominální cena (v dolarech daného roku) roste téměř monotónně kvůli inflaci. **Reálná cena** (deflátorem převedená na ceny pevného základního roku) má dlouhodobě **stagnující až klesající trend**, přerušený výraznými cykly (ropné šoky 1973/1979, čínský komoditní boom 2003–2008). Bez rozlišení nominální a reálné ceny lze udělat hluboký analytický omyl.
2. **Spotřeba roste**, navzdory stagnující reálné ceně — kombinace růstu světové populace, industrializace a substituce dražších kovů. Jde o **posun poptávky doprava**, který tlačí cenu nahoru, ale je vyvažován technologickým posunem nabídky doprava (efektivnější těžba, recyklace).
3. **Cykly.** Krátkodobé výchylky (5–10 let) jsou kombinací investičního cyklu v dolech, geopolitických šoků (válka v Africe / Latinské Americe), spekulativních pohybů a měnových efektů. **Trend je třeba oddělit od cyklu** (dekompozice časové řady, klouzavé průměry, HP filtr).

> [!warning] Past dat
> Investor, který by v roce 1980 viděl prudký růst nominální ceny mědi a usoudil "cena mědi dlouhodobě roste, koupím", by v reálných cenách prodělal — vrchol roku 1980 byl v reálných cenách překonán až po roce 2005.

### 6.1 Tržní potenciál

Pojem **tržní potenciál** označuje **maximální dosažitelný příjem** $TR = P \cdot Q$ na daném trhu při optimální cenové strategii. V bodě, kde se nachází tržní potenciál, je cenová elasticita poptávky $E_D = 1$ (jednotková elasticita) — odvození viz [[mikk-elasticita-poptavky|Elasticita poptávky (mikK)]]:

$$\frac{dTR}{dP} = 0 \quad \Longleftrightarrow \quad |E_D| = 1$$

Pro odhad tržního potenciálu z historických dat o ceně a množství se používají regresní modely poptávky (lineární, log-log, polynomiální), z nichž se odvodí maximum tržeb. Klíčová **úskalí**:
- data zachycují **rovnovážné body**, ne celou poptávkovou křivku (problém identifikace ze sekce 4);
- nutno **deflátorovat** ceny, aby se neměřila inflace místo cenové elasticity;
- nutno **kontrolovat necenové faktory** (důchody, ceny substitutů) — jinak je odhad zkreslený.

## 7. Necenové faktory ovlivňující nabídku

Posun **celé nabídkové křivky** $S$ doprava (růst $Q$ při dané ceně) nebo doleva (pokles $Q$ při dané ceně) způsobuje šest hlavních determinantů:

| determinant | příklad | směr posunu |
|-------------|---------|--------------|
| **Změny cen vstupů** | růst mzdových nákladů, růst ceny elektřiny | $\uparrow$ vstupy ⇒ $S$ doleva |
| **Vnější výrobní podmínky** | zpřísnění emisních limitů, nová regulace, daň ze sladkých nápojů | regulace ⇒ obvykle $S$ doleva |
| **Technologie a organizace výroby** | Mooreův zákon u čipů, automatizace ve výrobě, štíhlá výroba | pokrok ⇒ $S$ doprava |
| **Klimatické podmínky** | sucho v zemědělství, mírná zima v energetice | výkyvy ⇒ stochastické posuny $S$ |
| **Intenzita konkurence** | vstup nového výrobce, fúze, exit z odvětví | více firem ⇒ $S$ doprava |
| **Očekávání cen** | producent odkládá prodej, čeká vyšší cenu | očekávaný růst ⇒ dnešní $S$ doleva |

> [!info] Daň jako posun S
> Spotřební daň ze surovin nebo z výroby posouvá $S$ vertikálně nahoru o výši daně na jednotku. Nová rovnováha má **vyšší** cenu pro spotřebitele a **nižší** čistou cenu pro výrobce. Rozdělení daňového břemene mezi obě strany závisí na poměru elasticit — viz [[zdaneni-trhu|Zdanění trhu (ImeK)]].

## 8. Necenové faktory ovlivňující poptávku

Posun **celé poptávkové křivky** $D$ způsobuje pět hlavních determinantů:

| determinant | příklad | směr posunu |
|-------------|---------|--------------|
| **Důchody spotřebitelů** | růst reálných mezd | normální zboží ⇒ $D$ doprava; **inferiorní** zboží ⇒ $D$ doleva |
| **Preference** | módní trendy, kulturní vlivy, reklama | preference $\uparrow$ ⇒ $D$ doprava |
| **Očekávání spotřebitelů** | obava z neúrody, růst inflace, panika před lockdownem | očekávaný růst ceny ⇒ dnešní $D$ doprava |
| **Ceny souvisejících statků** | ceny **substitutů** $\uparrow$ ⇒ $D$ daného statku doprava; ceny **komplementů** $\uparrow$ ⇒ $D$ doleva | obojí směr |
| **Počet spotřebitelů** | populační růst, otevření trhu novým zákazníkům | $D$ doprava |

> [!tip] Test souvisejících statků
> Statky $X$ a $Y$ jsou **substituty**, pokud růst ceny $Y$ zvedá poptávku po $X$ (káva vs. čaj). Jsou **komplementy**, pokud růst ceny $Y$ snižuje poptávku po $X$ (auto vs. benzin). Křížová elasticita poptávky to formálně zachytí — kladná pro substituty, záporná pro komplementy.

## 9. Bandwagon efekt

Specifickou anomálií poptávky je **bandwagon effect** ("naskočit do rozjetého vlaku").

**Definice.** Spotřebitel poptává statek **proto, že ho poptávají ostatní**. Užitek z jednotky není funkcí pouze vlastní spotřeby, ale i agregátní spotřeby populace.

**Důsledek pro tržní křivku.** Tržní poptávková křivka **integruje** dva efekty:
1. Standardní cenový efekt — pokles ceny zvyšuje poptávané množství každého jednotlivce.
2. Bandwagonový efekt — pokles ceny zvyšuje agregátní spotřebu, což **dále zvyšuje** ochotu každého jednotlivce nakoupit.

Tržní poptávková křivka je proto **plošší** (více elastická), než by byla bez bandwagon efektu — daný cenový pokles vyvolá větší pohyb $Q$.

**Příklady.**
- **Móda.** Daný kus oblečení nosí "všichni", takže ho chcete také.
- **Sociální sítě.** Hodnota Facebooku/Instagramu je funkcí počtu uživatelů (síťový efekt).
- **Smartphone platformy.** iOS vs. Android — atraktivita každé platformy závisí na počtu uživatelů a vývojářů.
- **Akciové bubliny.** Kupujete proto, že kupují ostatní, ne kvůli fundamentu.

**Implikace pro firmu.** Bandwagon efekt motivuje strategii **rychlé akvizice prvních uživatelů** i za cenu ztrátového ocenění (Spotify, Uber, Airbnb v early-stage). Jakmile je překročen **kritický práh** rozšíření, efekt se sám zesiluje — produkt roste i bez další marketingové podpory.

## 10. Veblenův efekt

Opakem bandwagonu je tzv. **snob effect**, jehož extrémním projevem je Veblenův efekt.

**Definice.** Pro určité **luxusní statky** platí, že **vyšší cena vede k vyšší poptávce**, protože cena slouží jako **signál exkluzivity** a **bohatství**. Poptávková křivka má v některém úseku **pozitivní sklon** — vůbec neplatí standardní zákon klesající poptávky.

### 10.1 Příklad — pleťový krém Dr. Středa

Dermatolog a podnikatel Dr. Středa popsal v rozhovoru pro Lidové noviny (3. 4. 2009):

> Vyráběl jsem regenerační krém s lysozymem, který v obchodě stál **135 Kč**. Obrátil se na mě kamarád, že by chtěl prodávat kosmetiku. Nabídl jsem mu Středův regenerační krém, který dal do jiné lahvičky, oparfémoval a prodával nejdříve za dva, pak za čtyři a nakonec za **šest tisíc Kč**. A prodal jich **mnohem víc**, než já v době, kdy jsem ho prodával po těch 135 Kč.

**Mechanismus.** Spotřebitelka usuzuje na kvalitu z ceny: "drahé krémy musejí fungovat — proč by jinak byly tak drahé?" Cena je heuristikou pro kvalitu, kterou zákaznice nedokáže sama vyhodnotit (chemické složení nepoznáte z lahvičky).

### 10.2 Příklad — šampaňské Perrier-Jouet

(LN 20. 3. 2008) Pernod Ricard nabídl kufřík dvanácti lahví Perrier-Jouet za **50 000 €** — přes 100 000 Kč za láhev. Prodej omezen na "stovku superboháčů" v sedmi zemích. **Vysoká cena je hlavním marketingovým argumentem** — kdyby šampaňské stálo 1 000 Kč, ztratilo by exkluzivitu a poptávka v cílové skupině by klesla.

### 10.3 Empirický průzkum

K dispozici jsou **konkrétní data** z marketingového průzkumu tří výrobců bílého jogurtu (firmy A, B, C, cca 200 respondentů). U výrobce A vychází mezi 10,75 a 11,25 Kč elasticita kolem 0,6 a v pásmu 11,75–13,25 Kč hodnoty 1,9–6,8 — poptávka je **nelineární**, s mnoha přechody, a část úseků se chová netypicky. Demonstruje to, že:

1. **Reálná poptávka není hladká přímka.** I obyčejný jogurt ukazuje cenové prahy a lokální anomálie (preference balení, propagační akce).
2. **Pružnost se mění podél křivky.** Bod elasticity má smysl, ne celá křivka jednou hodnotou.
3. **Empirický odhad je pracný.** Ke spolehlivému odhadu je třeba kontrolovaný experiment (různé ceny, jiné faktory konstantní), což je v terénu téměř nemožné.

### 10.4 Důsledky

- **Poptávková křivka má rostoucí úseky** v určitém cenovém pásmu. Pod prahem exkluzivity i nad horní hranicí majetkových možností je sklon klasický.
- **Více rovnováh.** Pokud poptávka má rostoucí úsek, může protnout nabídku ve více bodech — některé jsou stabilní, jiné nestabilní.
- **Strategie firmy.** Snížení ceny luxusního produktu může **snížit** prodej. Burberry, Tiffany a další luxusní značky aktivně bojují s "downmarketingem".
- **Cenová psychologie.** I mimo segment luxusu spotřebitelé interpretují cenu jako signál kvality (placebo efekt vyšší ceny u vína, léků, vzdělávacích kurzů). Marketing s tím systematicky pracuje (anchoring, premium positioning).

> [!warning] Pozor na zaměnění
> Veblenův efekt nelze ztotožnit s bandwagonem. **Bandwagon**: chci to, protože to chtějí ostatní (masový efekt). **Veblen / snob**: chci to, protože to **nemůžou** ostatní (efekt vzácnosti). Oba jevy ale mohou působit současně — luxusní hodinky kombinují snobskou exkluzivitu s bandwagonovým "noste, co nosí slavní".

## 11. Komparativní statika rovnováhy

Po posunech $D$ či $S$ se trh ustálí v **nové rovnováze**. Cílem komparativní statiky je předpovědět směr změny $P_E$ a $Q_E$.

### 11.1 Posun jediné křivky

| co se stalo | $P_E$ | $Q_E$ |
|------------|:-----:|:-----:|
| $D \uparrow$ (poptávka roste) | $\uparrow$ | $\uparrow$ |
| $D \downarrow$ (poptávka klesá) | $\downarrow$ | $\downarrow$ |
| $S \uparrow$ (nabídka roste) | $\downarrow$ | $\uparrow$ |
| $S \downarrow$ (nabídka klesá) | $\uparrow$ | $\downarrow$ |

### 11.2 Současný posun obou křivek

| scénář | $Q_E$ | $P_E$ |
|--------|:-----:|:-----:|
| $D \uparrow$ a $S \uparrow$ | $\uparrow$ | nejednoznačné — záleží na **velikosti** posunů |
| $D \uparrow$ a $S \downarrow$ | nejednoznačné | $\uparrow$ |
| $D \downarrow$ a $S \uparrow$ | nejednoznačné | $\downarrow$ |
| $D \downarrow$ a $S \downarrow$ | $\downarrow$ | nejednoznačné |

> [!example] Trh chytrých telefonů 2010–2020
> Současně rostla **poptávka** (nový segment uživatelů, růst příjmů, síťový efekt) i **nabídka** (Mooreův zákon, čínští výrobci, úspory z rozsahu). Výsledek: $Q_E$ jednoznačně nahoru (počet smartphonů rostl řádově), $P_E$ smíšeně — průměrná cena mírně klesla, ale rozpětí se rozevřelo (top segment Apple zdražoval, low-end klesal).

### 11.3 Předpovědní modely poptávky

Klíčová otázka zní: "**Jak prognózovat vývoj trhu, například automobilů?**" Praktická odpověď kombinuje:

1. **Trendová složka** — dlouhodobý růst poptávky tažený růstem populace a důchodů (modely IS-LM, makroekonomické projekce).
2. **Cyklická složka** — investiční cykly, finanční cykly, dopady recesí.
3. **Sezónní složka** — u některých statků nezanedbatelná (předvánoční elektronika, jarní automobily).
4. **Strukturální zlomy** — technologické přechody (spalovací motory → elektromobily), regulatorní šoky (emisní normy), generační změny preferencí.

Praktická úskalí: modely lineární regrese selhávají v okamžiku **strukturální změny** trhu — proto je potřeba je doplnit kvalitativními panely, scénářovou analýzou a stresovým testováním předpokladů.

## 12. Strategická poloha trhu

Praktická otázka zní: "**V které pozici byste si přáli trh v budoucnu mít?**" V rovině $P \times Q$ rozeznáváme čtyři schematické polohy podle elasticit:

| poloha | $E_D$ | $E_S$ | charakteristika | příklad |
|--------|-------|-------|------------------|---------|
| 1 | nízká | nízká | strmé obě křivky — trh tuhý, malé výkyvy množství, **velké výkyvy ceny** | léky, energie krátkodobě |
| 2 | nízká | vysoká | spotřebitelé neelastičtí, výrobci pružní — **stabilní cena**, výrobci si pohodlně nastavují marži | pitná voda |
| 3 | vysoká | nízká | spotřebitelé pružní, výrobci tuzí — **velké cenové výkyvy** zatěžují producenty | zemědělské komodity |
| 4 | vysoká | vysoká | obě strany pružné — **stabilní ceny, vysoká likvidita** | vyspělé komoditní burzy |

**Která poloha je pro firmu nejvýhodnější?** Obvykle **poloha 2** — nízká $E_D$ (zákazníci nemohou snadno utéct ke konkurenci ani nepřestanou nakupovat při zdražení) v kombinaci s vysokou $E_S$ (firma sama je flexibilní v reakci na příležitosti). Tato kombinace dává firmě **cenovou sílu** a současně provozní pružnost.

Strategie firmy proto cílí na:
- snížení $E_D$ — diferenciace produktu, budování značky, věrnostní programy, vázané kontrakty;
- zvýšení $E_S$ — flexibilní výrobní kapacity, modulární architektura produktu, dodavatelská diverzifikace.

> [!note] Polohy 1 a 4 z pohledu hospodářské politiky
> **Poloha 1** (oba nízké $E$) je nebezpečná pro stabilitu — drobný šok způsobí velký cenový skok. Stát zde často zasahuje skrze **strategické zásoby** (ropa, zrno) nebo **regulaci ceny**.
> 
> **Poloha 4** (oba vysoké $E$) je ideálem **konkurenčního trhu** — informace se promítají do ceny rychle, alokační efektivita je vysoká. Politika se snaží trhy do této polohy posunout odbouráváním bariér vstupu, transparentností a tvorbou likvidních termínových burz.

## 12.1 Příklad propočtu nové rovnováhy

Mějme lineární poptávku $Q_D = 100 - 2P$ a lineární nabídku $Q_S = -20 + 3P$. Položíme $Q_D = Q_S$:

$$100 - 2P = -20 + 3P \quad \Longrightarrow \quad 5P = 120 \quad \Longrightarrow \quad P_E = 24, \, Q_E = 52.$$

Zavedeme spotřební daň $t = 5$ na jednotku, kterou odvádí výrobce. Nabídka se posune vertikálně nahoru: $Q_S' = -20 + 3(P - 5) = -35 + 3P$. Nová rovnováha:

$$100 - 2P = -35 + 3P \quad \Longrightarrow \quad 5P = 135 \quad \Longrightarrow \quad P_E' = 27, \, Q_E' = 46.$$

Cena pro spotřebitele se zvedla o 3 Kč (z 24 na 27), čistá cena výrobce klesla o 2 Kč (z 24 na 22 = 27 − 5). Daňové břemeno se rozdělilo **3:2 ve prospěch výrobce**, protože poptávka je v okolí rovnováhy strmější (méně elastická) než nabídka. Tento výpočet ilustruje princip **incidence daně**: břemeno nese více ta strana, která hůře ustoupí.

## 13. Návaznosti

Tato strana popsala **statiku** rovnováhy a její **základní dynamiku** (Cobweb). Pokračuje:

- [[mikk-utility-preference|Užitková teorie a preference]] — mikrofundace poptávky: odkud se bere její sklon a posuny.
- [[mikk-rovnovaha-spotrebitele|Rovnováha spotřebitele]] — individuální optimum, ze kterého agregací vzniká tržní poptávka.
- [[poptavka-nabidka|Poptávka a nabídka (ImeK)]] — paralelní výklad ze základního kursu Matematická ekonomie, vhodný k rekapitulaci.
- [[elasticita|Elasticita poptávky]] — kvantifikace sklonů, klíčová pro rozlišení Cobweb scénářů a strategickou polohu.
- [[zdaneni-trhu|Zdanění trhu]] — aplikace komparativní statiky na daňový posun nabídky.

Otevřené téma — **dlouhodobá rovnováha v různých tržních strukturách**:
- [[mikk-monopol-pokrocily|Monopol]] — jeden producent, $P > MC$, perzistentní DWL
- [[mikk-oligopol-cournot-stackelberg|Oligopol Cournot/Stackelberg]] — strategická interakce, $MR = MC$ + reakční křivky
- [[mikk-oligopol-bertrand-cenova-konkurence|Bertrand]] — cenová konkurence, $P = MC$ při homogenním zboží
- [[mikk-monopolisticka-konkurence|Monopolistická konkurence]] — $LAC = AR = P$ v dlouhém období, nulový ekonomický zisk
- [[mikk-cenova-diskriminace|Cenová diskriminace]] — alternativní cenová strategie monopolisty

Pro odhad poptávkové funkce z empirických dat viz [[mikk-odhad-poptavky|Odhad a predikce poptávky]] (ekonometrie, Delphi, dekompozice). Pro pokročilé chápání spotřebitele a substitučního chování viz [[mikk-substitucni-duchodovy-efekt|Substituční a důchodový efekt]] a [[mikk-marshall-hicks-poptavka|Marshallova a Hicksova poptávka]]. Pro zařazení do širšího kurzu viz [[mikk|Mikroekonomie 2]] a referenční [[mikk-vzorce-prehled|přehled vzorců]].

## 14. Shrnutí — co si odnést

1. **Tři atributy rovnováhy** — uspokojená poptávka, vyčerpaná nabídka, stabilní cena. Reálné trhy je často nesplňují.
2. **Cobweb model** — dynamika přizpůsobení závisí na poměru sklonů $|S'|$ vs. $|D'|$: konvergence, oscilace, divergence.
3. **Necenové determinanty** posouvají celou křivku, zatímco změna ceny pohybuje jen po křivce. Tento rozdíl je klíčový pro správnou diagnózu tržních pohybů.
4. **Veblen vs. bandwagon** — anomálie poptávky, které deformují její sklon a komplikují prognózování. V luxusním segmentu může být zákon klesající poptávky **lokálně obrácen**.
5. **Tržní potenciál** je dosažen v bodě jednotkové elasticity poptávky. Pro firmu jde o klíčové vodítko cenové strategie.
6. **Strategická poloha trhu** — kombinace $E_D$ a $E_S$ určuje, jak velkou cenovou sílu má firma a jak stabilní jsou tržní výsledky.
7. **Komparativní statika** umožňuje předpovědět směr změny $P_E, Q_E$ při posunech křivek; současný posun obou stran vyvolává nejednoznačnost u jedné z proměnných.
