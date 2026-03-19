# Historical Audit Competition Benchmark Contests

Public export of the 14 historical audit competition artifacts used by Wake Arena.

Ackee states that Wake Arena adopted the same 14-protocol historical audit competition dataset used by Zellic for its V12 benchmark comparisons. This repository is limited to that shared 14-contest set.

This is not the full set of examples discussed in Zellic's V12 launch post. That post also includes additional non-shared examples, including ZeroLend on Immunefi.

Each contest folder includes:
- `README.md` with contest metadata and scope summary
- `findings.md` with official High and Medium findings
- `scope.md` with the published in-scope files and LOC
- `source/` with the audited source snapshot at the pinned commit
- `metadata.json` with machine-readable contest metadata

| Contest | Protocol | Platform | Date | Highs | Mediums | Folder | Audited Source | Official Report |
| --- | --- | --- | --- | ---: | ---: | --- | --- | --- |
| Basin | Basin | Code4rena | 2023-07-03 to 2023-07-10 | 1 | 13 | [Basin](./contests/basin/) | [source](https://github.com/code-423n4/2023-07-basin/tree/9403cf973e95ef7219622dbbe2a08396af90b64c) | [report](https://code4rena.com/reports/2023-07-basin) |
| Blackhole | Blackhole | Code4rena | 2025-05-28 to 2025-06-09 | 2 | 22 | [Blackhole](./contests/blackhole/) | [source](https://github.com/code-423n4/2025-05-blackhole/tree/92fff849d3b266e609e6d63478c4164d9f608e91) | [report](https://code4rena.com/reports/2025-05-blackhole) |
| Burve | Burve | Sherlock | 2025-04-19 to 2025-05-07 | 9 | 6 | [Burve](./contests/burve/) | [source](https://github.com/itos-finance/Burve/tree/945f30bfae8afc41af21305ff8c2271ca0ffe6c3) | [report](https://github.com/sherlock-audit/2025-04-burve-judging/blob/main/README.md) |
| Crestal | Crestal Network | Sherlock | 2025-03-11 to 2025-03-14 | 1 | 6 | [Crestal](./contests/crestal/) | [source](https://github.com/crestalnetwork/crestal-omni-contracts/tree/dc45e98af5e247dce5bbe53b0bd5b1f256884f84) | [report](https://github.com/sherlock-protocol/sherlock-reports/blob/main/audits/2025.03.14%20-%20Final%20-%20Crestal%20Network%20Audit%20Report.pdf) |
| DODO | DODO Cross-Chain DEX | Sherlock | June 2025 | 5 | 3 | [DODO](./contests/dodo/) | [source](https://github.com/Skyewwww/omni-chain-contracts/tree/2fe44d3da76b721e4d32addfecb04ca97a39cb0d) | [report](https://github.com/sherlock-audit/2025-05-dodo-cross-chain-dex-judging/issues) |
| Lambo.win | Lambo.win | Code4rena | 2024-12-02 20:00 UTC to 2024-12-09 20:00 UTC | 4 | 10 | [Lambo.win](./contests/lambo_win/) | [source](https://github.com/code-423n4/2024-12-lambowin/tree/874fafc7b27042c59bdd765073f5e412a3b79192) | [report](https://code4rena.com/reports/2024-12-lambowin) |
| Lend | LEND | Sherlock | 2025-05-27 to 2025-06-03 | 28 | 11 | [Lend](./contests/lend/) | [source](https://github.com/tenfinance/Lend-V2/tree/5c9398fef079319ecc4e8457b11533d0d8838ee0) | [report](https://github.com/sherlock-audit/2025-05-lend-audit-contest-judging/issues) |
| Mellow | Mellow Flexible Vaults | Sherlock | July 2025 | 2 | 0 | [Mellow](./contests/mellow/) | [source](https://github.com/mellow-finance/flexible-vaults/tree/72f689f965e4ac1a4c2bcfb645a8b5416cf740c7) | [report](https://1022099409-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-Mk3LEacyGwD8y6mb9-2%2Fuploads%2FNs4351hVFYzadiFii2az%2FNethermind_Mellow-Core-Vaults_20250903.pdf?alt=media&token=f4d3480d-f11f-4bb2-8b8e-ff22c5f96298) |
| Munchables | Munchables | Code4rena | 2024-07-23 to 2024-07-29 | 5 | 1 | [Munchables](./contests/munchables/) | [source](https://github.com/code-423n4/2024-07-munchables/blob/94cf468aaabf526b7a8319f7eba34014ccebe7b9/src/managers/LandManager.sol) | [report](https://code4rena.com/reports/2024-07-munchables) |
| Notional Exponent | Notional Exponent | Sherlock | 2025-07-02 | 11 | 26 | [Notional Exponent](./contests/notional_exponent/) | [source](https://github.com/notional-finance/notional-v4/tree/0096f1f64071cafbf20062a7c092c6ec89c28275) | [report](https://github.com/sherlock-audit/2025-06-notional-exponent-judging/blob/main/README.md) |
| Phi | Phi Protocol | Code4rena | 2024-08-22 to 2024-09-03 | 7 | 8 | [Phi](./contests/phi/) | [source](https://github.com/code-423n4/2024-08-phi/tree/f67c29b7cb93b710080681c88a4dfcaf714d3e5d) | [report](https://code4rena.com/reports/2024-08-phi) |
| Superfluid | Superfluid Locker System | Sherlock | 2024-11-20 to 2024-11-24 | 3 | 3 | [Superfluid](./contests/superfluid/) | [source](https://github.com/superfluid-finance/fluid/tree/6cb9f19564f1af239d18916e68eaa2a62597497a) | [report](https://github.com/sherlock-audit/2024-11-superfluid-locking-contract-judging/issues) |
| TraitForge | TraitForge | Code4rena | 2024-07-29 to 2024-08-06 | 6 | 19 | [TraitForge](./contests/traitforge/) | [source](https://github.com/code-423n4/2024-07-traitforge/tree/279b2887e3d38bc219a05d332cbcb0655b2dc644) | [report](https://code4rena.com/reports/2024-07-traitforge) |
| Virtuals | Virtuals Protocol | Code4rena | 2025-04-17 to 2025-05-07 | 6 | 26 | [Virtuals](./contests/virtuals/) | [source](https://github.com/code-423n4/2025-04-virtuals-protocol/tree/28e93273daec5a9c73c438e216dde04c084be452) | [report](https://code4rena.com/reports/2025-04-virtuals-protocol) |

The full table is also available in [`contests_summary.md`](./contests_summary.md).
