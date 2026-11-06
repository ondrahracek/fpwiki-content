---
title: "Regresní analýza a kontingenční tabulky"
course: mask
type: summary
tags: [mask, statistika, regrese, korelace, kontingencni-tabulky, r]
sources: ["raw/mask/04 regresní analýza.pdf", "raw/mask/04 regresní analýza přednáška.pdf", "raw/mask/04 regresní analýza - návod R.pdf", "raw/mask/05 kontingenční tabulky.pdf", "raw/mask/05 kontingenční tabulky přednáška.pdf", "raw/mask/05 kontingenční tabulky - návod R.pdf", "raw/mask/příklady 04 a 05.docx", "raw/mask/04 05 příklady.docx", "raw/mask/příklady regrese.zip", "raw/mask/příklady kontingenční tabulky.zip", "raw/mask/test VZOR.docx"]
created: 2026-10-02
updated: 2026-11-06
---

# Regresní analýza a kontingenční tabulky

Souvislost mezi dvěma údaji můžeme zkoumat různě. U čísel, například délky praxe a produktivity, použijeme regresi a korelaci. U kategorií, například příjmové skupiny a způsobu placení, sestavíme kontingenční tabulku.

Oba přístupy patří do [[mask|aplikované statistiky]], ale odpovídají na jiné otázky.

## Číselné údaje: regrese a korelace

[[regresni-a-korelacni-analyza|Regresní model]] popisuje, jak se mění jedna veličina spolu s jinou. Na datech o produktivitě zaměstnanců lze porovnat přímku s logaritmickou křivkou. U tržeb nebo nákladů mohou lépe vyhovovat jiné tvary funkce.

Po odhadu modelu čteme jeho koeficienty a posuzujeme, jak dobře popisuje data. Kontrolujeme také, zda jsou vhodné předpoklady použitého modelu. Samotná souvislost neprokazuje příčinu.

## Kategoriální údaje: kontingenční tabulky

[[kontingencni-tabulky|Kontingenční tabulka]] obsahuje počty lidí nebo podniků v jednotlivých kombinacích kategorií. Test nezávislosti porovnává tyto počty s tím, co bychom očekávali, kdyby spolu znaky nesouvisely.

Řešené příklady zkoumají příjem domácností a financování nákupů nebo velikost podniku a používání umělé inteligence. Po testu popíšeme sílu vztahu pomocí Cramérova koeficientu. U opakovaného měření stejných osob před změnou a po ní používáme pro párová alternativní data McNemarův test.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[regresni-a-korelacni-analyza|Regresní a korelační analýza]]
- [[kontingencni-tabulky|Kontingenční tabulky]]
- [[mask-r-tahak|masK — Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.
