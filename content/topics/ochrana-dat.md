---
title: Ochrana dat
courses: [imork]
type: topic
tags: [imork, ochrana-dat, sifrovani, nac, ids, ips, dlp, gdpr]
sources: [raw/imork/2017 VUT_Ochrana dat-2022.pdf, raw/imork/2015 VUT_Bezp WWW-2019.pdf, raw/imork/2016 VUT_Bezp Email-2022.pdf]
created: 2026-04-12
updated: '2026-05-04'
---

# Ochrana dat

![[ochrana-dat-technologie.jpeg|Bezpečnostní technologie ochrany dat v síťové architektuře]]

Technologická řešení pro zabezpečení dat v interní infrastruktuře i kyberprostoru. Zahrnuje síťové, aplikační i datové bezpečnostní mechanismy.

## Formy zneužití dat

| Forma | Popis |
|---|---|
| Zašifrování | Ransomware |
| Zveřejnění | Double ransomware |
| Odposlech | Pasivní sběr dat |
| Krádež | Cílená exfiltrace |
| Krádež dodavatelského řetězce | Triple ransomware |
| Prodej | Darknet marketplace |

## Bezpečnostní technologie

### NAC (Network Access Control)
- Proaktivní ochrana sítě před neautorizovaným přístupem
- 4 fáze: detekce → autentizace → vyhodnocení → autorizace
- Ekvivalenty: MDM, BYOD

### IDS (Intrusion Detection System)
- Monitoruje síťový provoz, generuje alerty
- Pasivní systém — nezasahuje do provozu
- Signaturová a anomální detekce

### IPS (Intrusion Prevention System)
- Aktivní systém — blokuje škodlivý provoz
- Zařazen přímo do síťové cesty (in-line)

### SIEM (Security Information and Event Management)
- Centralizovaná správa bezpečnostních logů
- Sběr s agentem i bez agenta
- Prioritizace: třídy zpráv, zdroje, IP adresy, četnost

### DLP (Data Loss Prevention)
- Klasifikace citlivých dat a vynucení ochrany

### Šifrování
- AES (128/192/256 bit), 3DES
- RSA (2048+ bit), DSS
- SHA-256, SHA-1

### UTM (Unified Threat Management)

Jednotná správa hrozeb — FW + IDS/IPS + AV + VPN v jednom zařízení.

## SIEM podrobně

- **EPS** (Events Per Second) — klíčová metrika pro dimenzování SIEM.
- **Velikost logů** — plánování úložné kapacity dle objemu generovaných dat.
- **Typy zařízení** — síťové prvky, servery, aplikace, bezpečnostní systémy, endpointy.
- **Implementace** — začít s nejkritičtějšími zdroji logů, postupně rozšiřovat.
- **Provozní příručka + BCM** — dokumentace provozu SIEM a jeho zahrnutí do plánů kontinuity.

## DLP — tři stavy dat

| Stav | Popis | Ochrana |
|---|---|---|
| **Data in Use** | Aktivně zpracovávaná na endpointu | DLP koncových bodů (agent na stanici, kontrola USB, tisk, schránka, email) |
| **Data in Motion** | Přenášená po síti | Síťový DLP (gateway), monitorování a blokování na perimetru |
| **Data at Rest** | Uložená na discích, v databázích | Šifrování, řízení přístupu |

## Kryptografie — historický přehled

| Algoritmus | Rok | Typ | Délka klíče |
|---|---|---|---|
| **DES** | 1975 | Symetrický (blokový) | 64-bit (efektivních 56) |
| **IDEA** | 1990 | Symetrický (blokový) | 128-bit |
| **RSA** | 1977 (MIT) | Asymetrický | 1024–4096 bit |
| **AES** | 1997 (NIST) | Symetrický (blokový) | 128/192/256-bit |

### Steganografie

Skrytí informace ve zdánlivě neškodné zprávě — na rozdíl od kryptografie nezakrývá obsah, ale samotnou existenci tajné komunikace. Využití v obrázcích, zvuku, videu.

### Digitální podpisy a hašovací funkce

Ověření autora a integrity dokumentu pomocí asymetrické kryptografie. Hašovací funkce vytváří jednosměrný otisk dokumentu — základ pro ověření integrity. **4 vlastnosti elektronického podpisu**: identifikace, integrita, nepopiratelnost, nenapodobitelnost.

V ČR existují **3 akreditované certifikační autority** pro vydávání kvalifikovaných certifikátů.

### Dynamický biometrický podpis

**ISO/IEC 24745** — ochrana biometrických šablon. Zachycuje unikátní biometrickou stopu (tlak, rychlost, sklon pera, dynamika) — každý podpis je jedinečný i při opakování.

### eIDAS

**Nařízení EU č. 910/2014** o elektronické identifikaci a službách vytvářejících důvěru — elektronické pečetě, časová razítka, služby vytvářející důvěru (certifikační autority, doručovací služby).

### ENISA Data Protection Engineering

Doporučení pro technickou ochranu osobních údajů: **Privacy by Design / Default**, **DPIA** (Data Protection Impact Assessment), **PET** (Privacy Enhancing Technologies), **anonymizace**, **differential privacy**, **TEE** (Trusted Execution Environment), **synthetic data**.

## IPv6 bezpečnost

- **AH** (Authentication Header) — ověření odesílatele a integrity
- **ESP** (Encapsulating Security Payload) — šifrování dat
- Transportní a tunelovací režim
- SPD (Security Policy Database), bezpečnostní asociace

## Související stránky

- [[isms|ISMS]] — ochrana dat jako technická vrstva ISMS
- [[kyberneticka-bezpecnost|Kybernetická bezpečnost]] — kontext hrozeb
- [[rizeni-rizik|Řízení rizik]] — hodnocení aktiv a hrozeb
- [[imork-www|Bezpečnost webu]] — webové útoky a obrana
- [[imork-email|Bezpečnost emailu]] — emailové protokoly
- [[imork-ochrana-dat|Záznam přednášky Ochrana dat]] — bibliografická karta zdroje
