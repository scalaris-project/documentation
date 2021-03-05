title: Scalaris Fork Management Guide
description: This guide explains what a fork is, how to tell if you're on a fork, and what to do in order to get off the fork and onto the main chain.


# Fork Management
A fork in blockchain is similar to a fork in a road. In a perfect world, everybody running the Scalaris blockchain would have identical data and transaction history. However in the real world, technical events such as a wallet or protocol upgrade may cause a user's blockchain to start having different data after a certain point. The start of a fork is the point at which the blockchain data starts to differ. If you are the user with the different data from everyone else, then you are on a fork (forked chain).

![Fork Diagram](/img/forking/fork-diagram.png)

??? info "Note: SCA staked on a fork are not valid on the main chain."
	If you are on a fork you will likely earn many more staking rewards than usual. Many people mistaken continue to stay on the fork on purpose thinking that the SCA earned can be used on the main chain, which is incorrect. Once you get back on the main chain, there will be no record of any actions performed on a fork. In this case, being on a fork is similar to being in a parallel universe. 

---

## Check If You Are on a Fork
Use the following guide to check if you're on a fork by comparing the current block height of your wallet with the block height on the explorer.

??? example "Check using wallet"

	1. Select *Tools* from the left menu, then the *Debug Console* tab. The input field at the bottom is where you will type commands.
	1. Type `getblockcount` into the debug console and press the *Enter* or *Return* key.
		```
		getblockcount
		```
	1. The command will appear in the console window followed by a response with your current block height.
	1. Type `getblockhash <BLOCK HEIGHT>` into the debug console with `<BLOCK HEIGHT>` replaced with the block height returned in the previous step and press the *Enter* or *Return* key. Example:
		```
		getblockhash 11050942
		```
	1. The command will appear in the console window followed by a response with the hash of your current block height.
	1. Open a Scalaris blockchain explorer: [visit explorer.scalaris.info](https://explorer.scalaris.info/)
	1. Type the block height returned in step 4 into the search bar and press the *Enter* or *Return* key.
	1. The search result will return the hash of the block. Compare the returned block hash form the explorer with the block hash from your wallet returned in step 6. If the block hashed are different then you are on a fork. There is a chance that the explorer is on a fork, but this is much less likely to be the case.
	1. If you are on a fork, backup your wallet.dat file. And re-sync blockchain.

--8<-- "troubleshooting.md"

---









<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





