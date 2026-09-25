# D365 Architecture Standards

Standards that must be considered before any Dynamics 365 change is designed or built.
A reviewer agent reads this index first, then opens only the standards that apply.

## Index

| File | Use it when the requirement involves |
|---|---|
| `standards/standard-before-customisation.md` | Any new requirement at all. Always applies. |
| `standards/ui-changes-and-business-rules.md` | New fields, forms, screens, validation or business rules |
| `standards/integration-timeouts-and-dependencies.md` | Calling an external system, an API, or Dataverse during a transaction |
| `standards/data-model-extensions.md` | New tables, new columns, or extending an existing entity |
| `standards/security-and-data-classification.md` | Personal data, financial data, or anything shown to external users |

## How to read a standard

Each file has the same four sections:

- **Rule** — what must be true
- **Why** — the reason, so judgement can be applied to cases not listed here
- **Evidence required** — what a reviewer must see before approving
- **Examples** — accepted and rejected

## Scope

Applies to Dynamics 365 Finance and Operations, Dataverse and Power Platform work.
Owner: Architecture team. Review cycle: every 6 months.
