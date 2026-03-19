# Scope

Source of scope truth: https://code4rena.com/reports/2024-07-munchables

The Code4rena report publishes the contest-wide scope total, while the snapshot here preserves the audited source file. The table below records the checked-in file length for traceability.

## Files in Scope

| File | Contract | Snapshot lines |
| --- | --- | ---: |
| `source/src/managers/LandManager.sol` | `LandManager` | 347 |
| **Totals** | **1 contract** | **347** |

## Official Scope Total

- Report-published in-scope contracts: 1
- Report-published Solidity lines: 277

## Highlighted Areas of Concern

- Plot occupancy bookkeeping in `transferToUnoccupiedPlot()`
- Farming validation and dirty-flag handling in `_farmPlots()`
- Timestamp and reward-accounting edge cases around staking and unstaking

