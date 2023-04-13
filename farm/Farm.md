# Farm
Farm canister will hold at most 300 positions and distribute reward token every 10 minutes.

`stake`: transfer an NFT from user to farm and start to stake
```bash
stake '(positionId : Nat)'
```
`unstake`: transfer an NFT from farm to user and claim the reward token
```bash
unstake '(positionId : Nat)'
```
`close`: close the farm after finishing stake
```bash
close '()'
```
`getRewardInfo`: get reward infos of a group of position ids
```bash
getRewardInfo '(positionIds : [Nat])'
```
`getFarmInfo`: get total info of an user
```bash
getFarmInfo '(user : Principal)'
```
- user : if the user is FarmController, return all infos

`getUserPositionIds`: get one user's position ids
```bash
getUserPositionIds '(owner : Principal, offset : Nat, limit : Nat)'
```
- owner : positions' owner

`getPositionIds`: get all position ids
```bash
getPositionIds '()'
```
`getDeposit`: get information of a particular staked position
```bash
getDeposit '(positionId : Nat)'
```
`getRewardMeta`: get global reward meta data
```bash
getRewardMeta '()'
```
`getTVL`: get TVL info of this farm
```bash
getTVL '()'
```