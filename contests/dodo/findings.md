# Findings

| Finding ID | Severity | Title | Description |
|---|---|---|---|
| 347 | High | `claimRefund` lets any caller claim non-EVM refunds | When `refundInfo.walletAddress` is not 20 bytes, the authorization check collapses to `msg.sender == msg.sender`, so any caller can claim the refund. |
| 696 | High | DODO route proxy `mixSwap` signature does not match the router | The local `IDODORouteProxy.mixSwap` interface does not line up with DODO Router's expected signature, so mix swaps revert across the gateway flows. |
| 372 | High | `withdrawToNativeChain` can be abused to steal refunds through a DODO swap | A caller can set `amount == 0` and use a crafted message to swap refund-held tokens out of `GatewayTransferNative`. |
| 480 | High | `onCall` lacks a `params.toToken` versus `decoded.targetZRC20` check | After a DODO swap, the contract treats the swap output as if it were the intended target asset, which lets an attacker drain arbitrary held `decoded.targetZRC20`. |
| 917 | High | Revert/abort flows can record the wrong wallet and trap funds | The revert message can be populated with the destination-chain wallet instead of the user's ZetaChain wallet, causing funds to be stranded in `GatewayCrossChain`. |
| 155 | Medium | Fee deduction happens before approval, so DODO swaps revert | `GatewayCrossChain` approves less than the amount it later asks DODO to pull, so the swap path fails and wastes gas. |
| 752 | Medium | Refund metadata can be overwritten and hijacked | A crafted cross-chain payload can overwrite an existing `refundInfo` entry, letting an attacker claim a victim's pending refund. |
| 902 | Medium | `claimRefund` authorization is too broad for non-20-byte wallets | Both gateway contracts treat non-EVM wallet addresses as if `msg.sender` were the rightful receiver, which allows unauthorized refund claims. |
