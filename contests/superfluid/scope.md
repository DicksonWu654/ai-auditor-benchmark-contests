# Scope

Counts below are raw line counts from the audited snapshot. The Sherlock scope page did not publish per-file nSLOC/SLOC totals, so this file records the exact in-scope files and their line totals from `source/`.

Source URL for scope info: https://github.com/sherlock-audit/2025-06-superfluid-locker-system (audit scope section)

## In-Scope Files

| File | Raw lines |
| --- | ---: |
| `fluid/packages/contracts/src/EPProgramManager.sol` | 351 |
| `fluid/packages/contracts/src/FluidEPProgramManager.sol` | 661 |
| `fluid/packages/contracts/src/FluidLocker.sol` | 874 |
| `fluid/packages/contracts/src/FluidLockerFactory.sol` | 223 |
| `fluid/packages/contracts/src/Fontaine.sol` | 178 |
| `fluid/packages/contracts/src/StakingRewardController.sol` | 262 |
| `fluid/packages/contracts/src/interfaces/IEPProgramManager.sol` | 214 |
| `fluid/packages/contracts/src/interfaces/IStakingRewardController.sol` | 189 |
| `fluid/packages/contracts/src/vesting/SupVesting.sol` | 150 |
| `fluid/packages/contracts/src/vesting/SupVestingFactory.sol` | 231 |
| `protocol-monorepo/packages/ethereum-contracts/contracts/apps/SuperTokenV1Library.sol` | 1,982 |
| `protocol-monorepo/packages/ethereum-contracts/contracts/utils/MacroForwarder.sol` | 41 |

## Totals

- In-scope files: 12
- Total raw lines in scope: 5,356

## Highlighted Areas Of Concern

- `FluidEPProgramManager` and `FluidLocker` depend on trusted signer, unit, and timing assumptions that should be checked against replay, nonce, and flow-accounting failures.
- `FluidLocker::unlock`, `withdrawLiquidity`, and `collectFees` are the main tax and liquidity paths, so unlocking math, tax bypasses, and pool interactions are core risk areas.
- `Fontaine::initialize` and the Superfluid flow setup are especially sensitive to flow lifecycle mistakes and buffer loss.
- `SupVesting` and `SupVestingFactory` are part of the audited surface and rely on correct recipient accounting and admin assumptions.
