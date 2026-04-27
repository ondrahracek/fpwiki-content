---
title: "Wardův model zaměstnanecké firmy"
course: mikk
type: topic
tags: [mikk, mikroekonomie, ward, zamestnanecka-firma, behavior]
sources: [raw/mikk/Mikro KS prednaska 5 2026.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Wardův model zaměstnanecké firmy

> [!tldr] TL;DR
> **Wardův model** (Benjamin Ward, 1958) popisuje firmu vlastněnou a řízenou zaměstnanci. Cílem firmy **není** maximalizace zisku, ale maximalizace **příjmu na jednoho zaměstnance**:
> $$y = \frac{TR - FC}{L} = \frac{PQ - rK_0}{L}$$
> Klíčový (a paradoxní) výsledek: zaměstnanecká firma reaguje na růst ceny **opačně** než kapitalistická — místo aby najímala více pracovníků, **propouští** je. To je hlavní ekonomický paradox modelu a jádro veškeré následné kritiky samosprávných ekonomik.

Wardův model je jeden ze tří kanonických modelů [[mikk-alternativni-cile-firmy|alternativních cílů firmy]] vyučovaných v rámci [[mikk|Mikroekonomie 2]], vedle modelů manažerských (Baumol, Williamson, Marris) a [[mikk-behavioristicke-modely-firmy|behavioristických modelů]] (Cyert–March, Simon).

---

## 1. Historický kontext

Benjamin Ward publikoval v roce 1958 článek *"The Firm in Illyria: Market Syndicalism"* (*American Economic Review*), kde formálně analyzoval ekonomické chování firmy vlastněné svými zaměstnanci. Inspirací byla:

- **Jugoslávský experiment se samosprávou pracovníků** (Tito, od roku 1950): podniky byly formálně ve "společenském vlastnictví" a řízeny **dělnickými radami**, které rozhodovaly o investicích, zaměstnanosti i rozdělení zisku.
- **Hledání třetí cesty** mezi sovětským centrálním plánováním a západním kapitalismem.
- **Tradice utopického socialismu** (Robert Owen, Charles Fourier) a kooperativního hnutí 19. století.

Ward chtěl ukázat, že i samosprávná firma je **racionálním ekonomickým aktérem** — jen s jinou cílovou funkcí. Z toho vyplývají překvapivé predikce, které lze testovat na jugoslávských datech.

---

## 2. Předpoklady Wardova modelu

1. **Vlastníky jsou všichni zaměstnanci.** Firma nemá externí akcionáře; rozhodovacím orgánem je shromáždění zaměstnanců (resp. dělnická rada).
2. **Homogenní práce.** Všichni pracovníci mají stejnou produktivitu, stejný hlas a nárok na stejný podíl. Nejsou rozdíly ve kvalifikaci ani v intenzitě úsilí.
3. **Firma je price-taker.** Přijímá ceny statku $P$ i ceny kapitálu $r$ z trhu, neovlivňuje je.
4. **Krátké období.** Firma vlastní **fixní objem kapitálu** $K_0$. Investice (změna $K$) je v modelu mimo dosah; jediným rozhodovacím proměnnou je **počet zaměstnanců** $L$.

> [!note] Co zůstává implicitní
> Model nepředpokládá altruismus ani solidaritu — zaměstnanci jsou stejně sobečtí jako kapitalista. Jen sdílejí celý čistý příjem firmy, místo aby pobírali fixní mzdu.

---

## 3. Cílová funkce

Cílem firmy je maximalizovat **příjem na jednoho zaměstnance** (resp. na hodinu práce):

$$y = \frac{W + \pi}{L}$$

kde $W$ je celková mzdová suma a $\pi$ je zisk. Roznásobením:

$$y = \frac{wL + PQ - wL - rK_0}{L} = \frac{PQ - rK_0}{L} = \frac{TR - FC}{L}$$

Mzdová složka $wL$ se v zaměstnanecké firmě vyruší — zaměstnanci si **rozdělují celý čistý příjem** (tržby minus fixní náklady na kapitál). Tržní mzda $w$ tedy v cílové funkci vůbec nevystupuje; slouží jen jako **referenční bod** (zaměstnanci by měli pracovat ve firmě jen tehdy, je-li $y > w$).

---

## 4. Technologické omezení

Krátkoběžná produkční funkce s fixním kapitálem $K_0$:

$$Q = f(K_0, L)$$

Protože $K_0$ je dáno, $Q$ závisí už jen na $L$. Model se redukuje na **jedno-vstupový problém** s klesajícími mezními výnosy práce.

Pro numerické příklady se obvykle používá **Cobb–Douglas** s konstantními výnosy:

$$Q = K_0^{1/3} L^{2/3} \quad \text{nebo} \quad Q = 10\sqrt{L \cdot K_0}$$

Předpoklad **klesajícího mezního produktu práce** $f_{LL} < 0$ je nezbytný, jinak by problém neměl vnitřní řešení.

---

## 5. Optimalizační podmínka

Maximalizujeme

$$y(L) = \frac{P \cdot f(K_0, L) - rK_0}{L}$$

První derivace podle $L$ (kvocientový vzorec):

$$\frac{dy}{dL} = \frac{P \cdot f_L \cdot L - (PQ - rK_0)}{L^2} = 0$$

Čitatel = 0:

$$P \cdot f_L \cdot L = PQ - rK_0$$

$$P \cdot f_L = \frac{PQ - rK_0}{L} = y$$

> [!important] Optimální podmínka Wardovy firmy
> $$\boxed{\,P \cdot MP_L = y\,}$$
> Mezní příjmový produkt práce se rovná **průměrnému** příjmu na zaměstnance — ne mzdě.

Intuice: zaměstnanci přijmou nového člena pouze tehdy, pokud jeho příspěvek $P \cdot MP_L$ není menší než stávající průměr — jinak by nový člen "naředil" jejich podíl.

---

## 6. Srovnání s kapitalistickou firmou

![[mikk-wardova-firma.jpeg|Wardova zaměstnanecká firma — srovnání max π (klasická) vs. max π/L (Ward) s L_W* < L_K* a Wardovým paradoxem]]

| | **Kapitalistická firma** | **Wardova firma** |
|---|---|---|
| Cíl | $\max\ \pi = PQ - wL - rK_0$ | $\max\ y = (PQ - rK_0)/L$ |
| FOC pro $L$ | $P \cdot MP_L = w$ | $P \cdot MP_L = y$ |
| Co se rovná meznímu produktu | mzda (externí cena) | průměrný příjem (endogenní) |
| Reakce na $P \uparrow$ | $L \uparrow$ (najmout) | $L \downarrow$ (propustit) |
| Reakce na $r \uparrow$ | $L$ ~ stejné (krátkoběžně) | $L \uparrow$ (FC roste, $y$ klesá) |

Klíčový rozdíl je v tom, že u kapitalisty je referenční hladina pro mezní produkt **exogenní** (mzda určená trhem práce), u Wardovy firmy **endogenní** (průměr, který sama produkuje).

---

## 7. Paradoxní reakce na cenu

Toto je **slavný paradox Wardova modelu**.

- **Kapitalistická firma**: vyšší cena $P$ → vyšší marginální výnos práce → najmout více pracovníků → vyrobit více → kladný sklon nabídky.
- **Wardova firma**: vyšší cena $P$ → roste $y$ pro **stejný** počet pracovníků → optimum se posouvá tam, kde je $y$ ještě vyšší → **propustit pracovníky** → **záporný sklon nabídky**.

Geometricky: funkce $y(L)$ má tvar inverzního U s maximem při $L^*$. Růst $P$ zvedne křivku a **posune maximum doleva** (k nižšímu $L$), protože fixní náklad $rK_0$ se rozkládá na menší vliv.

> [!warning] Anti-Smithův výsledek
> Trh s Wardovými firmami má **klesající nabídku** — vyšší cena znamená nižší produkci. To podkopává standardní mechanismus tržní rovnováhy a vede k makroekonomické nestabilitě.

---

## 8. Numerický příklad

Cobb–Douglas s odmocninou:

$$Q = 10\sqrt{L \cdot K_0}, \quad K_0 = 100 \Rightarrow Q = 100\sqrt{L}$$

Parametry: $r = 1$, $FC = rK_0 = 100$.

Příjem na zaměstnance:

$$y(L) = \frac{100 P \sqrt{L} - 100}{L} = \frac{100 P}{\sqrt{L}} - \frac{100}{L}$$

První derivace:

$$\frac{dy}{dL} = -\frac{50 P}{L^{1{,}5}} + \frac{100}{L^2} = 0$$

$$\Rightarrow L^{0{,}5} = \frac{2}{P} \Rightarrow L^* = \frac{4}{P^2}$$

| $P$ | $L^*$ | $Q$ | $y$ |
|---|---|---|---|
| 1 | 4 | 200 | 25 |
| 2 | 1 | 100 | 100 |
| 4 | 0,25 | 50 | 200 |

Když cena vzroste z $P=1$ na $P=2$: zaměstnanost klesá ze 4 na 1, produkce klesá z 200 na 100, **ale** příjem každého zbylého zaměstnance vzroste z 25 na 100. Pro stávající členy je propuštění kolegů **racionální**.

---

## 9. Důsledky a kritika

1. **Záporný sklon nabídky práce** — anti-Smithův výsledek, makro-nestabilita.
2. **Kapitálová nedostatečnost** — Wardova firma nemá silnou motivaci investovat. Každý nový kapitál $\Delta K$ zvyšuje $rK_0$ a snižuje $y$. Investice se vyplatí jen tehdy, jsou-li externě dotované nebo financované z nesdílených zdrojů.
3. **Vanek (1970)** — *General Theory of Labor-Managed Market Economies*: doporučuje **externí financování investic** (státní banka), aby se obešel underinvestment problém.
4. **Free-rider problém** — viz sekce 14.
5. **Krátké pracovní horizonty** — odcházející zaměstnanec ztrácí podíl na kapitálu, takže preferuje rychlou spotřebu zisku před dlouhodobou akumulací.

---

## 10. Empirické testování

| Případ | Hodnocení |
|---|---|
| **Jugoslávie** (1950–1990) | Stagnační produktivita, chronický underinvestment, vysoká inflace, nezaměstnanost. Většina ekonomů (Estrin, Bartlett) potvrzuje Wardovy predikce. |
| **Mondragón** (Baskicko, ESP) | Úspěšný kooperativní konglomerát (>80 000 zaměstnanců). Funguje proto, že čelí **tržní konkurenci** a má **interní hierarchii** s diferencovanými mzdami. |
| **Kibucy** (Izrael) | Zemědělské kooperativy. Mnohé zanikly nebo se transformovaly; přežívající často spoléhají na státní dotace nebo turistiku. |
| **Worker co-ops** (USA, UK) | Stabilní v nikách (potravinářství, řemeslo), nedosahují měřítka kapitalistických firem. |

---

## 11. Aplikace v moderní době

- **Družstevní firmy**: zemědělská družstva, spotřebitelská družstva (COOP), bytová družstva.
- **Worker cooperatives**: některé tech firmy (Loomio, Ouishare), drobné výrobní podniky.
- **Velké kooperativní korporace**: Mondragón Corporación, Equal Exchange, John Lewis Partnership (UK, employee-owned).
- **Profit-sharing a ESOP** (Employee Stock Ownership Plans): hybridní řešení — zaměstnanci sdílejí zisk, ale ne plně řídí.

Tyto formy přebírají z Wardova modelu **motivační mechanismus** (sdílení zisku), ale obvykle **odstraňují** strukturální slabiny (fixní mzda + bonus, externí kapitál, manažerská hierarchie).

---

## 12. Rozšíření modelu

- **Pejovich (1969)**: dlouhé období s proměnným kapitálem. Predikuje, že Wardova firma bude **systematicky podkapitalizována** vůči kapitalistické firmě se stejnou produkční funkcí.
- **Drèze (1976)**: model s rizikem. Zaměstnanci jsou averzní k riziku a sdílejí volatilitu příjmu, což snižuje optimální velikost firmy.
- **Bonin & Putterman (1987)**: učebnice *Economics of Cooperation and the Labor-Managed Economy* — syntéza tří desetiletí výzkumu.
- **Kremer (1997)**: efektivita výběru členů — kvalitní pracovníci nemají motivaci vstoupit do firmy s méně kvalitními kolegy, protože sdílejí příjem.

---

## 13. Vazba na motivaci a principal-agent

Wardova firma **řeší** klasický [[mikk-alternativni-cile-firmy|principal-agent problém]] mezi vlastníkem a manažerem — protože **zaměstnanec i vlastník jsou tatáž osoba**. Není koho monitorovat zvenčí.

Ale otevírá **dva nové problémy**:

1. **Free-rider problém** uvnitř kolektivu. Každý zaměstnanec sdílí $1/L$ z marginálního výnosu vlastního úsilí, ale nese plnou cenu úsilí. Vznik tendence k **shirkingu** (snižování úsilí). Mondragón to řeší interními bonusy a peer monitoringem.
2. **Horizon problem**. Odcházející členové ztrácejí podíl na akumulovaném kapitálu, takže hlasují proti dlouhodobým investicím.

---

## 14. Klíčové poznatky pro zkoušku

> [!success] Co umět
> 1. **Cílová funkce**: $y = (TR - FC)/L = (PQ - rK_0)/L$. Mzda $w$ se vyruší.
> 2. **Optimální podmínka**: $P \cdot MP_L = y$ (mezní produkt = průměrný příjem, ne mzda).
> 3. **Předpoklady**: zaměstnanci = vlastníci, homogenní práce, fixní $K_0$, price-taker.
> 4. **Paradox**: $P \uparrow \Rightarrow L \downarrow$ (záporný sklon nabídky).
> 5. **Důsledky**: underinvestment, free-riding, horizon problem.
> 6. **Empirie**: Jugoslávie selhala, Mondragón funguje (s tržními principy a hierarchií).

> [!example] Typická úloha
> Cobb–Douglas $Q = 100\sqrt{L}$, $r = 1$, $K_0 = 100$. Najděte optimální $L^*(P)$ a ukažte, že $\partial L^*/\partial P < 0$. Srovnejte s kapitalistickou firmou se mzdou $w = 25$.

---

## 15. Vztah ke zkoušce z MikK

Wardův model je v kurzu **Mikroekonomie 2** pokryt poměrně stručně, ale tvoří **kanonický kontrast** ke kapitalistické firmě a manažerským modelům. U zkoušky se obvykle objevuje:

- **Konceptuální otázka**: rozdíl mezi cílovou funkcí Wardovy a kapitalistické firmy.
- **Matematická otázka**: odvození podmínky $P \cdot MP_L = y$ z maximalizace $y(L)$.
- **Aplikační otázka**: vysvětlit paradoxní reakci na cenu na jednoduchém numerickém příkladu.

Spojení s ostatními tématy: [[mikk-monopol-pokrocily|monopolní cenotvorba]], [[mikk-monopolisticka-konkurence|monopolistická konkurence]] a [[mikk-vzorce-prehled|přehled vzorců MikK]].

---

## Související stránky

- [[mikk|Mikroekonomie 2 (MikK)]] — kurzová stránka
- [[mikk-alternativni-cile-firmy]] — manažerské modely (Baumol, Williamson, Marris)
- [[mikk-behavioristicke-modely-firmy]] — Cyert–March, Simon
- [[mikk-monopol-pokrocily]] — pokročilá analýza monopolu
- [[mikk-monopolisticka-konkurence]] — Chamberlin
- [[mikk-vzorce-prehled]] — přehled klíčových vzorců
