# Basic integration (conceptual example)

This folder outlines a minimal partner integration against ValueRoost marketplace APIs. It is **documentation only**—no runnable production credentials, private source, or deployable backend is included.

**Network:** Base Sepolia  
**Settlement:** Mock USDC on testnet  
**Mainnet:** Not launched  

## Goal

Prove the headless partner path used by reference integrations such as **Motive** (our test integration, not an external paying customer):

1. Register a marketplace  
2. Obtain marketplace-scoped API credentials  
3. Create / read jobs  
4. Subscribe to webhooks  
5. Prepare write transactions  
6. Have the user wallet sign  
7. Let contracts execute escrow  
8. Read confirmed state from the indexer via APIs  

## Pseudocode flow

```text
# 1) Server holds secret key (never in the browser)
Authorization: Bearer vr_test_••••
# key is bound to marketplaceId

# 2) Read open jobs for this marketplace
GET /v1/jobs
→ indexer-backed list scoped to your marketplace

# 3) Register webhook endpoint
POST /v1/webhooks
→ receive signed job.posted / bid.placed (and related) events
→ verify signature; reject replays

# 4) Prepare a write (example: post job)
POST /v1/.../prepare  (write intent)
→ { to, data, value, ... } unsigned

# 5) Client wallet signs & submits
wallet.sendTransaction(prepared)
→ protocol contracts update escrow / job state

# 6) Wait for indexer
GET /v1/jobs/:id
→ confirmed public state for UI
```

## Partner responsibilities

| Do | Don't |
|----|--------|
| Keep secret API keys on the server | Embed `vr_test_` / `vr_live_` secrets in frontend bundles |
| Verify webhook signatures | Trust webhook bodies without verification |
| Let users review txs in-wallet | Assume ValueRoost submits transactions for users |
| Scope product UX to your brand | Treat ValueRoost Marketplace as your customer destination |

## SDK note

Partners typically use `@valueroost/sdk` for typed `/v1` calls, sending prepared transactions through a wallet connector, and verifying webhooks. Install and API details are provided during onboarding / in the live developer portal.

## See also

- [../../docs/developer-integration.md](../../docs/developer-integration.md)
- [../../docs/escrow-lifecycle.md](../../docs/escrow-lifecycle.md)
- [../../docs/security.md](../../docs/security.md)
- [../../README.md](../../README.md)
