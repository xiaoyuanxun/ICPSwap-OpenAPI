# FarmController
FarmController is a canister to create farm, hold farm list and update farm status.

`create`: create a new farm with the specified parameters
```bash
create '(Farm
        rewardToken : Types.Token,
        rewardAmount : Nat,
        rewardPool : Text,
        pool : Text,
        startTime : Nat,
        endTime : Nat,
        token0AmountLimit : Nat,
        token1AmountLimit : Nat,
        priceInsideLimit : Bool
)'
```
- rewardToken : token to be rewarded
- rewardAmount : total amount of reward token (with decimals)
- rewardPool : swap pool cid of reward token
- pool : swap pool cid of staked positions
- startTime : timestamp of start time (unit: second)
- endTime : timestamp of end time (unit: second)
- token0AmountLimit : minimum amount of staked token0, 0 means no limit
- token1AmountLimit : minimum amount of staked token1, 0 means no limit
- priceInsideLimit : whether current price needs to be within the price range of staked positions

`getFarmList`: get farm list by farm status
```bash
getFarmList '(offset : Nat, limit : Nat, status : Text)'
```
- status : "NOT_STARTED", "LIVE", "FINISHED", "CLOSED". Input "" means get all farms without closed ones

`getGlobalTVL`: get TVL of all farms
```bash
getGlobalTVL '()'
```