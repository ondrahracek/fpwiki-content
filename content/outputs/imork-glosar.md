---
title: ImorK — Glosář pojmů a zkratek
course: imork
type: output
tags: [imork, glosar, isms, kyberneticka-bezpecnost, ochrana-dat, oborova-reseni]
sources: [raw/imork/2001 VUT_Bezp Managerská 2022.pdf, raw/imork/2003 VUT_Bezp Risk Mngmt-2021.pdf, raw/imork/2014 VUT_Bezp BCM-2021.pdf, raw/imork/2017 VUT_Ochrana dat-2022.pdf, raw/imork/CV 02 VUT_Anatomie útoku-2022.pdf, raw/imork/CV 03 VUT_Síťové útoky-2023.pdf]
created: 2026-05-04
updated: '2026-05-04'
---

# ImorK — Glosář pojmů a zkratek

Abecední slovník bezpečnostní terminologie kurzu [[imork|ImorK]]. Ke každému pojmu uvedeno *rozvinutí zkratky, krátká definice, odkaz na stránku s plným výkladem*. Pro normy a regulace primárně viz [[imork-normy-prehled|Přehled norem]] — tady jsou jen zařazeny pro hledání v Ctrl-F.

## Čísla / Numerické

- **5G** — Pátá generace mobilních sítí. Bezpečnostní výzvy: nový radio interface, edge computing, network slicing, IoT density. [[imork-mobilni-bezpecnost|Mobilní bezpečnost]], [[imork-isp|ISP]].

## A

- **AAA** — Authentication, Authorization, Accounting. Tři pilíře řízení síťového přístupu. Viz [[imork-akademicke-prostredi|Akademické prostředí]], [[ochrana-dat|Ochrana dat]].
- **ACL** — Access Control List. Seznam pravidel řídících přístup k aktivům (NTFS ACL, síťové ACL na routerech). [[ochrana-dat|Ochrana dat]], [[imork-anatomie-utoku|útoky na L3]].
- **AES** — Advanced Encryption Standard (Rijndael, výběr NIST 1997, finalizace 2001). Symetrický blokový algoritmus, klíče 128/192/256-bit. [[ochrana-dat|Ochrana dat]].
- **AH** — Authentication Header (IPsec, RFC 4301). Autentizace a integrita IP paketů. [[imork-www|Bezpečnost webu]].
- **ANN** — Artificial Neural Network. Klasifikace, predikce, detekce anomálií. Cross-course do [[ipmrk|IpmrK]] / [[umele-neuronove-site]].
- **APT** — Advanced Persistent Threat. Pokročilá přetrvávající hrozba — dlouhodobý cílený útok. 4 fáze: příprava → infiltrace → kompromitace → dokončení. [[imork-anatomie-utoku]], [[imork-rizeny-hacking]].
- **APT28/29/34/37/41** — Konkrétní ruské/iránské/severokorejské/čínské státem sponzorované hackerské skupiny. [[imork-rizeny-hacking]].

## B

- **BCM** — Business Continuity Management. Řízení kontinuity činnosti. ISO 22301. [[bcm|BCM]].
- **BCMS** — Business Continuity Management System. Systémová implementace BCM. [[bcm|BCM]].
- **BCMaaS** — BCM as a Service. Cloudový outsourcingový model BCM. [[bcm|BCM]].
- **BEC** — Business Email Compromise. Zneužití firemního emailu k podvodným platbám; 5 typů dle FBI. [[imork-ai-utoky]], [[kyberneticka-bezpecnost]].
- **BIA** — Business Impact Analysis. Analýza dopadu výpadku procesů; orientace na dopad, ne příčinu. [[bcm|BCM]].
- **BICSI** — Building Industry Consulting Services International. Standardizační organizace pro kabeláž a infrastrukturu: **BICSI 001-2017** (vzdělávací instituce), **BICSI 002** (datová centra), **BICSI 004** (zdravotnictví), **BICSI 007** (inteligentní budovy), **BICSI 008** (WLAN). [[imork-akademicke-prostredi|Akademické prostředí]], [[imork-zdravotnictvi|Zdravotnictví]].
- **BYOD** — Bring Your Own Device. Politika vlastních zařízení v práci. [[imork-mobilni-bezpecnost]], [[imork-manazerska-bezpecnost]].

## C

- **CAN bus** — Controller Area Network. Sběrnice ve vozidlech (1986). [[imork-automotive|Automotive]].
- **CIA** — Confidentiality, Integrity, Availability. Tři pilíře informační bezpečnosti (+ Non-repudiation). [[isms|ISMS]].
- **CIO / CISO / CTO / ISSO** — Chief Information / Information Security / Technology Officer; Information System Security Officer. Bezpečnostní role. [[imork-manazerska-bezpecnost|Manažerská bezpečnost]].
- **CISA / CISM / CRISC / CGEIT** — ISACA profesní certifikace. [[imork-manazerska-bezpecnost|Manažerská bezpečnost]].
- **CMMC 2.0** — Cybersecurity Maturity Model Certification (DoD USA). 3 úrovně (Foundational / Advanced / Expert); 48 CFR final rule účinný 10. 11. 2025. [[imork-bezpecnostni-strategie|Bezpečnostní strategie]].
- **CRISP-DM** — Cross-Industry Standard Process for Data Mining. Cross-course do [[ipmrk-datamining|IpmrK]].
- **CSIRT** — Computer Security Incident Response Team. Tým pro reakci na incidenty. [[imork-manazerska-bezpecnost]].
- **CVE** — Common Vulnerabilities and Exposures. Standardizovaný identifikátor zranitelnosti. Příklad: **CVE-2022-38392** (rezonanční útok na HDD, [[imork-audio-hack]]).

## D

- **DDoS** — Distributed Denial of Service. Distribuovaný útok na dostupnost. [[imork-sitove-utoky]].
- **DES** — Data Encryption Standard (1975). Historický symetrický algoritmus, 64-bit klíč. [[ochrana-dat|Ochrana dat]].
- **DICOM** — Digital Imaging and Communications in Medicine. Standard zdravotnického zobrazování. [[imork-zdravotnictvi|Zdravotnictví]].
- **DKIM** — DomainKeys Identified Mail (RFC 6376). Digitální podpis emailu. [[imork-email|Email]].
- **DLP** — Data Loss Prevention. Prevence úniku dat (in use / in motion / at rest). [[ochrana-dat|Ochrana dat]].
- **DLT** — Distributed Ledger Technology. Blockchain a podobné. [[imork-financni-sektor|Finanční sektor]].
- **DMARC** — Domain-based Message Authentication, Reporting & Conformance (RFC 7489). Politika použití SPF + DKIM. [[imork-email|Email]].
- **DORA** — Digital Operational Resilience Act (EU 2022/2554). Regulace finančního sektoru. [[imork-financni-sektor|Finanční sektor]].
- **DoS** — Denial of Service. Útok na dostupnost (jednozdrojový předchůdce DDoS). [[imork-sitove-utoky|Síťové útoky]].
- **DPIA** — Data Protection Impact Assessment (čl. 35 GDPR). Posouzení dopadu na ochranu OÚ. [[gdpr|GDPR]].
- **DPO** — Data Protection Officer. Pověřenec pro ochranu OÚ (GDPR čl. 37–39). [[gdpr|GDPR]].
- **DR / DRP / DRaaS** — Disaster Recovery / Plan / as a Service. 7 tiers (0–7). [[imork-dr|Disaster Recovery]], [[bcm|BCM]].

## E

- **EAL** — Evaluation Assurance Level (Common Criteria, ISO/IEC 15408). Úrovně 1–7. [[imork-mobilni-bezpecnost|Mobilní bezpečnost]] (typicky EAL3+).
- **EDR / XDR** — Endpoint / Extended Detection and Response. Pokročilé sledování koncových bodů. [[imork-ransomware|Ransomware]].
- **eduroam** — Federace identit pro akademické instituce. [[imork-akademicke-prostredi|Akademické prostředí]].
- **EHR** — Electronic Health Record. Elektronický zdravotní záznam. [[imork-ehealth|eHealth]].
- **eIDAS** — Nařízení (EU) 910/2014, novelizováno **(EU) 2024/1183 — „eIDAS 2.0"** od 5/2024 (zavádí EUDI Wallet). Elektronická identifikace a důvěryhodné služby. [[ochrana-dat|Ochrana dat]].
- **EMM** — Enterprise Mobility Management. Rozšířená správa mobilních zařízení. [[imork-mobilni-bezpecnost]].
- **EMV** — Europay/Mastercard/Visa. Standard pro čipové karty. [[imork-payment|Bezpečnost plateb]].
- **ENISA** — European Union Agency for Cybersecurity. Evropská agentura pro kybernetickou bezpečnost.
- **EPS** — Events Per Second (SIEM dimenzování) / Elektrická požární signalizace (fyzická bezpečnost). [[ochrana-dat]], [[imork-manazerska-bezpecnost]].
- **ESP** — Encapsulating Security Payload (IPsec). Šifrování + autentizace. [[imork-www]].

## F

- **FIPS 140-3** — Federal Information Processing Standards. Validace kryptografických modulů. Schválen 2019, povinný pro nové validace od dubna 2022; **nahrazuje FIPS 140-2** (jeho validace přechází na Historical List 21. 9. 2026). [[imork-sprava-login]].

## G

- **GDPR** — General Data Protection Regulation, nařízení (EU) 2016/679. Účinnost 25. 5. 2018. [[gdpr|GDPR]].

## H

- **HIPAA** — Health Insurance Portability and Accountability Act (USA, 1996). 5 titulů (I–V): I. *Health Care Access, Portability, and Renewability*; II. *Administrative Simplification* (obsahuje Privacy Rule, Security Rule, Unique Identifiers Rule, Transactions Rule, Enforcement Rule, Breach Notification Rule); III. *Tax-Related Health Provisions*; IV. *Application and Enforcement of Group Health Plan Requirements*; V. *Revenue Offsets*. [[imork-zdravotnictvi|Zdravotnictví]].
- **HITECH Act** — Health Information Technology for Economic and Clinical Health Act (USA, 2009; součást ARRA). Rozšiřuje HIPAA na **business associates**, zavádí **Breach Notification Rule**, posiluje sankce. [[imork-zdravotnictvi|Zdravotnictví]].

## I

- **IAM / IdM** — Identity and Access Management / Identity Management. Správa identit a přístupu. [[imork-manazerska-bezpecnost]].
- **IDS / IPS** — Intrusion Detection / Prevention System. Pasivní detekce vs. aktivní in-line blokace. [[ochrana-dat|Ochrana dat]].
- **IEC 61850** — Standard pro komunikaci v elektrárnách (3-úrovňová architektura). [[imork-energetika]].
- **IEC 62351** — Bezpečnost protokolů IEC 61850. [[imork-smart-grid]].
- **IMS** — IP Multimedia Subsystem. Architektura pro multimediální služby přes IP, základ NGN. [[imork-isp]].
- **IoT** — Internet of Things. Internet věcí — zranitelný útokům přes botnety. [[imork-kradez-dat]], [[imork-smart-grid]].
- **IPsec** — Internet Protocol Security (RFC 4301). Bezpečnost na L3, AH/ESP, transportní/tunelovací režim. [[imork-www]].
- **IRP** — Incident Response Plan. 4 fáze (NIST SP 800-61 Rev. 3, duben 2025; profil CSF 2.0). [[imork-manazerska-bezpecnost]].
- **ISACA** — Information Systems Audit and Control Association. Profesní organizace.
- **ISMS** — Information Security Management System. Systém řízení bezpečnosti informací (ISO 27001). [[isms|ISMS]].
- **ISP** — Internet Service Provider. Poskytovatel internetových služeb. [[imork-isp]].
- **ISVS** — Informační systémy veřejné správy. Zákon č. 365/2000 Sb. (ČR).

## K

- **KII** — Kritická informační infrastruktura (ZKB). [[rizeni-rizik|Řízení rizik]].
- **KRACK** — Key Reinstallation Attack. Útok na WPA2 (2017). [[imork-internetova-bezpecnost]].
- **KYC** — Know Your Customer. Požadavek finančního sektoru. Cross-course do [[expertni-systemy]] (compliance).

## L

- **LDAP** — Lightweight Directory Access Protocol. Adresářové služby. [[imork-manazerska-bezpecnost]].

## M

- **MAD** — Mutually Assured Destruction. Cross-course z teorie her ([[mikk-vezno-dilema-teorie-her|MikK]]) — analog v kybernetické deterrence.
- **MBCO** — Minimum Business Continuity Objective. Minimální úroveň služeb pro kontinuitu. [[bcm|BCM]].
- **MCN** — Mission Critical Networks. Kritické sítě. [[imork-mcn]].
- **MDM** — Mobile Device Management. Správa mobilních zařízení. [[imork-mobilni-bezpecnost]].
- **MFA** — Multi-Factor Authentication. Vícefaktorové ověření (znalost / vlastnictví / biometrika). [[imork-sprava-login]].
- **MICA / MiCA** — Markets in Crypto-Assets, nařízení (EU) 2023/1114. [[imork-financni-sektor]].
- **MITRE ATT&CK** — Adversarial Tactics, Techniques, and Common Knowledge. Znalostní báze útoků. [[imork-anatomie-utoku]].

## N

- **NAC** — Network Access Control. Řízení přístupu k síti (4 fáze). [[ochrana-dat|Ochrana dat]].
- **NBA** — Network Behavior Analysis. Detekce hrozeb chováním sítě (zero-day, polymorfní malware). [[imork-manazerska-bezpecnost]].
- **NCPI** — Network Critical Physical Infrastructure. [[imork-mcn|MCN]].
- **NGN** — Next Generation Networks. Konvergence dat / vysílání / telekomunikace. [[imork-isp]].
- **NIS2** — Směrnice (EU) 2022/2555. Nahrazuje NIS1; rozšířený rozsah kritických služeb.
- **NÚKIB** — Národní úřad pro kybernetickou a informační bezpečnost (ČR). Založen **1. 8. 2017** (odštěpením z NBÚ zákonem č. 205/2017 Sb.); sídlo Brno. Vydává prováděcí vyhlášky k ZKB a Bezpečnostní strategii ČR. [[imork-bezpecnostni-strategie]].

## O

- **OSINT** — Open Source Intelligence. Sběr informací z veřejných zdrojů. [[imork-rizeny-hacking]], [[imork-internetova-bezpecnost]].
- **OWASP** — Open Web Application Security Project. Top 10 web rizik. [[imork-www]].

## P

- **PACS** — Picture Archiving and Communication System. Zdravotnické zobrazování. [[imork-zdravotnictvi]].
- **PCI DSS** — Payment Card Industry Data Security Standard. Aktuální **v4.0.1** (od 6/2024; v4.0 z 3/2022 vyřazena 31. 12. 2024). [[imork-payment]].
- **PDCA** — Plan-Do-Check-Act (Demingův cyklus). [[isms|ISMS]], [[bcm|BCM]].
- **PII** — Personally Identifiable Information. NIST analog k „osobnímu údaji" GDPR. [[gdpr|GDPR]], [[imork-kradez-dat]].
- **PIMS** — Privacy Information Management System. ISO/IEC 27701. [[gdpr|GDPR]].
- **PKI** — Public Key Infrastructure. Certifikační autority, digitální certifikáty. [[imork-manazerska-bezpecnost]].
- **PoA / SoA** — Prohlášení o aplikovatelnosti / Statement of Applicability. ISO 27001 Příloha A. [[rizeni-rizik|Řízení rizik]].

## R

- **RaaS** — Ransomware-as-a-Service. Obchodní model ransomware. [[imork-ransomware|Ransomware]].
- **RPO** — Recovery Point Objective. Maximální přípustná ztráta dat. [[bcm|BCM]].
- **RSA** — Rivest-Shamir-Adleman (1977). Asymetrický algoritmus. [[ochrana-dat|Ochrana dat]].
- **RTBH** — Remotely Triggered Black Hole. Ochrana ISP před DDoS. [[imork-isp]].
- **RTO** — Recovery Time Objective. Maximální přípustná doba výpadku. [[bcm|BCM]].
- **RTP** — Risk Treatment Plan. Plán zvládání rizik. [[rizeni-rizik|Řízení rizik]].
- **RYUK** — Ransomware z let 2018+; aktér v útoku Benešov. [[imork-nemocnice]], [[imork-ransomware]].

## S

- **S/MIME** — Secure/Multipurpose Internet Mail Extensions. End-to-end šifrování emailu. [[imork-email]].
- **SAE** — Security Awareness and Education. Budování bezpečnostního povědomí. **NIST SP 800-50 Rev. 1** (2024; sloučil původní 800-50 a vyřazený 800-16). [[sae|SAE]].
- **SAML** — Security Assertion Markup Language. Federovaná autentizace. [[imork-www]].
- **SCAP** — Security Content Automation Protocol. Automatizované hodnocení bezpečnosti. [[imork-manazerska-bezpecnost]].
- **SHA-256** — Secure Hash Algorithm, 256-bit. [[ochrana-dat]].
- **SIEM** — Security Information and Event Management. Centralizovaná správa bezpečnostních událostí. [[ochrana-dat|Ochrana dat]].
- **SIM swap / SIMjacker** — Útoky převzetím SIM karty. [[imork-mobilni-bezpecnost]].
- **SoA** → viz PoA / SoA.
- **SPF** — Sender Policy Framework (RFC 7208). Antispoofing email. [[imork-email]].
- **SPoF** — Single Point of Failure. Bod selhání zastavující celý proces. [[bcm|BCM]].
- **SSO** — Single Sign-On. Jednotné přihlášení (eduID, OAuth, SAML). [[imork-akademicke-prostredi]].
- **STARTTLS** — Příkaz povýšení nezabezpečené relace na TLS. [[imork-email]].
- **STEEPLE** — Social/Tech/Econ/Ethical/Polit/Legisl/Environ. Analýza vnějšího prostředí pro BCM. [[bcm|BCM]].

## T

- **TISAX** — Trusted Information Security Assessment Exchange. Bezpečnostní standard automotive. [[imork-automotive]].
- **TLP** — Traffic Light Protocol. Klasifikace sdílení informací (RED/AMBER/GREEN/CLEAR). [[imork-akademicke-prostredi]].
- **TLS** — Transport Layer Security. Bezpečnost L4 (3 fáze handshaku). [[imork-www]].
- **TOR** — The Onion Router. Anonymizační síť, exit relays. [[imork-tor|TOR]].

## U

- **UN R155** — UN Regulation No. 155. Cybersecurity Management System pro vozidla; povinné pro nové typy od července 2022, pro celou produkci od července 2024. [[imork-automotive]].
- **ÚOOÚ** — Úřad pro ochranu osobních údajů. Český dozorový úřad pro GDPR; přijímá oznámení o porušení podle čl. 33 GDPR. [[gdpr|GDPR]].
- **UTM** — Unified Threat Management. FW + IDS/IPS + AV + VPN v jednom zařízení. [[ochrana-dat]].

## V

- **VIS** — Významný informační systém (vyhl. 360/2020 Sb.). [[imork-akademicke-prostredi]].
- **VKB** — Vyhláška o kybernetické bezpečnosti. Původní **č. 82/2018 Sb.** (§15 = BCM požadavky) byla **zrušena 1. 11. 2025**; nahradila ji vyhl. č. 409/2025 Sb. (transpozice NIS2). [[bcm|BCM]].

## W

- **WAF** — Web Application Firewall. Aplikační firewall pro web. [[imork-www]].
- **WBAN** — Wireless Body Area Network. Síť senzorů na/v těle pacienta. [[imork-ehealth]].
- **WHOIS** — Protokol pro lookup vlastníka domény. [[imork-www]].
- **WormGPT** — Generativní AI nástroj pro automatizaci kybernetické kriminality. [[imork-ai-utoky]].

## X

- **X-Keyscore** — NSA program (odhalený 2013). [[imork-tor]].
- **XKMS / XACML / XML Encryption / XML Digital Signature** — XML Security stack. [[imork-www]].
- **XSS** — Cross-Site Scripting. Webový útok cílící na klienta. [[imork-www]], [[imork-anatomie-utoku]].

## Z

- **ZKB** — Zákon o kybernetické bezpečnosti. Původní **č. 181/2014 Sb.** byl **zrušen 1. 11. 2025** a nahrazen **zákonem č. 264/2025 Sb.** (transpozice **NIS2**). Definuje role: výbor pro řízení KB, manažer KB, architekt KB, auditor KB, garant aktiva. [[rizeni-rizik|Řízení rizik]].

## Související stránky

- [[imork|ImorK course hub]] — výchozí bod kurzu
- [[imork-normy-prehled|Přehled norem podle sektoru]] — komplementární referenční tabulka
- [[isms|ISMS]] — manažerský rámec, který sjednocuje většinu těchto pojmů
- [[gdpr|GDPR]] — nejčastěji odkazovaná regulace
