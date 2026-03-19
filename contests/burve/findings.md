# Burve Findings

| Finding ID | Severity | Title | Description |
| --- | --- | --- | --- |
| H-1 | High | Incorrect handling of ERC4626 vaults with fees | ERC4626 vault deposit and withdrawal fees are not fully accounted for when liquidity is added, so users can bypass the fee logic and the pool records too much value. |
| H-2 | High | Incorrect implementation of `ERC4626ViewAdjustor` | `ERC4626ViewAdjustor` reverses the share/asset conversions, so nominal and real amounts are computed backwards for LST-style vaults. |
| H-3 | High | Incorrect Netting Logic Leads to Excessive Withdrawal Amounts | The withdrawal netting logic subtracts deposit amounts incorrectly, so withdrawals can be larger than intended. |
| H-4 | High | Incorrect tax distribution when adding value single-sided | Single-sided value adds update `valueStaked` before fee distribution, which dilutes the reward share for existing LPs. |
| H-5 | High | Attacker captures unclaimed fees by timing deposit with range re-entry and price manipulation | When Burve ranges are out of bounds and the collected amounts are too small, fee recycling stalls until price re-enters the configured range. |
| H-6 | High | Fee Bypass in `ValueFacet.removeValueSingle` | `removeValueSingle` reads `removedBalance` as zero when computing `realTax`, allowing single-token withdrawals to bypass the intended swap/remove fee. |
| H-7 | High | An attacker can drain assets from a Closure by exploiting the NoopVault via a donation attack | A donation attack against `NoopVault` can skew the share ratio and let an attacker drain a closure's vertex vault. |
| H-8 | High | `ValueFacet::removeValueSingle(...)` will withdraw less than required from the vertex vault due to unaccounted tax | `removeValueSingle` withdraws less than the taxed amount from the vertex vault, so the tax is not fully backed by the vault withdrawal. |
| H-9 | High | Reserve Share Overflows Due to Too Strict Reward Calculation Mechanism | The reserve share calculation can over-mint shares during vertex rebalancing because the reward math is too strict. |
| M-1 | Medium | User can backrun an admin calling `setEX128` and steal the difference in tokens | Changing `setEX128` without recomputing the target lets a user backrun the admin action and capture the difference in value. |
| M-2 | Medium | Simplex ownership cannot be transferred | Facet wiring omits `acceptOwnership()`, so Simplex ownership cannot be transferred. |
| M-3 | Medium | Protocol fee resides in the diamond contract can be wrongly sent to users if the underlying vault temporarily disables withdrawal | If the underlying vault disables withdrawals, protocol fees left in the diamond can be sent back to users. |
| M-4 | Medium | The value of each closure is not the same, and the same ValueToken cannot be used for all cids | The same `ValueToken` is reused across all cids, so users can move value from a lower-value closure into a higher-value one. |
| M-5 | Medium | Invariant Breaking1 | Adding value scales both balances and target together without a de minimis cap, allowing the closure invariant to drift beyond its intended bound. |
| M-6 | Medium | Incorrect earnings calculation in `removeValueSingle()` function causes partial user losses | Calling `removeValueSingle()` before `trimBalance()` leaves earnings-per-value stale and can lose rewards. |
