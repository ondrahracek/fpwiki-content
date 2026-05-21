---
title: "Přirozený monopol a regulace"
course: mikk
type: topic
tags: [mikk, mikroekonomie, prirozeny-monopol, regulace, mrtva-vaha]
sources: [raw/mikk/mik2K prednaska 3 blok 2026.pdf, raw/mikk/Prikady pro KS 5 prednaska reseni 2026.pdf]
created: 2026-04-27
updated: '2026-04-27'
---

# Přirozený monopol a regulace

## TL;DR

**Přirozený monopol** je odvětví, ve kterém **dlouhodobé průměrné náklady (LAC) klesají** v celém relevantním rozsahu poptávky — jeden producent je pak nákladově efektivnější než dva či více. Klasické příklady: distribuce vody, plynu, elektřiny, železniční sítě.

Bez regulace monopolista nasadí cenu $P_M > MC$, vytvoří **náklady mrtvé váhy (DWL)** a sníží přebytek spotřebitele. Cenová regulace na úrovni $P = MC$ však u přirozeného monopolu **není realizovatelná** — firma by měla $AC > MC$, prodělávala by a opustila trh. Praktickým kompromisem je **regulace na úrovni $P_R = AC$**: firma má nulový ekonomický zisk, výstup $Q_R$ leží mezi monopolním $Q_M$ a konkurenčním $Q_C$.

Regulátor naráží na **informační asymetrii** (nezná přesné náklady ani poptávku), **regulatory capture** a **X-inefficiency**. Vedle DWL existují i **společenské náklady monopolu** v podobě lobování, nadměrné reklamy a strategického rozšiřování kapacit (Tullockova kritika rent-seekingu).

> Související: [[mikk|Mikroekonomie 2]] · [[mikk-monopol-pokrocily]] · [[mikk-cenova-diskriminace]] · [[mikk-monopson-mzdova-diskriminace]] · [[mikk-monopolisticka-konkurence]] · [[zdaneni-trhu|Zdanění trhu (ImeK)]] · [[prebytek-spotrebitele-vyrobce|Přebytek (ImeK)]] · [[mikk-vzorce-prehled]] · [[mikk-vzorove-zkousky]]

---

## 1. Definice přirozeného monopolu

Přirozený monopol vzniká tam, kde **technologie produkce vykazuje rostoucí výnosy z rozsahu** v celém pásmu poptávky:

- Funkce dlouhodobých průměrných nákladů $LAC(Q)$ je **klesající** — čím vyšší $Q$, tím nižší jednotkové náklady.
- Mezní náklady $MC(Q)$ leží **pod** $LAC(Q)$ (typický průběh — dokud klesá průměr, leží pod ním mezní).
- Pokud by trh sloužilo více firem, každá by produkovala menší $Q_i$ při vyšším $LAC$ — **celkové společenské náklady by byly vyšší** než u jediného producenta.

Formálně: $C(q_1 + q_2) < C(q_1) + C(q_2)$ pro všechna relevantní rozdělení (subaditivnost nákladové funkce).

### Hlavní zdroje přirozeného monopolu

1. **Vysoké fixní náklady, nízké variabilní** — jakmile je infrastruktura postavena, dodatečná jednotka stojí málo (klasická "duplikace nedává smysl").
2. **Nedělitelnost vstupů** — minimální efektivní velikost provozu je velká vůči trhu.
3. **Síťové efekty** — hodnota služby roste s počtem uživatelů.
4. **Zákonné bariéry** (licence, koncese) — někdy umělé, jindy navazují na fyzickou nemožnost duplikace.

---

## 2. Klasické příklady

### Klasická infrastruktura

- **Distribuce pitné vody a kanalizace** — síť potrubí pod městem; postavit paralelní vodovod by bylo absurdně drahé.
- **Distribuční sítě plynu a elektřiny** — vedení vysokého napětí, plynovody. *Pozn.:* výroba elektřiny dnes konkurenční, ale **distribuce zůstává přirozeným monopolem** (proto v ČR rozdělení ČEZ na výrobu a distribuci, regulace ze strany [ERÚ](https://www.eru.cz)).
- **Železniční tratě a dálnice** — fyzická síť kolejí. Provoz vlaků na ní může být konkurenční (open access), trať sama nikoli.
- **Odpadové hospodářství** ve městě — jeden svozový systém na popelnice je efektivnější než tři paralelní.
- **Kabelová televize / FTTH** — pokládka optického vlákna do každé domácnosti.

### Síťové efekty (digitální éra)

Hodnota služby pro uživatele roste s počtem ostatních uživatelů — typicky **"the winner takes most"** trhy:

- **Sociální sítě** — Facebook/Meta, X, Instagram, TikTok. Nová síť startuje od nuly proti zavedené.
- **Marketplaces** — eBay, Amazon, Booking.com (klasický oboustranný síťový efekt: kupující chtějí prodejce a naopak).
- **Platební systémy** — Visa, Mastercard, Apple Pay.
- **Encyklopedie** — Wikipedia (dobrovolnická, ale stejný princip kumulace obsahu).
- **Operační systémy a aplikační ekosystémy** — Windows, iOS/Android (vývojáři volí platformy s největší uživatelskou základnou).

> **Pozn.:** Síťový monopol je často **dynamický** — Myspace → Facebook → TikTok. Klasická infrastruktura takto nahraditelná zpravidla není.

---

## 3. Geometrie přirozeného monopolu

Klíčový obrázek:

```
P
│   ╲ poptávka (AR)
│    ╲     ╲ MR
│     ╲     ╲
P_M ──┼──────●──────────── monopolní cena
│     │      ╲
P_R ──┼──────────●──────── regulovaná cena (= AC)
│     │              ╲╲
P_C ──┼──────────────────●──── "konkurenční" cena (= MC)
│     │              ╲╲     ╲
│     │      AC ────────────
│     │       MC ──────────────────
│
└─────┴──────┴──────┴──────────── Q
    Q_M    Q_R    Q_C
```

### Interpretace

- **Bez regulace:** Monopolista volí $Q_M$ z podmínky $MR = MC$ a účtuje $P_M$ z poptávkové křivky. Velký zisk, vysoká DWL.
- **Cena = $P_C$ ($MC$):** Společensky efektivní, ale firma vyrábí pod $AC$ → ztráta → opustí trh. **Marginal-cost pricing není u přirozeného monopolu udržitelný.**
- **Regulovaná cena $P_R = AC$:** Firma má nulový ekonomický zisk (zachovává normální výnos kapitálu), výstup $Q_R \in (Q_M, Q_C)$. Je to **second-best řešení**.

> Reziduální DWL při $P_R$ stále existuje (mezi $Q_R$ a $Q_C$), ale je výrazně menší než nemusela by být v neregulovaném monopolu.

---

## 4. Důvody regulace

1. **Bránit zneužívání monopolní síly** — vyšší ceny než $P_R$, nižší kvalita, omezení přístupu.
2. **Univerzální dostupnost** — voda, energie, doprava jsou považovány za základní statky; regulace zajišťuje obsluhu i ekonomicky méně atraktivních lokalit (venkov, malá obec).
3. **Bezpečnost** — energetika, plyn, jaderná technologie vyžadují přísné technické standardy.
4. **Stabilita cen** — energetická inflace má makroekonomické dopady.
5. **Ochrana navazujících trhů** — pokud monopolista vlastní úzké hrdlo (železniční trať, plynovod), může diskriminovat konkurenty na navazujících (obvykle konkurenčních) trzích.

### Hlavní regulační režimy

![[mikk-prirozeny-monopol-regulace.jpeg|Regulace přirozeného monopolu — tři ceny P_M (monopol), P_FC=AC (férová) a P_MC=MC (efektivní s dotovanou ztrátou)]]

| Režim | Princip | Riziko |
|-------|---------|--------|
| **Rate-of-return regulation** (cost-plus) | Cena pokryje náklady + povolený výnos kapitálu | Žádná motivace snižovat náklady (X-inefficiency, Averch-Johnson efekt) |
| **Price-cap regulation** (RPI − X) | Cena se může zvedat o inflaci minus efficiency factor | Tlak na efektivitu, ale riziko podinvestování |
| **Yardstick competition** | Porovnání srovnatelných regulovaných firem | Vyžaduje více srovnatelných subjektů |
| **Antitrust** | Ex-post zákaz zneužití dominance, kontrola fúzí | Pomalejší, soudní spory roky trvají |

```graph
title: Price-cap regulace — vývoj stropu v čase
alt: Graf zobrazuje exponenciální vývoj cenového stropu v závislosti na rozdílu inflace a očekávané efektivity; při kladném rozdílu cap roste, při záporném klesá.
xAxis: { label: "Rok t", domain: [0, 20] }
yAxis: { label: "Strop ceny P_bar", domain: [0, 200] }
params:
  - { name: P0, label: "Počáteční cap", min: 50, max: 150, default: 100, step: 5 }
  - { name: CPI, label: "Inflace CPI", min: 0, max: 0.1, default: 0.03, step: 0.005 }
  - { name: Xx, label: "Efficiency factor X", min: 0, max: 0.1, default: 0.02, step: 0.005 }
curves:
  - { fn: "P0 * pow(1 + CPI - Xx, x)", label: "P_bar(t)", color: "fp-purple" }
  - { fn: "P0", label: "P_0", color: "paper-500" }
```

---

## 5. Praktické problémy regulace

### Informační asymetrie

Regulátor v principu **nezná přesnou nákladovou funkci** firmy ani **skutečnou poptávku**. Firma má motivaci nadhodnotit oboje (vyšší povolená cena). Pro regulační orgány je velice složité přesně stanovit firemní náklady a poptávkovou funkci, protože ty se mohou rychle měnit v závislosti na tržních podmínkách.

### Regulatory capture

Regulátor se postupem času ztotožňuje s perspektivou regulované firmy — sdílí lidi (otáčející se dveře), informační zdroje, profesní jazyk. Empiricky popsáno v sektorech jako americká FCC (Stigler 1971) nebo evropská energetika.

### X-inefficiency

Pokud regulace garantuje výnos nad náklady (cost-plus), firma nemá důvod hledat úspory — provozní neefektivnost se přelije do ceny. Leibensteinův koncept "X-efficiency" označuje rezervu mezi technickou a skutečnou efektivitou.

### Cream-skimming

Pokud regulátor povolí konkurenční vstup do dílčích segmentů přirozeného monopolu, noví hráči si **vyberou pouze ziskové části** (hustě obydlené čtvrti, vysoký objem). Regulovaný incumbent zůstane se ztrátovými segmenty (venkov), kde dotuje univerzální službu — což ho dlouhodobě poškodí. Klasický problém telekomunikační deregulace 90. let.

### Averch-Johnson efekt

Pokud je povolený výnos vázán na **kapitál**, firma nadinvestuje do hmotných aktiv (větší rate base = větší absolutní zisk při stejné % marži). Výsledkem jsou předimenzované elektrárny a sítě.

---

## 6. Náklady mrtvé váhy monopolu

Za vyšší cenu $P_M$ oproti $P_C$ spotřebitel:

- **ztrácí přebytek $A + B$** (oblast nad $P_C$ a pod $P_M$, levá od poptávky),
- výrobce **získává $A - C$** (transfer $A$ ze spotřebitele plus ztráta $C$ v pravé části, kde $MR < MC$ při tlaku na $Q$).

Náklady mrtvé váhy:

$$DWL = B + C = \tfrac{1}{2} (P_M - P_C)(Q_C - Q_M)$$

(za předpokladu lineární poptávky a konstantního $MC$).

DWL je **trvalá ztráta blahobytu** — neztotožňuje se s ničím přebytkem; jednotky $Q_C - Q_M$ se prostě **nevyrobí**, ač by je spotřebitelé byli ochotni koupit za cenu pokrývající mezní náklady.

---

## 7. Společenské náklady monopolu

Klasický přebytkový pohled (Harberger 1954) DWL kvantifikuje "trojúhelníkem". Tullock (1967) a Posner (1975) ale upozorňují, že **skutečné společenské náklady monopolu jsou vyšší** — firmy ochotně utratí část (až celý) potenciálního monopolního zisku na **získání a udržení** monopolního postavení:

- **Lobování (rent-seeking)** — výdaje na ovlivnění legislativy, regulátorů, soudních sporů.
- **Nadměrná reklama** — brand jako bariéra vstupu (sunk cost, který by konkurent musel duplikovat).
- **Strategické rozšiřování kapacit (capacity deterrence)** — předinvestování, aby případný vstupující nedostal prostor.
- **Predatory pricing** — krátkodobé snižování cen pod náklady k vytlačení vstupců.
- **X-inefficiency** — pohodlí monopolisty neoptimalizovat náklady.

> **Tullockův insight:** Pokud je trh o monopolní postavení sám konkurenční (více firem soutěží o úplatky / lobby / reklamu), v limitě se **na rent-seeking utratí přibližně celý monopolní zisk** = obdélník $A$, ne jen trojúhelník $B+C$. Skutečná ztráta blahobytu je pak až několikanásobně vyšší než klasická Harbergerova DWL.

---

## 8. Detailní příklad — Monopol vs. konkurence

Z ručně psaného řešení:

### Zadání

- Poptávka: $P = 100 - 5Q$
- Náklady: $TC = 10Q$ → $MC = 10$, $AC = 10$ (lineární, žádné fixní)

Otázky:

- **(a)** Maximální částka, kterou je firma ochotna zaplatit za získání monopolního postavení?
- **(b)** Náklady mrtvé váhy z monopolizace?
- **(c)** Změna přebytku spotřebitele?

### Monopolní rovnováha

$TR = P \cdot Q = (100 - 5Q)Q = 100Q - 5Q^2$

$MR = \dfrac{dTR}{dQ} = 100 - 10Q$

Z podmínky $MR = MC$:

$$100 - 10Q = 10 \;\;\Rightarrow\;\; Q^M = 9$$

$$P^M = 100 - 5 \cdot 9 = 55$$

Zisk:

$$\pi^M = TR - TC = 9 \cdot 55 - 9 \cdot 10 = 495 - 90 = 405$$

### Konkurenční (efektivní) rovnováha

V dokonalé konkurenci $P = MC$:

$$100 - 5Q = 10 \;\;\Rightarrow\;\; Q^K = 18, \;\; P^K = 10$$

Zisk: $\pi^K = 18 \cdot 10 - 18 \cdot 10 = 0$ (cenoví příjemci, normální výnos zahrnut v $TC$).

### Přebytek spotřebitele

V monopolu:
$$CS^M = \tfrac{1}{2} \cdot Q^M \cdot (100 - P^M) = \tfrac{1}{2} \cdot 9 \cdot 45 = 202{,}5$$

V konkurenci:
$$CS^K = \tfrac{1}{2} \cdot Q^K \cdot (100 - P^K) = \tfrac{1}{2} \cdot 18 \cdot 90 = 810$$

Pokles přebytku spotřebitele monopolizací:
$$\Delta CS = CS^K - CS^M = 810 - 202{,}5 = 607{,}5$$

### Náklady mrtvé váhy

$$DWL = \tfrac{1}{2} (P^M - P^K)(Q^K - Q^M) = \tfrac{1}{2} \cdot (55 - 10) \cdot (18 - 9) = \tfrac{1}{2} \cdot 45 \cdot 9 = 202{,}5$$

```graph
title: Monopolní DWL — D, MC, Q_M, Q_C
alt: Graf ukazuje strmě klesající poptávku, vodorovné mezní náklady a dvě svislé značky pro monopolní a konkurenční množství; trojúhelník mezi nimi je mrtvá ztráta blahobytu.
xAxis: { label: "Q", domain: [0, 25] }
yAxis: { label: "P, MC", domain: [0, 110] }
params:
  - { name: aa, label: "Intercept poptávky a", min: 50, max: 120, default: 100, step: 1 }
  - { name: slope, label: "Sklon poptávky", min: 1, max: 10, default: 5, step: 0.5 }
  - { name: MCc, label: "Mezní náklady", min: 0, max: 30, default: 10, step: 1 }
curves:
  - { fn: "aa - slope*x", label: "D", color: "fp-purple" }
  - { fn: "MCc", label: "MC", color: "paper-700" }
markers:
  - { x: "(aa - MCc)/(2*slope)", label: "Q_M" }
  - { x: "(aa - MCc)/slope", label: "Q_C" }
```

### Odpovědi

| Otázka | Hodnota | Komentář |
|--------|---------|----------|
| **(a) Max. ochota platit za monopol** | **405** | = $\pi^M$. Firma utratí na získání monopolu nejvýše tolik, kolik z něj vydělá. |
| **(b) DWL** | **202,5** | Trvalá ztráta blahobytu — jednotky 9 → 18 se nevyrobí. |
| **(c) Pokles CS** | **607,5** | Z toho **405** transfer na zisk monopolisty + **202,5** čistá DWL. |

### Kontrola — bilance přebytků

Celkový přebytek (CS + zisk) v konkurenci: $810 + 0 = 810$.

Celkový přebytek v monopolu: $CS^M + \pi^M = 202{,}5 + 405 = 607{,}5$.

Rozdíl $810 - 607{,}5 = 202{,}5 = DWL$ ✓

Nebo dohromady:

$$\pi^M + CS^M + DWL = 405 + 202{,}5 + 202{,}5 = 810 = CS^K$$

### Interpretace v kontextu rent-seekingu

Tullockova logika: pokud o monopolní rentu **soutěží** více kandidátů, mohou být ochotni utratit až celých 405 na lobby / reklamu / kapacity. **Skutečné společenské náklady monopolizace** pak činí $405 + 202{,}5 = 607{,}5$ — celý úbytek přebytku spotřebitele. Klasická Harbergerova DWL ($202{,}5$) **podhodnocuje** skutečnou ztrátu.

---

## 9. Politika regulace v praxi

### Česká republika

- **Úřad pro ochranu hospodářské soutěže (ÚOHS)** — antimonopolní úřad. Zakazuje kartelové dohody, zneužití dominance, schvaluje fúze.
- **Energetický regulační úřad (ERÚ)** — reguluje ceny distribuce elektřiny a plynu, dohlíží na trh s teplem.
- **Český telekomunikační úřad (ČTÚ)** — telekomunikace, poštovní služby, frekvenční spektrum.
- **Státní ústav pro kontrolu léčiv (SÚKL)** — cenová regulace léčiv (částečně přirozený monopol patentové ochrany).

### Evropská unie

- **DG COMP** (Generální ředitelství pro hospodářskou soutěž Evropské komise) — globální digitální platformy, fúze nadnárodních firem.
- **Digital Markets Act (DMA)** — od 2024 ex-ante regulace "gatekeeperů" (Google, Apple, Meta, Amazon, Microsoft, ByteDance).

### Známé případy

- **AT&T breakup (1984)** — americký telekomunikační gigant rozdělen na "Baby Bells". Klasický příklad strukturálního zásahu do přirozeného monopolu.
- **Microsoft (1998–2001)** — bundling Internet Exploreru s Windows; antitrustový spor skončil chováním-orientovanou nápravou (consent decree).
- **Google Shopping (EU 2017)** — pokuta 2,42 mld. EUR za upřednostňování vlastního srovnávače.
- **Google Android (EU 2018)** — pokuta 4,34 mld. EUR za vázání aplikací.

---

## 10. Diskuse: kdy regulovat, kdy deregulovat?

### Úspěchy deregulace

- **Telekomunikace 90. let** — rozdělení vertikálně integrovaných incumbents, otevření přístupu k poslední míli, vznik konkurence.
- **Letecká doprava (US Airline Deregulation Act 1978)** — pokles cen, růst přepravených pasažérů, ale i konsolidace a hub-and-spoke.

### Rizika deregulace

- **Kalifornská energetická krize 2000–2001** — částečná deregulace velkoobchodního trhu při zachování maloobchodních cenových stropů + manipulace ze strany Enronu vedla k blackoutům a krachu PG&E.
- **Britská železnice (privatizace 1993)** — fragmentace tratí (Railtrack), bezpečnostní incidenty, postupná renacionalizace infrastruktury (Network Rail 2002, Great British Railways 2024+).

### Klíčové ponaučení

- **Strukturální oddělení** přirozeně-monopolní vrstvy (síť) od konkurenčních vrstev (provoz, retail) je často robustnější než spoléhání na chování.
- **Funkční konkurence** vyžaduje rovný přístup k úzkému hrdlu — proto vertikálně integrovaný incumbent musí být buď **rozdělen**, nebo **přísně regulován** v přístupových podmínkách.
- **Žádná regulace není zdarma** — administrativní náklady, dynamická neefektivita, regulatory capture. Volba je vždy mezi nedokonalým trhem a nedokonalým regulátorem.

---

## 11. Shrnutí pojmů

| Pojem | Definice |
|-------|----------|
| **Přirozený monopol** | Odvětví s klesajícím $LAC$ v celém rozsahu poptávky; jediný producent efektivnější než více. |
| **Subaditivnost nákladů** | $C(\sum q_i) < \sum C(q_i)$ — formální podmínka přirozeného monopolu. |
| **Marginal-cost pricing** | $P = MC$ — efektivní, ale u přirozeného monopolu nerealizovatelné (ztráta). |
| **Average-cost pricing** | $P = AC$ — second-best, firma má nulový zisk, výstup mezi $Q_M$ a $Q_C$. |
| **DWL (mrtvá váha)** | $\tfrac{1}{2}(P_M-P_C)(Q_C-Q_M)$ — trvalá ztráta blahobytu monopolizací. |
| **Rent-seeking** | Výdaje na získání/udržení monopolní renty (lobby, reklama, kapacity). |
| **Regulatory capture** | Regulátor přejímá perspektivu regulované firmy. |
| **X-inefficiency** | Provozní neefektivnost regulované firmy bez tlaku na úspory. |
| **Cream-skimming** | Konkurence na ziskových segmentech, regulovaný incumbent zůstane se ztrátovými. |
| **Price-cap (RPI − X)** | Regulační režim s motivací k efektivitě. |

---

## 12. Související stránky

- [[mikk|Mikroekonomie 2 (MikK)]] — přehled kurzu
- [[mikk-monopol-pokrocily]] — monopolní rovnováha, Lernerův index, monopolní síla
- [[mikk-cenova-diskriminace]] — 1./2./3. stupeň, bundling
- [[mikk-monopson-mzdova-diskriminace]] — zrcadlový případ na trhu vstupů
- [[mikk-monopolisticka-konkurence]] — měkčí formy nedokonalé konkurence
- [[zdaneni-trhu|Zdanění trhu (ImeK)]] — DWL z daně, paralelní analytický nástroj
- [[prebytek-spotrebitele-vyrobce|Přebytek spotřebitele a výrobce (ImeK)]] — geometrie blahobytu
- [[mikk-vzorce-prehled]] — kompletní vzorcový taháček
- [[mikk-vzorove-zkousky]] — typové úlohy ke zkoušce
