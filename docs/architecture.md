# Architecture

High-level view of ValueRoost as trust and settlement infrastructure for service marketplaces.

## Positioning

ValueRoost is **infrastructure**, not a single vertical marketplace product. Partner marketplaces own branding, customer relationships, and UX. ValueRoost owns escrow settlement rules, portable professional identity (RoostID), reputation signals, dispute analysis (RoostAI), and the developer surface that binds them together.

The **ValueRoost Marketplace** app is the reference implementation. **Motive** is a reference/test headless integration—not an external paying customer.

## Layer diagram

```mermaid
flowchart TB
  subgraph UX["Partner & reference UX"]
    App[ValueRoost Marketplace]
    Motive[Motive reference portal]
    DevPortal[Developer portal + docs]
  end

  subgraph Control["Developer / control plane"]
    APIv1[Marketplace APIs]
    SDK[Developer SDK]
    Keys[Marketplace-scoped API keys]
    Webhooks[Signed webhooks]
    Intents[Prepared write intents]
    Fees[Fee configuration]
  end

  subgraph Trust["Trust products"]
    Escrow[Milestone escrow]
    ID[RoostID + verified providers]
    Notify[Notifications / chat / files]
  end

  subgraph OffChain["Off-chain analysis"]
    AI[RoostAI dispute analysis]
  end

  subgraph Chain["On-chain + indexed state"]
    Contracts[Protocol contracts on Base Sepolia]
    Indexer[Indexer read models]
  end

  App --> APIv1
  Motive --> SDK
  DevPortal --> APIv1
  SDK --> APIv1
  APIv1 --> Keys
  APIv1 --> Webhooks
  APIv1 --> Intents
  APIv1 --> Fees
  Intents -->|unsigned calldata| Contracts
  Contracts --> Escrow
  Contracts --> ID
  Contracts --> Indexer
  Indexer --> APIv1
  Notify --> App
  APIv1 --> AI
  AI -->|recommended split / escalate| APIv1
  APIv1 -->|resolution via prepared txs<br/>and contract rules| Contracts
```

## Trust boundaries

| Boundary | Responsibility |
|----------|----------------|
| Partner application | UX, user sessions, when to call APIs |
| ValueRoost API / SDK | Auth, marketplace scoping, prepare read/write orchestration, webhooks |
| User wallet | Signs transactions; holds keys |
| Protocol contracts | Escrow custody rules, milestone state, attribution checks |
| Indexer | Confirmed-state projections for API/UI reads |
| Off-chain services | KYC review, chat/files, RoostAI evidence analysis (no unilateral fund movement) |

**Important:** ValueRoost prepares write intents; it does not unilaterally move escrow. Funds move only through contract rules after valid signatures and state transitions.

## Marketplace scoping

Every job, bid, fee share, and webhook delivery is associated with a **marketplace id**. API keys are bound to a marketplace. Partner write paths that attribute work to a non-native marketplace use **marketplace attribution authorization** so escrow and discovery remain correctly scoped.

## Settlement today vs planned

| Concern | Current | Planned |
|---------|---------|---------|
| Chain | Base Sepolia | Base mainnet (not launched) |
| Settlement asset | Mock USDC | Circle USDC |
| Cross-chain | Not in production | CCTP |

## Related docs

- [marketplace-infrastructure.md](./marketplace-infrastructure.md)
- [escrow-lifecycle.md](./escrow-lifecycle.md)
- [developer-integration.md](./developer-integration.md)
- [security.md](./security.md)
