# qa-ai-portfolio — Jakub · Junior QA @ Ferrum Digital (simulace)

> Tohle není kurz. Je to simulovaná firma, ve které pracuju jako Junior QA Tester
> a učím se prací na skutečné aplikaci s AI jako součástí každého kroku.
> Vše v tomto repozitáři jsem vytvořil já; AI mi pomáhala tam, kde je to zaznamenáno v `ai/AI-USAGE-LOG.md`.

## Jak simulace funguje

| | |
|---|---|
| **Firma** | Ferrum Digital s.r.o. (fiktivní český e‑commerce) |
| **Produkt** | Toolshop — B2C e‑shop s nářadím: Angular frontend, Laravel REST API, MariaDB |
| **Moje role** | Junior QA Tester (jediný junior v týmu) |
| **Mentor** | Claude v rolích Senior QA / QA Lead (Honza), PO (Markéta), SM (Petra), BE dev (Tomáš), FE dev (Filip), BA (Lucie), DevOps (Radek), AI QA Specialist (Dan) |
| **Prostředí** | viz `project/README.md` |
| **Workflow** | Jira: TO DO → IN PROGRESS → READY FOR QA → IN QA → BUG → READY FOR RETEST → DONE |

Pracujeme ve sprintech (2 týdny mého času, ne kalendářní). Každý sprint má cíl, tickety, ceremonie (refinement, planning, daily, review, retro) a na konci moje rozhodnutí GO / NO‑GO.

## Standardní postup u každého významného úkolu

Před tím, než začnu, si odpovím na pět otázek — a odpovědi zapíšu k úkolu:

1. **Co bych udělal sám?**
2. **Co může udělat AI?**
3. **Co může udělat agent?**
4. **Co lze automatizovat?**
5. **Co musí ověřit člověk?**

Potom udělám práci nejdřív **sám** (HUMAN), pak přidám **AI review** (druhý názor), rozhodnu, co přijmu, a zapíšu řádek do `ai/AI-USAGE-LOG.md` s reálnými časy. U každé aktivity hledám: REDUCE · AUTOMATE · AUGMENT · DELEGATE · VERIFY · MEASURE.

## Pravidla

1. **Řešení nedostávám předem.** Když udělám chybu, mentor mě nejdřív navede otázkou, pak vysvětlí.
2. **Human‑in‑the‑loop.** AI navrhuje severity, test cases, příčinu selhání. Rozhoduji já a nesu za to odpovědnost.
3. **AI výstup není pravda.** Každý AI výstup ověřuji proti aplikaci, dokumentaci nebo datům.
4. **Žádné AI theatre.** Když je něco rychlejší ručně, řekne se to nahlas a zapíše do logu.
5. **Bezpečnost.** Do AI nikdy neposílám credentials, tokeny, PII, zákaznická data ani interní dokumenty. Demo účty Toolshopu jsou veřejné, ty ano.
6. **Do CV a portfolia jde jen to, co jsem skutečně udělal.**
7. **Jazyk:** komunikace česky, artefakty pro portfolio (test cases, bug reporty, kód, commity) anglicky.

## Příkazy pro mentora

| Příkaz | Význam |
|---|---|
| `TICKET` | Dej mi další ticket z boardu |
| `ODEVZDÁVÁM TS-101: …` | Odevzdání práce k review (číslo ticketu + obsah / soubor / odkaz) |
| `AI REVIEW` | Chci, abys zhodnotil můj prompt a AI výstup (rubrika: context, instructions, constraints, output format, missing info, verification) |
| `PO: …` / `DEV: …` / `SM: …` | Otázka nebo zpráva konkrétní roli |
| `DAILY` | Standup — řeknu, co dělám, co jsem našel, co mě blokuje |
| `REFINEMENT` / `PLANNING` / `REVIEW` / `RETRO` | Spustit ceremonii |
| `RELEASE` | Chci udělat rozhodnutí GO / NO‑GO |
| `AGENT: <účel>` | Chci navrhnout a postavit agenta pro konkrétní potřebu |
| `NÁPOVĚDA` | Navádějící otázka (max. 2 na úkol), ne řešení |
| `SHRNUTÍ` | Vygeneruj aktualizovaný `STUDENT_PROGRESS.md` k uložení |
| `POKRAČUJ` | V nové konverzaci — řekni mi, kde jsme; pošlu `STUDENT_PROGRESS.md` |
| `STATUS` | Kde jsme, skóre, co opakovat |

## Kontinuita mezi konverzacemi

Mentor si mezi konverzacemi pamatuje jen stručný stav (sprint, ticket, slabá místa). **Jediný zdroj pravdy je `STUDENT_PROGRESS.md` v tomto repu.** Na konci sezení: `SHRNUTÍ` → uložit → commit. V nové konverzaci soubor pošlu nebo napíšu `POKRAČUJ`.

## Onboarding — ticket TS-100

Co potřebuju mít hotové během Sprintu 1 (paralelně s prvním ticketem):

- [x] tento repozitář na GitHubu (public), první commit `docs: initial QA portfolio structure` — hotovo 6. 9., https://github.com/svobodaprojevu/qa-ai-portfolio
- [x] Jira Cloud Free: team‑managed Scrum projekt **Toolshop QA**, klíč **TS**, sloupce podle workflow výše (`jira/README.md`) — založeno 6. 9., mapování čísel v `jira/README.md`
- [ ] přístupy k prostředím ověřené: TEST i STAGE se načtou ✅ (6. 9., HTTP 200), Swagger se otevře ✅ — **zbývá:** přihlášení demo účtem ověřit ručně v prohlížeči
- [x] Postman nainstalovaný (API od Sprintu 3, ale ať je připravený) — nalezen 6. 9.
- [x] Claude Code nainstalovaný a spuštěný v tomto repu; `CLAUDE.md` přečtený a případně upravený — 6. 9.
- [x] nástroj na screenshoty s anotací a záznam obrazovky — Snipping Tool (Win+Shift+S, umí i záznam) + OBS Studio nalezeny 6. 9.
- [ ] `STUDENT_PROGRESS.md` uložený a commitnutý po prvním review

## Struktura repozitáře

```
qa-ai-portfolio/
├── README.md, MASTER-PLAN.md, STUDENT_PROGRESS.md, CLAUDE.md
├── project/          requirements, user-stories, test-plan, test-scenarios, test-cases,
│                     exploratory-testing, bug-reports, regression, test-reports, sprints
├── api/postman/      kolekce a environments (bez tokenů)
├── sql/              dotazy a ověření dat
├── automation/       playwright/ (hlavní), selenium/ (sekundární)
├── jira/             export/screenshoty boardu, ticket log
├── ai/               AI-QA-PLAYBOOK.md, AI-USAGE-LOG.md, AGENT-PLAYBOOK.md
├── ci/               GitHub Actions workflow + analýza běhů
├── final-report/     závěrečná zpráva, hodnocení, CV položka
├── templates/        šablony artefaktů
└── .claude/skills/   moje QA skills pro Claude Code (vznikají podle potřeby)
```
