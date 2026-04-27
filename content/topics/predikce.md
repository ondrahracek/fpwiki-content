---
title: Predikce a prognózování
courses: [ipmrk, irmank]
type: topic
tags: [ipmrk, irmank, predikce, casove-rady, prognozovani, box-jenkins, delphi]
sources: [raw/ipmrk/nn-aplikace.md, raw/ipmrk/ga-vyuziti.md, raw/ipmrk/chaos.md, raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-10
updated: '2026-04-27'
---

# Predikce a prognózování

Předpovídání budoucích hodnot na základě historických dat. Jedna z nejdůležitějších aplikačních oblastí v kurzu [[ipmrk|IpmrK]].

## Co se predikuje

- Akciové indexy
- Měnové kurzy (CZK/USD, USD/EUR)
- Kryptoměny
- Ceny komodit (zlato, ropa, obilí)
- Poptávka, prodeje, výrobní objem

## Metody predikce v kontextu kurzu

- [[umele-neuronove-site|Neuronové sítě]] — přímo se učí vzory z dat a predikují budoucí hodnoty
- [[geneticke-algoritmy|Genetické algoritmy]] — optimalizují parametry predikčního modelu nebo obchodní strategie
- [[fuzzy-logika|Fuzzy logika]] — modeluje expertní pravidla pro rozhodování o predikcích
- [[anfis|ANFIS]] — hybridně kombinuje fuzzy pravidla s učením z dat

## Omezení

- [[teorie-chaosu|Teorie chaosu]] ukazuje, že mnoho systémů je extrémně citlivých na počáteční podmínky → **dlouhodobá přesná předpověď bývá prakticky nemožná**
- Model nedává jistotu, ale informovaný odhad
- Budoucnost je nejistá — model může pracovat s více scénáři

## Hurstův exponent

Rozlišuje charakter časové řady: náhodná (H = 0,5), trendová (H > 0,5), antipersistentní (H < 0,5). Viz [[teorie-chaosu|teorie chaosu]].

## Prognostické metody v kurzu [[irmank|IrmanK]] — Risk management

![[ipmrk-predikce-srovnani.jpeg|Srovnání tří prognostických metod na časové řadě — klouzavý průměr, ARIMA a ANN]]

Prof. Rais používá v expertních systémech ([[expertni-systemy]]) tyto **prognostické metody** pro snížení rizika strategického rozhodování:

### Kvantitativní metody

- **Box-Jenkins (ARIMA)** — autoregresní pohyblivý průměr; klasická metoda time series. Vyžaduje stacionární data.
- **Klouzavé průměry** — vyhlazení šumu, identifikace trendu.
- **Extrapolace trendů** — lineární / kvadratická / exponenciální regrese.
- **Regresní modely** — víceproměnné, lze zahrnout exogenní vlivy (HDP, kurz, sezónnost).
- **Holt-Winters** — exponenciální vyhlazování pro data se sezónností.
- **State-space modely (Kalmanův filtr)** — pro dynamické systémy.

### Kvalitativní metody

- **Brainstorming** — neformální generování ve skupině (4–8 lidí, 30–60 min).
- **Delfská metoda (Delphi)** — strukturovaný expertní panel s anonymními iteracemi do konvergence.
- **Komunikační a prognostické hry** — wargaming, business gaming.
- **Systémová dynamika (Forrester 1961)** — kauzální smyčky, stocks-and-flows.
- **Simulační modely (ekonometrické)** — Monte Carlo simulace ekonomických scénářů.
- **Scenario planning (Shell, 1970s)** — generování několika konzistentních scénářů.

**Kdy použít kvalitativní metody (na rozdíl od kvantitativních):**

- Málo dat (nelze regresně modelovat).
- Strukturní změna (historie nereprezentativní).
- Politické / regulační rozhodnutí.
- Disruptivní technologie.

V kontextu IrmanK se prognózování považuje za **„nástroj snižování rizika v hospodářském životě firmy"** (osnova bod 12). Predikce není nikdy přesná, ale zužuje pásmo nejistoty manažerovi.

## Zdroje v kurzu [[ipmrk|IpmrK]]

- [[ipmrk-nn-aplikace|Neuronové sítě — aplikace]]
- [[ipmrk-ga-vyuziti|Genetické algoritmy — využití]]
- [[ipmrk-chaos|Teorie chaosu]]

## Zdroje v kurzu [[irmank|IrmanK]]

- [[irmank-cast-2|2. část přednášky]]
- [[expertni-systemy]] — FEL-EXPERT shell pro výběr prognostické techniky
