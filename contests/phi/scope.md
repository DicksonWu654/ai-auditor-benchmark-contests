# Scope

Source of scope truth: https://code4rena.com/reports/2024-08-phi

The Code4rena report publishes the contest-wide scope total, while the snapshot here preserves the audited source files. The table below records the checked-in file lengths for traceability.

## Files in Scope

| File | Contract | Snapshot lines |
| --- | --- | ---: |
| `source/src/Cred.sol` | `Cred` | 940 |
| `source/src/PhiFactory.sol` | `PhiFactory` | 789 |
| `source/src/abstract/Claimable.sol` | `Claimable` | 85 |
| `source/src/abstract/CreatorRoyaltiesControl.sol` | `CreatorRoyaltiesControl` | 74 |
| `source/src/abstract/RewardControl.sol` | `RewardControl` | 167 |
| `source/src/art/PhiNFT1155.sol` | `PhiNFT1155` | 362 |
| `source/src/curve/BondingCurve.sol` | `BondingCurve` | 150 |
| `source/src/reward/CuratorRewardsDistributor.sol` | `CuratorRewardsDistributor` | 131 |
| `source/src/reward/PhiRewards.sol` | `PhiRewards` | 156 |
| **Totals** | **9 contracts** | **2854** |

## Official Scope Total

- Report-published in-scope contracts: 9
- Report-published Solidity lines: 1546

## Highlighted Areas of Concern

- Signature and Merkle claim binding in `Claimable`, `Cred`, and `PhiFactory`
- Reward and fee accounting in `Cred`, `PhiRewards`, and `CuratorRewardsDistributor`
- Mutable art, royalty, and pause controls in `PhiNFT1155` and `PhiFactory`
- Bonding-curve pricing and fee calculations in `BondingCurve`

