# Scope

- Scope source URL: <https://github.com/sherlock-audit/2025-04-burve-judging/blob/main/README.md>
- Audited source URL: <https://github.com/itos-finance/Burve/tree/945f30bfae8afc41af21305ff8c2271ca0ffe6c3>
- Counts below are physical LOC from the audited `source/src` snapshot.

| File | Contract / library / interface | LOC |
| --- | --- | ---: |
| `src/FullMath.sol` | `FullMath` | 255 |
| `src/Timed.sol` | `Timed` | 170 |
| `src/TransferHelper.sol` | `TransferHelper` | 72 |
| `src/integrations/BGTExchange/BGTExchanger.sol` | `BGTExchanger` | 131 |
| `src/integrations/BGTExchange/IBGTExchanger.sol` | `IBGTExchanger` | 59 |
| `src/integrations/adjustor/DecimalAdjustor.sol` | `DecimalAdjustor` | 233 |
| `src/integrations/adjustor/E4626ViewAdjustor.sol` | `E4626ViewAdjustor` | 75 |
| `src/integrations/adjustor/FixedAdjustor.sol` | `FixedAdjustor` | 98 |
| `src/integrations/adjustor/IAdjustor.sol` | `IAdjustor` | 63 |
| `src/integrations/adjustor/MixedAdjustor.sol` | `MixedAdjustor` | 82 |
| `src/integrations/adjustor/NullAdjustor.sol` | `NullAdjustor` | 45 |
| `src/integrations/pseudo4626/noopVault.sol` | `noopVault` | 12 |
| `src/multi/Adjustor.sol` | `Adjustor` | 44 |
| `src/multi/Asset.sol` | `Asset` | 190 |
| `src/multi/Constants.sol` | `Constants` | 5 |
| `src/multi/Diamond.sol` | `Diamond` | 239 |
| `src/multi/Simplex.sol` | `Simplex` | 186 |
| `src/multi/Store.sol` | `Store` | 85 |
| `src/multi/Token.sol` | `Token` | 81 |
| `src/multi/Value.sol` | `Value` | 259 |
| `src/multi/closure/Closure.sol` | `Closure` | 893 |
| `src/multi/closure/Id.sol` | `Id` | 40 |
| `src/multi/facets/LockFacet.sol` | `LockFacet` | 56 |
| `src/multi/facets/SimplexFacet.sol` | `SimplexFacet` | 405 |
| `src/multi/facets/SwapFacet.sol` | `SwapFacet` | 199 |
| `src/multi/facets/ValueFacet.sol` | `ValueFacet` | 359 |
| `src/multi/facets/ValueTokenFacet.sol` | `ValueTokenFacet` | 44 |
| `src/multi/facets/VaultFacet.sol` | `VaultFacet` | 92 |
| `src/multi/vertex/E4626.sol` | `E4626` | 242 |
| `src/multi/vertex/Id.sol` | `Id` | 53 |
| `src/multi/vertex/Reserve.sol` | `Reserve` | 80 |
| `src/multi/vertex/VaultPointer.sol` | `VaultPointer` | 165 |
| `src/multi/vertex/VaultProxy.sol` | `VaultProxy` | 256 |
| `src/multi/vertex/Vertex.sol` | `Vertex` | 157 |
| `src/single/Burve.sol` | `Burve` | 1090 |
| `src/single/Fees.sol` | `Fees` | 133 |
| `src/single/IStationProxy.sol` | `IStationProxy` | 50 |
| `src/single/Info.sol` | `Info` | 33 |
| `src/single/TickRange.sol` | `TickRange` | 22 |
| **Total** | **39 files** | **6,753** |

## Highlighted Areas

- ERC4626 fee accounting in `ValueFacet`, `SwapFacet`, `Closure`, and `E4626ViewAdjustor`.
- Single-sided add/remove-value tax distribution and `removeValueSingle` tax flow.
- Vertex, reserve, and closure netting arithmetic during rebalancing.
- `NoopVault` edge cases and fee-on-transfer style accounting drift.
