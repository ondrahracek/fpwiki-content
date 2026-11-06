---
title: "Cloud computing"
course: ipis2k
type: topic
tags: [ipis2k, cloud-computing, iaas, paas, saas]
sources:
  - raw/ipis2k/prezentace.pdf
  - https://learn.microsoft.com/en-ca/azure/security/fundamentals/shared-responsibility
  - https://learn.microsoft.com/azure/virtual-machines/overview
  - https://learn.microsoft.com/en-us/azure/azure-sql/database/sql-database-paas-overview?view=azuresql
created: 2026-11-06
updated: 2026-11-06
---

# Cloud computing

> [!tldr] V kostce
> - Cloud computing znamená pronájem výpočetních a souvisejících zdrojů místo vlastnictví fyzického hardwaru.
> - Model nasazení popisuje uspořádání prostředí. Model služby určuje, co spravuje poskytovatel a co zákazník.
> - S vyšší úrovní služby přebírá dodavatel více provozu, ale zákazník stále odpovídá za svá data, přístupy a nastavení.

> [!example] Aplikace pro objednávky
> Podnik pro ni potřebuje výpočetní výkon, úložiště, síť, zálohy i lidi pro údržbu. Může koupit servery, nebo si zdroje pronajmout. Druhou možnost popisuje **cloud computing**: poskytovatel provozuje fyzickou infrastrukturu a zákazník využívá vybranou kapacitu jako službu.

Cloud není jeden produkt. Může zahrnovat výpočetní zdroje, síť, úložiště i další služby. Nezačínejte proto otázkou „cloud ano, nebo ne“, ale čtyřmi otázkami:

- Jakou **kontrolu** nad prostředím systém potřebuje?
- Kolik **provozní práce** organizace unese?
- Jakou **pružnost** vyžaduje zátěž?
- Jaké **náklady** budou vznikat v čase?

![[ipis2k-cloud-ilustrace-v2.png|Cloud provozovaný na fyzických serverech poskytuje výpočetní výkon, datová úložiště a aplikace.]]

## Od virtuálního stroje ke spuštění funkce

Výpočetní výkon lze zákazníkovi nabídnout v různě vysoké vrstvě abstrakce. Čím nižší vrstvu si zákazník spravuje, tím více má možností prostředí přizpůsobit; současně na něj přechází více běžného provozu.

![[ipis2k-cloud-provoz-v2.png|Virtuální stroj s vlastním operačním systémem, kontejner se sdíleným operačním systémem a kód funkce ve spravovaném běhovém prostředí.]]

| Způsob provozu | Co zákazník dostává | Co zůstává k rozhodnutí |
|---|---|---|
| **Virtuální stroj (VM)** | Softwarově vytvořený počítač s vlastním hostovaným operačním systémem. | Instalace programů, nastavení OS, aktualizace, software a konfigurace. Dává velkou kontrolu i mnoho povinností. |
| **Kontejner** | Aplikaci zabalenou se závislostmi; více kontejnerů sdílí OS hostitele. | Nasazování, škálování, aktualizace a zabezpečení. Usnadní přenos balíčku, ne automaticky celého řešení se sítěmi, daty a službami. |
| **Serverless** | Spravované servery a běhové prostředí; zákazník dodá hlavně kód funkce a spuštění. | Hodí se pro oddělitelnou, netrvalou práci, např. převod nově nahraného souboru. Cena závisí na skutečném běhu. |

Tyto tři způsoby nejsou žebříček, z něhož má každý systém dojít až na konec. VM může být rozumná tam, kde je nutná specifická konfigurace. Kontejnery pomáhají při balení a provozu více částí aplikace. Serverless omezuje správu infrastruktury u jasně vymezených úloh. Volba vychází z požadavků aplikace a z provozní odpovědnosti, kterou je organizace připravena nést.

## Kapacita, škálovatelnost a elasticita

| Pojem | Co znamená | Příklad |
|---|---|---|
| **Škálovatelnost** | Systém lze zvětšit pro vyšší zátěž. | Vertikálně: silnější procesor nebo více paměti jednoho stroje. Horizontálně: více instancí současně. |
| **Elasticita** | Kapacita se podle poptávky přidává i odebírá. | Automatické škálování reaguje na pravidla nebo naměřenou zátěž. |

Škálovatelný systém nemusí být elastický: kapacitu lze zvětšit ručně a natrvalo. Elastický systém se snaží držet kapacitu blízko skutečné potřebě.

U služby s nepravidelnou návštěvností je rozdíl praktický:

- **Vlastní infrastruktura** se dimenzuje předem. Malá nezvládne špičku, příliš velká nechává koupenou kapacitu nevyužitou.
- **Cloudové prostředí** může kapacitu přizpůsobit rychleji, ale stále je nutné plánovat limity, výkon a rozpočet.
- **Spotřeba roste** s další instancí, databázovým výkonem nebo přenesenými daty.

## CapEx, OpEx a náklady v čase

| Model výdaje | Co znamená v IT | Důsledek |
|---|---|---|
| **CapEx** — kapitálové výdaje | Majetek pořízený předem: servery, úložiště, síťové prvky či vybavení vlastního datového centra. | Váže kapitál a vyžaduje předem odhadnout budoucí kapacitu. |
| **OpEx** — provozní výdaje | Průběžná platba za využívané služby. Cloud často přesouvá část nákladů sem: organizace nekupuje celý hardware, platí za službu a spotřebu. | Účetní zachycení záleží na smlouvě a pravidlech organizace; technické rozlišení samo neurčuje zaúčtování. |

**Nákladový kompromis:**

- Vlastní prostředí má obvykle větší počáteční skok a hůře reaguje na krátké výkyvy.
- Cloud snižuje bariéru prvního nasazení a může lépe sledovat kolísající poptávku.
- Cloud **není automaticky levnější**. U stabilní velké zátěže záleží na dlouhodobých cenách, využití vlastního vybavení, přenosu dat, licencích, odborném týmu i nadměrně nastavené kapacitě.
- Náklady se řídí sledováním spotřeby a ověřováním, zda velikost zdrojů odpovídá přínosu systému.

## Dvě nezávislé osy: model nasazení a model služby

> [!tip] Dvě nezávislé otázky
> - **Model nasazení:** jak je prostředí uspořádané?
> - **Model služby:** kdo spravuje které vrstvy?
>
> Hybridní cloud tedy není čtvrtá alternativa k IaaS, PaaS a SaaS.

Model **nasazení** popisuje uspořádání prostředí.

![[ipis2k-cloud-nasazeni-v2.png|Tři modely nasazení: veřejný cloud, privátní cloud a hybridní propojení jejich částí. Veřejný cloud zde neznamená veřejně přístupná data.]]

- **Veřejný cloud** poskytuje sdílené cloudové služby více zákazníkům. Slovo „veřejný“ neznamená, že jsou data veřejná; přístup k datům se řídí nastavením identity, oprávnění a dalších kontrol.
- **Privátní cloud** je prostředí vyhrazené jedné organizaci nebo budované pro její specifické požadavky. Může nabídnout vyšší míru přizpůsobení či kontroly, ale často snižuje pružnost a přináší pevnější náklady.
- **Hybridní cloud** kombinuje části prostředí, například vlastní nebo privátní část s veřejným cloudem. Umožňuje rozdělit úlohy podle požadavků, ale zvyšuje náročnost propojení, správy a dohledatelnosti závislostí.

Při volbě prostředí záleží i na **regionu a umístění dat**. Požadavky organizace, smlouvy nebo použitelné regulace mohou omezovat, kde lze data zpracovávat a ukládat. Je proto potřeba ověřit dostupné regiony a služby; neplyne z toho obecné pravidlo, že určité odvětví vždy musí mít privátní cloud.

Model **služby** naproti tomu určuje, co provozuje zákazník a co poskytovatel. Modely lze kombinovat: aplikace ve veřejném i privátním prostředí může využívat IaaS, PaaS nebo SaaS. Hybridní prostředí proto není čtvrtou kategorií vedle IaaS, PaaS a SaaS.

| Model služby | Co zákazník získává | Co typicky spravuje zákazník |
|---|---|---|
| IaaS — infrastruktura jako služba | virtuální infrastrukturu, například VM, úložiště a síť | operační systém, middleware, aplikaci, data a konfiguraci |
| PaaS — platforma jako služba | spravovanou platformu pro běh aplikace nebo databáze | aplikaci či databázový obsah, data, přístupy a nastavení služby |
| SaaS — software jako služba | hotovou aplikaci | data, uživatele, přístupy a nastavení, které služba zpřístupňuje |

## IaaS, PaaS a SaaS na příkladu databáze

> [!example] Databáze: IaaS versus PaaS
> - **IaaS:** organizace získá VM, instaluje SQL Server a spravuje OS, aktualizace, konfiguraci i databázový software. Má více úprav i více práce.
> - **PaaS:** například Azure SQL Database je spravovaná databázová služba. Poskytovatel zajišťuje aktualizace, zálohy a monitoring platformy; zákazník řeší databázový návrh, výkon použití a aplikaci.
>
> PaaS neznamená „žádná správa“. Zákazník dál určuje přístupy, oprávnění, ochranu dat a konfiguraci služby.

SaaS je hotová aplikace poskytovaná uživatelům. Organizace obvykle neprovozuje její server ani platformu, ale vybírá uživatele, nastavuje role a spravuje vlastní obsah. Vyšší úroveň služby zkracuje provozní řetězec, neodstraňuje odpovědnost za smysluplnou a bezpečnou práci se službou.

![[ipis2k-cloud-odpovednost-v2.png|Zjednodušené rozdělení odpovědností mezi zákazníka a poskytovatele v IaaS, PaaS a SaaS; zákazník ve všech třech případech spravuje data, přístupy a dostupné konfigurace.]]

## Sdílená odpovědnost, závislosti a přenositelnost

**Sdílená odpovědnost neznamená rozpuštění odpovědnosti.**

- **Poskytovatel** provozuje fyzická datová centra a podle modelu služby přebírá další vrstvy.
- **Zákazník** ve všech modelech odpovídá za svá data, identity uživatelů a ovladatelná nastavení.
- **Důsledek:** v PaaS a SaaS není bezpečnost vlastnost, kterou jednou koupí. Slabé přístupy, nevhodné sdílení dat nebo chybná konfigurace mohou zůstat jeho problémem.

### Dostupnost a obnova

Cloud nabízí prostředky pro odolnost, ale jejich existence ještě neznamená, že je konkrétní aplikace správně využívá.

| Prostředek | K čemu slouží |
|---|---|
| **Záloha** | Uchovává kopii pro obnovu dat. |
| **Replikace** | Udržuje další kopii dat; sama nenahrazuje zálohování. |
| **Failover** | Převádí provoz na náhradní část při výpadku. |
| **Redundantní datacentra** | Omezují závislost na jednom místě; záleží na rozmístění a propojení služby. |
| **Obnova po havárii (disaster recovery)** | Spojuje postupy a prostředky pro obnovení služby po závažném narušení. |

Je nutné určit, co zajišťuje poskytovatel, co zákazník nastavuje a jak se ověří obnova. Dostupnost služby a bezpečnost aplikace jsou odlišné otázky. Ani zpráva o kontrolách nebo certifikace poskytovatele sama neprokazuje bezpečnost zákaznické aplikace.

**Multi-cloud** znamená využití více cloudových poskytovatelů. Sám nezaručí odolnost: pokud obě prostředí potřebují stejnou závislou službu, její výpadek může zasáhnout obě. Při návrhu obnovy se proto sleduje celý řetězec závislostí.

### Přenositelnost a závislost na dodavateli

**Vendor lock-in** je závislost na rozhraních, datech, cenách a provozních vlastnostech konkrétního poskytovatele. Není to automaticky chyba: specifická platformní služba může zrychlit dodání a snížit provozní práci.

Před rozhodnutím ověřte:

1. jak se vyexportují data,
2. které části aplikace závisejí na konkrétní službě,
3. jak se otestuje obnova,
4. co by vyžadoval přechod jinam.

Kontejnery mohou snížit překážku přenosu části aplikace, ale samy nevyřeší závislosti na datech, identitách, sítích a spravovaných službách.

## Související stránky

- [[ipis2k|Podnikové informační systémy 2]]
- [[rizeni-informatiky-a-itgc|Řízení informatiky a ITGC]]
- [[rizeni-rizik|Řízení rizik]]

## Reference

NOVÁK, Lukáš. *Podnikové informační systémy 2*. Výuková prezentace. Fakulta podnikatelská VUT v Brně, 2026.

Microsoft. [Shared responsibility in the cloud](https://learn.microsoft.com/en-ca/azure/security/fundamentals/shared-responsibility) — rozdělení odpovědností zákazníka a poskytovatele. Microsoft. [Overview of virtual machines in Azure](https://learn.microsoft.com/azure/virtual-machines/overview) — správa virtuálního stroje. Microsoft. [What is Azure SQL Database?](https://learn.microsoft.com/en-us/azure/azure-sql/database/sql-database-paas-overview?view=azuresql) — příklad spravované databázové platformy.
