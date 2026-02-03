# Backend Service

This directory represents the backend service that acts as the central authority for users, subscriptions, and entitlements.

All billing-related decisions are enforced here to ensure correctness, security, and consistency across the website and browser extension.

---

## Core Responsibilities

- User authentication and identity management
- Subscription state tracking
- Stripe customer and subscription mapping
- Stripe webhook handling
- Entitlement evaluation for extension and website
- API endpoints consumed by all client surfaces

---

## Subscription Authority Model

- Stripe is the **billing source of truth**
- Backend is the **entitlement source of truth**
- Clients (extension and website) are consumers only

Subscription state is derived exclusively from Stripe events and stored in the backend.

---

## Stripe Integration

The backend handles all Stripe interactions, including:
- Checkout session creation
- Subscription lifecycle webhooks
- Payment success and failure events
- Cancellation and renewal updates

All webhook handlers are idempotent and verified using Stripe signatures.

---

## Entitlement API

Example endpoint:

