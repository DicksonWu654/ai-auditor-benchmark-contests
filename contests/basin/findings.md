# Basin High and Medium Findings

| Finding ID | Severity | Title | Description |
| --- | --- | --- | --- |
| H-01 | High | Pumps are not updated in the `shift()` and `sync()` functions, allowing oracle manipulation | `shift()` and `sync()` can change reserves in the current block without first updating pumps with the prior block's reserves, which lets an attacker manipulate oracle values. |
| M-01 | Medium | Memory corruption in `getBytes32FromBytes()` can likely lead to loss of funds | `LibBytes.getBytes32FromBytes()` uses an incorrect bounds check, so the last chunk of a bytes array can read adjacent memory and corrupt values used by Well logic. |
| M-02 | Medium | Due to slot confusion, reserve amounts in the pump will be corrupted, resulting in wrong oracle values | `LibBytes16` and `LibLastReserveBytes` read and write the wrong storage slot for odd-length reserve arrays, corrupting packed reserve data. |
| M-03 | Medium | Due to bit-shifting errors, reserve amounts in the pump will be corrupted, resulting in wrong oracle values | `LibBytes16` applies the wrong bit shifting when packing and unpacking reserves, so pump state can be decoded incorrectly. |
| M-04 | Medium | Long term denial of service due to lack of fees in Well | Because swaps charge no fee, low-cost MEV griefing can repeatedly force swaps to revert and create a long-lived denial of service. |
| M-05 | Medium | The constant product invariant can be broken. | External token transfers followed by `sync()` can desynchronize reserves from LP supply, breaking the constant-product assumption and causing later liquidity operations to fail. |
| M-06 | Medium | There is a large precision error in sqrt calculation of lp | The square-root based LP minting math loses precision on imbalanced deposits, leaving excess tokens in the pool that can later be extracted. |
| M-07 | Medium | boreWell can be frontrun/DoS-d | `boreWell()` can be front-run or griefed by reusing the intended salt/address flow, which can block the user's Well creation or steal the deposit flow. |
| M-08 | Medium | Treating of BLOCK_TIME as permanent will cause serious economic flaws in the oracle when block times change | The pump hardcodes block time at deployment, so future network block-time changes can make oracle capping too strict or too permissive. |
| M-09 | Medium | Aquifer is vulnerable to Metamorphic Contract Attack | `Aquifer` allows deterministic deployments that can be reused in ways that undermine implementation immutability and make the recorded Well implementation unreliable. |
| M-10 | Medium | Transferout exclusive feeOnTransfer tokens will run out of well | The Well does not correctly account for exclusive fee-on-transfer behavior on transfers out, so repeated transfers can drain value from the pool. |
| M-11 | Medium | addLiquidity Sandwich Attack for unbalanced token deposits | Unbalanced liquidity adds can be sandwiched, letting an attacker front-run and back-run the deposit to extract part of the user's value. |
| M-12 | Medium | Single hardcoded cap used for multiple tokens in a pump causing some assets to be more stale, while having no effects on other stable assets | `MultiFlowPump` applies one cap to all reserves, so volatile assets can become stale while stable assets are overconstrained or underconstrained. |
| M-13 | Medium | Useless Modifier and Bad Assumptions in Constructor | The constructor has an unnecessary modifier and assumes block time stays fixed, which can make reserve-timing logic incorrect if the chain changes. |
