---
title: Přehled — Fakulta podnikatelská VUT v Brně
type: overview
tags: [fp-vut, prehled]
created: 2026-04-10
updated: '2026-05-04'
---

# Přehled — Fakulta podnikatelská VUT v Brně

Tato wiki slouží jako znalostní báze pro studium na Fakultě podnikatelské VUT v Brně. Obsahuje shrnutí přednášek, skripta, poznámky a propojená témata napříč kurzy.

## Kurzy

- [[ipmrk|Pokročilé metody v rozhodování (IpmrK)]] — fuzzy logika, neuronové sítě, genetické algoritmy, evoluční algoritmy, teorie chaosu, optimalizace, datamining, predikce. Garant: prof. Dostál. 13 zdrojů zpracováno.
- [[imork|Management oborových řešení (ImorK)]] — ISMS, kybernetická bezpečnost, oborová řešení (zdravotnictví, energetika, doprava, automotive, ISP). Garant: Ing. Novák. 34 zdrojů zpracováno.
- [[imek|Matematická ekonomie (ImeK)]] — derivace, integrály, Lagrangeova metoda v ekonomii; poptávka/nabídka, elasticita, produkce, užitečnost, národní důchod (IS-LM). Garant: doc. Půža, vyučující Mgr. Bobalová. 5 zdrojů zpracováno (3 PDF přednášky + sylabus + naskenovaná kniha Mezník, kap. 2–7, 107 stran).
- [[irmank|Risk management (IrmanK)]] — kritické faktory úspěchu firmy (7S, EFQM), modely změny ([[lewinuv-model|Lewin]], [[kaizen-vs-inovace|KAIZEN]]), riziko a jeho měření, mapa rizik, taktiky snižování, finanční nástroje (faktoring, forfaiting, akreditiv), AI metody (expertní systémy, GA, ANN), investiční rozhodování (BOT case study), krizové řízení. Garant: prof. Rais. 3 zdroje zpracovány (sylabus + 2 prezentace, celkem 174 slidů).
- [[mikk|Mikroekonomie 2 (mikK)]] — pokročilá analýza chování spotřebitele a firmy: elasticity, Marshallova/Hicksova poptávka, riziko/nejistota; tržní struktury (monopol, cenová diskriminace, monopson, Cournot/Stackelberg/Bertrand, kartely, monopolistická konkurence); behavioristické modely firmy (Simon, Cyert-March, Doyle). Garant: prof. Škapa, vyučující (KS): Ing. Luňáček. 6 zdrojů zpracováno (sylabus + 3 PDF přednášky + řešené Předtermíny + článek Buchta-Kovárník).

## Průřezová témata

Některá témata se prolínají více kurzy:

- [[predikce|Predikce]] — prognózování časových řad ([[ipmrk|IpmrK]]: NN/GA/chaos; [[irmank|IrmanK]]: Box-Jenkins, Delphi, systémová dynamika; [[mikk|MikK]]: ekonometrie + dekompozice)
- [[anfis|ANFIS]] — hybridní systém na pomezí fuzzy logiky a neuronových sítí
- [[optimalizace|Optimalizace]] — hledání minima/maxima, základ GA i evolučních algoritmů
- [[lagrangeova-metoda|Lagrangeova metoda]] — vázaná optimalizace s multiplikátory (ImeK — užitečnost, výdaje; MikK — Marshall/Hicks dualita)
- [[rizeni-rizik|Řízení rizik]] — kybernetické pojetí v ImorK (ISO 27005); podnikové pojetí v IrmanK ([[mapa-rizik]], [[taktiky-rizeni-rizik]])
- [[isms|ISMS]] — systém řízení bezpečnosti informací napříč obory
- [[gdpr|GDPR]] — nařízení (EU) 2016/679; cross-course koncept (ImorK [[imork-kradez-dat|krádež dat]] DPIA + ISO 27701; IrmanK [[mapa-rizik|regulační riziko]]; IpmrK [[expertni-systemy|compliance ES]])
- [[geneticke-algoritmy|Genetické algoritmy]] — optimalizace v IpmrK; validace NPV v IrmanK ([[investicni-rozhodovani-bot]])
- [[umele-neuronove-site|Umělé neuronové sítě]] — klasifikace a predikce v IpmrK; klasifikace investic v IrmanK
- [[expertni-systemy|Expertní systémy]] — FEL-EXPERT v IrmanK pro výběr prognostické techniky a metod snižování rizika
- **Elasticita poptávky** — základní pojem v [[elasticita|ImeK (primer)]]; pokročilé pojetí (cenová, geometrická, konstantní, EXY, EI) v [[mikk-elasticita-poptavky|MikK]]
- **Optimalizace spotřebitele** — Lagrangeovská v [[optimalizace-spotrebitele|ImeK]]; rozšířená o tři metody řešení a bod nasycení v [[mikk-rovnovaha-spotrebitele|MikK]]
- **Tržní struktury** — dokonalá konkurence + monopol v ImeK; pokročilé tržní struktury (oligopol, monopolistická konkurence, monopson) v MikK

## Propojení mezi kurzy

- **IpmrK ↔ ImorK**: Rozhodovací metody (fuzzy logika, neuronové sítě) se uplatňují i v predikci kybernetických hrozeb a optimalizaci bezpečnostních opatření. [[imork-ai-utoky|AI útoky]] (WormGPT, BEC) demonstrují zneužití generativní AI; obrana využívá [[umele-neuronove-site|ANN]] pro detekci anomálií.
- **IpmrK ↔ ImeK**: [[optimalizace|Optimalizační úlohy]] jsou tématem obou kurzů — ImeK nabízí klasický kalkul (Lagrange, extrémy funkcí), IpmrK metaheuristiky (GA, PSO, SA) pro problémy bez analytického řešení.
- **IpmrK ↔ IrmanK**: AI metody (GA, ANN, ES, fuzzy logika) jsou v IpmrK představeny obecně; IrmanK je aplikuje na **investiční rozhodování** ([[investicni-rozhodovani-bot|BOT case study]]) a výběr metod snižování rizika ([[expertni-systemy|FEL-EXPERT]]).
- **ImorK ↔ IrmanK**: Oba kurzy řeší rizika, ale z různých úhlů — ImorK kybernetické (ISO 27005), IrmanK podnikové (změnové procesy, investiční riziko, finanční nástroje). [[bcm|BCM]] z ImorK je nástrojem [[krizove-rizeni|krizového řízení]] v IrmanK.
- **ImeK ↔ IrmanK**: ImeK matematická příprava (derivace, Lagrange, optimalizace) podporuje IrmanK kvantitativní metody ([[mereni-rizika]], [[operacni-vyzkum]], [[investicni-rozhodovani-bot|NPV citlivostní analýzy]]).
- **ImeK ↔ MikK**: ImeK pokrývá matematický aparát (Lagrange, derivace, Cobb-Douglas, IS-LM) a základy mikroekonomie (poptávka/nabídka, elasticita, optimum spotřebitele/firmy) — slouží jako primer pro pokročilou MikK. MikK pak rozšiřuje na nedokonalé tržní struktury (monopol s vícezávody, cenová diskriminace, oligopol, MK), Slutsky/Hicks dualitu poptávky, riziko a behavioristické modely firmy.
- **MikK ↔ IpmrK**: MikK [[mikk-vezno-dilema-teorie-her|teorie her a Nashova rovnováha]] doplňuje IpmrK pojetí optimalizace pomocí GA/SA. Behavioristické modely firmy (Simon, Cyert-March) v MikK rezonují s rozhodovacími přístupy v IpmrK.
- **MikK ↔ IrmanK**: MikK [[mikk-riziko-nejistota-spotrebitele|očekávaný užitek a pojištění]] navazuje na IrmanK měření rizika; Doyleovy zóny tolerance (MikK) souvisí se strategickým plánováním (IrmanK). Behavioristické modely firmy se uplatňují v obou kurzech (Buchta-Kovárník článek).
