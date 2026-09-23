# Marketplace Infrastructure

ValueRoost sells **composable marketplace infrastructure** (MIaaS). Partners enable products they need; the reference marketplace proves the stack end to end.

## Product map

```text
ValueRoost Platform
│
├── ValueRoost Marketplace     ← reference implementation
├── Motive                     ← reference/test integration (not a paying customer)
│
├── Escrow                     ← programmable USDC milestone escrow
├── RoostAI                    ← dispute analysis & settlement assist
├── RoostID                    ← identity, verification, wallet-linked reputation
├── RoostVault                 ← evidence & document storage (product surface)
├── RoostNotify                ← notifications + partner webhooks
├── RoostReputation            ← reviews, stats, trust signals
├── RoostPay                   ← settlement / pay-with routing (product surface)
│
└── Developer Platform         ← API keys, SDK, docs, prepared txs
```

## What partners get

- **Programmable escrow** with milestones, revisions, auto-release windows, and disputes
- **Stablecoin settlement** denominated in USDC (mock on Base Sepolia today)
- **Marketplace APIs** for jobs, bids, configuration, and credentials
- **Webhooks** for signed lifecycle events
- **Prepared write intents** so partners never need direct privileged contract access
- **Marketplace fee infrastructure** for platform and marketplace share
- **Portable trust** via RoostID / reputation across ValueRoost-powered marketplaces (with consent)
- **Collaboration surfaces**: job chat, files, and notifications around the escrow lifecycle

## Integration depths (roadmap framing)

| Depth | Idea | Status framing |
|-------|------|----------------|
| **Headless** | APIs + SDK + wallet signing | Primary public integration path described here |
| **Embed** | Drop-in components | Planned product surface |
| **Hosted** | White-label hosted marketplace | Planned product surface |

## Dual identity (why partners keep customers)

Partners own branding, email, community, and discovery. ValueRoost powers professional identity, escrow history, and reputation behind that brand. The reference marketplace is for dogfooding—not a competing talent destination that partners must feed.

## Reference implementations

| Name | Role |
|------|------|
| **ValueRoost Marketplace** | Full-stack reference app on the protocol |
| **Motive** | Headless partner-style portal for sandbox testing |

## Related docs

- [architecture.md](./architecture.md)
- [developer-integration.md](./developer-integration.md)
- [roostid.md](./roostid.md)
- [roostai.md](./roostai.md)
