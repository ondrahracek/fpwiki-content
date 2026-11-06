---
title: Řízení informatiky a kontroly ITGC
course: ipis2k
type: topic
tags: [ipis2k, it-governance, itgc, kontroly, rizeni-zmen]
sources: [raw/ipis2k/prezentace.pdf, "https://www.iso.org/standard/27001"]
created: 2026-11-06
updated: 2026-11-06
---

# Řízení informatiky a kontroly ITGC

> [!tldr] V kostce
> - Řízení IT spojuje podnikové cíle, změny a každodenní provoz informačních služeb.
> - Rámce nelze zaměňovat: každý pomáhá řešit jinou řídicí otázku.
> - ITGC se neposuzují jen podle návrhu; důkaz musí ukázat jejich fungování v období.

> [!example] Tři situace, které ukazují smysl řízení IT
> - Změna se dostane do provozu bez testu.
> - Rozhraní potichu vynechá dávku dat.
> - Účet po odchodu pracovníka zůstane aktivní.
>
> Řízení informatiky určuje, jak jim podnik předchází a rozhoduje o nich. **ITGC** (*Information Technology General Controls*) poskytují ověřitelné kontroly nad prostředím, kde systémy fungují.

## A. Řízení a volba nástroje

### Od podnikových cílů k informační strategii

Řízení podnikové informatiky zahrnuje dvě propojené části:

- **rozvoj** — projekty a nové aplikace,
- **provoz** — monitoring, analýzu záznamů, správu infrastruktury a podporu uživatelů.

Smyslem strategického řízení IS/ICT je použít systémy a technologie tak, aby podporovaly hodnotu produktů a služeb podniku.

Informační strategie propojí:

1. **současný stav,**
2. **cílový stav,**
3. **cestu mezi nimi.**

Vedle technologií zohlední bezpečnost, finance, lidi, kvalitu, procesy a návaznost IT projektů na ostatní změny. Nákup aplikace tak není izolované technické rozhodnutí, ale součást podnikové změny.

Strategie se používá také jako:

- **podklad poptávky dodavatelům** — co má pořizované řešení splnit,
- **podklad plánování investic do IT** — které rozvojové záměry financovat,
- **spojnice s ostatními projekty** — například s výrobními změnami, vzděláváním nebo zaváděním norem.

### Rámce: nejdříve otázka, potom název

Rámec není automatické řešení. Pomáhá položit správnou otázku a rozdělit odpovědnost.

| Přístup | Jakou otázku pomáhá řešit |
|---|---|
| PRINCE2 | Jak řídit projekt tak, aby se hlídal čas, náklady, přínosy, rozsah, kvalita a riziko? |
| ITIL | Jak řídit a zlepšovat poskytování IT služeb? |
| COBIT | Jak sladit řízení a kontrolu IT s potřebami organizace? |
| ISO/IEC 27001 | Jak zavést systém řízení bezpečnosti informací s definovanými požadavky? |
| COSO | Jak přemýšlet o interní kontrole a řízení rizik v organizaci? |

Tyto přístupy se **doplňují**, nevybírají jako vzájemně zaměnitelné značky:

- **PRINCE2** je pohled na řízení projektu,
- **ITIL** na IT služby,
- **COBIT** na řízení a kontrolní cíle IT,
- **ISO/IEC 27001** je norma požadavků na řízení bezpečnosti; lze ji implementovat i bez certifikace; certifikát vydává externí certifikační orgán ([ISO/IEC 27001](https://www.iso.org/standard/27001)),
- **COSO** poskytuje širší jazyk pro interní kontrolu a riziko.

U projektu se šest hledisek — čas, náklady, přínosy, rozsah, kvalita a riziko — vzájemně ovlivňuje. Změna rozsahu například může změnit termín, náklady nebo očekávaný přínos. Řízení projektu tedy není administrativní sled kroků, ale vědomé rozhodování o těchto vazbách.

## B. Ověření kontrol ITGC

### Proč se kontroluje právě IT prostředí

ITGC (*Information Technology General Controls*) jsou obecné kontroly nad IT prostředím. Pomáhají zjistit, zda aplikace a infrastruktura fungují v podmínkách, v nichž lze věřit zpracování informací. V auditu se jejich rozsah vymezuje podle organizace, systémů a procesů; ne každá kontrola je relevantní pro každé riziko.

Rozsah se vymezuje ve třech krocích:

1. určit konkrétní podnikový proces a riziko,
2. vybrat aplikace, rozhraní a technické role, které mohou výsledek ovlivnit,
3. až potom zvolit kontroly a důkazy.

Tak se ITGC nezmění v dlouhý seznam stejných otázek bez vztahu k účelu auditu.

Například finanční audit se může ptát, zda lze spoléhat na aplikaci, přes kterou procházejí účetně významné transakce. Jestliže kdokoli může nezdokumentovaně změnit její program nebo má bývalý zaměstnanec stále přístup, samotná správnost několika vybraných transakcí nemusí stačit jako důkaz spolehlivého prostředí.

### Návrh kontroly není její fungování

Kontrola má nejprve dávat smysl ve svém návrhu: určuje odpovědnou roli, činnost, četnost a očekávaný záznam. Poté je nutné ověřit provozní účinnost — zda se skutečně prováděla v posuzovaném období. Schválená směrnice proto sama neprokazuje, že se účty skutečně rušily nebo že se změny skutečně testovaly.

![[ipis2k-itgc-overeni-v2.png|Vlevo pravidlo spojuje odchod pracovníka s blokací účtu; vpravo záznamy představují důkazy o provedení kontroly v posuzovaném období.]]

Při prověřování kontroly auditor spojuje situaci, riziko, kontrolu, důkaz a úsudek. Následující příklady nejsou univerzálními návody na konkrétní nastavení. Ukazují mechanismus, který je potřeba přizpůsobit systému a riziku.

### Přístupová oprávnění

> [!example] Případová karta: účet po odchodu pracovníka
> - **Situace:** pracovník odešel, ale účet zůstal aktivní.
> - **Riziko:** někdo může použít přístup, který už nemá být k dispozici.
> - **Kontrola:** informace o odchodu vyvolá odebrání nebo změnu oprávnění; odpovědná role pravidelně reviduje účty.
> - **Důkaz:** schválení, záznam o změně účtu, seznam oprávnění a výběr skutečných odchodů.
> - **Úsudek:** neposuzuje se jen existence účtu, ale i rozsah oprávnění, použití a dostupnost systému.

Pravidelná revize brání i postupnému hromadění oprávnění při změně rolí. Má ukázat, co oprávnění fakticky dovoluje. To je důležité pro **oddělení pravomocí** (*segregation of duties*, SoD): člověk by neměl sám založit objednávku, schválit ji a zajistit její proplacení.

Další přístupové kontroly pokrývají různé situace:

- **Nový účet a změna role:** existuje schválení a formální evidence přidělených oprávnění.
- **Hesla:** existuje politika a odpovídající nastavení; samotný dokument nestačí.
- **Sdílené administrátorské účty:** sdílení ztěžuje přiřazení akce konkrétnímu člověku.
- **Kmenová data:** změna údajů dodavatele, například bankovního účtu, může ovlivnit následné transakce; je třeba posoudit, kdo ji může provést a jak se kontroluje.

### Provoz, rozhraní a obnova

> [!example] Případová karta: dávkové rozhraní
> - **Situace:** aplikace předává dávku dat, ale nikdo nesleduje, zda doběhla.
> - **Riziko:** cílový systém pracuje s neúplnými nebo zastaralými údaji, aniž by si toho uživatel všiml.
> - **Kontrola:** monitoring zachytí chybu a určí, kdo ji vyřeší.
> - **Důkaz:** provozní záznamy, upozornění, evidence incidentu a doložení nápravy.
> - **Úsudek:** hodnotí se schopnost zachytit a řešit relevantní výpadek, ne pouhá existence rozhraní.

Stejný princip platí pro integritu dat a obnovu ze zálohy. Záloha sama nemusí znamenat obnovitelnost. Důkazem o provozní účinnosti může být zdokumentované ověření obnovy a výsledek, který ukáže, zda lze data a potřebnou službu skutečně vrátit do použitelného stavu. [[bcm|Řízení kontinuity činnosti]] poskytuje širší souvislost plánování obnovy.

**BCP** (*Business Continuity Plan*) je plán zachování nebo obnovení podnikových činností při narušení. **DRP** (*Disaster Recovery Plan*) se zaměřuje na obnovu IT po závažném výpadku. Záloha je jen jeden prostředek obnovy; nenahrazuje plán, odpovědnosti a ověření použitelnosti. Provozní kontroly se týkají také stavu infrastruktury a metodiky řízení provozních rizik.

### Řízení změn

> [!example] Případová karta: změna bez nezávislé kontroly
> - **Situace:** jeden člověk změnu navrhne, naprogramuje, otestuje i nasadí do produkce.
> - **Riziko:** chyba nebo účelová úprava projde bez nezávislého zachycení.
> - **Kontrola:** změna má evidovaný požadavek, odpovídající schválení a test; podle rizika jsou vývoj, testování, schválení a nasazení rozděleny mezi role.
> - **Důkaz:** záznam změny, testovací podklady, schválení a historie nasazení.
> - **Úsudek:** oddělení rolí snižuje riziko; nejde o samoúčelný počet lidí v procesu.

Zvláštní pozornost patří změnám, které mohou ovlivnit finanční data nebo kritický provoz. Nezdokumentovaná změna ztěžuje dohledání příčiny chyby; absence testu zvyšuje pravděpodobnost, že se chyba dostane do produkce.

### Řízení vývoje jako samostatná doména

Řízení změn hlídá konkrétní úpravu a její přechod do provozu. Řízení vývoje navíc řeší, jak podnik vývoj soustavně organizuje:

- **politika a metodika vývoje** určují společný postup,
- **projektové řízení** plánuje práci, odpovědnosti a zdroje,
- **koordinace útvarů a nástrojů** omezuje roztříštěnost postupů napříč firmou.

Případová studie zachytila i neplánování zdrojů a používání různých metodik a nástrojů ve více projektových útvarech. Správně schválená jednotlivá změna proto ještě nedokládá dobře řízený vývoj jako celek.

### Co ukázala případová studie

Případová studie pracovala s **devíti firmami**, z nichž sedm bylo výrobních, jedna z dopravy a skladování a jedna z energetiky. Její četnosti popisují tento konkrétní vzorek; nejsou reprezentativní statistikou českých podniků a nelze z nich odvozovat podíly pro obecnou populaci.

| Oblast | Příklad nálezu | Četnost v devíti firmách |
|---|---|---:|
| Přístupy | chyběla pravidelná revize uživatelských účtů | 5 |
| Přístupy | oprávnění byla příliš široká | 4 |
| Přístupy | u významných aplikací nebylo dostupné potřebné logování | 4 |
| Přístupy | účet zůstal aktivní po odchodu pracovníka | 3 |
| Provoz | neexistoval plán kontinuity činnosti | 3 |
| Provoz | rozhraní mezi aplikacemi nebylo monitorováno | 2 |
| Změny | chyběla evidence změn a jejich testování | 2 |
| Změny | jedna osoba změnu vyvinula, otestovala i zavedla | 2 |

Četnost neříká sama o sobě závažnost. Aktivní účet bývalého zaměstnance například vyžaduje další ověření oprávnění, použití a dostupnosti systému. Auditní závěr proto spojuje nález s konkrétním rizikem, důkazy a okolnostmi organizace — ne pouze s číslem v tabulce.

## Související stránky

- [[audit-informacnich-systemu|Audit informačních systémů]] — kritéria, důkazy a ujišťovací zprávy
- [[rizeni-rizik|Řízení rizik]] — vyhodnocení a ošetření rizik
- [[isms|ISMS]] — systém řízení bezpečnosti informací
- [[bcm|Řízení kontinuity činnosti]] — kontinuita a obnova provozu

## Reference

NOVÁK, Lukáš. *Podnikové informační systémy 2*. Výuková prezentace. Fakulta podnikatelská VUT v Brně, 2026.

- ISO, [ISO/IEC 27001:2022 — Information security management systems](https://www.iso.org/standard/27001).
