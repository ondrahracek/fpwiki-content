---
title: "Přehled metod aplikované statistiky"
course: mask
type: summary
tags: [mask, statistika, r]
sources: ["raw/mask/Detail předmětu.md", "raw/mask/informace k předmětu.docx"]
created: 2026-10-02
updated: 2026-11-06
---

# Přehled metod aplikované statistiky

Při práci s daty nejprve určíme, na jakou otázku chceme odpovědět. Jiný postup použijeme pro popis životnosti výrobků, jiný pro porovnání dvou skupin a jiný pro sledování výroby v čase.

[[mask|Metody aplikované statistiky]] propojují tyto úlohy: od průměru a histogramu přes statistické testy až po regresní modely a kontrolu výrobního procesu.

## Volba metody podle otázky

| Co potřebujeme zjistit | Vhodný postup |
|---|---|
| Jaké hodnoty se v souboru vyskytují a jak jsou rozptýlené? | [[popisna-statistika\|Průměr, medián, směrodatná odchylka, kvartily a histogram]] |
| Jaká je pravděpodobnost určitého výsledku? | [[nahodne-veliciny-a-rozdeleni\|Rozdělení pravděpodobnosti]] |
| Liší se dvě skupiny, nebo může rozdíl vzniknout náhodou? | [[testovani-hypotez\|Statistický test podle typu výběrů a předpokladů o datech]] |
| Jak se mění jedna číselná veličina spolu s druhou? | [[regresni-a-korelacni-analyza\|Regresní model a korelace]] |
| Souvisí spolu dvě kategoriální proměnné? | [[kontingencni-tabulky\|Kontingenční tabulka a test nezávislosti]] |
| Mění se výrobní proces v čase? | [[regulacni-diagramy-a-indexy-zpusobilosti\|Regulační diagram]] |
| Splňuje stabilní proces požadované tolerance? | [[regulacni-diagramy-a-indexy-zpusobilosti\|Indexy způsobilosti]] |

## Jak na sebe metody navazují

Popisná statistika ukáže střed, rozptýlení a tvar dat. Rozdělení pravděpodobnosti pak pomáhá popsat náhodné kolísání. O obojí se opíráme při volbě statistického testu.

Regrese hledá vztah mezi číselnými veličinami, například mezi investicemi a hodnotou produkce. U kategorií, jako je vzdělání nebo způsob platby, používáme kontingenční tabulky.

Při sledování výroby nejprve zkoumáme její stabilitu pomocí regulačního diagramu. Teprve u stabilního procesu posuzujeme, zda jeho výsledky vyhovují tolerancím zákazníka. Stabilní výroba může vyrábět příliš nepřesně; stabilita a způsobilost proto nejsou totéž.

## Výpočty a interpretace

Výsledek výpočtu potřebujeme převést zpět k původní otázce. U průměru uvedeme, co popisuje a v jakých jednotkách. U testu vyhodnotíme p-hodnotu. U regresního modelu vysvětlíme význam koeficientů a u regulačního diagramu popíšeme nalezené signály.

Příkazy pro tyto výpočty shrnuje [[mask-r-tahak|tahák pro R]].

## Reference

1. **KROPÁČ, J.** *Statistika A.* 4. vyd. Brno: Fakulta podnikatelská VUT, 2011. ISBN 978-80-214-4226-9.
2. **KROPÁČ, J.** *Statistika B.* 2. vyd. Brno: Fakulta podnikatelská VUT, 2009. ISBN 978-80-214-3295-6.
3. **KROPÁČ, J.** *Statistika C.* 2. vyd. Brno: Akademické nakladatelství CERM, 2012. ISBN 978-80-7204-789-5.
4. **KUPKA, K.** *Statistické řízení jakosti.* Pardubice: TriloByte Statistical Software, 1997. ISBN 80-238-1818-X.
5. **ČSN ISO 8258.** *Shewhartovy regulační diagramy.* Praha: Český normalizační institut, 1994.
6. **MONTGOMERY, D. C.** *Introduction to Statistical Quality Control.* 6. vyd. John Wiley & Sons, 2005. ISBN 978-0-470-16992-6.
7. **TOŠENOVSKÝ, J., NOSKIEVIČOVÁ, D.** *Statistické metody pro zlepšování jakosti.* 1. vyd. Ostrava: Montanex, 2000. ISBN 80-7225-040-X.


## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]]
- [[popisna-statistika|Popisná statistika a datové soubory]]
- [[testovani-hypotez|Testování statistických hypotéz]]
- [[regresni-a-korelacni-analyza|Regresní a korelační analýza]]
- [[kontingencni-tabulky|Kontingenční tabulky]]
- [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]]
- [[mask-r-tahak|masK — Tahák pro R]]
