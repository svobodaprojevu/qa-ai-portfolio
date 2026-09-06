# AI-USAGE-LOG.md

> Log skutečného použití AI v projektu. **Pouze reálná data.** Odhad času se zapisuje jako odhad (`~`), skutečný čas bez značky.
> Řádek přidávám po každém významném úkolu, u kterého jsem AI použil — nebo záměrně nepoužil (i to je záznam: `AI Tool: none — rychlejší ručně`).

## Jak měřit
- **Time Without AI:** buď skutečně změřený čas verze bez AI (když jsem úkol udělal nejdřív sám), nebo poctivý odhad označený `~`.
- **Time With AI:** skutečný čas včetně psaní promptu, čtení výstupu a **ověřování**. Ověření se počítá — bez něj je číslo lež.
- **Result:** co z AI výstupu bylo přijato / upraveno / zahozeno, a jaký byl finální stav.
- **Human Role:** co jsem dělal já (zadání kontextu, výběr, ověření, oprava, rozhodnutí).

## Log

| # | Datum | Task | AI Tool | AI Role | Human Role | Time Without AI | Time With AI | Result |
|---|---|---|---|---|---|---:|---:|---|
| 1 | 2026-09-06 | Git init + GitHub repo: inicializace repa, initial commit, vytvoření public repa `qa-ai-portfolio` přes `gh`, push `main`; doplnění `.gitattributes` (LF) | Claude Code (Fable 5.1) | Ověřil stav `gh auth`, spustil `git init`/`add`/`commit`, `gh repo create --push`, navrhl a přidal `.gitattributes` | Zadání kroků, rozhodnutí přidat `.gitattributes`, kontrola výsledku na GitHubu | ~10 min | 8 min | Přijato vše. 2 commity na `main`, repo https://github.com/svobodaprojevu/qa-ai-portfolio. Renormalizace LF nic nezměnila (soubory už byly LF), varování CRLF bylo jen z pracovní kopie na Windows. |
| 2 | 2026-09-06 | Dokumentace session 1: zápis do `ai/AI-USAGE-LOG.md` (řádek 1 + skutečný čas), aktualizace `STUDENT_PROGRESS.md` (repo ✅, AI metriky, důkaz Git/GitHub) | Claude Code (Fable 5.1) | Načetl formát obou souborů, navrhl a zapsal řádek logu a změny v progressu, 3 commity + push | Dodal skutečný čas session 1 (8 min), zadal rozsah aktualizace, schválil commity | ~8 min | 5 min | Přijato vše. Úrovně skillů a hodnocení nezměněny (rozhoduje mentor). Ušetřený čas v progressu označen jako odhad, protože „bez AI“ nebylo měřeno. |
| 3 | 2026-09-06 | Dorovnání AI metrik v `STUDENT_PROGRESS.md` (sekce 7) podle logu: úkolů s AI, ušetřený čas, přijaté návrhy; doplnění skutečného času session 2 | Claude Code (Fable 5.1) | Upozornil na nesoulad metrik s logem, po schválení přepsal 3 hodnoty, 2 commity + push | Dodal skutečný čas session 2 (5 min), rozhodl dorovnat metriky hned místo na konci sprintu | ~5 min | 3 min | Přijato vše. Nesoulad odhalil asistent, ne uživatel. |
| 4 | 2026-09-06 | Zápis session 3 do `ai/AI-USAGE-LOG.md` a doplnění jejího skutečného času | Claude Code (Fable 5.1) | Sestavil řádek logu z commitů, po dodání času přepsal odhad na skutečnost, 2 commity + push | Dodal skutečný čas session 3 (3 min), zadal zápis | ~3 min | ~1 min (podle commitů 18:58–18:59; TODO upřesnit) | Přijato vše. Doporučení asistenta: neloguj samostatně opravy jednoho čísla, sluč je do řádku úkolu, kterého se týkají. |

## Odmítnutá použití (AI by nepomohla)

| # | Datum | Task | Proč ne | Kolik času by to stálo navíc |
|---|---|---|---|---|
| | | | | |

## Souhrn (aktualizuje se na konci sprintu)

| Sprint | Úkolů s AI | Ušetřeno (skutečně) | Přijato / odmítnuto návrhů | AI failure cases odhalené |
|---|---|---|---|---|
| 1 | | | | |
