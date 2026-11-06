---
title: "Metody aplikované statistiky (masK)"
course: mask
type: course
degree: master
studyYear: 2
semester: winter
tags: [mask, statistika, r, testovani-hypotez, regrese, regulacni-diagramy]
sources: ["raw/mask/Detail předmětu.md", "raw/mask/informace k předmětu.docx", "raw/mask/test VZOR.docx"]
created: 2026-10-02
updated: 2026-11-06
---

# Metody aplikované statistiky (masK)

Aplikovaná statistika pomáhá shrnout naměřená data, porovnat skupiny a hledat souvislosti. Ve výrobě také sleduje, zda se proces v čase mění a zda výrobky splňují požadované rozměry.

## Základní témata

1. [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]] popisují náhodné výsledky, například životnost výrobku. Pomocí rozdělení počítáme pravděpodobnosti a určujeme hodnoty, které se vyskytují jen zřídka.
2. [[popisna-statistika|Popisná statistika a datové soubory]] shrnuje, co jsme naměřili. Průměr a medián popisují střed dat, směrodatná odchylka jejich rozptýlení a histogram tvar rozdělení.
3. [[testovani-hypotez|Testování statistických hypotéz]] pomáhá posoudit, zda pozorovaný rozdíl může být důsledkem náhodného kolísání. Výběr testu závisí na tom, co porovnáváme a jak byla data získána.
4. [[regresni-a-korelacni-analyza|Regresní a korelační analýza]] zkoumá vztahy mezi číselnými veličinami. Regresní model například popisuje, jak souvisí produktivita zaměstnance s délkou jeho praxe.
5. [[kontingencni-tabulky|Kontingenční tabulky]] zachycují počty v jednotlivých kategoriích. Umožňují zkoumat třeba souvislost mezi příjmem domácnosti a způsobem financování nákupů.
6. [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]] odpovídají na dvě různé otázky: je výroba v čase stabilní a vejdou se její výsledky do požadovaných tolerancí?

## Řešené příklady

| Příklad | Co zjišťujeme |
|---|---|
| [[popisna-statistika\|Doba života výrobku]] | průměr, směrodatnou odchylku, medián, kvartily a tvar histogramu |
| [[regresni-a-korelacni-analyza\|Produktivita a délka praxe]] | zda naměřené hodnoty lépe popisuje přímka, nebo logaritmická křivka |
| [[kontingencni-tabulky\|Příjmy domácností a financování nákupů]] | zda spolu oba znaky souvisejí a jak silná je souvislost ve výběru |
| [[regulacni-diagramy-a-indexy-zpusobilosti\|Rozměry výrobků a počty vadných kusů]] | který diagram použít, jak číst jeho signály a jak posoudit způsobilost výroby |

## Výpočty v R

U řešených příkladů je zadání dat oddělené od výpočtu. Jednotlivé kroky ukazují sestavení modelu nebo diagramu a potom přečtení výsledku.

[[mask-r-tahak|Tahák pro R]] shrnuje příkazy pro načtení dat, statistické testy, regresi a regulační diagramy. U jednotlivých metod ukazuje také nastavení, která mohou změnit výsledek.

## Přehledy metod

- [[mask-detail-predmetu|Přehled metod aplikované statistiky]] — propojení témat a volba metody podle otázky.
- [[mask-prednasky-veliciny-data-testy|Náhodné veličiny, datové soubory a testy hypotéz]] — od popisu dat k rozhodování pomocí testů.
- [[mask-prednasky-regrese-kontingence|Regresní analýza a kontingenční tabulky]] — vztahy mezi číselnými i kategoriálními údaji.
- [[mask-prednasky-regulace-zpusobilost|Regulační diagramy a způsobilost procesu]] — stabilita výroby a splnění tolerancí.
