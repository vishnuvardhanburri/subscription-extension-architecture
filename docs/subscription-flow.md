# Subscription and Entitlement Flow

This document describes how subscriptions are created, tracked, and enforced across the website, backend, and browser extension.

---

## Actors

- User
- Marketing Website
- Backend API
- Stripe
- Browser Extension

---

## Signup & Trial Flow

1. User signs up on the marketing website
2. Website initiates Stripe Checkout
3. Stripe creates:
   - Customer
   - Subscription with free trial
4. Stripe sends webhook to backend
5. Backend stores:
   - User identity
   - Stripe customer ID
   - Subscription status (trialing)

Backend is now the source of truth for entitlement.

---

## Extension Authentication Flow

1. User logs into the browser extension
2. Extension receives an auth token
3. Extension calls backend:
