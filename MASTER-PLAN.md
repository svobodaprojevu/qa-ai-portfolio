# MASTER PLAN — AI‑Powered Real‑World QA Engineer

| | |
|---|---|
| **Verze** | 2.0 — 6. 9. 2026 (nahrazuje COURSE_PLAN v1.0 z 31. 8.; znalostní rozsah zachován, formát změněn z lekcí na simulovanou firmu a sprinty) |
| **Cíl** | Junior QA / Software Tester se silným přesahem do AI‑assisted a AI‑augmented QA, schopný samostatně zpracovat ticket od requirementu po release decision a u každého kroku rozhodnout HUMAN / AI / AGENT / AUTOMATION / HUMAN+AI |
| **Poměr** | ~10 % teorie (jen když je potřeba) / ~90 % praxe na skutečné aplikaci |
| **Rozsah** | Sprint 0 (onboarding) + 8 sprintů + finální projekt + finální AI challenge · odhad 200–260 h · 4–6 měsíců při 10–12 h/týden |
| **Aplikace** | Toolshop — Practice Software Testing (Testsmith): hosted TEST/STAGE + lokální Docker s DB od Sprintu 3 |

---

## 1. Východiska

### 1.1 Reference Coders Lab „Manual Tester"
Veřejná osnova: prework (ISTQB terminologie, DB základy) → principy a techniky manuálního testování, řízení testů, nástroje → Scrum sprint na reálné aplikaci v týmu → AI workshop (nástroje, automatizace, bezpečnostní rizika) → ISTQB zkouška → volitelně Automation Tester → Career Lab (CV, LinkedIn, pohovor) → Test Lab (finanční, CRM, HR aplikace, record & play, projektová dokumentace). Nástroje: Jira, Postman, Scrum, web + API testing, základy kyberbezpečnosti. Celý tento rozsah je v plánu pokrytý.

### 1.2 Co v klasických kurzech chybí a co tento plán doplňuje

**Moderní AI/QA skills (hlavní přidaná hodnota):**
- prompt engineering a context engineering učené na reálných ticketech, ne akademicky
- AI output evaluation a verification jako samostatná dovednost (včetně záměrných AI failure cases)
- AI jako reviewer (second QA opinion) a debugging assistant (logy, HAR, trace, CI)
- AI‑assisted test generation → human review → AI‑assisted automation → AI code review
- agentic workflows: skills a subagenti v Claude Code, human‑in‑the‑loop, agent spec s limity
- rozhodovací rámec HUMAN / AI / AGENT / AUTOMATION / HUMAN+AI + smyčka REDUCE · AUTOMATE · AUGMENT · DELEGATE · VERIFY · MEASURE
- měření produktivity: skutečné časy s AI a bez AI, accepted/rejected návrhy, bugs found by me vs suggested by AI
- AI security: co nikdy neposílat, GDPR, firemní policy
- automation candidate analysis (ROI, stabilita, frekvence) a root cause analysis selhání testů
- CI/CD prakticky: GitHub Actions, čtení červené pipeline, flaky tests

**Moderní manuální QA, které Coders Lab nepokrývá explicitně:**
- accessibility (WCAG 2.2, European Accessibility Act), security basics pro testera (IDOR, cookie flags, obcházení FE validace), lokalizace pro CZ trh, exploratory testing s chartery (SBTM), test management nástroj, čtení logů a diagnostika FE vs BE, release proces a prostředí, estimace a prioritizace pod tlakem, angličtina pro artefakty

### 1.3 Simulovaná firma

**Ferrum Digital s.r.o.** — český e‑commerce. Produkt **Toolshop**: e‑shop s nářadím. Angular frontend, Laravel REST API se Swaggerem, MariaDB. Zákaznický a admin účet, registrace, katalog, košík, checkout, faktury, kontaktní formulář, oblíbené.

| Role | Jméno | Kdo hraje |
|---|---|---|
| Junior QA Tester | **Jakub** | Jakub |
| Senior QA / QA Lead | Honza | Claude — hlavní hlas mentora a reviewera |
| Product Owner | Markéta | Claude — zadání, AC, priority, tlak na release |
| Scrum Master | Petra | Claude — ceremonie, proces |
| Backend developer (Laravel) | Tomáš | Claude — „mně to funguje", API otázky |
| Frontend developer (Angular) | Filip | Claude — UI, locators, testovatelnost |
| Business Analyst | Lucie | Claude — requirements, business pravidla |
| DevOps | Radek | Claude — prostředí, CI, nasazení |
| AI QA Specialist | Dan | Claude — AI workflow, review promptů, agenti |

**Prostředí a přístupy:** `project/README.md`.

**Jira workflow:** TO DO → IN PROGRESS → READY FOR QA → IN QA → (BUG) → READY FOR RETEST → DONE. Bug je samostatný issue typ propojený se story.

**Definition of Ready (story):** má AC, má design nebo popis UI, závislosti vyjasněné, QA se ptal na nejasnosti a dostal odpověď, tým rozumí a umí odhadnout.
**Definition of Done (story):** kód v main, code review, nasazeno na TEST, otestováno QA podle test cases + exploratory, otevřené bugy pouze Minor/Trivial se souhlasem PO, regresní dopad ověřen, dokumentace/test cases aktualizované.

---

## 2. Rozhodovací rámec: HUMAN / AI / AGENT / AUTOMATION / HUMAN+AI

| Režim | Co to je | Kdy | Příklad |
|---|---|---|---|
| **HUMAN** | Úsudek, odpovědnost, kontext | riziko, priorita, „je to bug?", GO/NO‑GO, exploratory, obhajoba, otázky na PO | rozhodnout, že duplicitní účet je Critical, ne Major |
| **AI** | Přemýšlení a generování na vyžádání | draft scénářů, edge cases, test data, vysvětlení response, překlad, shrnutí | „navrhni edge cases pro DOB pole" → já filtruji |
| **AI jako reviewer** | Druhý názor nad mou hotovou prací | po každém mém artefaktu | „co jsem v test cases přehlédl?" |
| **AGENT** | Vícekrokový úkol s nástroji a rozhodováním mezi kroky | opakovaný postup s jasným vstupem, výstupem a verifikačním krokem | requirement agent: US + AC → nejasnosti, rizika, scénáře → soubor podle šablony |
| **AUTOMATION** | Deterministické opakování bez úsudku | regrese, smoke, API kontrakty, datové kontroly | Playwright suite v CI |
| **HUMAN+AI** | Párová práce v reálném čase | debugging, RCA, refactoring testů, analýza logů | AI navrhne hypotézu selhání → já ověřím v trace |

**Pět otázek před každým významným úkolem:** Co bych udělal sám? Co může AI? Co může agent? Co lze automatizovat? Co musí ověřit člověk?

**Smyčka efektivity u každého workflow:** REDUCE (co odstranit) · AUTOMATE (co automatizovat) · AUGMENT (co AI urychlí) · DELEGATE (co AI/agent provede) · VERIFY (co ověří člověk) · MEASURE (kolik času to ušetřilo — skutečná čísla).

**Pravidlo proti AI theatre:** když je něco rychlejší ručně, když AI vytvoří víc práce, než ušetří, když agent nemá opakované použití, když automatizace nemá ROI — řekne se to nahlas a zapíše do playbooku jako „nepoužívat".

---

## 3. AI maturity — deset úrovní a kde je potkáš

| Level | Popis | Sprint |
|---|---|---|
| 1 | AI jako chatbot — otázka, odpověď, ověření | 0–1 |
| 2 | AI jako QA assistant — draft scénářů, test dat, formátování podle šablony | 1 |
| 3 | AI jako reviewer — second opinion nad mou prací, rubrika promptu | 1–2 |
| 4 | AI jako debugging assistant — console, network, HAR, stack trace | 2–3 |
| 5 | AI + automation — Playwright generovaný s AI, review vygenerovaného kódu | 5 |
| 6 | AI + tools — Claude Code v repu, skills, Playwright MCP, CI logy | 5–6 |
| 7 | AI workflow — opakovatelný postup ticket → analýza → testy → report | 6 |
| 8 | AI agents — specializovaní agenti se spec, limity a verifikací | 6–7 |
| 9 | Multi‑step agentic QA workflow — agenti řetězené s human‑in‑the‑loop | 7 |
| 10 | AI‑augmented QA engineer — samostatný finální projekt + optimalizace procesu | 8 |

---

## 4. Sprint map

Sprint = cca 2 týdny mého času (10–12 h/týden). Každý sprint: planning → tickety → dailies → review → retro → release decision. Tickety chodí postupně; nikdy neuvidím řešení předem.

### Sprint 0 — Onboarding (2–3 sezení)
**Cíl:** pracovní prostředí a přístupy. Repo, Jira, Claude Code + CLAUDE.md, Postman, screenshot/video nástroj, přístup k TEST/STAGE, čtení `project/README.md`.
**Teorie just‑in‑time:** vrstvy aplikace, HTTP request/response, status codes, prostředí (jen tolik, kolik je potřeba pro první ticket).
**AI level:** 1. **Výstup:** funkční workspace, první commit.
*Pozn.: baseline z 31. 8. — cvičení „vrstvy přihlášení" 5/8 v pořadí, FE/BE rozlišení správně, DB vs BE aktér k dotažení.*

### Sprint 1 — Zákaznické účty
**Tickety:** TS‑101 Registrace (READY FOR QA) · TS‑102 Přihlášení/odhlášení · TS‑103 Profil · TS‑104 Zapomenuté heslo (v refinementu, chybí AC) · TS‑100 Onboarding.
**Naučím se prací:** requirement analysis, otázky na PO, risk analysis, test scenarios → test cases (EP, BVA, negativní), test data, manuální execution, exploratory (30min mise), bug report, Jira workflow, DevTools Network/Console/Application základ, retest, session/cookies.
**AI:** level 1–3 — prompt a context engineering na TS‑101 (rubrika: context, instructions, constraints, output format, missing info, verification); AI review mých scénářů; první záznamy v AI‑USAGE‑LOG; první záměrný AI failure case.
**Simulace:** dev „mně to funguje", PO změní jedno AC uprostřed sprintu, story bez AC v refinementu.
**Výstup do portfolia:** analýza TS‑101, scénáře, test cases (EN), 5+ bug reportů, exploratory notes, Jira board, sprint review, GO/NO‑GO #1.
**Hodnocení:** rubrika ticketu (kap. 6) + kvalita promptů.

### Sprint 2 — Katalog: vyhledávání, filtry, řazení, stránkování, detail produktu
**Naučím se:** decision tables, pairwise princip, stavy obrazovek (empty/loading/error), i18n (diakritika, řazení), responzivita, cross‑browser, základní accessibility (keyboard, labels, kontrast, axe), regression checklist první verze, triage meeting, severity/priority pod tlakem.
**AI:** level 3–4 — AI jako reviewer a debugging assistant (console/network); první skill v Claude Code: `bug-report` (z mých surových poznámek report podle šablony) — vznikne, protože v Sprintu 1 jsem psal 5 reportů ručně; **Requirement agent v1** (spec + použití na TS‑2xx).
**Simulace:** requirement se změní, design vs AC konflikt, intermitentní chyba.
**Výstup:** decision table pro filtry, a11y nálezy, regression checklist v1, `bug-report` skill, AGENT‑PLAYBOOK záznam #1.

### Sprint 3 — Košík a checkout + API + databáze
**Naučím se:** state transition (objednávka), peníze (ceny, množství, zaokrouhlení, DPH), checkout kroky, platba v sandboxu, faktura; **Postman**: REST, CRUD, auth (Bearer), environments, variables, positive/negative API testy, asserty, Collection Runner; **SQL**: lokální Docker instance Toolshopu (MariaDB přes phpMyAdmin/DBeaver, MailCatcher pro e‑maily) — SELECT/WHERE/JOIN/COUNT/GROUP BY, ověření, že UI/API zapsalo správně; API ↔ UI konzistence; obcházení FE validace.
**AI:** level 4 — **API test agent** (Swagger → návrh testů + test data → já ověřím), AI‑assisted SQL (musím vysvětlit, co dotaz dělá), AI analýza response; záměrný AI failure: vymyšlený endpoint a vymyšlený sloupec.
**Simulace:** API vrací jiná data než UI, databázová nekonzistence, dev nesouhlasí se severity.
**Výstup:** Postman kolekce (bez tokenů), API test cases, SQL ověření, API bug reporty, **Bug triage agent** spec + použití.

### Sprint 4 — Účet, role, oprávnění, admin + bezpečnost a release
**Naučím se:** role customer/admin, permission matrix, IDOR, cookie flags, přístup po logoutu, citlivá data v URL/storage; use case testing, Gherkin (AC → scénáře); regression plán před release; test report; **první plný GO/NO‑GO s obhajobou** proti PO.
**AI:** level 4 → 5 příprava — **Regression agent** (změna → kandidáti na regresi → já rozhodnu), **Test report agent** (výsledky → QA summary → já finalizuji).
**Simulace:** permissions bug závislý na roli, deadline pressure, hotfix.
**Výstup:** permission matrix, security nálezy, regression plan, test report Sprintu 4, release decision.

### Sprint 5 — Automatizace: Playwright
**Naučím se:** automation candidate analysis (20 test cases: automate now / later / don't; kritéria repeatability, stability, business value, maintenance, frequency, risk, ROI); Playwright setup, codegen, locators (role/label/testid), assertions, auto‑wait, Page Object Model, trace viewer; review AI‑generovaného testu (brittle locator, zbytečné waity, duplicita, špatné asserty, test dependency, flaky); Git branches + pull requests; **GitHub Actions** — první CI běh.
**AI:** level 5–6 — **Automation agent** (manual TC → Playwright draft → moje review), Claude Code v repu s Playwright MCP (ověřím dostupnost), AI code review mého i jeho kódu.
**Simulace:** AI vygeneruje test s brittle locatorem a falešně zeleným assertem — musím to najít.
**Výstup:** `automation/playwright/` suite (login, registrace, search, cart) s POM, CI workflow, automation candidate analysis, PR s review.

### Sprint 6 — Regrese, RCA, debugging, Selenium
**Naučím se:** root cause analysis selhání (reproduce → inspect → evidence → classify: app bug / automation bug / environment / data / infra / flaky → AI hypotéza → ověření); flaky test investigation; CI failure analysis; Selenium základ (WebDriver, locators, assertions, struktura) + Selenium vs Playwright a kdy který; AI‑assisted regression planning na skutečné změně (nová sprintová verze aplikace).
**AI:** level 6–7 — **Debug agent** (trace, console, network, CI log → hypotéza + důkaz), opakovatelný **AI workflow** ticket → analýza → testy → report.
**Simulace:** automation failure, prostředí padá, změna aplikace rozbije testy.
**Výstup:** RCA reporty, stabilizovaná suite, Selenium ukázka + srovnání, workflow dokument.

### Sprint 7 — Agentic QA workflow
**Naučím se:** návrh multi‑step agentního workflow s human‑in‑the‑loop (requirement → test design → execution support → triage → report), Claude Code subagenti a skills, měření produktivity (s AI / bez AI na stejném typu úkolu), AI security audit vlastního workflow, AI QA metriky.
**AI:** level 8–9. Všechny agenty mají spec v `ai/AGENT-PLAYBOOK.md` a byly skutečně použité; agenty bez použití se ruší.
**Simulace:** agent udělá chybu (špatná severity, halucinovaný endpoint) — musím ji zachytit; PO chce „AI pro AI" — musím říct ne.
**Výstup:** AGENT‑PLAYBOOK kompletní, AI‑QA‑PLAYBOOK z reálných situací, metriky za Sprinty 1–7.

### Sprint 8 — Finální projekt + finální AI challenge
**Finální projekt (bez návodu):** nová aplikace (jiná než Toolshop; kandidát: OrangeHRM demo nebo Restful Booker Platform — ověřím před startem), product description, requirements, user stories, AC, prostředí, deadline. 22 kroků z §50 zadání samostatně. Interní očekávání a inventář nálezů si vedu bez tvého přístupu; po skončení porovnáme *bugs I found / AI suggested / I missed / AI missed*.
**Finální AI challenge:** „Optimize this QA process with AI" — dostanu manuální QA workflow, navrhnu co ponechat manuálně, co automatizovat, kde AI, kde agent, co propojit, kde CI, kde AI nepoužívat. Review jako Senior QA + AI Automation Lead.
**Výstup:** `final-report/` — QA report, finální hodnocení (kap. 6.3), AI Productivity Score, Job readiness, CV položka, LinkedIn formulace.

### Průběžné vedlejší linky
- **ISTQB terminologie** — glosář roste s každým sprintem; na konci volitelná příprava na CTFL v4.0 (mocky).
- **Doménový trénink** — když bude čas: OrangeHRM (HR, role), Restful Booker (API), ParaBank (finance) jako krátké 90min mise.
- **Bonus reálný projekt** — QA web Tresor Club (vlastní projekt) jako portfolio navíc.

---

## 5. Agenti — roadmapa (stavíme až při reálné potřebě)

| Agent | Vzniká | Spouštěč | Verifikace člověkem |
|---|---|---|---|
| Requirement agent | Sprint 2 | 3. ticket, u kterého dělám analýzu ručně | přijmu/odmítnu každou nejasnost a riziko |
| Test design agent | Sprint 2–3 | opakované psaní scénářů ze stejných AC | duplicity, chybějící negativní, nereálné předpoklady |
| Bug triage agent | Sprint 3 | 10+ bugů v Jira | severity/priority potvrzuji já |
| API test agent | Sprint 3 | Swagger s 30+ endpointy | každý navržený test spustím a porovnám |
| Regression agent | Sprint 4 | první změna aplikace | rozhoduji, co skutečně spustíme |
| Test report agent | Sprint 4 | první sprint report | čísla ověřím proti Jira/test runu |
| Automation agent | Sprint 5 | první převod TC → Playwright | code review každého testu |
| Debug agent | Sprint 6 | první selhání v CI | hypotézu ověřím v trace/logu |

Každý agent musí mít: účel, vstupy, nástroje, pravidla, výstup, verifikační krok, limity, human approval, příklad. Formát: `templates/agent-spec.md`. Agent bez skutečného použití v projektu se z playbooku maže.

---

## 6. Hodnocení

### 6.1 Rubrika ticketu (každé odevzdání, 0–10)
Pokrytí (pozitivní, negativní, hranice) · Správnost (technicky) · Srozumitelnost (pochopí dev i PO) · QA myšlení (rizika, otázky, edge cases) · Profesionalita (šablona, jazyk, evidence). Každé 0–2. **Plus AI dimenze (0–5):** kvalita promptu a kontextu, správný výběr režimu (HUMAN/AI/AGENT/AUTOMATION), ověření AI výstupu, zápis do logu, poctivost (žádné vymyšlené časy).
Feedback formát: ✅ správně · ⚠️ zlepšit · ❌ chyba · 💡 senior tip · 🤖 AI tip.

### 6.2 Sprint review (0–100 %)
Kvalita artefaktů · nalezené chyby vs. dostupné (pokud známé) · komunikace (dailies, otázky, obhajoba) · release decision (správně zdůvodněné) · AI efektivita (skutečná úspora, ne deklarovaná). Práh pro „sprint splněn": 75 %.

### 6.3 Finální hodnocení (každé /100)
Manual Testing · Test Design · Exploratory Testing · Bug Hunting · Bug Reporting · API Testing · SQL · DevTools · Jira · Playwright · Selenium · Git · CI/CD · AI‑assisted QA · Prompt Engineering · Context Engineering · AI Verification · Agentic Workflow · Automation Thinking · Analytical Thinking · Communication · Independence

**AI Productivity Score /100:** výběr AI, kvalita promptů, práce s kontextem, ověřování, AI‑assisted testing, AI‑assisted automation, debugging, agentic workflows, bezpečnost, skutečná úspora času (z logu).

**Junior QA Readiness (READY / ALMOST / NOT READY):** Manual QA · API · SQL · Jira · Playwright · Selenium · Git · AI‑assisted QA · AI Agents.

### 6.4 Rubrika promptu (při `AI REVIEW`)
Context (dal jsem AI to, co potřebuje?) · Instructions (jasný úkol?) · Constraints (omezení, formát, co nedělat) · Output format (použitelný přímo?) · Missing information (co AI chybělo a domyslela si?) · Verification (jak ověřím výstup?).

### 6.5 Metriky AI (z `ai/AI-USAGE-LOG.md`, jen skutečná data)
time saved · test cases generated / accepted · AI suggestions rejected · bugs found by me / suggested by AI / missed by AI · automation generated by AI / corrected by me · flaky tests · debugging time saved.

---

## 7. Git a portfolio

- Větev na ticket (`ts-101-registration-tests`), pull request na `main`, review komentář (mentor jako reviewer), squash merge.
- Commit messages: `feat:`, `test:`, `fix:`, `docs:`, `ci:`, `chore:` — např. `test: add registration test cases (EP/BVA)`, `docs: add sprint 1 QA report`.
- Struktura repozitáře: viz `README.md`. Bez tokenů a osobních dat; `.gitignore` pro Postman environments.
- Na konci: `final-report/CV-ENTRY.md` a `final-report/LINKEDIN.md` — jen skutečně použité skills, transparentně označeno jako self‑directed projekt.

---

## 8. Pravidla, která platí celou dobu

1. Řešení nikdy předem; navádění otázkou, pak vysvětlení.
2. Human‑in‑the‑loop: AI navrhuje, já rozhoduji a obhajuji.
3. AI výstup se ověřuje vždy; záměrné AI failure cases jsou součást tréninku.
4. Žádné AI theatre; rychlejší ručně = ručně.
5. Bezpečnost: žádné credentials, PII, zákaznická data do AI; mentor upozorní, když se v simulaci objeví.
6. Do CV jen to, co jsem udělal.
7. Aplikace se mění — dostupnost prostředí se ověřuje před každým sprintem; náhrady připravené.
