---
title: "Regulační diagramy a způsobilost procesu"
course: mask
type: summary
tags: [mask, statistika, regulacni-diagramy, indexy-zpusobilosti, qcc, r]
sources: ["raw/mask/06 regulační diagramy.pdf", "raw/mask/06 regulační diagramy přednáška.pdf", "raw/mask/07 indexy způsobilosti.pdf", "raw/mask/07 indexy způsobilosti - Moodle 2026-11-06.pdf", "raw/mask/návod 06 a 07.pdf", "raw/mask/regulace a indexy způsobilosti příklady.pdf", "raw/mask/6_1.txt", "raw/mask/6_2.txt", "raw/mask/6_3.txt", "raw/mask/6_4.txt", "raw/mask/6_5.txt", "raw/mask/6_6.txt"]
created: 2026-10-02
updated: 2026-11-06
---

# Regulační diagramy a způsobilost procesu

Při kontrole výroby rozlišujeme dvě otázky. **Stabilita** říká, zda se proces v čase chová předvídatelně. **Způsobilost** říká, zda jeho výsledky vyhovují požadovaným tolerancím.

[[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]] na sebe navazují: nejprve posoudíme stabilitu, potom splnění tolerancí. Jde o použití [[mask|aplikované statistiky]] při kontrole jakosti.

## Volba regulačního diagramu

Pro délku nebo hmotnost výrobku používáme diagramy pro měřené hodnoty. Sledujeme u nich jak střed měření, tak jejich rozptýlení.

U počtů potřebujeme rozlišit **vady** a **vadné kusy**. Jedna deska může mít několik suků, ale jeden výrobek počítáme jako vadný kus jen jednou. Typ diagramu dále závisí na tom, zda kontrolujeme stále stejně velké série nebo stejně velkou plochu.

## Signály a tolerance

Bod mimo regulační meze je signál k vyšetření příčiny. Pozorování nelze vyřadit pouze proto, aby diagram vyšel bez signálů. Pokud byla příčina zjištěna a odstraněna, lze odůvodněné vyřazení zahrnout do přepočtu mezí.

Ani stabilní proces nemusí vyhovovat zákazníkovi. Naměřené rozměry mohou stále příliš kolísat nebo ležet mimo požadovaný interval. To posuzujeme pomocí indexů způsobilosti.

Řešené příklady zahrnují délky výrobků, suky na deskách, vady magnetických pásků a vadné tablety. Výpočty v R ukazují volbu diagramu, jeho meze i interpretaci výsledků.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[regulacni-diagramy-a-indexy-zpusobilosti|Regulační diagramy a indexy způsobilosti]]
- [[mask-r-tahak|masK — Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.

MONTGOMERY, D. C. *Introduction to Statistical Quality Control*. 6. vyd. John Wiley & Sons, 2005.

ČSN ISO 8258. *Shewhartovy regulační diagramy*. Praha: Český normalizační institut, 1994.

KUPKA, K. *Statistické řízení jakosti*. Pardubice: TriloByte, 1997.
