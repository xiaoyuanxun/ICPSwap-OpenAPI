# BaseDataStructure

A canister of basic data collection.

```bash
canister: 4coac-ryaaa-aaaag-qblkq-cai
```

## Methods

`get`: get transaction data by user address

input:

- account: address of the user
- offset: offset of the transaction list
- limit: data limit per query

output:

- from : payer of the transaction
- to : payee of the transaction
- action : type of transaction
- token0Id : canister id of token0
- token0Standard : standard of token0
- token0Symbol : symbol of token0
- token0Decimals : decimals of token0
- token0Price : price of token1
- token1Id : canister id of token1
- token1Standard : standard of token1
- token1Symbol : symbol of token1
- token1Decimals : decimals of token1
- token1Price : price of token1
- token0Fee : fee of token0
- token1Fee : fee of token1
- liquidityTotal : total liquidity
- exchangePrice : price when exchange
- tick : tick when exchange
- token0ChangeAmount : changed amount of token0
- token1ChangeAmount : changed amount of token1
- timestamp : timestamp when transfer
- poolId : canister id of SwapPool
- poolFee : rate of transaction fee
- amountUSD : turnover based on USD
- amountToken0 : amount of transfered token0
- amountToken1 : amount of transfered token1
- ----- fields below are optional -----
- sender : payer of the transaction
- recipient : payee of the transaction
- exchangeRate : rate of exchanging
- hash : transaction hash
- liquidityChange : changed amount of liquidity

`getProtocolData`: get TVL of transaction

output:

- volumeUSD: TVL of transaction
- feesUSD: TVL of transaction fee
- feesUSDChange: changed amount of fee in last 24H
- tvlUSD: TVL of transaction based on USD
- txCount: number of transaction actions
- volumeUSDChange: changed amount of transaction in last 24H
- tvlUSDChange: changed amount of transaction in last 24H based on USD
