---
title: "Dokumentární akreditiv"
course: irmank
type: topic
tags: [irmank, akreditiv, letter-of-credit, exportni-financovani, banky, dokumenty]
sources: [raw/irmank/Řízení rizik druhá část.ppt]
created: 2026-04-27
updated: '2026-04-27'
---

# Dokumentární akreditiv

> [!info] TL;DR
> **Dokumentární akreditiv** (Letter of Credit, L/C) je **bankovní zajištění** mezinárodní platby: banka kupujícího se písemně zavazuje zaplatit prodávajícímu po předložení **přesně specifikovaných dokumentů** (faktura, konosament, osvědčení o jakosti, pojistka aj.). Závazek banky **nezávisí na vůli kupujícího** — banka platí proti splnění formálních podmínek dokumentů, nikoli proti zboží. Jde o **nejbezpečnější platební nástroj v exportu**, ale je administrativně náročný a dražší než běžný převod, takže se používá zejména u rizikových destinací, nových obchodních partnerů a velkých kontraktů.
>
> ---

## Definice a právní rámec

**Letter of Credit (L/C)** je písemný, právně závazný platební instrument, kterým se **vydávající banka kupujícího** (issuing bank) zavazuje zaplatit beneficientovi (prodávajícímu) sjednanou částku po předložení dokumentů odpovídajících znění akreditivu.

**Právní úprava:**

- **§ 689 a násl. obchodního zákoníku** — domácí (česká) úprava smlouvy o otevření akreditivu.
- **UCP 600** (Uniform Customs and Practice for Documentary Credits) — mezinárodní pravidla vydaná **Mezinárodní obchodní komorou (ICC)**, platná od roku 2007. UCP 600 je standardně inkorporována do textu L/C odkazem.
- **eUCP** — doplněk UCP 600 pro elektronické předkládání dokumentů.
- **ISBP** (International Standard Banking Practice) — metodická příručka ICC pro kontrolu dokumentů bankami.

**Klíčový princip — separace dokumentů od zboží:**

> Banka platí proti **dokumentům**, ne proti zboží.

Pokud předložené dokumenty splňují všechny podmínky akreditivu → banka **musí** zaplatit. Pokud byť jen jediný dokument vykazuje formální diskrepanci → banka platbu **odmítne**, i kdyby zboží bylo bezvadné. Tato izolace závazku banky od skutečného obchodu je podstatou nástroje a jeho silnou i slabou stránkou zároveň.

---

## Odvolatelný × neodvolatelný akreditiv

| typ | charakteristika | použití |
|-----|-----------------|---------|
| **Odvolatelný (revocable)** | Kupující/issuing bank může jednostranně zrušit nebo změnit bez souhlasu prodávajícího. | **Vzácný v praxi** — neposkytuje prodávajícímu žádnou skutečnou záruku, jeho použití signalizuje slabou vyjednávací pozici exportéra. |
| **Neodvolatelný (irrevocable)** | Nelze jednostranně změnit ani zrušit; každá změna vyžaduje souhlas všech stran (kupující, prodávající, issuing bank, příp. potvrzující banka). | **Standard v ČR a EU.** Banka má pevný, vymahatelný závazek platby. |

**Důležitý detail UCP 600:** pokud akreditiv **výslovně neuvádí** typ, považuje se automaticky za **neodvolatelný**. Toto je opačné pravidlo než v dřívějším UCP 500.

V praxi se odvolatelný akreditiv prakticky nevyskytuje — exportér by ho neakceptoval jako dostatečnou zástavu.

---

## Aktéři a 7-step flow

![[irmank-akreditiv-flow.jpeg|Princip funkce dokumentárního akreditivu — 7 kroků mezi 4 aktéry]]

### Aktéři (4 strany)

1. **Kupující (importér)** — žadatel akreditivu (**applicant**). Iniciuje proces, financuje akreditiv, přebírá zboží.
2. **Banka kupujícího (issuing bank)** — vydávající/otevírající banka. Vystavuje L/C, nese hlavní závazek platby vůči prodávajícímu.
3. **Avizující (případně potvrzující) banka** — banka prodávajícího v jeho zemi (**advising / confirming bank**). Doručuje akreditiv beneficientovi, kontroluje dokumenty, předává platbu. Pokud akreditiv **potvrdí**, ručí za platbu i nezávisle na issuing bank.
4. **Prodávající (exportér)** — beneficient (**beneficiary**). Plní dodávku, předkládá dokumenty, přijímá platbu.

### 7 kroků akreditivního flow

1. **Smlouva o obchodu.** Kupující a prodávající uzavřou kupní smlouvu, ve které dohodnou, že platba proběhne formou neodvolatelného dokumentárního akreditivu. Smlouva specifikuje Incoterms, zboží, cenu, dodací lhůty a požadované dokumenty.
2. **Žádost o otevření akreditivu.** Kupující požádá svou banku (issuing bank) o vystavení L/C ve prospěch prodávajícího. Banka prověří úvěruschopnost kupujícího a způsob krytí (viz sekce „Domácí banky").
3. **Otevření akreditivu.** Issuing bank vystaví L/C podle SWIFT zprávy MT700 a odešle ho avizující bance v zemi prodávajícího.
4. **Avizace prodávajícímu.** Avizující banka ověří pravost L/C, přeloží/předá ho prodávajícímu. Prodávající nyní zná **přesné znění** podmínek a požadovaných dokumentů.
5. **Dodávka zboží.** Prodávající vyrobí/odešle zboží podle smlouvy, sestaví všechny dokumenty (faktura, konosament, pojistka, osvědčení o původu atd.).
6. **Předložení dokumentů.** Prodávající předloží avizující bance kompletní sadu dokumentů ve sjednané lhůtě (typicky max. 21 dnů od datumu vystavení dopravního dokumentu, ne-li v L/C uvedeno jinak).
7. **Platba.** Avizující banka **kontroluje dokumenty** vůči znění L/C. Pokud jsou v pořádku, předá je issuing bance, ta platí (přes avizující banku) prodávajícímu. Issuing bank pak zatíží účet kupujícího a předá mu dokumenty, se kterými si kupující v přístavu vyzvedne zboží.

---

## Požadované dokumenty

Standardní sada dokumentů u plnohodnotného L/C:

| dokument | účel |
|----------|------|
| **Komerční faktura** (commercial invoice) | Daňový a obchodní doklad, základ pro celní hodnotu. |
| **Osvědčení o jakosti** (quality certificate) | Potvrzení, že zboží splňuje sjednanou specifikaci. |
| **Konosament** (bill of lading, B/L) | Námořní dopravní dokument, představuje vlastnické právo ke zboží. |
| **Letecký nákladní list** (airway bill, AWB) | Letecký dopravní doklad (nepřevoditelný). |
| **Železniční nákladní list** (CIM / SMGS) | Dokument pro železniční přepravu. |
| **Pojistka** (insurance certificate / policy) | Často povinná u Incoterms CIF a CIP. |
| **Dodací list / packing list** | Detailní obsah zásilky, hmotnosti, rozměry. |
| **Osvědčení o původu zboží** (certificate of origin) | Pro celní řízení a preferenční sazby. |
| **Inspekční certifikát** (SGS, Bureau Veritas) | Nezávislá inspekce kvality a kvantity před nakládkou. |
| **Celní deklarace** (export declaration) | Potvrzení o vyclení v zemi vývozu. |

### Strict compliance (princip přísné shody)

Banka kontroluje dokumenty **přesně podle znění L/C**. I drobná diskrepance vede k odmítnutí:

- **Typo** v názvu firmy nebo adrese.
- **Nesprávné datum** (datum nakládky pozdější než L/C expiry, datum vystavení dokladu po datumu předložení).
- **Chybějící podpis** nebo razítko.
- **Nesoulad částky** (faktura zaokrouhlená, L/C uvádí přesnou částku).
- **Neodpovídající Incoterms** mezi fakturou a L/C.
- **Nesprávný popis zboží** — i jediné slovo navíc.

Pokud banka diskrepanci najde, vystaví **discrepancy notice** a buď platbu odmítne, nebo požádá kupujícího o **waiver** (souhlas s diskrepancí). V praxi se odhaduje, že **až 70 % prvních předložení** vykazuje nějakou diskrepanci.

---

## Výhody pro příjemce (prodávajícího/exportéra)

- **Jistota platby.** Závazek nese **banka**, ne kupující. I když importér zbankrotuje nebo odmítne převzít zboží, banka platí proti dokumentům.
- **Obchodovatelnost L/C.** Exportér může předložit otevřený L/C své bance jako kolaterál pro provozní úvěr (**post-shipment finance**) nebo pre-shipment financování výroby.
- **Garance compliance kupujícího.** Kupující si nemůže dovolit nedodržet sjednané podmínky — pokud chce zboží, musí spolupracovat (například prodloužit L/C, akceptovat amendmenty).
- **Snížení politického rizika.** Pokud je L/C **potvrzen** (confirmed) bankou v zemi prodávajícího, ručí tato banka i v případě selhání issuing bank nebo politické krize v zemi importéra (moratorium, sankce, devizové omezení).
- **Strukturovaný proces.** Jasný harmonogram, definované dokumenty, kontrolní body — nižší prostor pro improvizaci a spory.

---

## Výhody pro příkazce (kupujícího/importéra)

- **Compliance prodávajícího** s dodacími podmínkami. Banky kontrolují dokumenty, takže prodávající nemůže obdržet platbu bez splnění formálních podmínek (datum nakládky, kvalita, množství podle inspekčního certifikátu).
- **Lepší vyjednávací pozice.** Schopnost otevřít L/C signalizuje finanční stabilitu — kupující zpravidla získá **lepší ceny** nebo dodací podmínky než při platbě předem.
- **Strukturovaná dodávka.** Banka neuvolní platbu před splněním podmínek, takže riziko placení za nedodané zboží je minimalizováno.
- **Možnost odložené splatnosti** (deferred payment L/C). Kupující platí například **30, 60 nebo 90 dnů** po předložení dokumentů — má čas zboží přeprodat či zpracovat.
- **Pevně daná dokumentace** pro celní řízení a účetnictví.

---

## Rizika dokumentárního akreditivu pro kupujícího

- **Banka může odmítnout platbu** kvůli diskrepanci v dokumentech, i když zboží bylo dodáno řádně. To není problém kupujícího jako plátce, ale problém vztahu — prodávající bude tlačit na waiver či amendment.
- **Zpoždění.** Proces banking-to-banking trvá dny, někdy týdny. Není vhodný pro **rychlé** opakované dodávky (ty se řeší jinými nástroji, např. open account s pojištěním pohledávek).
- **Prodávající může požadovat amendmenty.** Každá změna L/C (prodloužení platnosti, změna množství, přidání dokumentu) stojí **poplatek** (cca 50–200 EUR za amendment) a ten obvykle nese kupující.
- **Dokumenty ≠ zboží.** Banka **nekontroluje skutečné zboží**, jen formální dokumenty. Hrozí podvod — předložení dokladů na neexistující nebo bezcennou zásilku. Obrana: **inspekční certifikát od nezávislé třetí strany** (SGS, Bureau Veritas).
- **Náklady.** Otevření, avizace, kontrola, potvrzení a amendmenty představují typicky **0,5 – 2 % objemu** akreditivu, rozdělené mezi obě strany podle konvencí (kupující obvykle platí poplatky issuing bank, prodávající poplatky avizující/potvrzující bance).

---

## Domácí banky a způsoby krytí akreditivu

České banky vystavují téměř výhradně **kryté akreditivy** — než issuing bank otevře L/C, vyžaduje od kupujícího zajištění odpovídající plné částce akreditivu plus rezervě na poplatky. Existují tři základní způsoby krytí, případně jejich kombinace.

### A) Blokace prostředků na účtu klienta

- Banka **zablokuje** na klientově účtu částku ve výši akreditivu.
- Klient ztrácí likviditu na celou dobu platnosti L/C, ale banka mu na blokovaných prostředcích **drží úroky** (často nižší sazba než běžný termínovaný vklad, ale ne nulová).
- **Plus:** nejlevnější varianta — žádné úvěrové marže, jen běžné poplatky za vystavení.
- **Mínus:** kapitál vázaný po celou dobu platnosti; nevhodné pro firmy s napjatým cash-flow nebo velkými L/C.

### B) Poskytnutí úvěru

- Klient nemá nebo nechce blokovat hotovost, banka mu poskytne **úvěr za standardních podmínek** ve výši celkové částky akreditivu.
- Klient platí **běžný úrok z úvěru** (typicky PRIBOR + marže) po celou dobu, kdy je akreditiv otevřený a po čerpání i během doby splatnosti.
- **Plus:** zachování likvidity; vhodné pro velké jednorázové dovozy.
- **Mínus:** dražší (úroková marže), vyžaduje **úvěruschopnost** klienta (rating, zajištění úvěru), proces schvalování trvá dny až týdny.

### C) Rezervace 10 obchodních dní

- Banka pouze **rezervuje** sumu na klientově účtu na **10 obchodních dnů**.
- Použitelné jen pro **krátkodobé akreditivy** s rychlým spuštěním a předpokládaným plněním v této lhůtě (například expresní dodávka z blízké země).
- **Plus:** minimální vázanost prostředků, rychlé schválení.
- **Mínus:** velmi omezená flexibilita; nevhodné pro standardní L/C s několikatýdenní lhůtou pro předložení dokumentů.

### D) Kombinace

V praxi se u **velkých akreditivů** používá **hybridní řešení** — část krytá blokací (například 30 %), zbytek úvěrovou linkou. Banka tím rozkládá riziko a klient optimalizuje náklady i likviditu.

---

## Typy akreditivu

| typ | charakteristika |
|-----|-----------------|
| **At-sight L/C** | Platba **okamžitě** po předložení dokumentů a jejich akceptaci bankou (tj. obvykle do 5 pracovních dnů). |
| **Deferred payment L/C** | Platba **30 / 60 / 90 dnů** po předložení nebo po datu konosamentu. Funguje jako forma dodavatelského úvěru. |
| **Stand-by L/C** | Záložní akreditiv — banka platí **jen tehdy, pokud kupující sám nezaplatí**. Podobné bankovní záruce, používá se v anglosaském světě. |
| **Revolving L/C** | Automaticky se obnovuje (v čase nebo po čerpání) pro **opakované dodávky**. Šetří poplatky za nové vystavení. |
| **Transferable L/C** | Exportér (první beneficient) může převést celý nebo část akreditivu na **svého subdodavatele** (druhý beneficient). Užitečné pro obchodníky bez vlastní výroby. |
| **Back-to-back L/C** | Exportér použije obdržený L/C jako zajištění pro vystavení **nového L/C** ve prospěch svého dodavatele. Dva nezávislé akreditivy. |
| **Red-clause L/C** | Akreditiv obsahuje doložku umožňující **zálohu pro exportéra ještě před dodávkou** (typicky proti prostému příslibu). Rizikové pro kupujícího. |

---

## Akreditiv v risk managementu

- **Taktika přenosu rizika** ([[taktiky-rizeni-rizik]]) — kreditní riziko kupujícího se přenáší na issuing bank, případně na potvrzující banku. Riziko se nesnižuje, ale přechází na lépe kapitalizovaný a regulovaný subjekt.
- **Konkrétní metoda snižování rizika** ([[metody-snizovani-rizika]]) — strukturované zajištění mezinárodní platby s definovaným procesem a dokumenty.
- **Synergie s [[forfaiting]]em.** Exportér obdrží neodvolatelný L/C s **odloženou splatností** (deferred payment) a může pohledávku z něj **prodat forfaitérovi** za okamžitou platbu (sníženou o diskont). Forfaitér nese dál riziko issuing bank a politické riziko země importéra.
- **Pokrytí politického rizika.** **Confirmed L/C** (akreditiv potvrzený bankou v zemi exportéra) přidává záruku proti politickým událostem — moratoriu, sankcím, devizovým omezením, znárodnění.
- **Náklady reflektují rizikový profil.** Diskontní sazby a poplatky se odvíjejí od ratingu issuing bank a country risk score (viz [[mereni-rizika]]).

---

## Praktické tipy

- **Pečlivě formulujte podmínky L/C.** Všechny podmínky musí být **splnitelné, jasné a kontrolovatelné z dokumentů**. Vágní formulace („zboží v dobré kvalitě") jsou nekontrolovatelné a vedou ke sporům.
- **Nezahrnujte podmínky ve sféře kupujícího.** Příklad špatné praxe: „inspekce kupujícím v přístavu nakládky". Pokud kupující inspekci neprovede nebo odmítne podepsat protokol, banka platbu nezaplatí — riziko leží mimo prodávajícího. Místo toho použít **nezávislou inspekční organizaci** (SGS).
- **Sjednejte amendmenty předem.** Každá změna stojí poplatky a čas. Lepší je do první verze L/C zahrnout dostatečné rezervy (delší lhůta, mírnější tolerance množství „about 5 %").
- **Použijte specialisty na trade finance.** Velké banky (ČSOB, KB, ČS, UniCredit, Raiffeisen) mají expertní oddělení **trade finance**, která pomáhají sestavit znění L/C a kontrolovat dokumenty před předložením (pre-check service). Ušetří diskrepance a poplatky.
- **Kontrolujte dokumenty dvakrát.** Před předáním bance projděte celou sadu proti znění L/C — slovo po slovu, datum po datu. Nejčastější diskrepance jsou opravitelné, pokud se najdou před expirací L/C.

---

## Souvislosti

- [[faktoring]] — alternativní zajištění pohledávek; vhodný pro **krátkodobé domácí** pohledávky bez akreditivu.
- [[forfaiting]] — kombinuje se s L/C; exportér prodá pohledávku z akreditivu s odloženou splatností a získá okamžitou platbu.
- [[metody-snizovani-rizika]] — L/C jako konkrétní metoda transferu kreditního rizika.
- [[taktiky-rizeni-rizik]] — taktika přenosu (transfer) rizika.
- [[mereni-rizika]] — diskontní sazby a poplatky odrážejí rizikový profil zemí a bank.

---

## Navigace
- **Předchozí:** [[forfaiting]]
- **Navazující:** [[operacni-vyzkum]]
- **Související:** [[faktoring]]
