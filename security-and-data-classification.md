# Security and Data Classification

## Rule

Personal data and financial data must be classified before design is approved. Any
field holding either must have a named owner, a retention period, and a statement of
who can see it.

Data must never leave the tenant without a documented reason.

## Why

Retrofitting classification after go-live means a data migration and a security review.
Doing it at design time costs an hour.

## Classification

| Class | Examples | Requirement |
|---|---|---|
| Public | Product names, published prices | None |
| Internal | Order volumes, stock levels | Role-based access |
| Personal | Contact names, phone numbers, addresses | Named owner, retention period, access list |
| Financial | Credit limits, payment terms, bank details | As personal, plus restricted roles and an audit trail |

## Evidence required

- Classification of every new field
- Retention period for personal and financial data
- Which roles can read, and which can change
- For any external call: what data is sent, to whom, and under what agreement

## Examples

**Accepted** — On-site contact name and phone stored on the work order, classified
personal, retained for 24 months, visible to dispatch and field technicians only.

**Rejected** — Customer bank details copied into a free-text note field with no
classification and no access restriction.

## Related

See `integration-timeouts-and-dependencies.md` for calls that send data outside D365.
