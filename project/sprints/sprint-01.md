# Sprint 1 — Zákaznické účty

| | |
|---|---|
| **Cíl sprintu** | Zákazník si může založit účet, přihlásit se, spravovat profil a obnovit heslo |
| **Délka** | 2 týdny Jakubova času (cca 20–24 h) |
| **Release** | 5.1 — plánovaný na konec sprintu; QA doporučuje GO / NO‑GO, PO rozhoduje |
| **Prostředí** | TEST (with-bugs) · reference STAGE |

## Board

| Ticket | Typ | Název | Status | Assignee |
|---|---|---|---|---|
| TS-100 | Task | Onboarding QA (repo, Jira, nástroje, přístupy) | IN PROGRESS | Jakub |
| TS-101 | Story | Registrace nového zákazníka | READY FOR QA | Jakub |
| TS-102 | Story | Přihlášení a odhlášení | IN PROGRESS | Filip / Tomáš |
| TS-103 | Story | Profil zákazníka — úprava údajů a změna hesla | TO DO | — |
| TS-104 | Story | Zapomenuté heslo | TO DO (refinement — chybí AC) | — |
| TS-105 | Task | Smoke checklist pro release 5.1 | TO DO | Jakub |

## Ceremonie (simulované)
- **Planning** — proběhl 5. 9. bez QA (Jakub nastoupil 6. 9.). Odhad testování story: neuveden.
- **Daily** — na vyžádání `DAILY`: co dělám, co jsem našel, co mě blokuje.
- **Refinement TS‑104** — v průběhu sprintu; QA připraví otázky.
- **Review** — stav kvality, otevřené bugy, doporučení k release.
- **Retro** — co změnit v procesu.

## Definition of Done (story)
Kód v main · code review · nasazeno na TEST · otestováno QA (test cases + exploratory) · otevřené bugy jen Minor/Trivial se souhlasem PO · regresní dopad ověřen · test cases uložené v repu.

## Co QA Lead očekává u každé story
1. Analýza ticketu: nejasnosti, otázky na PO/dev, rizika — **před testováním, ne po něm.**
2. Test scenarios → po vyjasnění test cases (`templates/test-case.md`).
3. Execution: výsledky, exploratory session (`templates/exploratory-session.md`), bugy v Jira (`templates/bug-report.md`).
4. Komentář v ticketu s verdiktem (READY FOR RETEST / DONE / blokováno) a odkazem na artefakty.
5. Řádek v `ai/AI-USAGE-LOG.md` za každou AI‑asistovanou část.
