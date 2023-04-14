# FarmController
FarmController is a canister to create farm, hold farm list and update farm status.

## Methods

`create`: create a new farm with the specified parameters

input:
- rewardToken : token to be rewarded
- rewardAmount : total amount of reward token (with decimals)
- rewardPool : swap pool cid of reward token
- pool : swap pool cid of staked positions
- startTime : timestamp of start time (unit: second)
- endTime : timestamp of end time (unit: second)
- secondPerCycle: time interval for distributing benefits
- token0AmountLimit : minimum amount of staked token0, 0 means no limit
- token1AmountLimit : minimum amount of staked token1, 0 means no limit
- priceInsideLimit : whether current price needs to be within the price range of staked position

output:
- canister id of the created Farm

`getFarmList`: get farm list by farm status

input:
- offset number
- limit number
- status text, includes: "NOT_STARTED", "LIVE", "FINISHED", "CLOSED". "" means get all farms without closed ones

output:
- totalElements: total number of positions
- content: list of Farm info
- offset: offset number
- limit: limit number

`getGlobalTVL`: get TVL of all farms

output:
- stakedTokenTVL: TVL of staked tokens based on ICP price
- rewardTokenTVL: TVL of reward tokens based on ICP price