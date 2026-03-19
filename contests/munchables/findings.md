# Official High and Medium Findings

| Finding ID | Severity | Title | Description |
|---|---|---|---|
| H-01 | High | Single plot can be occupied by multiple renters | `transferToUnoccupiedPlot()` updates plot occupancy but does not update `toilerState[tokenId].plotId`, so occupancy bookkeeping can drift and a plot can end up treated as both vacated and still occupied. |
| H-02 | High | Invalid validation in _farmPlots function allowing a malicious user repeated farming without locked funds | `_farmPlots()` only marks a position dirty when `_getNumPlots(landlord) < plotId`, which leaves plot `0` farmable after the landlord unlocks funds and allows rewards to keep accruing without any locked stake. |
| H-03 | High | Miscalculation in _farmPlots function could lead to a user unable to unstake all NFTs | The `finalBonus` math in `_farmPlots()` can turn a negative adjustment into a huge unsigned value after the cast back to `uint256`, causing `unstakeMunchable()` to revert and potentially locking NFTs in the protocol. |
| H-04 | High | in farmPlots() an underflow in edge case leading to freeze of funds (NFT) | When `PRICE_PER_PLOT` increases and a staked plot becomes invalid, `_farmPlots()` can end up subtracting a larger `lastToilDate` from an older `timestamp`, triggering a panic revert that freezes farming and unstaking. |
| H-05 | High | Failure to update dirty flag in transferToUnoccupiedPlot prevents reward accumulation on valid plot | Moving to a valid plot does not clear the `dirty` flag or reset `lastToilDate`, so a transferred Munchable can remain ineligible for rewards even after it reaches a valid plot. |
| M-01 | Medium | Users can farm on zero-tax land if the landlord locked tokens before the LandManager deployment | `stakeMunchable()` does not require `plotMetadata[landlord]` to be initialized, so users can stake on a landlord whose metadata has not yet been populated and farm at a zero-tax rate until `triggerPlotMetadata()` or `updatePlotMetadata()` runs. |

