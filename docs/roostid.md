# RoostID

RoostID is ValueRoost’s portable professional identity and trust layer for service marketplaces.

## Problem

Marketplaces repeatedly re-verify the same providers. Reputation resets when a freelancer joins a new platform. RoostID aims to make **verification and professional history wallet-linked**, so trust can travel—with consent—across ValueRoost-powered marketplaces.

## What RoostID provides (high level)

- **Wallet-native identity** — connect a wallet; ownership is proven by signature
- **Verified provider path** — KYC review off-chain; on-chain credential recognition for verified freelancers
- **Portable reputation signals** — completed work, volume, and review-derived trust readable across marketplaces
- **Marketplace-scoped listings** — discovery stays owned by each marketplace; trust graph is infrastructure

## Dual identity with partners

| Partner marketplace owns | ValueRoost / RoostID powers |
|--------------------------|-----------------------------|
| Brand, domain, UX | Professional identity bound to wallet |
| Customer relationship | Escrow and settlement history signals |
| Community and marketing | Reputation / review graph |

Cross-marketplace trust import is **opt-in**. ValueRoost does not position itself as a competing talent destination that partners must feed.

## Verification (public overview)

1. Connect wallet  
2. Submit identity documents (stored encrypted off-chain for review)  
3. Human review  
4. On-chain credential mint / recognition for verified status  

Sensitive documents are **not** published on-chain. Only the verification outcome needed for protocol participation is represented on-chain.

## How apps use it

- Reference **ValueRoost Marketplace** requires verified freelancers to bid and work in the full protocol loop.
- Partner apps (including the **Motive** reference integration) can read wallet reputation / talent signals through marketplace APIs while keeping their own branding.

## Related docs

- [marketplace-infrastructure.md](./marketplace-infrastructure.md)
- [architecture.md](./architecture.md)
- Screenshot: [../screenshots/valueroost/roostid-identity-portal.png](../screenshots/valueroost/roostid-identity-portal.png)
