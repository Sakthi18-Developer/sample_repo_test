# Integration Timeouts and External Dependencies

## Rule

A Dynamics 365 transaction must never depend on an external system responding in real
time. Any call to an API, a Dataverse service or a third party during a transaction
must be asynchronous, or must have a defined timeout and a defined behaviour when that
timeout is reached.

## Why

A synchronous call inside a transaction holds database locks for as long as the remote
system takes to answer. One slow endpoint then stops unrelated users from posting.
This is the single most common cause of production outages.

## Evidence required

Every integration design must state:

1. **Timeout** — the maximum wait, in seconds
2. **Locking** — what records are locked while waiting, and for how long
3. **Availability** — what happens when the remote system is down: queue, skip, or
   fail the transaction
4. **Dependencies** — which business processes stop working if this call fails
5. **Performance** — expected calls per hour at peak, and the effect on posting time

## Examples

**Accepted** — Tax calculation called asynchronously, result written back to the order.
Timeout 30 seconds. On failure the order is saved with tax pending and a batch job
retries. Posting is never blocked.

**Rejected** — Address validation called synchronously during sales order creation with
no timeout. A slow response would lock the order table for every user.

**Rejected** — "The API is fast, a timeout is not needed."

## Related

See `security-and-data-classification.md` when the external call sends personal data.
