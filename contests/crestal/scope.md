# Scope

- Scope source URL: <https://github.com/sherlock-protocol/sherlock-reports/blob/main/audits/2025.03.14%20-%20Final%20-%20Crestal%20Network%20Audit%20Report.pdf>
- Audited source URL: <https://github.com/crestalnetwork/crestal-omni-contracts/tree/dc45e98af5e247dce5bbe53b0bd5b1f256884f84>
- Counts below are physical LOC from the audited `source/` snapshot.

| File | Contract | LOC |
| --- | --- | ---: |
| `src/Blueprint.sol` | `Blueprint` | 91 |
| `src/BlueprintCore.sol` | `BlueprintCore` | 763 |
| `src/BlueprintV5.sol` | `BlueprintV5` | 25 |
| `src/EIP712.sol` | `EIP712` | 52 |
| `src/Payment.sol` | `Payment` | 33 |
| **Total** | **5 files** | **964** |

## Highlighted Areas

- Public ERC20 payment handling in `Payment`.
- Signature-based agent creation and deployment updates in `Blueprint`/`BlueprintCore`.
- Worker registration, whitelist enforcement, and project lifecycle transitions.
- Upgradeability and replay-protection boundaries around the `BlueprintV5` flow.
