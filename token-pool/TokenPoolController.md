# TokenPoolController
    
    TokenPoolController is a canister for creating, maintaining and querying TokenPools.
    
## Canister
    canister ID:o5xzb-ryaaa-aaaak-aejmq-cai

## Methods

### 1、createTokenPool
     Create a TokenPool by specific parameters.
#### input:
- name: name of a TokenPool
- rewardToken : reward token
- rewardTokenDecimals : decimals of reward token
- rewardTokenSymbol : symbol of reward token
- rewardTokenFee : fee of reward token
- startTime : time to start reward
- bonusEndTime : time to end reward
- rewardPerTime : reward token amount per second
- stakingToken : token should be staked
- stakingTokenDecimals : decimals of staking token
- stakingTokenSymbol : symbol of staking token
- stakingTokenFee : fee of staking token
- BONUS_MULTIPLIER : reward coefficient, default to 1000

#### output:
- canister id of the created TokenPool


### 2、findTokenPoolPage
    get TokenPool list
#### input:
- offset: offset number
- limit: limit number
- ----- fields below are optional -----
- state: '1' means 'not started', '2' means 'living', '3' means 'finished'

#### output:
- totalElements: total number of TokenPool
- content<[TokenPoolInfo]>: list of TokenPool info
- offset: offset number
- limit: limit number

##### TokenPoolInfo:
- canisterId : TokenPool canister id
- name : TokenPool names
- createTime : creation time
- startTime : time to start reward
- bonusEndTime : time to end reward
- stakingToken : token should be staked
- stakingTokenSymbol : symbol of staking token
- stakingTokenDecimals : decimals of staking token
- stakingTokenFee : fee of staking token
- rewardToken : reward token
- rewardTokenSymbol : symbol of reward token
- rewardTokenDecimals : decimals of reward token
- rewardTokenFee : fee of reward token
- creator : creator of TokenPool
- storageCid : storage canister id
- version : version of TokenPool

### 3、getTokenPoolsGlobalData
     get TVL of all Token Pool
#### output:
- stakingAmount : TVL of staked tokens based on ICP price
- rewardAmount : TVL of reward tokens based on ICP price




    
    