# SwapFactory

SwapFactory is a canister to create SwapPool and hold pool list mainly.

## Methods

`createPool`: create a SwapPool if necessary.

input:
- token0: { address : Text; standard : Text; }
- token1: { address : Text; standard : Text; }
- fee: rate of transaction fee (500 means 0.05%, 3000 means 0.3%, 10000 means 1%)
- sqrtPriceX96: initial price of token0 exchange token1

output: 
- key: token0.address_token1.address_fee
- token0: { address : Text; standard : Text; }
- token1: { address : Text; standard : Text; }
- fee: rate of transaction fee
- tickSpacing: tickSpacing value inside
- canisterId: canister id of the pool

`getPools`: get all pools

output:
- key: token0.address_token1.address_fee
- token0: { address : Text; standard : Text; }
- token1: { address : Text; standard : Text; }
- fee: rate of transaction fee
- tickSpacing: tickSpacing value inside
- canisterId: canister id of the pool

`getPool`: get pool by parameters

input:
- token0: { address : Text; standard : Text; }
- token1: { address : Text; standard : Text; }
- fee: rate of transaction fee (500: 0.05%, 3000: 0.3%, 10000: 1%)

output: 
- same as 'getPools'

`getRemovedPools`: get all removed pools

output:
- same as 'getPools'

`getAvailabilityState`: get availability state of SwapFactory

output:
- available: state of availability
- whiteList: a list of principals that can access the methods when the availability state is 'false'

`getAccessControlState`: get principals group by role

output:
- owners: principals with 'owner' role
- clients: principals with 'client' role