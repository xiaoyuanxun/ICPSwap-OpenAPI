# SwapFactory

SwapFactory is a canister to create SwapPool and hold pool list mainly.

## Methods

`getPools`: get all pools

output parameters:
- key: token0.address_token1.address_fee
- token0: { address : Text; standard : Text; }
- token1: { address : Text; standard : Text; }
- fee: rate of transaction fee
- tickSpacing: tickSpacing value inside
- canisterId: canister id of the pool

`getPool`: get pool by parameters

input parameters:
- token0: { address : Text; standard : Text; }
- token1: { address : Text; standard : Text; }
- fee: rate of transaction fee (500: 0.05%, 3000: 0.3%, 10000: 1%)

output parameters: 
- same as 'getPools'

`getRemovedPools`: get all removed pools

output parameters:
- same as 'getPools'

`getAvailabilityState`: get availability state of SwapFactory

output parameters:
- available: state of availability
- whiteList: a list of principals that can access the methods when the availability state is 'false'

`getAccessControlState`: get principals group by role

output parameters:
- owners: principals with 'owner' role
- clients: principals with 'client' role