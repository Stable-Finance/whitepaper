# USDX Whitepaper

**A USD-pegged stablecoin backed by U.S. residential mortgages and agency MBS.**

Read the whitepaper in [Stable's Docs](https://docs.trystable.co/usdx-whitepaper), or find the PDF in this repository.

*Version 0.2 · May 2026 · [trystable.co](https://trystable.co)*

---

## Abstract

Stablecoins now move tens of trillions of dollars in annualized onchain transaction volume, with a combined market capitalization of approximately $322 billion as of May 2026. Yet the assets backing them remain narrowly concentrated in short-duration U.S. Treasuries and cash — the posture of a money market fund, not of a durable monetary system.

The U.S. dollar, in its institutional form, rests on a much broader asset base, and the largest single component of that base is not Treasuries but real estate debt. U.S. residential mortgage debt outstanding stands at approximately $13.2 trillion, well over half the $22.6 trillion M2 money supply, with the substantial majority securitized in agency MBS and traded in one of the deepest fixed-income markets in the world. The Federal Reserve itself holds roughly $2.2 trillion of agency MBS.

**USDX brings that collateral class onchain.** Holders can stake USDX for **mUSDX**, a yield-bearing token that accrues the return of the underlying mortgage portfolio net of protocol fees. Peg integrity is maintained by direct redemption against reserves, repo lines against agency MBS, and a decentralized arbitrage surface across liquidity pools. A separate token, **RATES**, serves two functions: validators stake RATES to verify loan data and property attestations that gate the minting of new collateral, and RATES stakers provide a first-loss safety module between protocol risk and stablecoin holders.

USDX sources collateral both from secondary markets and from a native onchain origination channel, so the reserve can grow with newly originated loans rather than only through secondary purchases.

**Keywords:** stablecoin, mortgage-backed securities, tokenized real estate, peg stability, collateralized debt, safety module, onchain finance.

---

## Contents

| § | Section |
|---|---|
| 1 | [Introduction](https://docs.trystable.co/usdx-whitepaper/introduction) |
| 2 | [Background](https://docs.trystable.co/usdx-whitepaper/background) |
| 3 | [System Overview](https://docs.trystable.co/usdx-whitepaper/system-overview) |
| 4 | [Collateral Framework](https://docs.trystable.co/usdx-whitepaper/collateral-framework) |
| 5 | [Mint and Redeem](https://docs.trystable.co/usdx-whitepaper/mint-and-redeem) |
| 6 | [mUSDX: Staked USDX](https://docs.trystable.co/usdx-whitepaper/musdx-staked-usdx) |
| 7 | [Peg Stability](https://docs.trystable.co/usdx-whitepaper/peg-stability) |
| 8 | [Risk Management and the Loss Waterfall](https://docs.trystable.co/usdx-whitepaper/risk-management-and-the-loss-waterfall) |
| 9 | [The RATES Token](https://docs.trystable.co/usdx-whitepaper/the-rates-token) |
| 10 | [Technical Architecture](https://docs.trystable.co/usdx-whitepaper/technical-architecture) |
| 11 | [Native Origination Channel](https://docs.trystable.co/usdx-whitepaper/native-origination-channel) |
| 12 | [Regulatory Framework](https://docs.trystable.co/usdx-whitepaper/regulatory-framework) |
| 13 | [Roadmap](https://docs.trystable.co/usdx-whitepaper/roadmap) |
| 14 | [Related Work](https://docs.trystable.co/usdx-whitepaper/related-work) |
| 15 | [Conclusion](https://docs.trystable.co/usdx-whitepaper/conclusion) |
| 16 | [References](https://docs.trystable.co/usdx-whitepaper/references) |
| A | [Glossary](https://docs.trystable.co/usdx-whitepaper/appendix-a-glossary) |
| B | [Key Formulas and Parameters](https://docs.trystable.co/usdx-whitepaper/appendix-b-key-formulas-and-parameters) |
| C | [RATES Reference](https://docs.trystable.co/usdx-whitepaper/appendix-c-rates-reference) |

---

## The token system

| Token | Role |
|---|---|
| **USDX** | USD-pegged stablecoin. Backed by residential mortgages and agency MBS. Redeemable against reserves |
| **mUSDX** | Yield-bearing staked USDX. Accrues portfolio return net of protocol fees via a rising exchange rate |
| **RATES** | Validator, safety-module, and governance token. Fixed genesis supply of 1,000,000,000 |

---

## The loss waterfall

Losses are absorbed across four tranches in strict seniority. Each fires once, in order, and only if the prior tranche is insufficient. Unstaked USDX is the instrument being protected.

| Step | Tranche | Action | Cap |
|---|---|---|---|
| 1 | RATES Safety Module | Slash staked RATES pro rata | To exhaustion |
| 2 | Stablecoin Vault | Draw vault balance pro rata | To exhaustion |
| 3 | mUSDX Yield | Reduce mUSDX exchange rate | Up to 67% of accumulated yield |
| 4 | New RATES Mint | Mint and sell new RATES | Uncapped |

Each tranche operates within a coverage band expressed as a percentage of outstanding USDX supply — see [Appendix C](https://docs.trystable.co/usdx-whitepaper/appendix-c-rates-reference). Recovery runs in the inverse order, last-in first-out.

Full detail in [Section 8](https://docs.trystable.co/usdx-whitepaper/risk-management-and-the-loss-waterfall).

---

## Repository contents

| Path | Description |
|---|---|
| `USDX Whitepaper.pdf` | Full whitepaper, v0.2 |
| `images/` | Figures |

---

## Related

- [Stable Docs](https://docs.trystable.co) — product documentation, APIs, and contract addresses
- [Official Accounts](https://docs.trystable.co/official-accounts) — verified accounts and contract addresses
- [trystable.co](https://trystable.co)

---

*This whitepaper is a technical description of the USDX protocol as designed. It does not constitute an offer to sell, or the solicitation of an offer to buy, any security or financial instrument. Forward-looking statements reflect the current intentions of the protocol's developers as of the publication date and are subject to change based on technical, regulatory, and market developments.*
