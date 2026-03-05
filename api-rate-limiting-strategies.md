# API Rate Limiting Strategies

Rate limiting protects services from abuse, traffic spikes,
and accidental overload.

It is an important part of building reliable APIs.

---

## Why Rate Limiting Matters

Without rate limiting:

- One client can overload the system
- Bots can abuse endpoints
- Traffic spikes can crash the service

Rate limiting ensures fair usage and system stability.

---

## Common Rate Limiting Strategies

### 1. Fixed Window

Requests are counted within a fixed time window.

Example:
100 requests per minute.

Problem:
Traffic spikes can happen at window boundaries.

---

### 2. Sliding Window

Instead of fixed intervals, the request count is evaluated
continuously over time.

This smooths out bursts and is more accurate.

---

### 3. Token Bucket

Each request consumes a token.

Tokens are added to the bucket at a fixed rate.

Benefits:
- Allows short bursts
- Maintains long-term limits

---

### 4. Leaky Bucket

Requests enter a queue and are processed at a constant rate.

This ensures smooth traffic flow.

---

## Practical Example

Typical API limits:

- 100 requests per minute per user
- 1000 requests per minute per API key
- Global limit for system protection

---

## Key Takeaway

Rate limiting is not just about preventing abuse.

It is about maintaining system reliability
when traffic becomes unpredictable.

Design APIs assuming traffic spikes will happen.

— CodeWithIshwar
