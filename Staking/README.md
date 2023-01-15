# StakingToken Contract

The StakingToken contract is an ERC20 token contract that allows users to stake their tokens in order to earn rewards. It also allows users to delegate their staked tokens to another address, and provides functions for distributing rewards and unlocking staked balances.

## Properties

- stakedBalance: a mapping from user addresses to their staked balance
- delegate: a mapping from user addresses to their delegate
- unlockBlock: a mapping from user addresses to the block number at which their staked balance will be unlocked
- stakers: an array of users that are currently staking
- rewardRate: the current reward rate
- paused: a flag to indicate whether the contract is paused
- owner: the address of the contract owner

## Functions

### ERC20 Functions

The StakingToken contract implements the following ERC20 functions:

- totalSupply: returns the total supply of the token
- balanceOf: returns the balance of the specified account
- transfer: transfers the specified amount of tokens from the caller's balance to the recipient's balance
- approve: allows the specified spender to transfer tokens from the caller's balance on the caller's behalf

### Staking Functions

The StakingToken contract also has the following staking-related functions:

- stake: allows the caller to stake a specified amount of tokens
- unstake: allows the caller to unstake a specified amount of tokens
- delegate: allows the caller to delegate their staked tokens to another address
- undelegate: allows the caller to undelegate their staked tokens and take back control

### Reward Distribution Function

- distributeRewards: distributes rewards to all stakers in proportion to their staked balance

### Administration Functions

- pause: allows the owner to pause the contract, preventing any new stakings or unstakings from being processed
- unpause: allows the owner to unpause the contract, allowing new stakings and unstakings to be processed

### Events

The StakingToken contract emits the following events:

- Staked: emitted when a user stakes tokens
- Unstaked: emitted when a user unstakes tokens
- Delegated: emitted when a user delegates their staked tokens to another address
- Undelegated: emitted when a user undelegates their staked tokens
- RewardsDistributed: emitted when rewards are distributed to stakers
