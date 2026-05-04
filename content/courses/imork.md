---
title: Management oborových řešení (ImorK)
course: imork
type: course
tags: [imork, isms, informacni-bezpecnost, kyberneticka-bezpecnost, oborova-reseni, iso-27000]
sources: [raw/imork/Detail předmětu.md]
created: 2026-04-12
updated: '2026-05-04'
---

# Management oborových řešení (ImorK)

| | |
|---|---|
| **Zkratka** | ImorK |
| **Fakulta** | Fakulta podnikatelská, VUT v Brně |
| **Semestr** | letní 2025/2026 |
| **Ukončení** | zkouška |
| **Garant** | Ing. Lukáš Novák, Ph.D. |
| **Vyučující** | Ing. Petr Sedlák |
| **Ústav** | Ústav informatiky |
| **Prerekvizita** | Management informační bezpečnosti (ImibePA) |

## Cíle předmětu

- Znalosti o specifických problémech a odlišnostech při **oborovém řešení informační bezpečnosti**
- Porozumění jednotlivých řešení na úrovni **případových studií**
- Přehled o rozdílných aspektech v závislosti na oborové řešení **ISMS**
- Metodika pro budování bezpečných IS na bázi norem řady **ISO/IEC 27000**

## Osnova

1. Bezpečnost v kyberprostoru
2. Budování bezpečnostního povědomí — SAE
3. Manažerská informační bezpečnost
4. Problematika GDPR
5. ISMS v ISVS
6. ISMS v univerzitním prostředí
7. ISMS ve zdravotnictví
8. ISMS v energetice
9. ISMS poskytovatelů konektivity (ISP)
10. Bezpečnost konvergovaných sítí
11. Řízení bezpečnosti www aplikací
12. Řízení bezpečnosti mailových aplikací
13. Řízení mobilní bezpečnosti

## Témata kurzu

Souhrnné koncepční stránky, na nichž stojí celý kurz:

- [[isms|ISMS]] — systém řízení bezpečnosti informací; rodina ISO 27000
- [[rizeni-rizik|Řízení rizik]] — proces ISO 27005 / ISO 31000, RTP, SoA
- [[kyberneticka-bezpecnost|Kybernetická bezpečnost]] — útoky, obrana, defense-in-depth
- [[sae|SAE]] — budování bezpečnostního povědomí, NIST SP 800-50/16
- [[bcm|BCM a Disaster Recovery]] — kontinuita činnosti, ISO 22301, RPO/RTO
- [[ochrana-dat|Ochrana dat]] — NAC, IDS/IPS, SIEM, DLP, kryptografie, eIDAS
- [[gdpr|GDPR]] — nařízení (EU) 2016/679, DPIA, Privacy by Design, ISO 27701

## Referenční výstupy

- [[imork-normy-prehled|Přehled norem podle sektoru]] — rodina ISO 27000, NIST SP 800, EU regulace (GDPR, NIS2, DORA, MiCA), české předpisy (ZKB, VKB), frameworky (NIST CSF, MITRE ATT&CK, OWASP, CMMC); řazeno podle oborového sektoru
- [[imork-glosar|Glosář pojmů a zkratek]] — abecední slovník ~120 zkratek a pojmů kurzu

## Záznamy přednášek

### Manažerské a strategické téma

- [[imork-detail-predmetu|Detail předmětu]] — sylabus, hodnocení, literatura
- [[imork-manazerska-bezpecnost|Manažerská informační bezpečnost]] — governance, SIEM, IAM, incident management, penetrační testy
- [[imork-bezpecnostni-strategie|Bezpečnostní strategie]] — ENISA NCSS, CMMC, NÚKIB strategie ČR
- [[imork-sae|Záznam přednášky SAE]] — bibliografická karta zdroje
- [[imork-risk-management|Záznam přednášky Risk Management]] — bibliografická karta zdroje

### Oborová ISMS

- [[imork-akademicke-prostredi|Akademické prostředí]] — kampus, eduroam, BICSI, VIS, TLP
- [[imork-financni-sektor|Finanční sektor]] — DORA, MiCA, DLT/blockchain
- [[imork-zdravotnictvi|Zdravotnictví]] — HIPAA, ISO 27799, PACS, DICOM
- [[imork-energetika|Energetika]] — ISO 27019, IEC 61850, PLC/SBC/RTU
- [[imork-smart-grid|Smart Grid]] — NISTIR 7628, IEC 62351, prosumers, IoT
- [[imork-doprava|Doprava (železnice)]] — CLC/TS 50701, kritická infrastruktura
- [[imork-automotive|Automotive]] — CAN bus, TISAX, UN Reg. 155
- [[imork-isp|ISP a telekomunikace]] — ISO 27011, NGN, IMS, 5G, RTBH
- [[imork-mcn|Mission Critical Networks]] — NCPI, model hrozeb ITU-T X.805

### Bezpečnost aplikací a dat

- [[imork-www|Bezpečnost webových služeb]] — OWASP, IPsec, TLS, XML Security
- [[imork-email|Bezpečnost emailových služeb]] — SPF, DKIM, DMARC, S/MIME, BEC
- [[imork-ochrana-dat|Záznam přednášky Ochrana dat]] — bibliografická karta zdroje

### Kontinuita a obnova

- [[imork-bcm|Záznam přednášky BCM]] — bibliografická karta zdroje
- [[imork-dr|Disaster Recovery]] — RPO/RTO, cloud DR, 7 tiers, DRaaS

### Kybernetické útoky

- [[imork-anatomie-utoku|Anatomie kybernetického útoku]] — APT, vektory, MITRE ATT&CK, ISO/OSI
- [[imork-ai-utoky|AI útoky a obrana]] — WormGPT, BEC 5 typů
- [[imork-sitove-utoky|Síťové útoky]] — DDoS, spoofing, kill chain Emotet→Trickbot→Ryuk
- [[imork-ransomware|Ransomware]] — historie 1989–2024, RaaS, NISTIR 8374, IR plán
- [[imork-rizeny-hacking|Řízený hacking a APT skupiny]] — APT28/29/41, Ghost Net
- [[imork-internetova-bezpecnost|Internetová bezpečnost]] — kyberprostor, OSINT, KRACKs

### Případové studie

- [[imork-nemocnice|Útoky na nemocnice]] — Benešov, FN Brno, Nymburk
- [[imork-kradez-dat|Krádež dat]] — PII, ISO 27701, Privacy by Design
- [[imork-sprava-login|Správa přihlašování]] — privilegované účty, NIST SP 800-63
- [[imork-ehealth|eHealth]] — telemedicína, NSeZ, WBAN
- [[imork-tor|TOR — anonymizační síť]] — onion routing, NSA X-Keyscore
- [[imork-payment|Bezpečnost plateb]] — PCI DSS v4.0.1, NFC/tokenizace, EMV
- [[imork-mobilni-bezpecnost|Mobilní bezpečnost]] — SIMJaker, SIM swapping, 5G
- [[imork-audio-hack|Audio Hack]] — fyzická zranitelnost HDD, CVE-2022-38392

### Další

- [[imork-digitalni-identita|Digitální identita a digitální stopa]] — online identita, footprint

## Doporučená literatura

- JORDÁN, V. a ONDRÁK, V.: *Integrovaná podniková infrastruktura.* Brno: CERM, 2016. ISBN 978-80-214-5241-1
- SEDLÁK, P. a KONEČNÝ, M.: *Přeměna ISMS v manažerské informatice.* Brno: CERM, 2023. ISBN 978-80-7623-110-8
- SEDLÁK, P. a KONEČNÝ, M.: *Kybernetická (ne)bezpečnost.* Brno: CERM, 2021. ISBN 978-80-7623-068-2
- ČSN EN ISO/IEC 27011 — Bezpečnost pro telekomunikační organizace
- ČSN EN ISO/IEC 27019 — Bezpečnost pro energetický průmysl
- ČSN EN ISO 27799 — Bezpečnost ve zdravotnictví
