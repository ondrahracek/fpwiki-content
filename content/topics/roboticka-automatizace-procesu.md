---
title: "Robotická automatizace procesů"
course: ipis2k
type: topic
tags: [ipis2k, rpa, automatizace, robot, licence]
sources: [raw/ipis2k/prezentace.pdf]
created: 2026-11-06
updated: 2026-11-06
---

# Robotická automatizace procesů

> [!tldr] V kostce
> - RPA je software, který podle pravidel napodobuje práci uživatele v aplikacích.
> - Automatizovat se vyplatí až po posouzení pravidel, objemu, výjimek, stability a rizik procesu.
> - Robot potřebuje řízené nasazení, provozní správu a náklady na platformu, infrastrukturu i údržbu.

Robotická automatizace procesů (**RPA**, *Robotic Process Automation*) převádí opakovaný postup uživatele přes obrazovky aplikací do softwarového robota. Typická posloupnost vypadá takto:

1. pracovník podle pravidla najde záznam v tabulce,
2. otevře odpovídající položku v podnikové aplikaci,
3. přepíše údaje a zkontroluje výsledek.

Software ji může provádět za něj, jen pokud jsou kroky a pravidla dostatečně určité.

![[ipis2k-rpa-ilustrace-v2.png|Barevná ilustrace tabulky, softwarového robota uvnitř počítačové aplikace a cílového formuláře.]]

## Softwarový robot a jeho způsob práce

RPA robot je počítačově vytvořený software. Napodobuje interakce uživatele a automatizuje opakované procesy řízené pravidly.

- **Není** to humanoidní stroj ani automatická náhrada lidí.
- **Neznamená** to lidské porozumění úloze: robot opakuje naprogramovaný postup.
- **Může** snížit chybovost u rutinní práce, ale nenapraví špatně definované pravidlo ani nekvalitní vstup.

RPA se připojuje k existujícím uživatelským rozhraním. Proto může pracovat i se starším ERP, mainframem nebo vlastní aplikací, aniž by byla technicky integrována přímo do jejich vnitřku. Část procesu přitom může zůstat na člověku. Tento neinvazivní přístup je užitečný tam, kde není jiné rozhraní dostupné, současně však činí robota citlivým na změny obrazovek a pracovního postupu. RPA je tedy jednou z možností [[integrace-podnikovych-aplikaci|integrace na bázi uživatelského rozhraní]], ne obecná náhrada přímého propojení systémů přes data nebo aplikační programové rozhraní (API).

Proč může tento přístup dávat smysl:

- **Rychlost a náklady zavedení:** využití existujících obrazovek může být rychlejší a levnější než složitá přímá integrace. Není to garance krátké implementace ani návratnosti; záleží na procesu a prostředí.
- **Škálování:** kapacitu robotů lze přizpůsobovat poptávce, pokud to dovolí aplikace, infrastruktura a licence.
- **Auditní stopa:** záznamy přístupů a provedených změn umožňují dohledat činnost robota. Jejich dostupnost závisí na nastavení a uchování logů.

| Pojem | Význam v provozu |
|---|---|
| **Robotické řešení** | Řešení vytvořené na RPA platformě pro určitý proces v konkrétním podnikovém a IT prostředí. |
| **Robot machine** | Pracovní místo, kde bot běží. V jednoduchém modelu je v jednom okamžiku přiřazeno jednomu řešení; nejde o pravidlo všech platforem. |
| **Control panel** | Nástroje pro správu, plánování, ochranu a záznam činnosti robotů. |

Každý bot pracuje s přístupovými údaji podobně jako zaměstnanec. Oprávnění a logy proto zůstávají provozní i kontrolní otázkou.

## Který proces je vhodný

Nejprve se rozhoduje, zda proces automatizovat celý, jen zčásti, nebo jej nejdřív upravit.

| Varianta | Význam |
|---|---|
| Úplná automatizace | Proces lze provést od začátku do konce bez změny procesu samotného. |
| Částečná automatizace | Některé kroky lze automatizovat, jiné zůstávají na člověku. |
| Reengineering | Proces potřebuje změnu, aby šlo automatizovat celý proces nebo jeho část. |

Posouzení může skončit také závěrem **RPA nepoužít**. Pak se hledá jiné zlepšení procesu nebo vhodnější platforma. Cílem není za každou cenu nasadit robota, ale vybrat způsob řešení, který dává pro daný proces smysl.

**Dobří kandidáti** jsou řízení pravidly, spouští je elektronický vstup, opakují se a mají dobře vymezený nebo zdokumentovaný postup. Samotná opakovanost nestačí: posouzení musí zachytit také variace, výjimky, potřebná oprávnění a dostupnost aplikací.

**Typické situace pro RPA:**

- vyhledat záznam v Excelu podle kritérií a vložit jej do Oracle,
- po dokončení aktivity odeslat e-mail se správnou přílohou,
- vyčistit data z více systémů, provést výpočet a vytvořit finanční report,
- projít obrazovky jednoho systému a dokončit zadání dat,
- porovnat pole z více systémů, vytěžit pole z PDF pomocí optického rozpoznání textu (OCR) nebo plánovaně vytvořit report přes API.

Ne každá taková úloha je automaticky vhodná: rozhoduje konkrétní proces, kvalita vstupů a jeho výjimky.

## Posouzení a výběr procesu

Technické posouzení sleduje přínos i překážky. Kapacita se ptá, kolik práce lze uvolnit a zda je tato kapacita potřebná. Kvalita zvažuje, zda lze snížit chybovost nebo lépe zvládat výjimky. Dále se hodnotí objem transakcí a jeho špičky, stabilita procesu, provozní riziko při selhání, složitost kroků a systémů i vlastnictví procesu napříč útvary. Business pohled doplňuje složitost robota, dostupnost a stabilitu prostředí, kvalitu vstupů, kritičnost procesu, rychlost zpracování, podíl případů vracených operátorovi a očekávanou spokojenost.

Výsledkem není automatický výpočet návratnosti, ale podklad pro prioritizaci a business case. Přínosy a připravenost či složitost lze porovnat pomocí skórování; hodnoty a prahy se mají dohodnout pro konkrétní organizaci. Matice složitosti také ukazuje, že k náročnosti přispívá obchodní logika, technologické prostředí, počet kroků, aplikací či vstupních souborů a výjimek. U velmi složitých procesů přibývají varianty, výjimky, nestrukturované dokumenty nebo OCR; takový proces nelze hodnotit jen podle počtu kroků.

## Od návrhu k provozu

Zavedení robota pro jeden proces lze číst jako šest navazujících kroků:

1. **Posouzení** — vstupy, systémy, výstupy, objemy, jednotkové časy, oprávnění, variace, výjimky a reportování.
2. **Definice procesu** — pozorování krok za krokem včetně výjimkových cest.
3. **Návrh řešení** — automatizace i způsob obsluhy výjimek.
4. **Sestavení a konfigurace** robota.
5. **Test** — jednotkový, end-to-end i uživatelský akceptační.
6. **Řízené spuštění** — nejprve vymezený počet případů a potvrzení odpovědné osoby.

![[ipis2k-rpa-zivotni-cyklus-v2.png|Šest navazujících etap zavedení RPA: posouzení, definice procesu, návrh řešení, sestavení, test a řízené spuštění do provozu.]]

**Řízené spuštění** po úspěšném uživatelském akceptačním testu zahrnuje:

- ověření dostupnosti aplikací a odpovídajících oprávnění v produkci,
- případnou řízenou úpravu produkční konfigurace ve spolupráci s oprávněnými IT rolemi a následné nasazení,
- zkušební běh na vzorku případů,
- potvrzení výstupů i výjimek odpovědným uživatelem nebo vlastníkem procesu,
- postupné rozšíření na případy zahrnuté do automatizace a jejich naplánování ke zpracování robotem.

Tento tok popisuje **jeden proces**. Program zavádění RPA má širší rytmus:

- **pilot / ověření konceptu** — první zkušenost na procesech s malou potřebou změn,
- **širší automatizace** — dohoda o podpoře a údržbě, postupy, dokumentace a ukazatele,
- **běžný provoz** — automatizace i procesů vyžadujících větší změnu a ustálení řízení životního cyklu robotů.

## Infrastruktura, řízení a náklady

RPA potřebuje:

- produkční i vývojové a testovací prostředí,
- řídicí nástroje, přístup k podnikovým aplikacím a účty pro roboty,
- oddělení testu a produkce, aby se změny ověřily před nasazením.

V modelovém uspořádání odpovídají oprávnění robota v produkci oprávněním pracovníka, jehož úlohy provádí; vývojáři mají do testu jen dočasná oprávnění. Oddělení rolí je důležité pro kontrolu změn. Počty serverů a jejich parametry jsou pouze návrhem konkrétní architektury: závisejí na objemu transakcí a dostupnosti systémů, nejde o univerzální minimum pro každou platformu.

Náklady nejsou pouze cenou botu. Celkové náklady zahrnují infrastrukturu, licenci RPA platformy, vývoj botu, nastavení řízení RPA, údržbu botu a údržbu infrastruktury. V pilotní fázi může být řízení zjednodušené, ale s rozšiřováním automatizace se podpora, odpovědnosti a údržba stávají součástí běžného provozu.

### Dokumentace a ekonomické posouzení

Pro podporu po pilotu jsou potřeba:

- **popis procesu** — kroky, vstupy, výstupy a výjimky,
- **návrh řešení** — jak robot proces provádí,
- **provozní příručka** — jak řešení obsluhovat a udržovat,
- **spolupráce businessu a IT** — pochopení využití RPA, příprava bezpečnostních požadavků a přístupů.

Ekonomické posouzení (*business case*) porovnává náklady s očekávaným přínosem. Vedle licencí a infrastruktury zahrnuje také:

| Vstup | Proč jej sledovat |
|---|---|
| Práce na vývoji a údržbě | Robot potřebuje vytvoření i průběžné změny. |
| Zbývající práce operátorů, podpory a IT | Část provozní práce po automatizaci zůstává. |
| Uvolněná pracovní kapacita | Ukazuje rozsah práce, kterou může robot převzít. |
| Očekávaná účinnost robota | Ovlivňuje skutečně dosažitelný přínos. |

Technická proveditelnost tedy sama neznamená ekonomickou výhodnost. Uvolněná kapacita také není automaticky hotovostní úspora; je třeba rozlišit práci převzatou robotem od lidí, kteří zajišťují zbývající provoz.

## Licence: plánování podle skutečného provozu

Před volbou počtu virtuálních strojů (VM) a licencí se vytváří inventář procesů: objem a vývoj transakcí, čas na jednotku a špičky. Posuzují se také závislosti procesů, kontrolní body, požadavky na shodu a dostupnost IT prostředí. Pro každý server nebo VM je nutné znát servisní okna, řešení obnovy a kontinuity, omezení přístupu a dostupnost aplikací či dat, například při uzávěrce nebo migraci dat. Teprve z těchto údajů vznikne tabulka využití VM a licencí.

Počet potřebných licencí ukazují dvě modelové situace. Čtěte je jako plánování podle zatížení, ne jako obecné licenční pravidlo:

| Modelová situace | Co ukazuje |
|---|---|
| Dva roboti pracují postupně na jedné VM: druhý začne po dokončení prvního; část dne je blokována uzávěrkou a servisním oknem. | V tomto konkrétním modelu stačí jedna VM a jedna runtime licence RPA. |
| Jeden robot má kvůli vysokému objemu práce rozdělené mezi dvě VM; část dne blokuje migrace dat a servisní okno. | V tomto konkrétním modelu jsou potřeba dvě VM a dvě runtime licence RPA. |

![[ipis2k-rpa-licence-v2.png|Porovnání dvou modelových situací: dva postupně běžící roboti sdílejí jednu virtuální stanici, zatímco jeden objemově náročný robot pracuje na dvou virtuálních stanicích.]]

> [!important] Co z příkladu nevyvozovat
> Pravidla „jedna VM = jedna runtime licence“ a „dvě VM = dvě runtime licence“ patří jen k těmto modelům. Skutečný licenční model se ověřuje pro konkrétní platformu a nasazení; každý robot nemusí mít vlastní VM a roboty nelze bez omezení sdílet.

## Související stránky

- [[ipis2k|Podnikové informační systémy 2]]
- [[integrace-podnikovych-aplikaci|Integrace podnikových aplikací]]
- [[rizeni-informatiky-a-itgc|Řízení informatiky a kontroly ITGC]]

## Reference

NOVÁK, Lukáš. *Podnikové informační systémy 2*. Výuková prezentace. Fakulta podnikatelská VUT v Brně, 2026.
