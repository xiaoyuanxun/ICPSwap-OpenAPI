# Tokens

A canister for collecting statistical data about Tokens.

```bash
canister: zl3xd-7iaaa-aaaan-qa35q-cai
```

## Methods

`getAllToken`: get a list of data of tokens

output:

- id: index of data
- totalVolumeUSD: total transaction volume based on USD
- name: token name
- priceUSDChangeWeek: price changed based on USD in 7D
- volumeUSD: transaction volume based on USD in 24H
- feesUSD: fee based on USD
- priceUSDChange: price changed based on USD in 24H
- tvlUSD: TVL based on USD
- address: token canister id
- volumeUSDWeek: transaction volume based on USD in 7D
- txCount: number of transaction actions
- priceUSD: price based on USD
- volumeUSDChange: volume changed based on USD in 24H
- tvlUSDChange: TVL changed based on USD
- standard: token standard
- tvlToken: total TVL
- symbol: token symbol

`getToken`: get token data by token canister id

input:

- canister id of the token

output:

- same as 'getAllToken'

`getTokenTransactions`: get transaction data by token canister id

input:

- id: canister of token id
- offset: offset of the transaction list
- limit: data limit per query

output:

- same as 'BaseDataStructure.get'

`getPoolsForToken`: get SwapPools by token canister id

input:

- id: canister of token id

output:

- fee: rate of transaction fee
- token0Id: canister id of token0
- token1Id: canister id of token1
- pool: canister id of pool
- token1Price: price of token1
- token1Decimals: decimals of token1
- token0Symbol: symbol of token0
- token0Decimals: decimals of token0
- token0Price: price of token0
- token1Symbol: symbol of token1

`getTokenChartData`: get chart data by token canister id

input:

- id: canister of token id
- offset: offset of the transaction list
- limit: data limit per query

output: 

- id : data id
- volumeUSD : transaction volume based on USD in 24H
- tvlUSD : TVL based on USD
- timestamp : timestamp of data
- txCount : number of transaction actions

`getTokenPricesData`: get chart data about price by token canister id

input:

- id: canister of token id
- startTimestamp: start timestamp
- interval: interval
- limit: data limit per query

output:

- id: data id
- low: lower price
- high: upper price
- close: closing price
- open: opening price
- timestamp: timestamp
