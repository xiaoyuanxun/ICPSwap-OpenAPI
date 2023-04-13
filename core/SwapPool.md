# SwapPool

SwapPool is the most important canister in the whole business process. Each SwapPool is a canister with a specific token transaction pair to hold users' positions and do swap operations.

## Operations

### Mint
...
### Increase liquidity
...
### Decrease liquidity
...
### Claim
...
### Swap
...

## Methods

`deposit`: deposit token from current user's subaccount in pool to the current pool, for ICP/ICRC1/ICRC2 standards

input parameters:
- token: canister id of the token
- amount: token amount to be deposited

output parameters: 
- deposited token amount

`depositFrom`: deposit token from current user to pool, for DIP20/DIP20-WICP/DIP20-XTC/EXT standards

input parameters:
- token: canister id of the token
- amount: token amount to be deposited

output parameters: 
- deposited token amount

`withdraw`: withdraw token from pool to current user

input parameters:
- token: canister id of the token
- amount: token amount to be deposited

output parameters: 
- withdrawed token amount

`mint`: mint a position

Mint work flow:

ICP/ICRC1/ICRC2: transfer token -> deposit -> mint

DIP20-WICP/DIP20-XTC/EXT: depositFrom -> mint

input parameters:
- token0: canister id of token0
- token1: canister id of token1
- fee: rate of transaction fee
- tickLower: tick corresponding to the lowest price
- tickUpper: tick corresponding to the highest price
- amount0Desired: amount of token0 expected to be minted
- amount1Desired: amount of token1 expected to be minted
- amount0Min: minimum amount of token0 expected to be minted, not currently used
- amount1Min: minimum amount of token1 expected to be minted, not currently used
- operator: principal of current user

output parameters: 
- position id

`increaseLiquidity`: increase liquidity into a position

Increase work flow:

ICP/ICRC1/ICRC2: transfer token -> deposit -> increaseLiquidity

DIP20-WICP/DIP20-XTC/EXT: depositFrom -> increaseLiquidity

input parameters:
- positionId: id of the position
- amount0Desired: amount of token0 to be increased
- amount1Desired: amount of token1 to be increased
- amount0Min: minimum amount of token0 expected to be increased, not currently used
- amount1Min: minimum amount of token1 expected to be increased, not currently used
- operator: principal of current user

output parameters: 
- position id

`decreaseLiquidity`: decrease liquidity from a position

Decrease work flow:

ICP/ICRC1/ICRC2: decreaseLiquidity -> withdraw

DIP20-WICP/DIP20-XTC/EXT: decreaseLiquidity -> withdraw

input parameters:
- positionId: id of the position
- liquidity: amount of liquidity to be decreased
- amount0Min: minimum amount of token0 expected to be collected, not currently used
- amount1Min: minimum amount of token1 expected to be collected, not currently used
- operator: principal of current user

output parameters: 
- amount0: amount of collected token0
- amount1: amount of collected token1

`claim`: claim incomes of the position

Claim work flow:

ICP/ICRC1/ICRC2: claim -> withdraw

DIP20-WICP/DIP20-XTC/EXT: claim -> withdraw

input parameters:
- positionId: id of the position
- operator: principal of current user

output parameters: 
- amount0: income amount of token0
- amount1: income amount of token1

`swap`: swap token0 to token1 or swap token1 to token0

Swap work flow:

ICP/ICRC1/ICRC2: transfer token -> deposit -> swap -> withdraw

DIP20-WICP/DIP20-XTC/EXT: depositFrom -> swap -> withdraw

input parameters:
- operator: principal of current user
- zeroForOne: if token0 swap to token1, true or false
- amountIn: input token amount
- amountOutMinimum: minimum amount of token expected to be swapped

output parameters: 
- swap result

`quote`: precomputation of swap

input parameters:
- operator: principal of current user
- zeroForOne: if token0 swap to token1, true or false
- amountIn: input token amount
- amountOutMinimum: minimum amount of token expected to be swapped

output parameters: 
- precomputation result

`allTokenBalance`: get all unused balances and their holders

output parameters: 
- user principal
- balance0: balance of token0
- balance1: balance of token1

`batchRefreshIncome`: refresh the benefits of a group of positions by ids

input parameters:
- a list of position id

output parameters: 
- totalTokensOwed0: total token0 benefit of the position id list
- totalTokensOwed1: total token1 benefit of the position id list
- tokenIncome: detailed benefit information of each position id. 
    - position id
    - tokensOwed0: token0 benefit of current position id
    - tokensOwed1: token1 benefit of current position id

`getAccessControlState`: get principals group by role

output parameters:
- owners: principals with 'owner' role
- admins: principals with 'admins' role
- clients: principals with 'client' role

`getAvailabilityState`: get availability state of SwapFactory

output parameters:
- available: state of availability
- whiteList: a list of principals that can access the methods when the availability state is 'false'

`getConfigCids`: get some dependent canister ids

output parameters: 
- nftCid: canister id of SwapNFT
- infoCid: canister id of data collector
- ticketCid: canister id of ticket
- scheduleCid: canister id of timing scheduler

`getCycleInfo`: get cycle information of current pool

output parameters: 
- balance: balance number of cycles
- available: available number of cycles

`getPosition`: get position information by args

input parameters:
- tickLower: lower tick
- tickUpper: upper tick

output parameters: 
- liquidity: liquidity amount
- feeGrowthInside0LastX128: token0 fee amount growth inside
- feeGrowthInside1LastX128: token1 fee amount growth inside
- tokensOwed0: income amount of token0
- tokensOwed1: income amount of token1

`getPositions`: get position list by page

input parameters:
- offset number
- limit number

output parameters: 
- totalElements: total number of positions
- content: list of position info
- offset: offset number
- limit: limit number

`getTickInfos`: get tick list by page

input parameters:
- offset number
- limit number

output parameters: 
- totalElements: total number of positions
- content: list of tick info
- offset: offset number
- limit: limit number

`getTokenAmountState`: get token amounts

output parameters: 
- token0Amount: token0 amount in the pool
- token1Amount: token1 amount in the pool
- swapFee0Repurchase: repurchase fee of token0
- swapFee1Repurchase: repurchase fee of token1

`getTokenBalance`: get token balances of the pool

output parameters: 
- token0: token0 amount in the pool
- token1: token1 amount in the pool

`getTokenMeta`: get token meta of the pool

output parameters: 
- token0: meta of token0
- token1: meta of token1

`getUserPosition`: get user position by id

input parameters:
- position id

output parameters: 
- tickLower: tick lower
- tickUpper: tick upper
- liquidity: liquidity amount
- feeGrowthInside0LastX128: token0 fee amount growth inside
- feeGrowthInside1LastX128: token1 fee amount growth inside
- tokensOwed0: income amount of token0
- tokensOwed1: income amount of token0

`getUserPositionWithTokenAmount`: get user position by id (compute liquidity amount to token amount)

input parameters:
- offset number
- limit number

output parameters: 
- totalElements: total number of positions
- content: list of tick info
- offset: offset number
- limit: limit number

`getUserPositions`: get user position list by page

input parameters:
- offset number
- limit number

output parameters: 
- totalElements: total number of positions
- content: list of user position info
- offset: offset number
- limit: limit number

`getUserUnusedBalance`: get current user's unused balance

input parameters:
- principal of user

output parameters: 
- balance0: unused balance of token0
- balance1: unused balance of token1

`metadata`: metadata of the pool

output parameters: 
- key: pool key
- token0: { address : Text; standard : Text; }
- token1: { address : Text; standard : Text; }
- fee: rate of transaction fee
- tick: current tick in pool
- liquidity: total liquidity amount
- sqrtPriceX96: current sqrt price
- maxLiquidityPerTick: max liquidity per tick
- feeGrowthGlobal0X128: token0 fee amount growth
- feeGrowthGlobal1X128: token1 fee amount growth

`refreshIncome`: refresh income by position id

input parameters:
- position id

output parameters: 
- tokensOwed0: income amount of token0
- tokensOwed1: income amount of token1