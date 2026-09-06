# STUDENT_PROGRESS.md — Jakub · Junior QA @ Ferrum Digital

> Jediný zdroj pravdy o tom, kde jsme. Aktualizuje mentor po každém review (`SHRNUTÍ`), Jakub commituje.
> V nové konverzaci pošli tento soubor nebo napiš `POKRAČUJ`.

## 1. Stav

| | |
|---|---|
| **Start simulace** | 6. 9. 2026 |
| **Poslední aktualizace** | 6. 9. 2026 (TS-100: prostředí ověřena, nástroje zkontrolovány, kostra analýzy TS-101 připravena) |
| **Aktuální sprint** | Sprint 1 — Zákaznické účty (den 1) |
| **Aktuální ticket** | TS-101 Registrace nového zákazníka — READY FOR QA → čeká na moji analýzu |
| **Paralelně** | TS-100 Onboarding |
| **AI maturity level** | 1 (chatbot) → cíl Sprintu 1: 3 (reviewer) |
| **Sprinty splněny** | 0 / 8 |
| **Průměr rubriky ticketů** | — |
| **Silné stránky** | — |
| **Slabší oblasti** | — |
| **K opakování** | aktér vs. kanál (BE provádí, API přenáší, DB jen vydává data) |

## 2. Baseline před startem (z 31. 8. 2026)
- Cvičení „vrstvy přihlášení": pořadí 5/8, FE/BE rozlišení správně, chyby: pořadí DB→BE u ověření hesla, DB označena jako aktér místo BE.
- Zázemí: Windows + PowerShell, Cursor, Git/GitHub, Claude Code, Chrome + Claude in Chrome, zkušenost s webem (Next.js), příprava na Playwright.
- Audio podklady pro NotebookLM (EP01–EP12) vytvořeny 1. 9. — použitelné jako teorie just‑in‑time.

## 3. Sprinty

| Sprint | Téma | Stav | Skóre | Release decision | Poznámka |
|---|---|---|---|---|---|
| 0 | Onboarding | 🔄 | — | — | běží jako TS-100 v rámci Sprintu 1 |
| 1 | Zákaznické účty | 🔄 | — | — | TS-101 zadán 6. 9. |
| 2 | Katalog | ⏳ | — | — | |
| 3 | Košík, checkout, API, DB | ⏳ | — | — | |
| 4 | Role, oprávnění, release | ⏳ | — | — | |
| 5 | Playwright + CI | ⏳ | — | — | |
| 6 | Regrese, RCA, Selenium | ⏳ | — | — | |
| 7 | Agentic workflow | ⏳ | — | — | |
| 8 | Finální projekt + AI challenge | ⏳ | — | — | |

## 4. Log ticketů

| Datum | Ticket | Fáze odevzdání | Rubrika /10 | AI dimenze /5 | Hlavní feedback |
|---|---|---|---|---|---|
| — | — | — | — | — | — |

## 5. Skills matrix (0 = neznám · 1 = viděl · 2 = udělal s pomocí · 3 = samostatně · 4 = učím ostatní)

| Skill | Úroveň | Poslední důkaz |
|---|---|---|
| Requirement analysis | 0 | — |
| Risk analysis | 0 | — |
| Test design (EP/BVA/DT/ST) | 0 | — |
| Test cases | 0 | — |
| Exploratory testing | 0 | — |
| Bug reporting | 0 | — |
| Jira | 0 | — |
| DevTools | 1 | L0.1 náhled |
| API / Postman | 0 | — |
| SQL | 0 | — |
| Playwright | 1 | samostudium před kurzem |
| Selenium | 0 | — |
| Git/GitHub | 2 | vlastní projekty; 6. 9. init repa `qa-ai-portfolio`, `.gitattributes`, push přes `gh` |
| CI/CD | 0 | — |
| Prompt engineering | 1 | běžné používání Claude |
| Context engineering | 0 | — |
| AI verification | 0 | — |
| Agentic workflow | 0 | — |
| Automation thinking | 0 | — |
| Communication (QA↔dev/PO) | 0 | — |

## 6. Časté chyby (opakující se vzorce)

| Vzorec | Poprvé | Kolikrát | Stav |
|---|---|---|---|
| DB jako aktér místo BE | 31. 8. | 1 | sledovat v TS-101 |

## 7. AI metriky (souhrn z `ai/AI-USAGE-LOG.md`)

| Metrika | Hodnota |
|---|---|
| Úkolů s AI | 2 |
| Skutečně ušetřený čas | ~5 min (session 1: 8 vs. ~10 min; session 2: 5 vs. ~8 min; „bez AI“ = odhad) |
| AI návrhy přijaté / odmítnuté | 2 / 0 |
| Bugs found by me / suggested by AI / missed by AI | 0 / 0 / 0 |
| AI failure cases odhalené / celkem | 0 / 0 |

## 8. Agenti a skills

| Název | Stav | Použito v | Spec |
|---|---|---|---|
| — | — | — | `ai/AGENT-PLAYBOOK.md` |

## 9. Portfolio — výstupy

| Artefakt | Stav |
|---|---|
| Repo na GitHubu | ✅ 6. 9. — https://github.com/svobodaprojevu/qa-ai-portfolio |
| TS-101 analýza + scénáře | ⏳ |
| TS-101 test cases (EN) | ⏳ |
| První bug reporty | ⏳ |
| Sprint 1 review + release decision | ⏳ |

## 10. Poznámky mentora
- 6. 9. 2026 — Přechod na formát simulované firmy (MASTER‑PLAN v2). Plán v1 (lekce) je nahrazen; audio podklady zůstávají jako teorie na vyžádání. Sprint 1 začíná ticketem TS‑101; onboarding TS‑100 běží paralelně.

## 11. Poznámky a otázky Jakuba
- —
