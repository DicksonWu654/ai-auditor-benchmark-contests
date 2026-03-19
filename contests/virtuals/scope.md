# Scope

Source URL: https://github.com/code-423n4/2025-04-virtuals-protocol/blob/main/README.md#scope

The published scope table lists 67 in-scope files and a reviewed contract set of 5,238 nSLOC.
This corresponds to 43 smart contracts and 24 interfaces in the published table.

## In-Scope Files

| File | nSLOC |
| --- | ---: |
| `/contracts/AgentInference.sol` | 63 |
| `/contracts/contribution/ContributionNft.sol` | 113 |
| `/contracts/contribution/IContributionNft.sol` | 4 |
| `/contracts/contribution/IServiceNft.sol` | 3 |
| `/contracts/contribution/ServiceNft.sol` | 124 |
| `/contracts/fun/Bonding.sol` | 300 |
| `/contracts/fun/FERC20.sol` | 94 |
| `/contracts/fun/FFactory.sol` | 58 |
| `/contracts/fun/FPair.sol` | 78 |
| `/contracts/fun/FRouter.sol` | 108 |
| `/contracts/fun/IFPair.sol` | 3 |
| `/contracts/genesis/FGenesis.sol` | 115 |
| `/contracts/genesis/Genesis.sol` | 353 |
| `/contracts/genesis/GenesisLib.sol` | 35 |
| `/contracts/genesis/GenesisTypes.sol` | 34 |
| `/contracts/genesis/MockAgentFactoryV3.sol` | 40 |
| `/contracts/genesis/MockERC20.sol` | 12 |
| `/contracts/governance/GovernorCountingSimple.sol` | 54 |
| `/contracts/governance/VirtualGenesisDAO.sol` | 95 |
| `/contracts/governance/VirtualProtocolDAO.sol` | 49 |
| `/contracts/governance/veVirtualToken.sol` | 32 |
| `/contracts/libs/AddressCheckpoints.sol` | 61 |
| `/contracts/libs/Elo.sol` | 32 |
| `/contracts/libs/FixedPointMathLib.sol` | 131 |
| `/contracts/libs/IERC6551Registry.sol` | 11 |
| `/contracts/libs/RewardSettingsCheckpoints.sol` | 68 |
| `/contracts/libs/RewardSettingsCheckpointsV2.sol` | 65 |
| `/contracts/libs/TokenSaver.sol` | 17 |
| `/contracts/pool/AeroAdaptor.sol` | 36 |
| `/contracts/pool/IRouter.sol` | 3 |
| `/contracts/pool/IUniswapV2Factory.sol` | 4 |
| `/contracts/pool/IUniswapV2Pair.sol` | 5 |
| `/contracts/pool/IUniswapV2Router01.sol` | 3 |
| `/contracts/pool/IUniswapV2Router02.sol` | 4 |
| `/contracts/tax/AgentTax.sol` | 219 |
| `/contracts/tax/BondingTax.sol` | 112 |
| `/contracts/tax/IBondingTax.sol` | 3 |
| `/contracts/tax/ITBABonus.sol` | 3 |
| `/contracts/tax/LPRefund.sol` | 45 |
| `/contracts/tax/TBABonus.sol` | 61 |
| `/contracts/token/Airdrop.sol` | 45 |
| `/contracts/token/Virtual.sol` | 15 |
| `/contracts/virtualPersona/AgentDAO.sol` | 150 |
| `/contracts/virtualPersona/AgentFactory.sol` | 275 |
| `/contracts/virtualPersona/AgentFactoryV3.sol` | 327 |
| `/contracts/virtualPersona/AgentFactoryV4.sol` | 369 |
| `/contracts/virtualPersona/AgentMigrator.sol` | 129 |
| `/contracts/virtualPersona/AgentNftV2.sol` | 192 |
| `/contracts/virtualPersona/AgentToken.sol` | 422 |
| `/contracts/virtualPersona/AgentVeToken.sol` | 98 |
| `/contracts/virtualPersona/CoreRegistry.sol` | 18 |
| `/contracts/virtualPersona/ERC20Votes.sol` | 19 |
| `/contracts/virtualPersona/EloCalculator.sol` | 49 |
| `/contracts/virtualPersona/GovernorCountingSimpleUpgradeable.sol` | 55 |
| `/contracts/virtualPersona/IAgentDAO.sol` | 5 |
| `/contracts/virtualPersona/IAgentFactory.sol` | 4 |
| `/contracts/virtualPersona/IAgentFactoryV3.sol` | 4 |
| `/contracts/virtualPersona/IAgentFactoryV4.sol` | 4 |
| `/contracts/virtualPersona/IAgentNft.sol` | 16 |
| `/contracts/virtualPersona/IAgentToken.sol` | 144 |
| `/contracts/virtualPersona/IAgentVeToken.sol` | 3 |
| `/contracts/virtualPersona/IERC20Config.sol` | 28 |
| `/contracts/virtualPersona/IEloCalculator.sol` | 3 |
| `/contracts/virtualPersona/IErrors.sol` | 156 |
| `/contracts/virtualPersona/IExecutionInterface.sol` | 3 |
| `/contracts/virtualPersona/IValidatorRegistry.sol` | 4 |
| `/contracts/virtualPersona/ValidatorRegistry.sol` | 51 |
| **Total** | **5,238** |

## Highlighted Areas of Concern

- Bonding pool accounting, liquidity extraction, and access control.
- Staking, delegation, reward accounting, and validator registration flows.
- Factory, mint, and governance execution paths across the Virtuals lifecycle.
