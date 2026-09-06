# TS-101 — Registrace nového zákazníka

| | |
|---|---|
| **Typ** | Story |
| **Epic** | TS-90 Zákaznické účty |
| **Sprint** | Sprint 1 |
| **Status** | READY FOR QA |
| **Reporter** | Markéta (PO) |
| **Assignee (dev)** | Filip (FE), Tomáš (BE) |
| **Assignee (QA)** | Jakub |
| **Priority** | High |
| **Build** | 5.0-rc na TEST |
| **Labels** | auth, customer-account |

## User Story
**As a** visitor of the Toolshop
**I want** to create a customer account
**so that** I can place orders, see my order history and save favourite products.

## Acceptance Criteria (Markéta)
1. Registrační formulář je dostupný z přihlašovací stránky přes odkaz „Register your account".
2. Formulář obsahuje pole: First name, Last name, Date of birth, Street, Postal code, City, State, Country, Phone, Email, Password.
3. Všechna pole jsou povinná.
4. E‑mail musí mít validní formát a musí být v systému unikátní.
5. Heslo musí být dostatečně silné. Pravidla jsou zobrazená u pole.
6. Uživatel musí být starší 18 let.
7. Telefonní číslo obsahuje pouze číslice.
8. Chybové hlášky se zobrazují u příslušného pole.
9. Po úspěšné registraci je uživatel přesměrován na přihlašovací stránku a může se novým účtem přihlásit.
10. Registrace funguje v Chrome, Firefox a v mobilním zobrazení.

## Poznámky
- Filip (FE, 5. 9.): „Formulář hotový, validace jsou na klientu, testujte klidně i na mobilu."
- Tomáš (BE, 5. 9.): „Endpoint `POST /users/register` je nasazený, viz Swagger."
- Markéta (PO, 5. 9.): „Chceme to v releasu 5.1 příští týden."

## Přílohy
- Swagger TEST: https://api-with-bugs.practicesoftwaretesting.com/api/documentation
- Design: aktuální UI na TEST je považováno za design (samostatný návrh neexistuje)

## Komentáře
*(sem se zapisují otázky a odpovědi, jako v Jira)*
