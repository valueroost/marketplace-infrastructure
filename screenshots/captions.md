# Screenshot captions

Curated public-safe images only. Skipped assets are listed at the bottom with reasons.

---

## ValueRoost Marketplace — `screenshots/valueroost/`

| File | What it proves |
|------|----------------|
| `landing.png` | Public marketing surface for programmable escrow infrastructure, USDC settlement messaging, and RoostAI positioning. |
| `marketplace-home.png` | Reference marketplace home: wallet-native protocol UX, milestone escrow narrative, Base L2 framing. |
| `browse-jobs.png` | Marketplace job discovery with USDC budgets and skill filters (reference implementation). |
| `find-talent.png` | Verified / browseable provider directory surface for hiring talent. |
| `post-job.png` | Client job posting flow priced in USDC with skills taxonomy and milestone funding note. |
| `job-escrow-detail.png` | Per-job escrow contract surface, bidding, and USDC settlement detail on the reference app. |
| `disputes.png` | Dispute lifecycle UI (raised → mediation → resolved) backing RoostAI / arbitration narrative. |
| `roostid-identity-portal.png` | RoostID / identity verification portal landing (wallet connect, off-chain review, on-chain credential messaging). |

---

## Developer portal — `screenshots/developer-portal/`

| File | What it proves |
|------|----------------|
| `developer-platform-landing.png` | Developer platform positioning: Base Sepolia sandbox, marketplace APIs, webhooks, product primitives. |
| `api-authentication-docs.png` | Public docs for marketplace-scoped API keys (`vr_test_` / `vr_live_` placeholders only) and Base Sepolia status. |
| `docs-getting-started-mobile.png` | Docs “getting started” emphasizing prepared unsigned txs and that ValueRoost does not submit user transactions. |

---

## Motive — `screenshots/motive/`

Motive is our **reference/test partner integration** (not an external paying customer). These shots show a separate marketplace UI that consumes ValueRoost via partner SDK / APIs (no direct diamond access from the portal).

| File | What it proves |
|------|----------------|
| `motive-dashboard.png` | Motive hiring portal home: Partner SDK positioning, USDC settlement banner, marketplace metadata from the SDK, and job/talent/credits entry points. |
| `motive-post-job.png` | Post-job entry on Motive with wallet connect gate; “Powered by ValueRoost Protocol” settlement banner. |
| `motive-jobs.png` | Manage Jobs list scoped to Motive, indexed via the ValueRoost partner API (demo placeholders only). |
| `motive-talent.png` | Motive talent directory surface labeled “MOTIVE · SDK”, powered by ValueRoost protocol messaging. |

---


## Skipped (not copied) — with reasons

| Source | Reason skipped |
|--------|----------------|
| `screenshots/out/06-app-profile.png` | Optional; already covered RoostID via identity portal; profile earnings UI adds little beyond other shots. |
| `screenshots/out/05-app-my-work.png`, `07-app-portfolio.png`, `08-app-skills.png`, `10-app-reviews.png`, `11-app-credits.png`, `14-app-my-jobs.png`, `15-app-direct-offers.png` | Redundant UX; curation prefers fewer high-signal shots. |
| `screenshots/out/17-kyc-help.png` | Help/content page; identity portal already covers RoostID. |
| `valueroost-kyc-portal-main/backend/uploads/**` | Real KYC document / selfie uploads — personal data. |
| `.e2e-secrets/**` | Test identity images and secret-adjacent fixture tree. |
| Smart contract audit PNGs / attack diagrams under contracts libs | Internal/attack illustration material — not for public showcase. |
| Any `.env`, dashboard key-management captures, admin CRM | Secrets / admin surfaces. |
| Freelancer template stock photos | Not ValueRoost product UI. |
