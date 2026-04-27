---
title: Umělé neuronové sítě
courses: [ipmrk, irmank]
type: topic
tags: [ipmrk, irmank, neuronove-site, perceptron, backpropagation, klasifikace, predikce]
sources: [raw/ipmrk/nn-teorie.md, raw/ipmrk/nn-vypocet.md, raw/ipmrk/nn-aplikace.md, raw/ipmrk/kniha.md, raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-10
updated: '2026-04-27'
---

# Umělé neuronové sítě

![[nn-vicevrstva-sit.jpeg|Vícevrstvá neuronová síť — vstupní, skryté a výstupní vrstvy]]

Výpočetní model inspirovaný biologickým nervovým systémem. Soustava propojených neuronů, které se z dat učí rozpoznávat vzory, klasifikovat a predikovat.

## Stavební kameny

### Perceptron (umělý neuron)

![[nn-perceptron.jpeg|Perceptron — vstupy, váhy, vážený součet, aktivační funkce, výstup]]

- Vstupy i₁..iₙ × váhy w₁..wₙ → vážený součet + bias → aktivační funkce → výstup
- Matematicky: a = Σ(iⱼ·wⱼ) + b, výstup m = f(a)
- **Váhy** nesou naučenou znalost (kladné posilují, záporné tlumí)
- **Bias** posouvá rozhodovací hranici

### Aktivační funkce

| Funkce | Vzorec | Výstup | Použití |
|---|---|---|---|
| Lineární | m = a | ℝ | Jednoduchý, bez nelinearity |
| Logistický sigmoid | m = 1/(1+e⁻ᵃ) | (0, 1) | Pravděpodobnost, binární klasifikace |
| Hyperbolický tangens | m = tanh(a) | (−1, 1) | Kladné i záporné aktivace |

### Vícevrstvá síť

- **Vstupní vrstva** — přijímá data
- **Skryté vrstvy** — vytvářejí vnitřní reprezentace, zachycují nelinearitu
- **Výstupní vrstva** — konečné rozhodnutí nebo predikce
- **Deep learning** — mnoho vrstev a parametrů, pro složité úlohy s velkým objemem dat

## Učení

### [[backpropagation|Backpropagation]]

![[nn-backpropagation.jpeg|Backpropagation — dopředný průchod a zpětné šíření chyby s úpravou vah]]

1. Dopředný průchod — výpočet výstupu
2. Výpočet chyby (e = cíl − výstup)
3. Zpětné šíření chyby přes vrstvy
4. Úprava vah ve směru snížení chyby
5. Opakování (iterativní proces)

### Praktický postup

1. Připravit data (matice vstupů a výstupů)
2. Zvolit architekturu (počet vrstev, neuronů, aktivační funkce)
3. Rozdělit data na trénovací/testovací (např. 75/25 %)
4. Trénovat a sledovat průběh chyby
5. Kritéria ukončení: min chyba, max iterací, max čas

### Kompromis jednoduchost vs. složitost

- **Podučený model** — příliš jednoduchý, vysoká chyba
- **Přeučený model** — naučí se i šum, nefunguje na nových datech

## Aplikace

- Hodnocení bonity klienta (scoring)
- Oceňování (nemovitosti, auta, produkty)
- Vyhodnocení investic a rizika
- Detekce podvodů (praní peněz, daňové anomálie)
- Rozpoznávání obrazu, písma, zvuku, překlad
- [[predikce|Predikce]] časových řad (akcie, měny, komodity)
- Diagnostika nemocí, autonomní systémy

## Aplikace v řízení rizik (kurz [[irmank|IrmanK]])

V kurzu **Risk management** prof. Rais používá ANN pro **klasifikaci investičních projektů** podle míry realizovatelnosti. Detail viz [[investicni-rozhodovani-bot]].

**Investiční vektor X:**

Každá investice je popsána vektorem $X = (X_1, X_2, ..., X_M)$, kde jednotlivé prvky kódují:

- $X_1$ — typ projektu (energetika / infrastruktura / průmysl).
- $X_2$ — obor (vodní / solární / vítr / fosil).
- $X_3$ — velikost investice (mil USD).
- $X_4$ — geografická lokace (země, region).
- $X_5$ — investující společnost.
- $X_6$ — doba trvání projektu.
- $X_7..X_M$ — účetní data (rozvaha + výsledovka).

**Trénovací matice:**

| Investice | $X_1$ | $X_2$ | ... | $X_M$ | Realizovatelnost |
|---|---|---|---|---|---|
| $Y_1$ | $a_{11}$ | $a_{12}$ | ... | $a_{1M}$ | známá (úspěch / neúspěch) |
| $Y_2$ | $a_{21}$ | $a_{22}$ | ... | $a_{2M}$ | známá |
| ... | ... | ... | ... | ... | ... |
| $Y_N$ | $a_{N1}$ | $a_{N2}$ | ... | $a_{NM}$ | známá |
| $Y_{N+1}$ | $a_{N+1,1}$ | $a_{N+1,2}$ | ... | $a_{N+1,M}$ | **predikce ANN** |

ANN je natrénována na $N$ historických případech (supervised learning) a predikuje realizovatelnost nového investičního projektu $Y_{N+1}$.

**Komplementárnost s GA:**

- ANN se naučí ze vzorků (data-driven).
- [[geneticke-algoritmy|GA]] optimalizují parametry projektu (model-driven).
- Spolu poskytují **dva nezávislé pohledy** na investiční rozhodnutí.

**Caveat:** „Metody AI jsou asistenty, ne náhrada za originální tvůrčí myšlení manažera." ANN klasifikuje, ale **lidský úsudek** zůstává klíčový pro strategické rozhodnutí.

## Propojení s dalšími tématy

- [[anfis|ANFIS]] — hybridní systém: fuzzy struktura + učení neuronové sítě
- [[fuzzy-logika|Fuzzy logika]] — partner v ANFIS
- [[geneticke-algoritmy|Genetické algoritmy]] — mohou optimalizovat architekturu sítě
- [[investicni-rozhodovani-bot]] — ANN klasifikace investičních projektů (kurz IrmanK)
- [[expertni-systemy]] — komplementární AI metoda v risk managementu
- [[predikce]] — ANN pro time-series prognózování

## Kontrolní otázky ke zkoušce

1. Popište metodu a vysvětlete princip neuronových sítí.
2. Popište realizaci a výpočet neuronových sítí na počítači.
3. Jak lze využít neuronových sítí v praxi?
4. Kdy je vhodné použít neuronových sítí?
5. Jaký je správný postup kroků při výpočtu pomocí neuronových sítí?
6. Jaké vrstvy mají neuronové sítě?
7. Jaké jsou typy přenosových funkcí?

## Pojmy k zapamatování

Neuronová síť, učení, testování, vstupní matice, přenosová funkce.

## Zdroje v kurzu [[ipmrk|IpmrK]]

- [[ipmrk-nn-teorie|Neuronové sítě — teorie]]
- [[ipmrk-nn-vypocet|Neuronové sítě — výpočet]]
- [[ipmrk-nn-aplikace|Neuronové sítě — aplikace]]
- [[ipmrk-kniha|Kniha]] — shrnutí kapitoly, kontrolní otázky, pojmy
