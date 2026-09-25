# User Interface Changes and Business Rules

## Rule

Any new field, form change, validation or business rule must state what standard
capability was tried first, and why it did not work.

New fields must be added to an existing entity where one fits. A new table is a last
resort and requires an owner, a retention period and a reporting plan.

## Why

Field sprawl is the most common cause of unusable forms and broken reporting.
Every added field is permanent in practice: nobody ever removes one.

## Evidence required

- The existing entity and column that were considered, by name
- Whether the value is transactional (changes per document) or master data
  (belongs to the customer, vendor or item)
- Who maintains the value, and how it is populated for existing records
- Whether the field must appear in reporting, and where

## Examples

**Accepted** — Requirement: flag customers who require export documentation. Added as
a column on the existing Customer entity, maintained by the sales admin team,
backfilled from the country field, included in the customer master report.

**Rejected** — Requirement: capture a compliance note per customer. A new form with a
new table was proposed. The Customer entity has an existing notes capability that was
never mentioned.

**Rejected** — Validation added as a plug-in where a standard business rule would do.

## Related

See `data-model-extensions.md` for the technical pattern once the field is agreed.
