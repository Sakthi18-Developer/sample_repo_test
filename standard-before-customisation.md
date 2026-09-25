# Standard Before Customisation

## Rule

Standard Dynamics 365 functionality must be used wherever it can meet the requirement.
Custom code may only be proposed after standard capability has been checked and found
unsuitable, and the reason has been written down.

This applies to configuration, extensions, plug-ins, custom tables and custom forms.

## Why

Custom code carries permanent cost: it must be regression tested at every platform
update, it blocks some upgrade paths, and it is invisible to Microsoft support.
Most rejected designs are rejected because nobody checked the standard feature first.

## Evidence required

A reviewer must see all three before approving any customisation:

1. The standard feature that was considered, named exactly (for example
   *Terms of delivery*, *Trade agreements*, *Customer payment journals*).
2. What it does not do, stated specifically. "It is not flexible enough" is not an
   answer. "It cannot store more than one value per customer" is.
3. The smallest change that closes the gap. Prefer configuration, then extension,
   then new code.

## Examples

**Accepted** — Requirement: record Incoterms per customer. Standard *Terms of delivery*
was checked and covers it. No customisation proposed.

**Accepted** — Requirement: block sales orders for customers over their credit limit
during month end only. Standard credit management covers the block but not the date
condition. Extension proposed on the existing rule, with the gap stated.

**Rejected** — Requirement: store a compliance flag per customer. A new custom table
was proposed without checking that the Customer entity already has extensible fields.
Standard capability was never named.

## Related

See `ui-changes-and-business-rules.md` when the gap is closed with a new field or form.
