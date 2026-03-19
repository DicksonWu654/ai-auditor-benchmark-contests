# Notional Exponent Findings

Official High/Medium findings from the Sherlock judging report.

| Finding ID | Severity | Title | Description |
| --- | --- | --- | --- |
| H-1 | High | Cross-contract reentrancy allows YIELD_TOKEN theft for the `GenericERC4626` `WithdrawalRequestManager` variant | A shared withdrawal manager can be reentered across vaults, letting an attacker inflate the manager's post-stake balance check and mint extra yield tokens. |
| H-2 | High | Attacker can drain the entire suppliers on Morpho market by inflating collateral price | A faulty collateral pricing path lets an attacker overvalue their position, borrow far more than intended, and drain suppliers from the Morpho market. |
| H-3 | High | `DineroWithdrawRequestManager` vulnerable to token overwithdrawal via batch ID overlap | Overlapping batch identifiers let one withdrawal request reuse another request's accounting and withdraw more tokens than deposited. |
| H-4 | High | When users borrow directly from Morpho price of the collateral will not be accurate | The direct-borrow path uses the wrong collateral price source, so health checks and leverage calculations can be materially off. |
| H-5 | High | `migrateRewardPool` Fails Due to Incompatible Storage Design in `CurveConvexLib` | Migration logic assumes a storage layout that `CurveConvexLib` does not provide, so reward pool migration reverts. |
| H-6 | High | DoS might happen to `DineroWithdrawRequestManager#_initiateWithdrawImpl()` due to overflow on `++s_batchNonce` | The batch nonce can overflow on repeated withdrawals, bricking new withdrawal initiation. |
| H-7 | High | `RewardManagerMixin.claimAccountRewards` lacks of necessary param check. | Missing validation on the account parameter lets callers claim rewards with incorrect inputs and breaks the intended authorization model. |
| H-8 | High | Incorrect assumption that one (1) Pendle Standard Yield (SY) token is equal to one (1) Yield Token when computing the price in the oracle | The oracle treats SY and yield tokens as 1:1 when they are not always equivalent, so collateral and share pricing can be wrong. |
| H-9 | High | Hardcoded `useEth = true` in `remove_liquidity_one_coin` or `remove_liquidity` lead to stuck fund | Forcing ETH mode in Curve removals can leave assets stuck when the pool or asset configuration expects ERC20 handling. |
| H-10 | High | Malicious user can change the `TradeType` to steal funds from the vault or withdraw request manager | User-controlled trade type selection can redirect swaps through unsafe paths and drain vault or withdrawal-manager funds. |
| H-11 | High | Missing Slippage Protection in Expired PT Redemption Causes User Fund Loss | Expired PT redemption executes without a minimum-out check, exposing users to avoidable slippage loss. |
| M-1 | Medium | Hard-Coded Mainnet WETH Address Breaks All Non-Mainnet Deployments | A mainnet-only WETH address is baked into the code, so deployments on other chains will fail or behave incorrectly. |
| M-2 | Medium | Incorrect `tokensClaimed` calculation in `EthenaCooldownHolder::_finalizeCooldown()` blocks withdrawals | The cooldown finalization math miscomputes the claimed amount, preventing withdrawals from completing. |
| M-3 | Medium | Single sided strategy cant do trades for ETH pools | ETH-denominated pools cannot execute the single-sided trade flow because the strategy does not handle native ETH properly. |
| M-4 | Medium | Liquidations can be frontrunned to avoid by paying as little as 1 share. | An attacker can frontrun liquidation and satisfy the position with a minimal share payment, defeating the intended liquidation path. |
| M-5 | Medium | Minting yield tokens single sided can be impossible if CURVE_V2 dexId is used on redemptions | The CURVE_V2 redemption path can fail in single-sided mint flows, blocking yield-token issuance. |
| M-6 | Medium | Withdrawals ongoing for OETH, apxETH, weETH, and almost any LST are overpriced by the oracle | The oracle overvalues several rebasing or liquid staking tokens during withdrawals, causing users to receive inflated valuations. |
| M-7 | Medium | Rounding discrepancy between `MorphoLendingRouter::healthFactor` and `Morpho::repay` causes position migration failures | Slight rounding differences between the router and Morpho can make otherwise valid migration repayments revert. |
| M-8 | Medium | Emission rewards will keep accruing even the yield strategy is empty | Reward emission accounting continues even when the strategy holds no assets, producing misleading or unfair accruals. |
| M-9 | Medium | OETH Strategy Broken as Rebasing Not Enabled | The OETH strategy does not enable rebasing handling, so it cannot track balances correctly. |
| M-10 | Medium | Incorrect asset matching for ETH/WETH leads to potential DoS of exitPosition in CurveConvexStrategy | ETH and WETH are compared incorrectly, which can make strategy exits revert for valid positions. |
| M-11 | Medium | Users unable to claim rewards when Curve LP tokens are staked to Curve Gauge. | Gauge-staked Curve LP positions cannot pass the reward-claim flow, so rewards become unclaimable. |
| M-12 | Medium | `PendlePTOracle._getPTRate` isn't correct for some market | Some Pendle markets return the wrong PT rate, leading to inaccurate oracle pricing. |
| M-13 | Medium | Incompatibility of `ERC20::approve` function with USDT tokens on Ethereum Mainnet chain | The standard approve flow does not work with USDT's non-standard behavior, breaking mainnet integrations. |
| M-14 | Medium | Value of Etherna's Withdrawal Request is incorrect | The Etherna withdrawal request valuation does not match the actual claimable amount. |
| M-15 | Medium | Loss of reward tokens during initiating withdrawal due to cooldown | Rewards can be lost or stranded when a withdrawal starts while tokens are still cooling down. |
| M-16 | Medium | Users will be unfairly liquidated if collateral value drops after initiating withdraw request | After a withdrawal request, stale accounting can make users look undercollateralized and trigger unfair liquidations. |
| M-17 | Medium | User unable to migrate under certain edge case | A specific edge case prevents migrating a position even though migration should be allowed. |
| M-18 | Medium | Reducing liquidity in the hardcoded Curve sDAI/sUSDe pool leads to unnecessary slippage loss | The hardcoded pool path can push trades through shallow liquidity and cause avoidable slippage. |
| M-19 | Medium | Unable to deposit to Convex in Arbitrum | The Arbitrum Convex configuration is incomplete, so deposits cannot be routed there. |
| M-20 | Medium | Lack of minimum debt threshold enables unliquidatable small positions | Very small debt positions can avoid liquidation because no minimum threshold is enforced. |
| M-21 | Medium | Funds stuck if one of the withdrawal requests cannot be finalized | A single failing withdrawal request can block the rest and leave funds locked in the manager. |
| M-22 | Medium | Setup with `asset = WETH` and a Curve pool that contains Native ETH will lead to a loss for the users | When WETH is paired with a native-ETH Curve pool, the asset handling mismatch can lose user funds. |
| M-23 | Medium | Unable to support Curve Pool with Native ETH | Native-ETH Curve pools are not handled by the integration, so those pools cannot be supported safely. |
| M-24 | Medium | Convex cannot be configured for the Yield Strategy vault in Arbitrum even though Convex is available in Arbitrum | The Arbitrum yield strategy cannot be wired to Convex even though the protocol exists on that chain. |
| M-25 | Medium | Revert in `getWithdrawRequestValue()` function will brick the account | If withdraw-request valuation reverts, the account becomes unusable for related flows. |
| M-26 | Medium | `initializeMarket` can be frontran, preventing markets from being configured in `MorphoLendingRouter ` | An attacker can front-run market initialization and lock out the intended Morpho configuration. |
