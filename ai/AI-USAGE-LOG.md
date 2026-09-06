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
| 1 | 2026-09-06 | Git init + GitHub repo: inicializace repa, initial commit, vytvoření public repa `qa-ai-portfolio` přes `gh`, push `main`; doplnění `.gitattributes` (LF) | Claude Code (Fable 5.1) | Ověřil stav `gh auth`, spustil `git init`/`add`/`commit`, `gh repo create --push`, navrhl a přidal `.gitattributes` | Zadání kroků, rozhodnutí přidat `.gitattributes`, kontrola výsledku na GitHubu | ~10 min | ~5 min (TODO: doplnit skutečný čas; commity 18:48–18:49) | Přijato vše. 2 commity na `main`, repo https://github.com/svobodaprojevu/qa-ai-portfolio. Renormalizace LF nic nezměnila (soubory už byly LF), varování CRLF bylo jen z pracovní kopie na Windows. |

## Odmítnutá použití (AI by nepomohla)

| # | Datum | Task | Proč ne | Kolik času by to stálo navíc |
|---|---|---|---|---|
| | | | | |

## Souhrn (aktualizuje se na konci sprintu)

| Sprint | Úkolů s AI | Ušetřeno (skutečně) | Přijato / odmítnuto návrhů | AI failure cases odhalené |
|---|---|---|---|---|
| 1 | | | | |
