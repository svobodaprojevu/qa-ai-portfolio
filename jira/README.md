# Jira — nastavení projektu

1. Jira Software Cloud, **Free** plán (do 10 uživatelů).
2. Nový projekt → **Scrum** → **team‑managed** (umožňuje vlastní sloupce bez placeného plánu).
3. Název **Toolshop QA**, klíč **TS**.
4. Board → sloupce (= statusy): **TO DO · IN PROGRESS · READY FOR QA · IN QA · READY FOR RETEST · DONE**. Bug je vlastní issue typ (zapnout v nastavení projektu), propojený se story přes link *is caused by / blocks*.
5. Issue typy: Epic, Story, Task, Bug, Sub‑task.
6. Vytvoř Epic **TS‑90 Zákaznické účty** a tickety ze `project/sprints/sprint-01.md` s odpovídajícími statusy. Čísla se v Jira přidělí automaticky — pokud nesedí s dokumenty, uveď mapování sem:

| Dokument | Jira |
|---|---|
| TS-101 | |

7. Šablona popisu bugu: zkopíruj z `templates/bug-report.md` do pole Description.
8. Filtry, které se hodí od začátku: `project = TS AND type = Bug AND status != Done ORDER BY priority DESC` a `project = TS AND assignee = currentUser() AND status in ("READY FOR QA","IN QA")`.
9. Do této složky se ukládají screenshoty boardu na konci každého sprintu a `ticket-log.md` (co jsem kdy posunul a proč).
