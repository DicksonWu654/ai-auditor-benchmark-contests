# Scope

Source of truth:
- Sherlock contest scope page: https://github.com/sherlock-audit/2025-05-dodo-cross-chain-dex
- Audited source tree: https://github.com/Skyewwww/omni-chain-contracts/tree/2fe44d3da76b721e4d32addfecb04ca97a39cb0d

Counts below use the archived Sherlock GitHub file pages, which publish `loc` for each scoped file.

| File | Contract / Library | GitHub `loc` |
|---|---|---:|
| `source/contracts/GatewayCrossChain.sol` | `GatewayCrossChain` | 528 |
| `source/contracts/GatewaySend.sol` | `GatewaySend` | 362 |
| `source/contracts/GatewayTransferNative.sol` | `GatewayTransferNative` | 610 |
| `source/contracts/interfaces/IDODORouteProxy.sol` | `IDODORouteProxy` | 18 |
| `source/contracts/interfaces/IUniswapV2Factory.sol` | `IUniswapV2Factory` | 13 |
| `source/contracts/interfaces/IUniswapV2Router01.sol` | `IUniswapV2Router01` | 93 |
| `source/contracts/interfaces/IWETH9.sol` | `IWETH9` | 19 |
| `source/contracts/libraries/AccountEncoder.sol` | `AccountEncoder` | 42 |
| `source/contracts/libraries/BytesHelperLib.sol` | `BytesHelperLib` | 37 |
| `source/contracts/libraries/SafeMath.sol` | `SafeMath` | 14 |
| `source/contracts/libraries/SwapDataHelperLib.sol` | `SwapDataHelperLib` | 241 |
| `source/contracts/libraries/TransferHelper.sol` | `TransferHelper` | 24 |
| `source/contracts/libraries/UniswapV2Library.sol` | `UniswapV2Library` | 84 |

Total in-scope files: 13
Total in-scope `loc`: 2,085

Highlighted areas of concern:
- Cross-chain message handling in `GatewayCrossChain.sol`, `GatewaySend.sol`, and `GatewayTransferNative.sol`.
- Refund handling and bot/manual recovery flows for non-EOA recipients.
- DODO Router / UniswapV2 integration and helper library assumptions.
