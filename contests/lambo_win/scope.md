# Scope

Source of scope info: [Lambo.win repository README scope section](https://github.com/code-423n4/2024-12-lambowin/blob/874fafc7b27042c59bdd765073f5e412a3b79192/README.md#scope) and [scope.txt](https://github.com/code-423n4/2024-12-lambowin/blob/874fafc7b27042c59bdd765073f5e412a3b79192/scope.txt).

Audited commit: `874fafc7b27042c59bdd765073f5e412a3b79192`

Totals: 7 in-scope files, 601 nSLOC.

Highlighted areas of concern:
- `VirtualToken.cashIn()` minting and debt accounting.
- `LamboFactory.createLaunchPad()` deterministic deployment and pair-creation DoS risk.
- `LamboVEthRouter` quote, swap, and ETH-rescue flows.
- `LamboRebalanceOnUniwap` direction, amount, and flash-loan parameter handling.

## In Scope

| File | nSLOC | Logic Contracts | Interfaces | Notes |
| --- | ---: | ---: | ---: | --- |
| `src/LamboFactory.sol` | 58 | 1 | **** | contract |
| `src/LamboToken.sol` | 122 | 1 | **** | contract |
| `src/LamboVEthRouter.sol` | 115 | 1 | **** | contract |
| `src/VirtualToken.sol` | 117 | 1 | **** | contract |
| `src/rebalance/LamboRebalanceOnUniwap.sol` | 131 | 1 | **** | contract |
| `src/Utils/LaunchPadUtils.sol` | 10 | 1 | **** | library/utility |
| `src/libraries/UniswapV2Library.sol` | 48 | - | **** | library/utility |
| **Total** | **601** |  |  |  |
