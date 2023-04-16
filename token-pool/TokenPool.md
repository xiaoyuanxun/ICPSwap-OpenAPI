# TokenPool

    TokenPool is a canister for users to stake their tokens and earn reward tokens by staked token amount and staked time.
    
## Methods

### 1、deposit
    Firstly, transfer tokens to user's subaccount in TokenPool. Then call 'deposit' to transfer and deposit tokens from user's subaccount in TokenPool to the TokenPool itself. For ICP/ICRC1/ICRC2 standards only.
#### output:
- success or failure message


### 2、depositFrom

    Firstly, approve specific amount of tokens to the TokenPool. Then call 'depositFrom' to transfer and deposit tokens from user to TokenPool. For DIP20/EXT standards only.
#### input:
- _amount: token amount to stake in

#### output:
- success or failure message

### 3、withdraw
    withdraw staked token

#### input:
- _amount: token amount to withdraw

#### output:
- success or failure message


### 4、harvest
    harvest all income belonging to current user
    
#### output:
- success or failure message

### 5、claim
    claim unused token belonging to current user

#### output:
- success or failure message


### 6、getPoolInfo
    get info about current TokenPool
#### output:
- rewardToken : reward token
- rewardTokenSymbol : symbol of reward token
- rewardTokenDecimals : decimals of reward token
- rewardTokenFee : fee of reward token
- bonusEndTime : time to end reward
- lastRewardTime : last reward time
- rewardPerTime : reward token amount per second
- stakingToken : token should be staked
- stakingTokenSymbol : symbol of staking token
- stakingTokenDecimals : decimals of staking token
- stakingTokenFee : fee of staking token
- BONUS_MULTIPLIER : reward coefficient, default to 1000
- totalDeposit : total amount of deposited token
- storageCid : data storage canister id
- rewardDebt : total amount of reward token

### 7、pendingReward
    get income amount which are not harvested belonging to current user
#### input:
- User = { #address : Text; #principal : Principal; }

#### output:
- success or failure message





    
    