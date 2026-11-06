---
title: "Náhodné veličiny, datové soubory a testy hypotéz"
course: mask
type: summary
tags: [mask, statistika, normalni-rozdeleni, testovani-hypotez, r]
sources: ["raw/mask/01 náhodné veličiny.pdf", "raw/mask/01 náhodné veličiny - návod R.pdf", "raw/mask/02 datové soubory.pdf", "raw/mask/02 datové soubory - návod R.pdf", "raw/mask/03 testy hypotéz.pdf", "raw/mask/03 testování hypotéz - návod R 01.pdf", "raw/mask/03 testování hypotéz - návod R 02.pdf", "raw/mask/příklady 01 a 02.docx", "raw/mask/příklady 03.docx"]
created: 2026-10-02
updated: 2026-11-06
---

# Náhodné veličiny, datové soubory a testy hypotéz

[[mask|Aplikovaná statistika]] začíná popisem naměřených hodnot. Průměr, medián a histogram ukážou, jak data vypadají. Rozdělení pravděpodobnosti pomůže popsat jejich náhodné kolísání a statistický test posoudit konkrétní hypotézu.

## Od dat k testu

| Otázka | Co použijeme |
|---|---|
| Jaké výsledky mohou nastat a jak jsou pravděpodobné? | [[nahodne-veliciny-a-rozdeleni\|Náhodnou veličinu a její rozdělení]] |
| Kde je střed dat a jak moc se hodnoty liší? | [[popisna-statistika\|Průměr, medián, rozptyl a směrodatnou odchylku]] |
| Jak data rozdělit a zobrazit? | [[popisna-statistika\|Kvartily, empirickou distribuční funkci a histogram]] |
| Liší se průměry nebo rozptyly dvou výběrů? | [[testovani-hypotez\|t-test nebo F-test, pokud jsou splněny jejich předpoklady]] |
| Jak postupovat, když předpoklady parametrického testu nejsou vhodné? | [[testovani-hypotez\|Wilcoxonovy testy a další neparametrické metody]] |

## Výběr statistického testu

Nejprve rozlišíme, zda máme jeden výběr, dvě nezávislé skupiny, nebo párová měření. Párová jsou například dvě měření provedená na stejných výrobcích. Nezávislé skupiny tvoří různé výrobky nebo různí lidé.

Potom určíme, co chceme porovnat a jaké předpoklady o datech můžeme použít. Nezamítnutí nulové hypotézy neprokazuje, že platí; znamená, že proti ní daná data neposkytla dostatečný důkaz.

## Související stránky

- [[mask|Metody aplikované statistiky]]
- [[nahodne-veliciny-a-rozdeleni|Náhodné veličiny a rozdělení pravděpodobnosti]]
- [[popisna-statistika|Popisná statistika a datové soubory]]
- [[testovani-hypotez|Testování statistických hypotéz]]
- [[mask-r-tahak|masK — Tahák pro R]]

## Reference

KROPÁČ, J. *Statistika A*. 4. vyd. Brno: Fakulta podnikatelská VUT, 2011.
