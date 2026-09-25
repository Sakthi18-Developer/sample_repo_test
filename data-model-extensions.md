# Data Model Extensions

## Rule

Extend existing tables rather than creating new ones. A new table is justified only
when the data has its own lifecycle, its own security, or a different cardinality from
anything that already exists.

Every new column must have a data type chosen deliberately, not defaulted to string.

## Why

Extensions upgrade cleanly. New tables bring their own security, reporting, data
retention and integration work, all of which is usually forgotten at design time.

## Evidence required

- Which existing entity was considered and why it does not fit
- Cardinality: one value per customer, or many per customer
- Data type and length, with the reason
- Whether the value is needed in reporting, integration or both
- Retention: how long the data is kept and who deletes it

## Choosing a data type

| Data | Use | Do not use |
|---|---|---|
| Yes/no flag | Boolean | String "Y" or "N" |
| Fixed list of values | Enum or option set | Free text |
| Money | Currency with the currency code | Decimal alone |
| A date with no time | Date | DateTime |
| Reference to another record | Lookup or relation | Copied text of the name |

## Examples

**Accepted** — Compliance flag added as a Boolean column on Customer, no new table,
one value per customer.

**Rejected** — Payment terms stored as free text on a new table, duplicating a standard
field that already exists with a validated list.

## Related

See `standard-before-customisation.md` — no extension is approved without that check.
