# AGENT-PLAYBOOK.md

> Agenti v tomto projektu vznikají **až když je potřeba** — třetí opakování stejné práce, ne dřív. Každý má spec podle šablony níže a musí být skutečně použit na reálném ticketu. Agent bez použití se maže.

## Pojmy

- **AI** — pomáhá přemýšlet a generovat. Vstup → výstup. Bez nástrojů, bez vlastního rozhodování o dalším kroku.
- **Automation** — deterministické provedení. Stejný vstup → stejný výsledek. Playwright, Postman runner, CI. Žádný úsudek.
- **Agent** — dostane úkol, analyzuje kontext, použije nástroj, získá výsledek, rozhodne další krok, použije další nástroj, ověří výsledek, vytvoří artefakt. Řídí víc kroků.
- **Human‑in‑the‑loop** — agent smí navrhnout severity, test cases, příčinu selhání. Nesmí rozhodnout. Finální rozhodnutí a schválení dělám já a zapisuji ho.

**Otázka u každého problému:** je lepší AI, automation, agent, nebo kombinace? Odpověď s důvodem patří do playbooku.

## Implementační možnosti (ověřuje se při stavbě prvního agenta, protože se mění)
- **Claude Code skill** — opakovaný postup s pevným vstupem a výstupem (např. z poznámek udělat bug report podle šablony). Nejlevnější forma; většina „agentů" v tomto projektu bude skill.
- **Claude Code subagent** — samostatný kontext s vlastními instrukcemi a omezenými nástroji (např. review test cases, analýza CI logu).
- **Claude Code + MCP** — přístup k nástrojům (Playwright MCP pro procházení aplikace, souborový systém, git).
- **Claude Projects / Chrome extension** — pro práci nad aplikací v prohlížeči a s dokumenty bez repa.

## Pravidla pro každého agenta
1. Má jeden účel. Univerzální agent je špatný agent.
2. Vstup je definovaný (soubory, formát). Bez vstupu nedělá nic.
3. Výstup jde do souboru podle šablony, ne do chatu.
4. Má verifikační krok, který provádí člověk, a je v něm napsáno **co** se ověřuje.
5. Má limity: co nesmí (rozhodovat, mazat, posílat data mimo repo, vymýšlet endpointy).
6. Má příklad skutečného použití s odkazem na ticket.
7. Má záznam, kolikrát byl použit a kolik času ušetřil (z AI‑USAGE‑LOG).

## Šablona spec (kopie v `templates/agent-spec.md`)

```
## <Název agenta>
### Purpose
### Input
### Tools
### Instructions
### Output
### Verification (co ověřuje člověk a jak)
### Limitations
### Human approval (co musí schválit člověk před dalším krokem)
### Example (ticket, datum, vstup, výstup, co jsem opravil)
### Usage log (datum · ticket · čas ušetřený · přijato/odmítnuto)
```

## Roadmapa (kdy a proč; nic z toho neexistuje, dokud není potřeba)

| Agent | Účel | Plánovaný spouštěč |
|---|---|---|
| Requirement agent | US + AC → nejasnosti, chybějící kritéria, edge cases, rizika | po 3. ručně provedené analýze |
| Test design agent | scénáře, negativní, hranice, regresní kandidáti | po 3. ručním návrhu scénářů ze stejného typu AC |
| Bug triage agent | duplicita?, severity?, priority?, reprodukovatelnost?, release risk? | 10+ bugů v Jira |
| API test agent | Swagger → návrh testů, test data, analýza response | Sprint 3 |
| Automation agent | manual TC → Playwright, locators, assertions, analýza selhání, refactoring | Sprint 5 |
| Debug agent | stack trace, console, network, Playwright failure, API error → hypotéza + důkaz | první selhání v CI |
| Regression agent | změna → co znovu otestovat | první změna aplikace mezi sprinty |
| Test report agent | passed/failed/blocked/bugs/risk → QA summary | první sprint report |

## Aktivní agenti
*(zatím žádný)*

## Zrušení agenti (a proč)
*(zatím žádný)*
