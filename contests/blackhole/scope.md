# Blackhole Scope

- Source URL: https://github.com/code-423n4/2025-05-blackhole#scope
- Report URL: https://code4rena.com/reports/2025-05-blackhole
- In-scope files: 116
- Total SLOC: 10,108

## In Scope

| Contest path | SLOC |
| --- | ---: |
| `contracts/APIHelper/AlgebraPoolAPI.sol` | 288 |
| `contracts/APIHelper/AlgebraPoolAPIStorage.sol` | 43 |
| `contracts/APIHelper/BlackholePairAPIV2.sol` | 582 |
| `contracts/APIHelper/GenesisPoolAPI.sol` | 171 |
| `contracts/APIHelper/RewardAPI.sol` | 109 |
| `contracts/APIHelper/TokenAPI.sol` | 51 |
| `contracts/APIHelper/TradeHelper.sol` | 124 |
| `contracts/APIHelper/veNFTAPI.sol` | 300 |
| `contracts/APIHelper/veNFTAPIV1.sol` | 367 |
| `contracts/AVM/AutoVotingEscrow.sol` | 94 |
| `contracts/AVM/AutoVotingEscrowManager.sol` | 157 |
| `contracts/AVM/interfaces/IAutoVotingEscrow.sol` | 7 |
| `contracts/AVM/interfaces/IAutoVotingEscrowManager.sol` | 4 |
| `contracts/AlgebraCLVe33/GaugeCL.sol` | 232 |
| `contracts/AlgebraCLVe33/GaugeFactoryCL.sol` | 104 |
| `contracts/Black.sol` | 81 |
| `contracts/BlackClaims.sol` | 145 |
| `contracts/BlackGovernor.sol` | 78 |
| `contracts/Bribes.sol` | 270 |
| `contracts/CustomPoolDeployer.sol` | 150 |
| `contracts/CustomToken.sol` | 20 |
| `contracts/Fan.sol` | 15 |
| `contracts/FixedAuction.sol` | 28 |
| `contracts/GaugeExtraRewarder.sol` | 128 |
| `contracts/GaugeManager.sol` | 418 |
| `contracts/GaugeV2.sol` | 287 |
| `contracts/GenesisPool.sol` | 328 |
| `contracts/GenesisPoolManager.sol` | 244 |
| `contracts/GlobalRouter.sol` | 144 |
| `contracts/MinterUpgradeable.sol` | 168 |
| `contracts/Pair.sol` | 453 |
| `contracts/PairFees.sol` | 46 |
| `contracts/PairGenerator.sol` | 16 |
| `contracts/PermissionsRegistry.sol` | 151 |
| `contracts/RewardsDistributor.sol` | 215 |
| `contracts/RouterV2.sol` | 520 |
| `contracts/SetterTopNPoolsStrategy.sol` | 60 |
| `contracts/SetterVoteWeightStrategy.sol` | 57 |
| `contracts/Thenian.sol` | 113 |
| `contracts/TokenHandler.sol` | 150 |
| `contracts/VeArtProxyUpgradeable.sol` | 38 |
| `contracts/VoterV3.sol` | 185 |
| `contracts/VotingEscrow.sol` | 803 |
| `contracts/WAVAX.sol` | 56 |
| `contracts/chainlink/AutomationBase.sol` | 13 |
| `contracts/chainlink/AutomationCompatible.sol` | 4 |
| `contracts/chainlink/AutomationCompatibleInterface.sol` | 3 |
| `contracts/chainlink/EpochController.sol` | 68 |
| `contracts/factories/AuctionFactory.sol` | 50 |
| `contracts/factories/BribeFactoryV3.sol` | 133 |
| `contracts/factories/GaugeFactory.sol` | 83 |
| `contracts/factories/GenesisPoolFactory.sol` | 65 |
| `contracts/factories/PairFactory.sol` | 129 |
| `contracts/governance/Governor.sol` | 349 |
| `contracts/governance/L2Governor.sol` | 254 |
| `contracts/governance/L2GovernorCountingSimple.sol` | 52 |
| `contracts/governance/L2GovernorVotes.sol` | 12 |
| `contracts/governance/L2GovernorVotesQuorumFraction.sol` | 30 |
| `contracts/interfaces/IAlgebraCLFactory.sol` | 4 |
| `contracts/interfaces/IAlgebraCustomCommunityVault.sol` | 4 |
| `contracts/interfaces/IAlgebraEternalFarmingCustom.sol` | 5 |
| `contracts/interfaces/IAlgebraFarmingProxyPluginFactory.sol` | 3 |
| `contracts/interfaces/IAlgebraPoolAPIStorage.sol` | 3 |
| `contracts/interfaces/IAuction.sol` | 3 |
| `contracts/interfaces/IAuctionFactory.sol` | 3 |
| `contracts/interfaces/IAutomatedVotingManager.sol` | 3 |
| `contracts/interfaces/IBlack.sol` | 3 |
| `contracts/interfaces/IBlackClaims.sol` | 9 |
| `contracts/interfaces/IBlackGovernor.sol` | 13 |
| `contracts/interfaces/IBlackHoleVotes.sol` | 4 |
| `contracts/interfaces/IBlackholePairApiV2.sol` | 43 |
| `contracts/interfaces/IBribe.sol` | 3 |
| `contracts/interfaces/IBribeAPI.sol` | 3 |
| `contracts/interfaces/IBribeDistribution.sol` | 3 |
| `contracts/interfaces/IBribeFactory.sol` | 3 |
| `contracts/interfaces/IBribeFull.sol` | 3 |
| `contracts/interfaces/IDibs.sol` | 3 |
| `contracts/interfaces/IERC20.sol` | 3 |
| `contracts/interfaces/IGauge.sol` | 3 |
| `contracts/interfaces/IGaugeAPI.sol` | 3 |
| `contracts/interfaces/IGaugeCL.sol` | 4 |
| `contracts/interfaces/IGaugeDistribution.sol` | 3 |
| `contracts/interfaces/IGaugeFactory.sol` | 3 |
| `contracts/interfaces/IGaugeFactoryCL.sol` | 4 |
| `contracts/interfaces/IGaugeManager.sol` | 8 |
| `contracts/interfaces/IGenesisPool.sol` | 4 |
| `contracts/interfaces/IGenesisPoolBase.sol` | 42 |
| `contracts/interfaces/IGenesisPoolFactory.sol` | 3 |
| `contracts/interfaces/IGenesisPoolManager.sol` | 3 |
| `contracts/interfaces/IMinter.sol` | 3 |
| `contracts/interfaces/IPair.sol` | 3 |
| `contracts/interfaces/IPairCallee.sol` | 3 |
| `contracts/interfaces/IPairFactory.sol` | 3 |
| `contracts/interfaces/IPairGenerator.sol` | 3 |
| `contracts/interfaces/IPairInfo.sol` | 3 |
| `contracts/interfaces/IPermissionsRegistry.sol` | 3 |
| `contracts/interfaces/IRewardsDistributor.sol` | 3 |
| `contracts/interfaces/IRouter.sol` | 8 |
| `contracts/interfaces/ITokenHandler.sol` | 3 |
| `contracts/interfaces/ITopNPoolsStrategy.sol` | 3 |
| `contracts/interfaces/IUniswapRouterETH.sol` | 3 |
| `contracts/interfaces/IUniswapV2Pair.sol` | 3 |
| `contracts/interfaces/IVeArtProxy.sol` | 3 |
| `contracts/interfaces/IVoteWeightStrategy.sol` | 4 |
| `contracts/interfaces/IVoter.sol` | 3 |
| `contracts/interfaces/IVotingEscrow.sol` | 18 |
| `contracts/interfaces/IWETH.sol` | 3 |
| `contracts/interfaces/IWrappedBribeFactory.sol` | 3 |
| `contracts/libraries/Base64.sol` | 41 |
| `contracts/libraries/BlackTimeLibrary.sol` | 52 |
| `contracts/libraries/Math.sol` | 33 |
| `contracts/libraries/PoolsAndRewardsLibrary.sol` | 10 |
| `contracts/libraries/SignedSafeMath.sol` | 33 |
| `contracts/libraries/VoterFactoryLib.sol` | 63 |
| `contracts/libraries/VotingBalanceLogic.sol` | 178 |
| `contracts/libraries/VotingDelegationLib.sol` | 174 |

## Highlighted Areas of Concern

- The contest guidance emphasizes the code delta over the ThenaFi fork baseline, so inherited behavior should be treated as background context rather than fresh audit signal.
- Review access control and permissions carefully, especially around factory/admin paths and role-based configuration.
- Validate logic and flow across emissions, voting, genesis pools, and liquidity operations, with extra attention to edge cases and race conditions.
