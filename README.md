# Bug Bounty Report

**20 bug bounties and audit contests, checked one by one — November 13, 2026.**

Source list: [@shelleymaeph on X](https://x.com/shelleymaeph/status/2119323955056312438) — "19 bug bounties and audit creator contests PT.2" (actually 20 entries). This is a curated list, not a giveaway. Every program below was checked against its official platform page on November 13, 2026.

![Bug Bounty Report Cover](images/bug-bounty-report-cover.webp)

## TL;DR

- **3 you can try right now without audit skills:** Ticko, XE Network, BrainChain.
- **15 professional programs** — all still open, but they need real auditing skills (Solidity, Rust, Move, Clarity, or C).
- **2 unverified — don't waste time:** Hastra (no submission path found) and BYDFi (probably no program at all).
- **Avoid unless you're ready:** Firedancer (burns 1 SOL per report), Lombard (non-refundable submission fee).

Suggested order: **Ticko → XE Network → BrainChain → Plether (only if you're learning Solidity for the Nov 16 deadline).**

---

## 1. Tryable without audit skills

### 1.1 Ticko — up to 200,000 USDT headline

![Ticko Capybara](images/bug-bounty-ticko-capy.webp)

**Status: OPEN, permanent, no deadline.** Announced October 31, 2026.

Ticko is a perpetuals exchange. The headline "up to 200,000 USDT" is for critical vulnerabilities. The realistic paths for a non-auditor:

| Track | Reward | How |
|---|---|---|
| Reproducible testnet bug | 30 USDT | Report via the testnet form, 10 slots, first-come-first-served |
| Product suggestion | 5 USDT (+5 if adopted) | Same form |
| Beta Mainnet Opening Session bug | 20 USDT | **AVOID** — requires ≥100 USDT net deposit + ≥1,000 USDT trading volume |
| Capy Meme Contest | — | Capybara meme on X (#Tickoer #CapyMode, tag @tickoxyz) or Discord — use Discord; needs an Access Code from the Ticko Discord; runs until Public Mainnet launch (est. Q4 2026, near) |
| Ticko Paladin | 1,000 USDT/month | Quality feedback can earn a monthly "Paladin Star" (500 USDT + 500 USDT futures bonus) |

- Testnet form (bugs, documentation issues, or product suggestions): https://tally.so/r/ob8KjN
- Write in English, include reproduction steps and a screenshot.
- Paid to your Ticko Chain wallet within 7 days after mainnet launch.
- Security reports: security@ticko.market
- Read more: [Introducing the Ticko Bug Bounty](https://medium.com/ticko/introducing-the-ticko-bug-bounty-up-to-200-000-usdt-for-critical-vulnerabilities-1ebdf48df341) · [Beta Bug Bounty, Trader Rewards and the Capy Meme Contest](https://medium.com/ticko/welcome-to-beta-bug-bounty-trader-rewards-and-the-capy-meme-contest-10b07245e623) · [Introducing Ticko Paladin](https://medium.com/ticko/introducing-ticko-paladin-monthly-paladin-stars-earn-1-000-usdt-in-rewards-85c8d0d58cab)

**Verdict:** the most approachable one on this list. Test the testnet, report what breaks.

### 1.2 XE Network Testnet Bounty — up to 50,000 XE per finding

![XE Network](images/bug-bounty-xe-network.webp)

**Status: OPEN, standing programme, no deadline. Zero reports accepted yet (leaderboard empty).**

XE Network ([@xeinternet](https://x.com/xeinternet/status/2114469350371717417)) calls itself an "agent-native network": identity, discovery, payment, compute, and messaging, with per-second compute rental paid into escrow. 2% of the XE supply is set aside for the bounty.

| Tier | Reward | Examples |
|---|---|---|
| Critical | 50,000 XE | Unauthorized mint, double-spend, escrow theft, key recovery, consensus finalizing conflicting histories |
| Severe | 25,000 XE | Signature forgery, validation bypass, node compromise, finality stall under load |
| High | 10,000 XE | Targeted DoS, race conditions, replay, privilege escalation |
| Medium | 2,500 XE | Validation gaps, accounting mismatches, inconsistent API responses, measurable slowdowns |
| Minor | 650 XE | UI bugs, typos, broken explorer views, misleading logs, doc errors |

There is also a volume/resilience track (sustained load with reproducible measurements).

- Official page: https://test.network/bounty
- Submit at: https://bounty.xe.network/report (sign in with GitHub or a desk key; no KYC mentioned)
- Get on the testnet via the web wallet at test.network, or run a node/CLI from github.com/xeprotocol/xe. Faucet test XE has no value.
- Out of scope: volumetric DDoS against the hosting layer (nginx/DNS/faucet), social engineering.
- Rewards are paid in native XE at mainnet genesis, discretionary — no guaranteed monetary value.

**Realistic for a non-auditor:** Minor tier, parts of Medium, and the volume track. Use the product, break the UI, measure the API.

**Verdict:** wide open, nobody has claimed anything yet. Low competition.

### 1.3 BrainChain Bug Hunt — $100 per bug

![BrainChain](images/bug-bounty-brainchain.webp)

**Status: STILL OPEN. Round 1: 10 × $100 prizes, 4 paid, 6 slots left. No public deadline — it's a race for the slots.**

BrainChain is a task marketplace where work is posted, graded, and paid, with bonds and refunds in escrow. Scope: the contracts in `src/` plus the behavior documented in the docs. The v3 mainnet contracts were never externally audited and hold user funds in escrow.

- Realistic submissions: use the product as a user (post a task, grading, refund, bond) and compare it against the docs. Functional and UI bugs in the task flow, with reproduction steps and a screenshot.
- Bugs that can take or lock funds go through a private bounty instead — up to $1,000.
- Submit via the private "Report a vulnerability" form in the GitHub repo `usebrainchain/brainchain`, or email hello@usebrainchain.com with subject "Security". **Never file a public issue.**
- Paid $100 in USDC on Base or USDG on Robinhood Chain. No KYC, no token, no auditor background mentioned.
- **Read the eligibility rules in the X post first:** https://x.com/usebrainchain/status/2119163442309353590
- Rules: https://github.com/usebrainchain/brainchain/blob/843ae8ed4101f5a221ec5d2b74d8b1bcaaf0d0e5/SECURITY.md
- Site: https://usebrainchain.com/

Note: BrainChain runs on Robinhood Chain (4663), not BSC — but this is a bounty, not a mint, so the chain doesn't matter here.

**Verdict:** 6 slots left, $100 each, and the bar is "use the product and find where it disagrees with its own docs." The fastest money on this list if you move now.

---

## 2. Professional programs (all still open)

These need real auditing skills. Listed with the facts that matter: pool, language, gates, and deadlines.

### 2.1 Plether Audit Competition — $80,000 pool

**DEADLINE: November 16, 2026, 17:00 WIB (about 3 days left).**

- $56,000 main pool + $16,000 All Stars + $8,000 podium.
- Solidity only. Perpetuals on Arbitrum, 21,400 lines, on Arbitrum Sepolia, no mainnet yet.
- Open to anyone 18+. No KYC, no reputation requirement, no submission fee.
- A runnable proof-of-concept is mandatory for ALL severities.
- Code already audited twice and AI-scanned.
- Results December 17, paid December 18, 2026.
- https://immunefi.com/audit-competition/plether/information/

**Verdict:** the only professional one with a hard deadline this week and no gatekeeping. Worth it only if you're already learning Solidity and Foundry.

### 2.2 NAVI Protocol Web — max $300,000

- That max is for smart contracts; the web tier amounts are not listed.
- Web scope: XSS, IDOR, SSRF, CSRF, SQL injection, XXE injection, RCE, data leaks.
- No reputation or KYC gate listed.
- Submit via https://hackenproof.com/programs/navi-protocol-web

### 2.3 Rhea Finance — $250,000

- HackenProof. Rust / NEAR.
- Code access needs KYC + at least 1 paid Medium report + 150 HackenProof reputation.
- 168 submissions, $0 paid so far.

### 2.4 Current Finance — $15,000

- Move / Sui.
- Minimum 100 HackenProof reputation blocks new accounts.
- 77 submissions, $0 paid.

### 2.5 NAVI Smart Contract — $300,000

- Move / Sui, OtterSec-audited, proof-of-concept required.

### 2.6 Firedancer — $300,000 — AVOID unless ready

- **Must BURN 1 SOL (~$100) per report. Lost even if the report is rejected or a duplicate.**
- KYC mandatory. C validator.
- 2×/3× bonus ends November 20, 2026.

### 2.7 Granite — $100,000

- Clarity / Stacks. KYC + code proof-of-concept mandatory for all severities.

### 2.8 RedStone — $250,000

- Minimum 150 HackenProof reputation — new accounts can't submit.
- 201+ professional reports already filed.

### 2.9 Whitechain — $10,000

- Bridge + web/API/RPC. Proof-of-concept mandatory. 119 submissions, $0 paid.

### 2.10 stake.link — official max $100,000, NOT $250,000

- The $250,000 figure was the 2023 Code4rena Chainlink contest, long closed.
- Proof-of-concept + KYC mandatory.

### 2.11 Aero — $500,000

- Sherlock. No creator-content track — pure smart contract bounty, coded proof-of-concept on a local fork.
- The $400,000 audit contest is closed.

### 2.12 Kamino — $1,000,000

- Sherlock, Solana/Rust, 43 audits, TVL $1.185B.
- The old Immunefi $1.5M program is dead, and the $150,000 critical floor was removed.

### 2.13 Paxos Labs — $500,000

- Immunefi. KYC + proof-of-concept mandatory.

### 2.14 Enzyme — $200,000

- Immunefi, no KYC, Solidity only, proof-of-concept mandatory.
- Medium $1,000–$5,000, High $5,000–$20,000.

### 2.15 Lombard — $500,000 — AVOID

- **Non-refundable submission fee for ALL reports before review** (amount not listed) + audit proof-of-concept.

### 2.16 Cetus — $1,000,000

- HackenProof, Move/Sui only, KYC for full scope.
- Low $10–$100, Medium $100–$1,000.

---

## 3. Unverified — don't waste time

### 3.1 Hastra — $100,000

Announced as live, but **no public submission path was found anywhere**. No form, no email, no platform listing. Skip until a real path appears.

### 3.2 BYDFi — $15,000

Probably no program exists. Independent reviews and CertiK Skynet state that BYDFi has **no bug bounty program**. Skip.

---

## 4. Suggested work order

1. **Ticko** — test the testnet, report a reproducible bug (30 USDT) or a product suggestion (5 USDT). No KYC, no cost, no deadline.
2. **XE Network** — same approach, Minor tier and the volume track. Leaderboard is empty.
3. **BrainChain** — 6 slots left at $100 each. Race.
4. **Plether** — only if you're learning Solidity + Foundry and can make the November 16 deadline.
5. Skip Hastra, BYDFi, Firedancer, and Lombard unless you already meet their costs and gates.

---

## Disclaimer

- Rewards, tiers, and deadlines are as published on the official pages on November 13, 2026. They can change. Check the linked page before you submit.
- Headline maximums ("up to $200,000", "up to $1,000,000") are for critical vulnerabilities found by professional auditors. The realistic amounts for a non-auditor are the small tiers listed above.
- XE rewards are paid in native XE at mainnet genesis and have no guaranteed monetary value.
- Nothing here is financial advice. Never pay a submission fee or burn tokens to report a bug unless you have read the program's own rules and decided the cost is worth it.
- Report privately. Never file a public issue for a vulnerability.

---

*Report compiled November 13, 2026. Source list via @shelleymaeph. Cover and section images are AI-generated illustrations, not official program artwork.*
