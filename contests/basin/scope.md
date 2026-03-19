# Basin Scope

- Source URL: https://github.com/code-423n4/2023-07-basin#scope
- Report URL: https://code4rena.com/reports/2023-07-basin
- In-scope files: 10
- Total SLOC: 1,145

## In Scope

| Contest path | SLOC |
| --- | ---: |
| `src/functions/ConstantProduct2.sol` | 47 |
| `src/functions/ProportionalLPToken2.sol` | 14 |
| `src/pumps/MultiFlowPump.sol` | 231 |
| `src/Aquifer.sol` | 58 |
| `src/Well.sol` | 486 |
| `src/libraries/LibBytes.sol` | 73 |
| `src/libraries/LibBytes16.sol` | 58 |
| `src/libraries/LibContractInfo.sol` | 29 |
| `src/libraries/LibLastReserveBytes.sol` | 92 |
| `src/libraries/LibWellConstructor.sol` | 57 |

## Highlighted Areas of Concern

- The contest organizers explicitly focus review effort on the `src/` delta and the composable trust boundary between Wells, Pumps, and Aquifers.
- Oracle timing, reserve updates, and the math behind the whitepaper-driven components are the main places where incorrect assumptions can turn into exploit paths.
- Prior audits and known issues were called out in the contest materials, so inherited behavior should be treated as the baseline and not the primary audit target.
