# SwapNFT

SwapNFT is a canister to hold non-fungible tokens which reflect the positions in SwapPool. It is based on the EXT standard and added some business related query interfaces.

## Methods

Methods in EXT standard will not be listed.

`findTokenList`: get token list of current user

input:
- User = { #address : Text; #principal : Principal; }
- offset number
- limit number

output: 
- totalElements: total number of NFTs
- content: list of user NFT info
- offset: offset number
- limit: limit number

`findTokenListByPool`: get token list of current pool

input:
- canister id of pool
- offset number
- limit number

output: 
- totalElements: total number of NFTs
- content: list of NFT info
- offset: offset number
- limit: limit number