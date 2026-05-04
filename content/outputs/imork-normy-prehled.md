---
title: ImorK — Přehled norem a standardů podle sektoru
course: imork
type: output
tags: [imork, isms, normy, iso-27000, nist, oborova-reseni, governance]
sources: [raw/imork/2001 VUT_Bezp Managerská 2022.pdf, raw/imork/2002 VUT_Bezp SAE-2025.pdf, raw/imork/2003 VUT_Bezp Risk Mngmt-2021.pdf, raw/imork/2014 VUT_Bezp BCM-2021.pdf, raw/imork/2017 VUT_Ochrana dat-2022.pdf, raw/imork/Detail předmětu.md]
created: 2026-05-04
updated: '2026-05-04'
---

# ImorK — Přehled norem a standardů podle sektoru

Referenční tabulka všech bezpečnostních norem, standardů, regulací a metodik probíraných v kurzu [[imork|ImorK]]. Slouží jako rychlý lookup k orientaci ve změti zkratek — pro každou normu uvedeno *co normalizuje, kde se v kurzu objevuje, jaký zdroj v repozitáři ji rozebírá*.

## Rodina ISO/IEC 27000

Mezinárodní normy pro řízení informační bezpečnosti.

| Norma | Co normalizuje | Kontext v kurzu |
|---|---|---|
| **ISO/IEC 27001** | Požadavky na ISMS — certifikační norma | Jádro kurzu, [[isms\|ISMS]] |
| **ISO/IEC 27002** | Soubor bezpečnostních opatření (best practices) | [[isms\|ISMS]] |
| **ISO/IEC 27005:2022** | Řízení rizik bezpečnosti informací | [[rizeni-rizik\|Řízení rizik]], [[imork-risk-management]] |
| **ISO/IEC 27011:2024** | ISMS pro telekomunikační organizace | [[imork-isp\|ISP a telekomunikace]] |
| **ISO/IEC 27014:2020** | Governance bezpečnosti informací | [[imork-manazerska-bezpecnost\|Manažerská bezpečnost]] |
| **ISO/IEC 27019:2024** | ISMS pro energetický průmysl | [[imork-energetika\|Energetika]] |
| **ISO/IEC 27031:2025** | Připravenost ICT pro kontinuitu podnikání | [[bcm\|BCM]] |
| **ISO/IEC 27035** | Řízení incidentů informační bezpečnosti (multipart: -1:2023, -2:2023, -3:2020, -4:2024) | [[imork-manazerska-bezpecnost\|Incident management]] |
| **ISO/IEC 27701:2025** | Privacy Information Management System (PIMS); 1. vydání 2019 | [[gdpr\|GDPR]], [[imork-kradez-dat\|Krádež dat]] |
| **ISO 27799:2025** | ISMS pro zdravotnictví (publikováno samostatně, ne ISO/IEC) | [[imork-zdravotnictvi\|Zdravotnictví]] |
| **ISO/IEC 24745:2022** | Ochrana biometrických šablon | [[ochrana-dat\|Ochrana dat]] (biometrický podpis) |
| **ISO 22301:2019** | Požadavky na BCMS — kontinuita činnosti (Amd. 1:2024) | [[bcm\|BCM]] |
| **ISO 31000:2018** | Obecné principy řízení rizik | [[rizeni-rizik\|Řízení rizik]] (umbrella) |
| **IEC 31010:2019** | Techniky posuzování rizik | [[rizeni-rizik\|Řízení rizik]] |

## Normy podle oborového sektoru

Která ISO/sektorová norma platí pro který sektor — tabulka pro rychlou disambiguaci.

| Sektor | Hlavní norma | Doplňující normy/regulace | Stránka |
|---|---|---|---|
| **Zdravotnictví (EU)** | ISO 27799:2025 | GDPR (zvláštní kategorie); ENISA medical | [[imork-zdravotnictvi]] |
| **Zdravotnictví (USA)** | HIPAA (5 titulů I–V) | HITECH Act | [[imork-zdravotnictvi]] |
| **Energetika** | ISO/IEC 27019 | IEC 61850, IEC 62351, IEC TC57 | [[imork-energetika]] |
| **Smart Grid** | NISTIR 7628 | IEC 62351 | [[imork-smart-grid]] |
| **Doprava (železnice)** | CLC/TS 50701 | ENISA Railway, kritická infrastruktura ČR | [[imork-doprava]] |
| **Automotive** | TISAX | UN Regulation 155 (CSMS), ISO/SAE 21434, CHT | [[imork-automotive]] |
| **ISP / telekomunikace** | ISO/IEC 27011 | NGN, IMS, RTBH | [[imork-isp]] |
| **Mission Critical Networks** | ITU-T X.805 (model hrozeb) | NCPI | [[imork-mcn]] |
| **Akademické prostředí** | BICSI 001/004/007/008 | Vyhl. 360/2020 Sb. (VIS), TLP | [[imork-akademicke-prostredi]] |
| **Finanční sektor (EU)** | DORA (2022/2554) | MiCA, NIS2 | [[imork-financni-sektor]] |
| **Platební služby** | PCI DSS v4.0.1 (od 6/2024; v4.0 vyřazena 31. 12. 2024) | EMV, eIDAS | [[imork-payment]] |
| **Web** | NIST SP 800-95, OWASP Top 10 | W3C Web Services | [[imork-www]] |
| **Email** | RFC 7208 (SPF), 6376 (DKIM), 7489 (DMARC) | RFC 8461 (MTA-STS) | [[imork-email]] |

## Další ISO / ITU-T / IEC normy

| Norma | Co normalizuje | Kontext v kurzu |
|---|---|---|
| **ISO/IEC 20000** | IT Service Management System (ITSM) | [[imork-akademicke-prostredi\|Akademické prostředí]] (kombinace s ISO 27001) |
| **ISO/IEC 15408** | Common Criteria — kritéria hodnocení bezpečnosti (EAL 1–7) | [[imork-mobilni-bezpecnost\|Mobilní bezpečnost]] |
| **ISA/IEC 62443** | Cybersecurity for Industrial Automation and Control Systems | [[imork-doprava\|Doprava]], průmyslové řídicí systémy |
| **ISO 11898** | Standard CAN bus — sériová sběrnice ve vozidlech | [[imork-automotive\|Automotive]] |
| **ITU-T X.1051** | ISMS guidelines pro telekomunikační organizace (mirror ISO 27011) | [[imork-isp\|ISP]] |
| **ITU-T Y.2001** | Next Generation Networks — obecná architektura | [[imork-isp\|ISP]] |
| **ITU-T Y.2720** | NGN identity management framework | [[imork-isp\|ISP]], [[imork-manazerska-bezpecnost\|IAM]] |
| **EU 93/42/EEC** | Medical Devices Directive — zdravotnické prostředky | [[imork-zdravotnictvi\|Zdravotnictví]] |
| **EU 93/68/EEC** | CE marking — označování shody | [[imork-zdravotnictvi\|Zdravotnictví]] |
| **BICSI 001-2017** | Vzdělávací instituce — kabeláž, infrastruktura | [[imork-akademicke-prostredi\|Akademické prostředí]] |
| **BICSI 004** | Healthcare Facilities — infrastruktura zdravotnických zařízení | [[imork-zdravotnictvi\|Zdravotnictví]] |
| **BICSI 002** | Data Center Design — návrh datových center | [[imork-isp]] |
| **BICSI 007** | Inteligentní budovy | [[imork-akademicke-prostredi]] |
| **BICSI 008** | Wireless / WLAN | [[imork-akademicke-prostredi]], [[imork-isp]] |

## NIST Special Publications (SP 800)

Americké standardy pro federální systémy, široce používané jako de facto best practices.

| SP | Téma | Kontext v kurzu |
|---|---|---|
| **800-16** | IT Security Training Requirements (1998; **vyřazeno 12. 9. 2024**, sloučeno do 800-50r1) | [[sae\|SAE]] |
| **800-30 Rev. 1** | Guide for Conducting Risk Assessments (2012) | [[rizeni-rizik\|Řízení rizik]] |
| **800-39** | Managing Information Security Risk (2011) — 3 úrovně: organizace / mise / IS | [[rizeni-rizik\|Řízení rizik]] |
| **800-45 v2** | Guidelines on Electronic Mail Security (2007) | [[imork-email\|Email]] |
| **800-50 Rev. 1** | Building a Cybersecurity and Privacy Learning Program (2024; nahrazuje původní 800-50 a 800-16) | [[sae\|SAE]] |
| **800-57** | Recommendation for Key Management (Part 1 Rev. 5) | [[imork-manazerska-bezpecnost\|Správa klíčů]] |
| **800-61 Rev. 3** | Incident Response Recommendations (4/2025; CSF 2.0 Community Profile) | [[imork-manazerska-bezpecnost\|Incident management]] |
| **800-63 Rev. 4** | Digital Identity Guidelines (7/2025; suite 800-63 + 800-63A/B/C) | [[imork-sprava-login\|Správa přihlašování]] |
| **800-92** | Guide to Computer Security Log Management (2006; Rev. 1 v draftu) | [[imork-manazerska-bezpecnost\|SIEM/Log mgmt]] |
| **800-95** | Guide to Secure Web Services (2007, dlouho neaktualizováno) | [[imork-www\|Bezpečnost webu]] |
| **800-100** | Information Security Handbook for Managers | [[imork-manazerska-bezpecnost\|Governance]] |
| **800-115** | Technical Guide to Information Security Testing | [[imork-manazerska-bezpecnost\|Penetrační testy]] |
| **800-122** | Guide to Protecting Confidentiality of PII (2010) | [[gdpr\|GDPR]] (americký analog) |
| **500-172** | Computer Security Training Guidelines (1989; **vyřazeno 1998**, historický) | [[sae\|SAE]] |
| **NISTIR 7628 Rev. 1** | Smart Grid Cybersecurity (2014) | [[imork-smart-grid\|Smart Grid]] |
| **NISTIR 8062** | Privacy Engineering and Risk Management (2017) | [[gdpr\|GDPR]] |
| **NISTIR 8374** | Ransomware Risk Management Framework (2/2022; profil CSF 1.1) | [[imork-ransomware\|Ransomware]] |

## EU regulace a směrnice

| Regulace | Plné označení | Oblast | Stránka |
|---|---|---|---|
| **GDPR** | Nařízení (EU) 2016/679 | Ochrana osobních údajů (od 25. 5. 2018) | [[gdpr\|GDPR]] |
| **eIDAS** | Nařízení (EU) 910/2014, novelizováno **(EU) 2024/1183 — „eIDAS 2.0"** od 5/2024 | Elektronická identifikace a služby vytvářející důvěru; eIDAS 2.0 zavádí EUDI Wallet | [[ochrana-dat\|Ochrana dat]] |
| **NIS2** | Směrnice (EU) 2022/2555 | Kybernetická bezpečnost provozovatelů kritických služeb | [[gdpr\|GDPR]] (cross-link) |
| **DORA** | Nařízení (EU) 2022/2554 | Digital Operational Resilience pro finanční sektor | [[imork-financni-sektor\|Finanční sektor]] |
| **MiCA** | Nařízení (EU) 2023/1114 | Markets in Crypto-Assets | [[imork-financni-sektor\|Finanční sektor]] |
| **UN R155** | UN Regulation No. 155 | Cybersecurity Management System pro vozidla | [[imork-automotive\|Automotive]] |

## České právní předpisy

| Předpis | Plný název | Oblast | Stránka |
|---|---|---|---|
| **ZKB (původní)** | Zákon č. 181/2014 Sb. | Kybernetická bezpečnost (KII, VIS); **zrušen 1. 11. 2025** | [[rizeni-rizik\|Řízení rizik]], [[isms]] |
| **ZKB (nový)** | Zákon č. 264/2025 Sb. | Nový zákon o kybernetické bezpečnosti — transpozice **NIS2**, účinný od 1. 11. 2025 | [[rizeni-rizik\|Řízení rizik]], [[isms]] |
| **VKB (původní)** | Vyhláška č. 82/2018 Sb. | Provádění ZKB; §15 = BCM požadavky; **zrušena 1. 11. 2025** | [[bcm\|BCM]] |
| **Nová prováděcí vyhláška** | Vyhláška č. 409/2025 Sb. | Bezpečnostní opatření poskytovatele regulované služby v režimu vyšších povinností; Příloha č. 6 = doporučená témata SAE; účinná 1. 11. 2025 | [[sae\|SAE]] |
| — | Vyhláška č. 360/2020 Sb. | Významné informační systémy (VIS); **zrušena 1. 11. 2025** | [[imork-akademicke-prostredi]] |
| — | Vyhláška č. 437/2017 Sb. | Kritéria pro určení provozovatele základní služby (vč. zdravotnictví); novelizována 12/2020 po útocích na nemocnice; **zrušena 1. 11. 2025** | [[imork-nemocnice]] |
| — | Zákon č. 110/2019 Sb. | Zpracování osobních údajů (doplněk GDPR v ČR) | [[gdpr\|GDPR]] |
| **TZ §312d** | Trestní zákoník (zák. č. 40/2009 Sb.) | Financování terorismu — riziko při platbě ransomu APT/RaaS skupinám | [[imork-ransomware\|Ransomware]] |
| **TZ §361** | Trestní zákoník (zák. č. 40/2009 Sb.) | Účast na organizované zločinecké skupině — riziko při platbě RaaS | [[imork-ransomware\|Ransomware]] |
| **TZ §216** | Trestní zákoník (zák. č. 40/2009 Sb.) | Legalizace výnosů z trestné činnosti — riziko při platbě ransomu | [[imork-ransomware\|Ransomware]] |
| **TZ §230** | Trestní zákoník (zák. č. 40/2009 Sb.) | Neoprávněný přístup k počítačovému systému — trestnost útočníka | [[imork-anatomie-utoku]] |

## Frameworky a metodiky

| Framework | Vydavatel | Účel |
|---|---|---|
| **NIST CSF 2.0** (2024) | NIST | **6 funkcí**: Govern (nová od 2.0), Identify, Protect, Detect, Respond, Recover |
| **MITRE ATT&CK** | MITRE Corp. | Znalostní báze taktik a technik útočníků |
| **OWASP Top 10** | OWASP | 10 nejkritičtějších rizik webových aplikací |
| **CIS Controls** | Center for Internet Security | 18 (v8) prioritizovaných kontrol |
| **CMMC 2.0** | DoD (USA) | Cybersecurity Maturity Model Certification — 3 úrovně (Foundational / Advanced / Expert); 48 CFR final rule účinný 10. 11. 2025 |
| **ENISA NCSS** | ENISA | National Cyber Security Strategy guidance |
| **CRISP-DM** | konsorcium | Cross-Industry Standard Process for Data Mining |
| **STEEPLE** | — | Analýza vnějšího prostředí pro BCM (Social/Tech/Econ/Ethical/Polit/Legisl/Environ) |

## Bezpečnostní role (governance)

Standardní role v ISMS organizaci.

| Role | Anglicky | Odpovědnost | Norma |
|---|---|---|---|
| **CIO** | Chief Information Officer | Celkové řízení ICT | obecná |
| **CISO** | Chief Information Security Officer | Řízení informační bezpečnosti, reporting vedení | obecná |
| **CTO** | Chief Technology Officer | Technologická strategie | obecná |
| **ISSO** | Information System Security Officer | Operativní bezpečnost systémů | NIST |
| **DPO** | Data Protection Officer | Pověřenec pro ochranu osobních údajů | GDPR (čl. 37–39) |
| **Manažer KB** | — | Odpovědný za ISMS | ZKB |
| **Architekt KB** | — | Návrh a implementace opatření | ZKB |
| **Auditor KB** | — | Provádění auditů | ZKB |
| **Garant aktiva** | Asset owner | Rozvoj, použití a bezpečnost aktiva | ZKB |

## Profesní certifikace ISACA / (ISC)²

| Cert | Vydavatel | Zaměření |
|---|---|---|
| **CISA** | ISACA | Certified Information Systems Auditor |
| **CISM** | ISACA | Certified Information Security Manager |
| **CRISC** | ISACA | Risk and Information Systems Control |
| **CGEIT** | ISACA | Governance of Enterprise IT |
| **CISSP** | (ISC)² | Certified Information Systems Security Professional |
| **Common Criteria EAL** | ISO/IEC 15408 | Evaluation Assurance Level (EAL1–7) |

## Architektonické referenční modely

| Model | Vrstvy / dimenze | Stránka |
|---|---|---|
| **ISO/OSI** | 7 vrstev (L1 fyzická → L7 aplikační) | [[imork-anatomie-utoku]], [[imork-sitove-utoky]] |
| **ITU-T X.805** | Bezpečnostní dimenze, vrstvy, plány | [[imork-mcn\|MCN]] |
| **IEC 61850** | 3 úrovně: stanice / stanové / procesní | [[imork-energetika\|Energetika]] |
| **NCPI** | Network Critical Physical Infrastructure | [[imork-mcn\|MCN]] |

## Související stránky

- [[imork|ImorK course hub]] — výchozí bod do všech 34 záznamů přednášek
- [[imork-glosar|ImorK — Glosář pojmů]] — abecední slovník zkratek a klíčových konceptů
- [[isms|ISMS]] — manažerský rámec, který tyto normy sjednocuje
- [[rizeni-rizik|Řízení rizik]] — metodika napříč ISO 27005 / 31000 / NIST 800-30
- [[gdpr|GDPR]] — nejčastěji odkazovaná regulace v kurzu
