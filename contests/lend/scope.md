# Scope

Source of truth:
- Sherlock contest scope page: https://github.com/sherlock-audit/2025-05-lend-audit-contest
- Audited source tree: https://github.com/tenfinance/Lend-V2/tree/5c9398fef079319ecc4e8457b11533d0d8838ee0

Counts below use the archived Sherlock GitHub file pages, which publish `loc` for each scoped file.

| File | Contract | GitHub `loc` |
|---|---|---:|
| `source/src/LayerZero/CoreRouter.sol` | `CoreRouter` | 407 |
| `source/src/LayerZero/CrossChainRouter.sol` | `CrossChainRouter` | 708 |
| `source/src/LayerZero/LendStorage.sol` | `LendStorage` | 592 |

Total in-scope files: 3
Total in-scope `loc`: 1,707

Highlighted areas of concern:
- Cross-chain borrow, repay, and liquidation state transitions in the LayerZero router flow.
- Collateral and debt accounting between chains, especially around cross-chain positions.
- Trusted owner/governance assumptions and the whitelisted ERC20 token set.
