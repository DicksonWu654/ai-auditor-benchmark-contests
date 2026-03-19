# TraitForge High and Medium Findings

| Finding ID | Severity | Title | Description |
| --- | --- | --- | --- |
| H-01 | High | Wrong minting logic based on total token count across generations | `mintWithBudget()` uses the total minted token count to cap a generation, so minting stops after the first full generation instead of per generation. |
| H-02 | High | Griefing attack on seller's airdrop benefits | Transferred NFTs keep the original minting airdrop credit, so a buyer can burn or nuke the token and reduce the seller's airdrop benefits. |
| H-03 | High | Incorrect percentage calculation in NukeFund and EntityForging when taxCut is changed from default value | If `taxCut` changes from 10, both `NukeFund::receive` and `EntityForging::forgeWithListed` split fees with division instead of percentage math, causing incorrect fund distribution. |
| H-04 | High | Number of entities in generation can surpass the 10k number | Generation mint counts can be reset in a way that misses forged entities, letting a generation exceed the intended 10k cap. |
| H-05 | High | The maximum number of generations is infinite | `TraitForgeNft` does not enforce the intended generation cap, so users can mint beyond the maximum number of generations. |
| H-06 | High | `mintToken()`, `mintWithBudget()`, and `forge()` in the `TraitForgeNft` contract will fail due to a wrong modifier used in `EntropyGenerator.initializeAlphaIndices()` | `EntropyGenerator.initializeAlphaIndices()` is protected by `onlyOwner` instead of `onlyAllowedCaller`, which blocks the `TraitForgeNft` minting and forging flow. |
| M-01 | Medium | Potential uninitialized `entropySlots` reading in `getNextEntropy`, causing 0 entropy mint | `getNextEntropy()` can run before entropy batches are fully written, returning zero entropy and producing useless mints with no future airdrop value. |
| M-02 | Medium | Funds can be locked indefinitely in `NukeFund.sol` | Because withdrawals rely entirely on `nuke()`, any path that blocks that function can leave ETH stuck in `NukeFund` indefinitely. |
| M-03 | Medium | A dev will lose rewards if after claiming his rewards he mints an NFT | A developer can have `rewardDebt` updated unexpectedly during reward claiming, which can reduce or erase rewards if they mint immediately afterward. |
| M-04 | Medium | Lack of slippage protection in dynamic pricing mint function | `mintWithBudget()` has no user-specified max price, so dynamic pricing can make callers pay more than expected during the loop. |
| M-05 | Medium | Incorrect check against golden entropy value in the first two batches | The first two entropy-writing batches do not fully exclude the golden value `999999`, so it can appear earlier than intended. |
| M-06 | Medium | TraitForgeNft: Generations without a golden god are possible | Forging can advance generation mint counts before the Golden God entropy is reached, leaving a generation with none. |
| M-07 | Medium | Discrepancy between nfts minted, price of nft when a generation changes & position of `_incrementGeneration()` inside `_mintInternal()` and `_mintNewEntity()` | Generation rollover and price updates happen at the wrong time, so mint pricing can be based on the wrong generation state. |
| M-08 | Medium | Lack of ability to make an some external function calls makes the DAO stage unreachable | The in-scope contracts do not expose the external calls needed to move the protocol into the DAO stage. |
| M-09 | Medium | Golden God tokens can be minted twice per generation | The entropy-generation logic can produce two `Golden God` NFTs in one generation, breaking the intended uniqueness. |
| M-10 | Medium | Imprecise token age calculation results in an incorrect nuke factor, causing users to claim the wrong amount | Token age is truncated to whole days before the nuke factor is calculated, so users can claim a slightly wrong amount. |
| M-11 | Medium | Duplicate NFT generation via repeated forging with the same parent | Forging the same parent repeatedly can recreate the same generation and entropy combination. |
| M-12 | Medium | NFTs mature too slowly under default settings. | With the default parameters, NFTs take longer to mature than intended before they can be nuked. |
| M-13 | Medium | Pause and unpause functions are inaccessible | The contracts inherit `Pausable`, but the public API never exposes `_pause()` or `_unpause()`. |
| M-14 | Medium | Forger Entities can forge more times than intended | Entities with nonzero forging potential can exceed the intended forge count. |
| M-15 | Medium | Users' ability to nuke will be DoSed for three days after putting NFTs up for sale and canceling the sale | Canceling a sale resets the transfer timestamp, so the NFT stays non-nukable for another three days. |
| M-16 | Medium | There is no slippage check in the `nuke()` function | The nuke flow does not let the caller set a minimum acceptable payout, so the received ETH can be lower than expected. |
| M-17 | Medium | Incorrect `isApprovedForAll` check in the `NukeFund.nuke()` function | `NukeFund.nuke()` checks approval against the caller instead of the owner, so approved operators cannot nuke on the owner's behalf. |
| M-18 | Medium | Excess ETH from `forgingFee` can get stuck in `EntityForging` under certain situations | If the forging fee changes between submission and execution, excess ETH sent with the transaction can remain locked in the contract. |
| M-19 | Medium | Each generation should have 1 "Golden God" NFT, but there could be 0 | The entropy flow can leave a generation with zero Golden God NFTs even though the design expects one. |
