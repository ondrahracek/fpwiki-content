---
title: Kybernetická bezpečnost
courses: [imork]
type: topic
tags: [imork, kyberneticka-bezpecnost, utoky, apt, ransomware, phishing, owasp]
sources: [raw/imork/CV 02 VUT_Anatomie útoku-2022.pdf, raw/imork/CV 05 VUT_ AI útoky-2023 (1).pdf, raw/imork/2001 VUT_Bezp Managerská 2022.pdf]
created: 2026-04-12
updated: '2026-05-04'
---

# Kybernetická bezpečnost

![[kb-defense-in-depth.jpeg|Defense-in-Depth — 5 vrstev ochrany od perimetru po data]]

Ochrana informačních systémů, sítí a dat před kybernetickými hrozbami. V kontextu [[isms|ISMS]] zahrnuje jak manažerské, tak technické aspekty bezpečnosti.

## Základní pojmy

- **Útočná plocha** (Attack Surface) — celkový počet vstupních bodů pro neoprávněný přístup (digitální + fyzická)
- **Vektor útoku** (Attack Vector) — způsob zneužití zranitelnosti
- **Zranitelnost** (Vulnerability) — slabé místo v aktivu nebo procesu
- **Exploit** — kód zneužívající konkrétní zranitelnost
- **Payload** — kód spuštěný po úspěšném exploitu
- **Shellcode** — kód spouštěný v shellu napadeného systému

## Typy útoků

### Podle cílení

| Typ | Popis | Cíl |
|---|---|---|
| **Plošný** | Útočníkovi je jedno, kdo je obětí | Botnety, spam, ransomware |
| **Cílený (APT)** | Soustředěná pozornost na konkrétní cíl | Špionáž, sabotáž, krádež dat |

### APT — Advanced Persistent Threat

![[apt-faze-utoku.jpeg|Čtyři fáze APT útoku — příprava, průnik, kompromitace, dokončení]]

4 fáze:
1. **Příprava** — sběr informací, skenování zranitelností, sociální inženýrství
2. **Průnik** — spear phishing, watering hole, malvertising
3. **Kompromitace** — laterální pohyb, eskalace oprávnění, trvalý přístup
4. **Dokončení** — exfiltrace dat, vydírání, sabotáž

### Základní vektory útoku

- Email s přílohou (spear phishing)
- Trojanizované aplikace
- Drive-by download (webové exploity)
- Výměnná média (BadUSB)
- Watering hole (kompromitace důvěryhodného webu)

### Software útoky

- **Adware/Spyware** — sběr dat, odposlech
- **Viry** — poškození HW/SW
- **Trojské koně** — skrytá funkčnost
- **Ransomware** — šifrování dat za výkupné (single/double/triple)
- **WormGPT** — AI nástroj pro automatizaci kybernetické kriminality

## Webové útoky (OWASP)

| Útok | Cíl | Efekt |
|---|---|---|
| Content Spoofing | Klient | Ztráta přihlašovacích údajů |
| XSS | Klient | Přístup k cookies |
| SQL Injection | Server | Neoprávněný přístup do DB |
| DoS/DDoS | Server | Nedostupnost služby |
| Path Traversal | Server | Přístup k souborům |

## BEC — Business Email Compromise

Zneužití firemního emailu k podvodným platbám. 5 typů dle FBI:
1. Vydávání se za právníka
2. Podvod na CEO
3. Krádež dat (personální oddělení)
4. Kompromitace účtu
5. Falešné faktury

## Obranné technologie

- **NAC** — řízení přístupu k síti
- **IDS** — detekce průniku (pasivní)
- **IPS** — prevence průniku (aktivní, in-line)
- **SIEM** — centralizovaná správa bezpečnostních událostí
- **DLP** — prevence úniku dat
- **FW/VPN** — perimetrová ochrana

## Související stránky

- [[isms|ISMS]] — manažerský rámec bezpečnosti
- [[rizeni-rizik|Řízení rizik]] — hodnocení hrozeb a zranitelností
- [[sae|SAE]] — budování povědomí jako obrana č. 1
- [[bcm|BCM]] / [[imork-dr|DR]] — reakce na incidenty a obnova
- [[ochrana-dat|Ochrana dat]] — technologická ochrana

### Záznamy přednášek a útočné techniky

- [[imork-anatomie-utoku|Anatomie kybernetického útoku]] — APT, vektory, MITRE ATT&CK
- [[imork-ai-utoky|AI útoky a obrana]] — WormGPT, BEC
- [[imork-sitove-utoky|Síťové útoky]] — DDoS, spoofing, ISO/OSI L1–L7
- [[imork-ransomware|Ransomware]] — historie, RaaS, NISTIR 8374
- [[imork-rizeny-hacking|Řízený hacking a APT skupiny]] — APT28/29/41
- [[imork-internetova-bezpecnost|Internetová bezpečnost]] — OSINT, behaviorální biometrika
- [[imork-www|Bezpečnost webových služeb]] — OWASP, XSS, SQL injection

### Případové studie

- [[imork-nemocnice|Útoky na nemocnice]] — Benešov, FN Brno, Nymburk
- [[imork-kradez-dat|Krádež dat]] — PII, ISO 27701
- [[imork-sprava-login|Správa přihlašování]] — privilegované účty, NIST SP 800-63
- [[imork-payment|Bezpečnost plateb]] — PCI DSS v4.0.1
- [[imork-mobilni-bezpecnost|Mobilní bezpečnost]] — SIMJaker, 5G
- [[imork-tor|TOR síť]] — onion routing, dark web
- [[imork-audio-hack|Audio Hack]] — CVE-2022-38392
- [[imork-ehealth|eHealth]] — telemedicína, NSeZ
