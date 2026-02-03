# Marketing Website

This directory represents the public-facing marketing website and user account entry point for the subscription-based browser extension.

The website is responsible for acquisition, onboarding, and subscription management, while relying on the backend for all entitlement decisions.

---

## Core Responsibilities

- Public marketing pages
- User signup and login
- Subscription checkout flow
- Free trial initiation
- Account and billing management
- Education and onboarding content

---

## Subscription Flow

1. User signs up or logs in on the website
2. Website initiates Stripe Checkout
3. Stripe creates or updates subscription
4. Stripe sends webhook events to backend
5. Backend updates entitlement state

The website does not directly manage subscription state.

---

## Shared Identity Model

- Website and extension share the same user identity
- Authentication tokens issued by backend
- Subscription status queried via backend APIs

This ensures consistent entitlement enforcement across surfaces.

---

## Design Principles

- Backend as the single source of truth
- No client-side billing logic
- Clear separation between marketing and application concerns
- Scalable to support future features (automation, AI-verified coupons)

---

## Technology Considerations

- Framework: React / Next.js
- Authentication: Backend-issued tokens
- Billing UI: Stripe-hosted checkout and portals

Implementation details can evolve without impacting entitlement logic.
