# Scope

Source of scope info: [Nethermind Mellow Core Vaults report PDF](https://1022099409-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-Mk3LEacyGwD8y6mb9-2%2Fuploads%2FNs4351hVFYzadiFii2az%2FNethermind_Mellow-Core-Vaults_20250903.pdf?alt=media&token=f4d3480d-f11f-4bb2-8b8e-ff22c5f96298), pages 3-5.

Audited commit: `72f689f965e4ac1a4c2bcfb645a8b5416cf740c7`

Totals: 75 in-scope files, 4217 LoC, 6710 total lines.

Highlighted areas of concern:
- Oracle pricing and iteration logic in `src/oracles/OracleHelper.sol` and `src/oracles/Oracle.sol`.
- Queue transitions and time-buffered deposit/redeem flows.
- Verifier and permission plumbing for vault and strategy operations.

## In Scope

| # | File | LoC | Total |
| ---: | --- | ---: | ---: |
| 1 | `src/permissions/BitmaskVerifier.sol` | 37 | 76 |
| 2 | `src/permissions/Consensus.sol` | 100 | 135 |
| 3 | `src/permissions/Verifier.sol` | 137 | 185 |
| 4 | `src/permissions/MellowACL.sol` | 45 | 64 |
| 5 | `src/permissions/protocols/EigenLayerVerifier.sol` | 122 | 132 |
| 6 | `src/permissions/protocols/OwnedCustomVerifier.sol` | 23 | 30 |
| 7 | `src/permissions/protocols/ERC20Verifier.sol` | 36 | 44 |
| 8 | `src/permissions/protocols/SymbioticVerifier.sol` | 78 | 88 |
| 9 | `src/strategies/SymbioticStrategy.sol` | 54 | 65 |
| 10 | `src/queues/SignatureDepositQueue.sol` | 18 | 24 |
| 11 | `src/queues/RedeemQueue.sol` | 201 | 247 |
| 12 | `src/queues/SignatureQueue.sol` | 112 | 153 |
| 13 | `src/queues/Queue.sol` | 48 | 70 |
| 14 | `src/queues/DepositQueue.sol` | 172 | 214 |
| 15 | `src/queues/SignatureRedeemQueue.sol` | 22 | 30 |
| 16 | `src/managers/TokenizedShareManager.sol` | 51 | 76 |
| 17 | `src/managers/RiskManager.sol` | 206 | 264 |
| 18 | `src/managers/ShareManager.sol` | 191 | 256 |
| 19 | `src/managers/FeeManager.sol` | 131 | 177 |
| 20 | `src/managers/BasicShareManager.sol` | 51 | 72 |
| 21 | `src/hooks/LidoDepositHook.sol` | 40 | 49 |
| 22 | `src/hooks/RedirectingDepositHook.sol` | 24 | 27 |
| 23 | `src/hooks/BasicRedeemHook.sol` | 48 | 53 |
| 24 | `src/libraries/TransferLibrary.sol` | 31 | 61 |
| 25 | `src/libraries/ShareManagerFlagLibrary.sol` | 26 | 67 |
| 26 | `src/libraries/SlotLibrary.sol` | 10 | 20 |
| 27 | `src/libraries/FenwickTreeLibrary.sol` | 66 | 130 |
| 28 | `src/interfaces/permissions/IMellowACL.sol` | 12 | 32 |
| 29 | `src/interfaces/permissions/IConsensus.sol` | 37 | 105 |
| 30 | `src/interfaces/permissions/IVerifier.sol` | 74 | 156 |
| 31 | `src/interfaces/permissions/ICustomVerifier.sol` | 10 | 22 |
| 32 | `src/interfaces/queues/IQueue.sol` | 21 | 56 |
| 33 | `src/interfaces/queues/IRedeemQueue.sol` | 44 | 161 |
| 34 | `src/interfaces/queues/IDepositQueue.sol` | 31 | 129 |
| 35 | `src/interfaces/queues/ISignatureQueue.sol` | 54 | 160 |
| 36 | `src/interfaces/managers/IRiskManager.sol` | 61 | 145 |
| 37 | `src/interfaces/managers/ITokenizedShareManager.sol` | 6 | 15 |
| 38 | `src/interfaces/managers/IShareManager.sol` | 70 | 179 |
| 39 | `src/interfaces/managers/IFeeManager.sol` | 42 | 105 |
| 40 | `src/interfaces/hooks/IHook.sol` | 4 | 14 |
| 41 | `src/interfaces/hooks/IRedeemHook.sol` | 5 | 14 |
| 42 | `src/interfaces/factories/IFactory.sol` | 34 | 90 |
| 43 | `src/interfaces/factories/IFactoryEntity.sol` | 5 | 13 |
| 44 | `src/interfaces/oracles/IOracle.sol` | 65 | 183 |
| 45 | `src/interfaces/external/symbiotic/ISymbioticRegistry.sol` | 4 | 6 |
| 46 | `src/interfaces/external/symbiotic/ISymbioticVault.sol` | 8 | 12 |
| 47 | `src/interfaces/external/symbiotic/ISymbioticStakerRewards.sol` | 7 | 12 |
| 48 | `src/interfaces/external/eigen-layer/IRewardsCoordinator.sol` | 90 | 134 |
| 49 | `src/interfaces/external/eigen-layer/IDelegationManager.sol` | 86 | 120 |
| 50 | `src/interfaces/external/eigen-layer/IAllocationManager.sol` | 118 | 164 |
| 51 | `src/interfaces/external/eigen-layer/ISignatureUtils.sol` | 13 | 17 |
| 52 | `src/interfaces/external/eigen-layer/IStrategy.sol` | 16 | 30 |
| 53 | `src/interfaces/external/eigen-layer/IStrategyManager.sol` | 39 | 58 |
| 54 | `src/interfaces/external/tokens/IWSTETH.sol` | 6 | 9 |
| 55 | `src/interfaces/external/tokens/IWETH.sol` | 4 | 6 |
| 56 | `src/interfaces/modules/IVerifierModule.sol` | 10 | 21 |
| 57 | `src/interfaces/modules/IBaseModule.sol` | 8 | 16 |
| 58 | `src/interfaces/modules/IShareModule.sol` | 76 | 177 |
| 59 | `src/interfaces/modules/IACLModule.sol` | 7 | 14 |
| 60 | `src/interfaces/modules/IVaultModule.sol` | 40 | 131 |
| 61 | `src/interfaces/modules/ISubvaultModule.sol` | 11 | 36 |
| 62 | `src/interfaces/modules/ICallModule.sol` | 9 | 21 |
| 63 | `src/factories/Factory.sol` | 92 | 131 |
| 64 | `src/oracles/OracleHelper.sol` | 122 | 149 |
| 65 | `src/oracles/Oracle.sol` | 195 | 248 |
| 66 | `src/vaults/Subvault.sol` | 16 | 20 |
| 67 | `src/vaults/VaultConfigurator.sol` | 65 | 74 |
| 68 | `src/vaults/Vault.sol` | 49 | 55 |
| 69 | `src/modules/VerifierModule.sol` | 25 | 39 |
| 70 | `src/modules/SubvaultModule.sol` | 31 | 49 |
| 71 | `src/modules/ACLModule.sol` | 14 | 22 |
| 72 | `src/modules/CallModule.sol` | 13 | 20 |
| 73 | `src/modules/ShareModule.sol` | 247 | 327 |
| 74 | `src/modules/VaultModule.sol` | 124 | 172 |
| 75 | `src/modules/BaseModule.sol` | 17 | 32 |
| **Total** | **75 files** | **4217** | **6710** |
