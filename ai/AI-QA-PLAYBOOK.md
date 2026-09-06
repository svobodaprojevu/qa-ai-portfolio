# AI-QA-PLAYBOOK.md

> Playbook vzniká z **reálných situací v projektu**. Každý záznam má skutečný prompt, který jsem použil, co jsem AI dal jako kontext, co vyšlo, co jsem musel opravit, a verdikt: používat / používat s úpravou / nepoužívat.
> Prázdné sekce = zatím jsme tu situaci nepotkali. Nic se sem nepíše dopředu.

## Rámec

**Pět otázek před úkolem:** Co bych udělal sám? · Co může AI? · Co může agent? · Co lze automatizovat? · Co musí ověřit člověk?

**Smyčka:** REDUCE · AUTOMATE · AUGMENT · DELEGATE · VERIFY · MEASURE

**Rubrika promptu:** Context · Instructions · Constraints · Output format · Missing information · Verification

**Zásady kontextu (context engineering):** AI dostává to, co má tester na stole — user story, AC, screenshot, response, log, existující test cases, DOM, network request. Ne otázku „jak testovat registraci", ale „tady je AC, tady je formulář, tady jsou moje scénáře — co mi chybí?". Kontext se dává strukturovaně (sekce, ne odstavce) a vždy se říká, v jakém formátu chci výstup.

**Bezpečnost:** do veřejné AI nikdy credentials, tokeny, API keys, produkční tajemství, PII, zákaznická data, interní dokumenty pod NDA. V simulaci: demo účty Toolshopu jsou veřejné; cokoli, co vypadá jako reálná osoba, se nahrazuje smyšlenými daty.

## Šablona záznamu

```
### <Situace> — <ticket> — <datum>
**Co jsem udělal sám:**
**Režim:** HUMAN / AI / AI reviewer / AGENT / AUTOMATION / HUMAN+AI
**Prompt (doslova):**
**Kontext, který jsem dal:**
**Co AI vrátila (stručně):**
**Co jsem ověřil a jak:**
**Co jsem opravil / zahodil:**
**Čas bez AI / s AI:**
**Verdikt:** používat / s úpravou / nepoužívat — proč
```

## 1. Requirement Analysis
*(zatím prázdné)*

## 2. Test Design
*(zatím prázdné)*

## 3. Exploratory Testing
*(zatím prázdné)*

## 4. Bug Reporting
*(zatím prázdné)*

## 5. Bug Triage
*(zatím prázdné)*

## 6. API Testing
*(zatím prázdné)*

## 7. SQL
*(zatím prázdné)*

## 8. Debugging
*(zatím prázdné)*

## 9. Playwright
*(zatím prázdné)*

## 10. Selenium
*(zatím prázdné)*

## 11. Regression
*(zatím prázdné)*

## 12. Documentation
*(zatím prázdné)*

## 13. Root Cause Analysis
*(zatím prázdné)*

## 14. Test Reporting
*(zatím prázdné)*

## 15. Agent Workflows
*(zatím prázdné — viz AGENT-PLAYBOOK.md)*

## AI failure cases, které jsem odhalil

| # | Datum | Co AI tvrdila | Jak jsem na to přišel | Poučení |
|---|---|---|---|---|
| | | | | |

## Co nepoužívat (rychlejší ručně / vytváří víc práce)

| Situace | Proč | Datum zjištění |
|---|---|---|
| | | |
