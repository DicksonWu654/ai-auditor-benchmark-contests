# Scope

Counts below are raw line counts from the audited snapshot. The Sherlock scope page did not publish per-file nSLOC/SLOC totals, so this file records the exact in-scope files and their line totals from `source/`.

Source URL for scope info: https://github.com/sherlock-audit/2025-06-notional-exponent (audit scope section)

## In-Scope Files

| File | Raw lines |
| --- | ---: |
| `src/AbstractYieldStrategy.sol` | 479 |
| `src/oracles/AbstractCustomOracle.sol` | 90 |
| `src/oracles/AbstractLPOracle.sol` | 111 |
| `src/oracles/Curve2TokenOracle.sol` | 108 |
| `src/oracles/PendlePTOracle.sol` | 90 |
| `src/proxy/AddressRegistry.sol` | 151 |
| `src/proxy/Initializable.sol` | 20 |
| `src/proxy/TimelockUpgradeableProxy.sol` | 87 |
| `src/rewards/AbstractRewardManager.sol` | 320 |
| `src/rewards/ConvexRewardManager.sol` | 31 |
| `src/rewards/RewardManagerMixin.sol` | 194 |
| `src/routers/AbstractLendingRouter.sol` | 329 |
| `src/routers/MorphoLendingRouter.sol` | 287 |
| `src/single-sided-lp/AbstractSingleSidedLP.sol` | 418 |
| `src/single-sided-lp/CurveConvex2Token.sol` | 310 |
| `src/staking/AbstractStakingStrategy.sol` | 151 |
| `src/staking/PendlePT.sol` | 146 |
| `src/staking/PendlePTLib.sol` | 89 |
| `src/staking/PendlePT_sUSDe.sol` | 71 |
| `src/staking/StakingStrategy.sol` | 15 |
| `src/utils/Constants.sol` | 20 |
| `src/utils/TokenUtils.sol` | 54 |
| `src/utils/TypeConvert.sol` | 26 |
| `src/withdraws/AbstractWithdrawRequestManager.sol` | 342 |
| `src/withdraws/ClonedCooldownHolder.sol` | 38 |
| `src/withdraws/Dinero.sol` | 89 |
| `src/withdraws/Ethena.sol` | 102 |
| `src/withdraws/EtherFi.sol` | 57 |
| `src/withdraws/GenericERC20.sol` | 42 |
| `src/withdraws/GenericERC4626.sol` | 45 |
| `src/withdraws/Origin.sol` | 52 |

## Totals

- In-scope files: 31
- Total raw lines in scope: 4,364

## Highlighted Areas Of Concern

- Yield strategy shares can only be minted, redeemed, or transferred through the lending router, so router-only authorization and transient state clearing are critical.
- Open withdraw requests change share valuation and must not allow users to increase their balance or bypass solvent accounting.
- The lending router, Morpho integration, oracle pricing, and liquidation paths all need consistent valuation logic to preserve solvency.
- Reward managers, single-sided LP flows, and withdraw managers all depend on external protocols and token behavior, so compatibility and edge-case handling are part of the core audit surface.
