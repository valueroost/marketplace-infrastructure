# Security

Public, high-level security posture for ValueRoost marketplace infrastructure. This document does **not** include attack instructions, exploit reproductions, or internal audit finding narratives.

## Principles

- **Non-custodial writes** — APIs prepare unsigned transactions; user wallets sign; contracts enforce escrow.
- **Marketplace scoping** — API keys and jobs are bound to a marketplace; attribution authorization protects fee and discovery integrity.
- **Least privilege off-chain** — KYC documents, chat, and evidence stay off-chain with restricted access; escrow movement is on-chain only.
- **Defense in depth** — contract tests, upgrade/layout checks, and escrow invariants back the settlement layer.

## Areas of focus (high level)

| Area | Intent |
|------|--------|
| **Contract testing** | Automated suites exercise escrow and marketplace behaviors before upgrades |
| **Upgrade / layout testing** | Storage layout and upgrade safety checks reduce corruption risk across diamond upgrades |
| **Escrow invariants** | Funds accounting and milestone state transitions must hold under expected flows |
| **Marketplace attribution authorization** | Partner marketplace attribution requires valid authorization so jobs cannot be falsely attributed |
| **Replay protection** | Webhook and signed-message flows are designed so captured payloads cannot be trivially replayed |

## What partners should do

- Keep `vr_test_` / `vr_live_` **secret keys on the server only**
- Verify webhook signatures before acting on events
- Treat prepared transactions as untrusted until the user reviews them in-wallet
- Rotate credentials if a secret may have been exposed
- Use Base Sepolia sandbox credentials separately from any future mainnet credentials

## What this overview deliberately omits

- Private keys, signer material, deployment keys
- Internal audit attack details
- Database schema internals
- Production contract source and privileged admin runbooks

For audit status and remediation history, rely on formal reports shared under NDA or official public summaries—not this showcase repo.

## Deployment honesty

Current public deployment described here is **Base Sepolia**. **Mainnet is not launched.** Testnet uses **mock USDC**. Real Circle USDC and CCTP are planned.

## Related docs

- [architecture.md](./architecture.md)
- [developer-integration.md](./developer-integration.md)
- [escrow-lifecycle.md](./escrow-lifecycle.md)
