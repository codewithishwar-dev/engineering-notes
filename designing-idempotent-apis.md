# Designing Idempotent APIs

## What is Idempotency?

An API is idempotent if making the same request multiple times
produces the same result as making it once.

This is critical in production systems.

---

## Why It Matters

In real systems:

- Network retries happen
- Clients retry on timeout
- Payment gateways retry requests
- Mobile apps resend requests on poor connectivity

If your API is not idempotent,
you risk:

- Duplicate payments
- Duplicate orders
- Inconsistent database state
- Corrupted business logic

---

## Example Problem

POST /create-order

User clicks "Pay" twice.
Network times out.
Client retries.

Without idempotency:
→ Two orders are created.

---

## Solution: Idempotency Key

Client sends:

Idempotency-Key: unique-request-id

Server:

1. Stores the key
2. Associates it with response
3. If same key appears again:
   - Return stored response
   - Do NOT execute logic again

---

## Database Strategy

- Unique constraint on idempotency_key
- Store response snapshot
- Return cached result for duplicates

---

## Key Lesson

Production systems must assume:
- Retries will happen
- Failures will happen
- Duplicate requests will happen

Design APIs to be safe by default.

Engineering maturity = designing for real-world behavior.

— CodeWithIshwar
