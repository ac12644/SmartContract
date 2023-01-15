## Contract Structure

The contract has a constructor that takes an address of a native token wrapper, it's using Initializable, ContractMetadata, PermissionsEnumerable, ERC2771ContextUpgradeable, MulticallUpgradeable, Staking20Upgradeable and ITokenStake libraries.

It has several variables such as rewardToken which is the ERC20 Reward Token address, rewardTokenBalance which is the Total amount of reward tokens in the contract.

It's using several functions such as:

- **initialize()** called only once and is responsible for initializing the contract and setting up different parameters.

- **depositRewardTokens()** allows the admin to deposit reward tokens.

- **receive()** allows the contract to receive Ether to unwrap native tokens.

It also has several events such as RewardTokensDepositedByAdmin which is emitted when the admin deposits reward tokens.
