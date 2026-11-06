---
title: "Integrace podnikových aplikací"
course: ipis2k
type: topic
tags: [ipis2k, integrace, eai, middleware, podnikove-aplikace]
sources: [raw/ipis2k/prezentace.pdf]
created: 2026-11-06
updated: 2026-11-06
---

# Integrace podnikových aplikací

> [!tldr] V kostce
> - Oddělené aplikace vytvářejí duplicity dat, zdržují rozhodování a zdražují změny.
> - EAI propojuje dosud samostatné systémy tak, aby spolu mohly řízeně spolupracovat.
> - Přímé vazby fungují pro omezený počet spojení; middleware soustředí předávání a převod dat.

> [!example] Zákazník v několika aplikacích
> Obchodník pracuje v **CRM** (systému pro vztahy se zákazníky), ale platební morálku zákazníka zná účetnictví. Bez propojení musí hledat ve více místech nebo udržovat pomocný index zákazníků. Ten se také může zastarat.
>
> Důsledkem jsou duplicity, rozpory v datech, pomalé rozhodování a ruční předávání.

## Co znamená integrace

**Integrace podnikových aplikací** neboli **EAI** (*Enterprise Application Integration*) propojuje původně nezávislé informační systémy, které mohou být vzájemně nekompatibilní a spravované odděleně. Nejde jen o to, aby mezi nimi „něco teklo“. Cílem je, aby se aplikace dokázaly domluvit, předat si data ve srozumitelné podobě a podpořit práci napříč podnikovým procesem.

Neintegrovaná architektura obvykle znamená, že tytéž údaje vznikají na více místech a mohou se rozcházet. Integrace má být:

- **spolehlivá a výkonná** — předání se neztrácí a nezpomaluje práci,
- **spravovatelná a rozšiřitelná** — změna se nemusí pracně opakovat u každé vazby,
- **ekonomicky obhajitelná** — zvažují se náklady i přínosy; samotná integrace návratnost nezaručuje.

Na integraci se dívají různé role odlišně:

| Pohled | Co řeší |
|---|---|
| Ekonomický | Celkové náklady vlastnictví (TCO): provoz a správa, opravy chyb, školení, změny procesu, hardware, licence i konzultační služby. |
| Vlastník firmy a manažer | Pružnou reakci na změny, informace pro rozhodování a výkazy podle potřeb řízení. |
| Vlastník procesu a liniový manažer | Spolupráci lidí a jednotné, srozumitelné pracovní prostředí. |
| IT | Bezpečné a spolehlivé komunikační kanály, konzistenci dat, správu metadat (údajů o struktuře a významu dat) a nástroje pro údržbu integrační platformy. |

## Tři problémy, které má integrace řešit

### 1. Koordinace dat

Stejná podniková skutečnost může být zadávána na více místech: například informace o novém zaměstnanci v personálním systému, mzdové agendě a podnikovém systému ERP, který sdružuje více podnikových agend. Vazba mezi aplikacemi může změnu předat dál. Jinou možností je data získat, upravit do požadované struktury a uložit je do datového skladu. Tento postup se označuje ETL: data se **extrahují**, **transformují** a **nahrávají** do cílového úložiště.

### 2. Celostní pohled na data

Uživatel nemá mít nutně přístup do každé odborné aplikace, ale může potřebovat její výsledek. Obchodník například zjišťuje platební morálku zákazníka, zatímco účetní transakce jsou mimo jeho běžný systém. Jednotná hlavní platforma, například ERP, nebo analytické zpracování v datovém skladu a Business Intelligence mohou zpřístupnit souhrnný i detailní pohled podle účelu práce.

### 3. Procesní orientace a informace během procesu

Samostatné systémy často neumějí společně provést pracovní tok, uplatnit pravidla ani reagovat na změnu stavu. Propojením existujících aplikací, služeb, workflow a integrační logiky může vzniknout kompozitní aplikace: nový proces skládá z již dostupných částí. S procesní integrací souvisí také sledování podnikových aktivit nad živými daty (BAM), které může nabídnout informaci pro okamžitou reakci, zatímco datový sklad slouží analytickému zpracování.

## Příklad: jedna informace o zákazníkovi

> [!example] Jedna informace o zákazníkovi
> - **Problém:** zákazníci jsou rozptýleni ve více aplikacích a množiny se jen částečně překrývají. Dotaz na jednu aplikaci proto nestačí.
> - **Špatná zkratka:** vedle systémů vznikne pomocný index s identifikátory; i ten potřebuje databázi, vývoj, testování a údržbu.
> - **Úloha integrace:** určit, jak se systémy identifikují, co si předají a kde vznikne společný pohled — ne bez rozmyslu zkopírovat všechna data všude.

## Přímé propojení a middleware

| Varianta | Princip | Co si pamatovat |
|---|---|---|
| **Point-to-point** | Samostatná vazba mezi konkrétní dvojicí aplikací. | Běžná např. mezi personalistikou, mzdami a ERP; s každou další vazbou přibývá vývoj, protokoly a údržba. Může být synchronní i asynchronní — název popisuje uspořádání, ne časování. Při synchronním volání nedostupného cíle se transakce neprovede. |
| **Middleware** | Sdílená mezivrstva přijme data, případně je převede a předá dál. | Přidání aplikace se soustředí do společného místa. Fronta umožní asynchronní předání: odesílající a přijímající nemusí být dostupní současně. |

![[ipis2k-integrace-vazby-v2.png|Stejné podnikové aplikace jsou vlevo propojené samostatnými vazbami point-to-point, vpravo komunikují přes společnou mezivrstvu middleware.]]

> [!important] I přes middleware je nutné řídit rozhraní
> Určete formát a význam dat, ošetřete chyby a sledujte, zda předání opravdu proběhlo. Integrita přenášených dat a monitoring rozhraní jsou proto tématem i pro [[audit-informacnich-systemu|audit informačních systémů]].

## Úrovně integrace

| Úroveň | Jak funguje | Vhodné použití a omezení |
|---|---|---|
| Datová | Přesouvá data mezi úložišti; ETL je vyčistí, transformuje a uloží v cílové struktuře. | Pomáhá s redukcí nákladů a datovým skladem, ale mnoho tabulek zvyšuje náročnost údržby. |
| Uživatelské rozhraní | Robot napodobuje postup uživatele v obrazovkách aplikací. | Pomáhá u starých aplikací nebo tam, kde není zdrojový kód ani jiná cesta; závisí na neměnnosti rozhraní. [[roboticka-automatizace-procesu\|RPA]] je příkladem takové integrace. |
| Aplikační rozhraní | Aplikační programové rozhraní (API) zpřístupňuje data a logiku poskytovanou výrobcem aplikace; nad aplikacemi může stát jednotný portál. | API není totéž co uživatelské rozhraní: API slouží programovému přístupu, portál sjednocuje uživatelský přístup. |
| Business logika | Aplikace si vzdáleně volají vnitřní metody nebo objekty. | Nemusí se v každé aplikaci zvlášť hlídat pravidla uložení dat, ale vyžaduje zásah a znalost vnitřní struktury každé aplikace; u starších systémů to nemusí být možné. |

Volba úrovně je technické i procesní rozhodnutí. RPA dokáže propojit práci přes obrazovky bez přímého zásahu do aplikace, ale není náhradou každého API ani každé datové integrace. Když je potřeba stabilní výměna dat nebo sdílená podniková logika, je třeba posoudit, zda robot pouze neobchází problém, který má řešit vhodnější integrační rozhraní.

## Související stránky

- [[ipis2k|Podnikové informační systémy 2]]
- [[roboticka-automatizace-procesu|Robotická automatizace procesů]]
- [[audit-informacnich-systemu|Audit informačních systémů]]

## Reference

NOVÁK, Lukáš. *Podnikové informační systémy 2*. Výuková prezentace. Fakulta podnikatelská VUT v Brně, 2026.
