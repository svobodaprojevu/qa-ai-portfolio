# Projekt Toolshop — Ferrum Digital s.r.o.

## Produkt
Toolshop je B2C e‑shop s ručním a elektrickým nářadím. Zákazník si založí účet, prochází katalog (kategorie, vyhledávání, filtry, řazení), přidává zboží do košíku, projde checkoutem (adresa, platba) a vidí své objednávky a faktury. Administrátor spravuje produkty, kategorie, značky, uživatele, objednávky a zprávy z kontaktního formuláře.

**Technologie:** Angular frontend · Laravel REST API (OpenAPI/Swagger) · MariaDB. Mobilní aplikace sdílí backend (Sprint 4 verze).

**Skutečná aplikace:** *Practice Software Testing / Toolshop* od Testsmith (open source, určená k tréninku testování). Firma, tým a tickety jsou simulace; aplikace, API a data jsou skutečné.

## Prostředí

| Prostředí | Použití | Aplikace | API + Swagger |
|---|---|---|---|
| **TEST** | sprintový build, sem chodí tickety k otestování | https://with-bugs.practicesoftwaretesting.com | https://api-with-bugs.practicesoftwaretesting.com (Swagger: `/api/documentation`) |
| **STAGE** | poslední release 5.0, referenční chování | https://practicesoftwaretesting.com | https://api.practicesoftwaretesting.com |
| **Historie releasů** | verze ze sprintů 1–4 (pro regresní srovnání) | https://v1…v4.practicesoftwaretesting.com | https://api-v1…v4.practicesoftwaretesting.com |
| **LOCAL** (od Sprintu 3) | plný přístup: DB (phpMyAdmin root/root, port 8000), e‑maily (MailCatcher, port 1080), reset dat | Docker: https://github.com/testsmith-io/practice-software-testing | http://localhost:8091 |

Poznámka QA Leada: TEST je build, o kterém vývoj tvrdí, že je hotový. STAGE je to, co dnes vidí zákazníci. Rozdíl mezi nimi je jeden z tvých testovacích orákulí — ale ne jediný a ne vždy správný.

Veřejná dema se resetují a občas mění. Před každým sprintem se dostupnost ověřuje; když prostředí nejede, hlásí se to jako blocker DevOpsovi (Radek).

## Testovací účty (veřejné demo účty aplikace — smí se používat i v AI)

| Role | E‑mail | Heslo |
|---|---|---|
| Admin | admin@practicesoftwaretesting.com | welcome01 |
| Zákazník 1 | customer@practicesoftwaretesting.com | welcome01 |
| Zákazník 2 | customer2@practicesoftwaretesting.com | welcome01 |

Nové účty, které si při testování vytvoříš, pojmenovávej tak, aby byly poznat (`qa.jakub.<něco>@example.com`) a používej smyšlená data.

## Tým

| Role | Jméno | Na co se ptát |
|---|---|---|
| Product Owner | Markéta | zadání, AC, priority, „je to blocker?", scope |
| Senior QA / QA Lead | Honza | review, standardy, kam s nejistotou |
| Scrum Master | Petra | proces, ceremonie, překážky |
| Backend dev | Tomáš | API, validace na serveru, data |
| Frontend dev | Filip | UI, validace na klientu, locators, testovatelnost |
| Business Analyst | Lucie | business pravidla, proč to tak má být |
| DevOps | Radek | prostředí, nasazení, CI, přístupy |
| AI QA Specialist | Dan | prompty, agenti, AI review, bezpečnost AI |

Otázky se pokládají konkrétní roli (`PO: …`, `DEV: …`). Odpovědi budou realistické — někdy neúplné, někdy si role protiřečí. To je záměr.

## Slovník domény
- **Zákazník (customer)** — registrovaný uživatel s rolí user.
- **Admin** — role s přístupem do administrace.
- **Objednávka / faktura (invoice)** — v Toolshopu se objednávka po checkoutu ukládá jako *invoice* se stavem.
- **Sprintový build** — verze nasazená na TEST; číslo verze v patičce/aplikaci.
