# Browser Extension

This directory represents the browser extension layer of the system.

The extension is intentionally designed to be thin and stateless, with all billing and entitlement decisions delegated to the backend.

---

## Responsibilities

- Authenticate the user
- Detect supported product and checkout pages
- Surface available coupons
- Display price comparison results
- Request entitlement status from backend
- Enable or disable premium features based on entitlement

---

## Entitlement Handling

The extension calls the backend API to determine access:

