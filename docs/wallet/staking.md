title: Scalaris Wallet Staking Guide
description: This guide explains how to setup your Scalaris wallet for staking to validate transactions on the network and earn block rewards.


# Staking SCA
Staking is the Proof-of-Stake equivelant of mining in Proof-of-Work blockchains. Stakers validate transactions on the network. These transactions are grouped in blocks. With [Scalaris](/project/introduction), there is 1 block every minute with a 1 [SCA](/blockchain/introduction) reward. You can stake with any amount of SCA and are rewarded for supporting the network with block rewards and all the transaction fees included in that block.

---

## Staking Guide
Staking can be performed with any amount of SCA, there is no minimum. However, since staking with Scalaris is probability-based, you will receive rewards more frequently by owning and staking more SCA. SCA can be acquired through [various options available](/project/exchanges).

Use the following guide to enable staking and start earning rewards.

??? example "Stake using the redesigned wallet"
	![Redesigned Wallet](/img/wallet-redesign/wallet-redesign.png)

	1. [Install and setup](/wallet/setup) the Scalaris wallet.
	1. Open and [sync the wallet](/wallet/syncing).
	1. Make sure there's SCA in your wallet.
	1. [Unlock the wallet for staking only](/wallet/lock-unlock/#unlock-for-staking).
	1. It may take a minute for the staking to activate. 
	1. You can verify the wallet is staking with the status icon in the upper-right corner.

		![Status Bar](/img/wallet-redesign/status-bar-synced.png)

		1. The 2nd icon from the left indicates the staking status. If it is Red, staking is inactive. If it is Green, staking is active. You can also hover over the icon to read the staking status.

			![Staking Inactive](/img/wallet-redesign/status-staking-inactive.png)
			![Staking Active](/img/wallet-redesign/status-staking-active.png)

		??? info "Note: Staking will not activate if the wallet is not synced."
			Since staking is the act of confirming the latest transactions, staking cannot be active until the wallet is synced to the more recent transaction on the network.

		??? info "Note: Newly deposited SCA can't stake for 60 minutes."
			Funds cannot stake until they have had 60 confirmation on the network. This a security precaution and will take roughly 60 minutes (1 confirmation a minute) to be eligible for staking.

	1. When staking, you may see your wallet balance show as *Immature*. This is a normal part of staking. The funds in your wallet that "won" the staking reward will remain immature until they have 101 confirmations (101 minutes). When funds are immature, they are unspendable and do not count towards your probability for receiving another reward. After 101 confirmations, these funds can be spent again and the balance will show up as normal.

--8<-- "troubleshooting.md"

---

## Staking Rewards

### Probability
The selection of the staker that confirms each block is probability-based. This means that everyone’s chance of being selected to confirm the next block is equal to the amount of SCA staking divided by the total amount of SCA being staked on the network. 

![Staking Probability](/img/wallet/staking-probability.png)

??? abstract "Example: Calculating staking reward probability."
	Assume:

	* You're staking 5000 SCA
	* There's a total of 3,325,000 SCA active staking on the network

	The probability you will earn the next reward is: 

		5000 / 3325000 = 0.0015 * 100 = 0.15%

	This means that, on average, you will earn a reward every:

		1 / 0.0015 = 665 minutes = 11.08 hours

	And the average amount of SCA rewarded per day is:

		1440 minutes a day / 665 minutes per reward * 1 SCA per reward = 2.16 SCA

	With SCA valued example at $2, that would equate to $4,32 per day and $1576,8 per year.


### ROI
Building off the probabilistic ratio above, the following equation can be derived to estimate the yearly return (in SCA) on the initial amount started with. This does not account for compounding, which would increase this value. 

> Staking ROI = ( [525600] / [total SCA staked on the network] ) * 100

* *525600 = 1 SCA reward per minute * 1440 minutes per day * 365 days per year*

??? abstract "Example: Calculating staking reward ROI."
	Assume:

	* There's a total of 3,325,000 SCA staking on the network
	* The amount you're staking is irrelevant because ROI is a per unit value

	The yearly ROI under these conditions will be:

		525600 / 3325000 = 0.158 * 100 = 15.8%

	This means that in a year, if you staked 1000 SCA the rewards would be:

		1000 * 0.158 = 158 SCA

	With SCA valued at $2, that would equate to $316 per year.

---

<!-- 
## Reward Calculator

There is a simple staking calculator at [block-node.info](https://block-node.info/blocknet_revenue1.php) built by Discord user @ishkb1 (thanks for all your work!)
 -->





<!-- 
- rewards
	- equation
	- calculator
		- how much
		- how often
-->
<!-- 
what are the cli commands to do the following on windows:
1) start wallet
2) close wallet
3) start syncing
4) get syncing status
5) encrypt wallet

-->












<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





