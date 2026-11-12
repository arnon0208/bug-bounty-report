# XE Network Testnet Bounty

**Status: OPEN, standing programme, no deadline. Zero reports accepted yet (leaderboard empty).**

XE Network ([@xeinternet](https://x.com/xeinternet/status/2114469350371717417)) calls itself an "agent-native network": identity, discovery, payment, compute, and messaging, with per-second compute rental paid into escrow. 2% of the XE supply is set aside for the bounty.

## Reward tiers

| Tier | Reward | Examples |
|---|---|---|
| Critical | 50,000 XE | Unauthorized mint, double-spend, escrow theft, key recovery, consensus finalizing conflicting histories |
| Severe | 25,000 XE | Signature forgery, validation bypass, node compromise, finality stall under load |
| High | 10,000 XE | Targeted DoS, race conditions, replay, privilege escalation |
| Medium | 2,500 XE | Validation gaps, accounting mismatches, inconsistent API responses, measurable slowdowns |
| Minor | 650 XE | UI bugs, typos, broken explorer views, misleading logs, doc errors |

There is also a volume/resilience track (sustained load with reproducible measurements).

## How to submit

- Official page: https://test.network/bounty
- Submit at: https://bounty.xe.network/report (sign in with GitHub or a desk key; no KYC mentioned)
- Get on the testnet via the web wallet at test.network, or run a node/CLI from github.com/xeprotocol/xe. Faucet test XE has no value.
- Out of scope: volumetric DDoS against the hosting layer (nginx/DNS/faucet), social engineering.
- Rewards are paid in native XE at mainnet genesis, discretionary — no guaranteed monetary value.

## Realistic for a non-auditor

Minor tier, parts of Medium, and the volume track. Use the product, break the UI, measure the API.

## Verdict

Wide open, nobody has claimed anything yet. Low competition.

---

*Part of the [Bug Bounty Report](../README.md) — 20 programs checked November 13, 2026.*
