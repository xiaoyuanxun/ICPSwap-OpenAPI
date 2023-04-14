# Farm
Farm is a canister for users to stake their NFTs and earn reward tokens. It will allow at most 300 NFTs to be staked in by default.

## Methods

`stake`: transfer an NFT from user to farm and start to stake

input:
- id of non-fungible token

output:
- success or failure message

`unstake`: transfer an NFT from farm to user and claim the reward token

input:
- id of non-fungible token

output:
- success or failure message

`getRewardInfo`: get reward info by a group of NFT ids

input:
- a list of NFT ids

output:
- amount of earned reward tokens

`getFarmInfo`: get farm info by user principal, it will return all information if the user principal is the canister id of FarmController

input:
- principal of particular user

output:
- rewardToken : address and standard of reward token
- pool :canister id of SwapPool
- poolToken0 : address and standard of token0 in SwapPool
- poolToken1 : address and standard of token1 in SwapPool
- poolFee : rate of transaction fee
- startTime : time stamp of start time
- endTime : time stamp of end time
- refunder : principal of user who will receive the reward token balance after the Farm closed
- totalReward : total amount of reward token
- totalRewardBalance : balance of reward token
- totalRewardClaimed : amount of claimed reward token
- totalRewardUnclaimed : amount of distributed but not be claimed reward token
- numberOfStakes : total number of NFTs in this Farm canister
- userNumberOfStakes : number of NFTs which current user staked in
- farmCid : canister id of this Farm
- status : status of this Farm, includes: 'NOT_STARTED', 'LIVE', 'FINISHED', 'CLOSED'
- nftIds: current user's NFT list
- rewardTokenSymbol : symbol of reward token
- rewardTokenDecimals : decimals of reward token
- rewardTokenFee : fee of reward token
- creator : principal of user who created the Farm

`getNFTIds`: get all NFT ids

output:
- a list of NFT ids

`getPositionIds`: get all position ids

output:
- a list of position ids

`getDeposit`: get information of a particular staked position

input:
- NFT id

output:
- owner : owner of the staked NFT
- holder : holder of the staked NFT
- pool : canister id of the SwapPool
- initTime : the time when the NFT was staked
- nftId: id of the NFT
- positionId : id of the position
- tickLower : lower tick of the position
- tickUpper : upper tick of the position
- liquidity : liquidity amount in the position
- rewardAmount : amount of the reward token the position has earned until now
- token0Amount : roughly amount of token0 in the position
- token1Amount : roughly amount of token1 in the position
- tokenMetadata : NFT metadata

`getRewardMeta`: get global reward metadata

output:
- totalReward: total amount of reward token
- totalRewardClaimed: total claimed amount of reward token
- totalRewardUnclaimed: total amount of distributed but not be claimed reward token
- totalRewardBalance: balance of reward token
- secondPerCycle: seconds per cycle
- rewardPerCycle: reward token distributed per cycle
- currentCycleCount: number of cycles that have distributed
- totalCycleCount: total number of cycles

`getTVL`: get TVL info of this farm

output:
- stakedTokenTVL: TVL of staked tokens based on ICP price
- rewardTokenTVL: TVL of reward tokens based on ICP price