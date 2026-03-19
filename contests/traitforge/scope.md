# Scope

Source URL: https://github.com/code-423n4/2024-07-traitforge/blob/main/README.md#scope

The published scope table lists 6 in-scope logic contracts and 880 nSLOC.

## In-Scope Contracts

| File | nSLOC |
| --- | ---: |
| `/contracts/DevFund/DevFund.sol` | 77 |
| `/contracts/EntityForging/EntityForging.sol` | 152 |
| `/contracts/EntityTrading/EntityTrading.sol` | 82 |
| `/contracts/EntropyGenerator/EntropyGenerator.sol` | 147 |
| `/contracts/NukeFund/NukeFund.sol` | 150 |
| `/contracts/TraitForgeNft/TraitForgeNft.sol` | 272 |
| **Total** | **880** |

## Highlighted Areas of Concern

- Nuke fund accounting, claim flow, and payout timing.
- Entity forging, trading, listing cancellation, and transfer bookkeeping.
- Entropy generation, generation rollover, and mint pricing edge cases.
