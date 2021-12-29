# clarity-timelocked-wallet
## Learning Clarity

GOAL: Demonstrate how blockchains can change over time. Use the block height (length of the chain) to create a contract that unlocks when an amount of time has passed.

Such a contract can be useful if you want to bestow tokens to someone after a certain time period. Imagine that in the crypto-future you want to put some money aside for when your child comes of age

The contract has the following features:

- A user can deploy the time-locked wallet contract.
- Then, the user specifies a block height at which the wallet unlocks and a beneficiary.
- Anyone, not just the contract deployer, can send tokens to the contract.
- The beneficiary can claim the tokens once the specified block height is reached.
- Additionally, the beneficiary can transfer the right to claim the wallet to a different principal. (For whatever reason.)

With the above in mind, the contract will feature the following public functions:
- lock, takes the principal, unlock height, and an initial deposit amount.
- claim, transfers the tokens to the tx-sender if and only if the unlock height has been reached and the tx-sender is equal to the beneficiary.
- bestow, allows the beneficiary to transfer the right to claim the wallet.