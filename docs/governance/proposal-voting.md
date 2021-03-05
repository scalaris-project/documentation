title: Scalaris Superblock Proposal Voting Guide
description: This guide explains how to vote on Scalaris's Superblock proposals for funding initiatives and governance management with a Service Node.


# Proposal Voting
This guide explains how to vote on Scalaris's [Superblock](/governance/introduction/#superblock) proposals for funding initiatives and governance management. Voting on proposals is important for the decentralized governance model to function properly.

???+ warning "Voting Requirements & Important Information"
	**2500 [SCA](/blockchain/introduction) is required in order to vote.** The process of voting can take place from a wallet containing at least 2500 SCA, or a Service Node collateral wallet. An active [Service Node](/service-nodes/introduction) is *not* required.

	* **Voting for proposals ends 106 blocks prior the Superblock.** It'd be safer to make sure you vote no later than 107 blocks before the Superblock to make sure your voting transaction gets at least 1 confirmation.
	* The inputs (UTXOs) used for the 2500 SCA (to vote) must be 100 SCA or larger.
	* The inputs used for the 2500 SCA must be in the same address.
	* Since the votes are recorded on-chain, casting a vote requires you to pay a network fee. This requires *each address* to have an input *separate* from the inputs used for the 2500 SCA to pay for the network fees. **This input used for the fee cannot be immature**. Funds will remain immature for about 60 minutes (60 blocks) after they staked.
	* If you are staking, your vote will automatically re-cast.
	* Your vote is not counted until the voting transaction fee has 1 confirmation (typically 1 minute), after which your votes will be accounted for when viewing the `listproposals` command.
	* If you vote again you will have to pay another network fee to do so.
	* The voting system will automatically calculate how many votes you have available according to your balance (1 vote per 2500 SCA) and cast your full vote weight when voting (4999 SCA balance = 1 vote, 49635 SCA balance = 19 votes.
	* The deadline for creating proposals is 2000 blocks prior to the Superblock.

??? info "Examples Of Valid Input Setups"

	1. Counts as 1 single vote:
		* Address A
			* Inputs: 1250, 1250, 1 (tx fee input)
			* Total: 5000 + 1 (tx fee input)
	1. Counts as 1 single vote:
		* Address A
			* Inputs: 500, 500, 500, 500, 500, 1 (tx fee input)
			* Total: 2500 + 1 (tx fee input)
	1. Counts as 1 single vote wth excess (inefficient):
		* Address A
			* Inputs: 1000, 1250, 1250, 1 (tx fee input)
			* Total: 3500 + 1 (tx fee input)
		* Address B
			* Inputs: 1500 + 1 (tx fee input)
			* Total: 1500 + 1 (tx fee input)
	1. Counts as 1 vote (inefficient):
		* Address A
			* Inputs: 1000, 1000, 500, 1 (tx fee input)
			* Total: 2500 + 1 (tx fee input)
		* Address B
			* Inputs: 2000, 500
			* Total: 2500 (no tx fee input)
	1. Counts as 2 votes:
		* Address A
			* Inputs: 1000, 1000, 1500, 1500, 1 (tx fee input)
			* Total: 5000 + 1 (tx fee input)
	1. Counts as 3 votes with excess (inefficient):
		* Address A
			* Inputs: 2500, 2000, 1000, 500, 1 (tx fee input)
			* Total: 6000 + 1 (tx fee input)
		* Address B
			* Inputs: 1000, 1000, 500, 1000, 1 (tx fee input)
			* Total: 3500 + 1 (tx fee input)

??? info "Examples Of Invalid Input Setups"

	1. Not at least 2500 SCA:
		* Address A
			* Inputs: 1250, 1200, 1 (tx fee input)
			* Total: 2450 + 1 (tx fee input)
	1. Not enought to cover fee:
		* Address A
			* Inputs: 1250, 1250
			* Total: 2500
	1. Fee is not a separate input:
		* Address A
			* Inputs: 1251, 1250
			* Total: 2501
	1. 2500 SCA not in a single address:
		* Address A
			* Inputs: 2000, 1 (tx fee input)
			* Total: 2000 + 1 (tx fee input)
		* Address B
			* Inputs: 500, 1 (tx fee input)
			* Total: 500 + 1 (tx fee input)

Proposals should be carefully reviewed along with the amount requested. It's a good idea to consider the total Superblock budget (30,000 SCA), the other proposals amounts requested, the priorities of the project, and if the proposal aligns with those priorities and greater vision of the project. The link for each proposal should lead to a description of what the proposal is for with background information and objectives. See [how to view proposals](/governance/view-proposals).

---

## Voting from the Qt Wallet
--8<-- "wallet-comparison.md"


??? example "Vote using the redesigned wallet"
	![Redesigned Wallet](/img/wallet-redesign/wallet-redesign.png)

	1. Open the [wallet](/wallet/setup) and in the side menu, go to *Proposals*. The wallet needs to be unlocked to cast votes.
	1. The Proposals screen shows all the proposals submitted to the network. Above the list of proposals there is an option to filter by *Upcoming*, which displays the proposals that can currently be voted on. Select this filter to view all proposals currently open for voting.

		![Filter Proposals](/img/wallet-redesign/proposals-filter.png)

	1. **Review the proposals and the amount requested.** It's a good idea to consider the total Superblock budget, the other proposals amounts requested, the priorities of the project, and if the proposal aligns with those priorities and greater vision of the project. The link for each proposal should lead to a description of what the proposal is for with some background information and objectives.
	1. The voting system will automatically calculate how many votes you have available according to your balance (1 vote per 2500 SCA) and cast your full vote weight when voting (4999 SCA balance = 1 vote, 49635 SCA balance = 19 votes.
	1. When ready to vote on a proposal, select the *Vote* button. A popup will appear that will be used to vote from. Select whether you'd like to approve the proposal (*Yes*) or vote against the proposal (*No*). After you have selected how you wish to vote, select the *Vote* button. This registers your vote to the network after the vote transaction has 1 confirmation (about 1 minute).
	1. Once you have voted you can change your vote by selecting the *Cast Votes* button and selecting you new vote. 

	--8<-- "complete-proposal-voting.md"

---


## Voting from the Terminal

??? example "Linux"
	1. Start the [wallet](/wallet/setup). If it's not already running, use the following instructions to start it. 
		1. Navigate to the `bin` folder within your Scalaris wallet installation directory (EG: `~/scalaris/bin/`)
		1. Type in the following command, replacing `[USERNAME]` and `[PASSWORD]` with the respective `rpcuser=` and `rpcpassword=` values from your `scalaris.infonf` file located in your `~/.scalaris/` directory.

				./scalarisd -rpcuser=[USERNAME] -rpcpassword=[PASSWORD] -daemon

			*Example:*

				./scalarisd -rpcuser=JohnScalaris -rpcpassword=supersecretpassword -daemon

	1. The wallet process will begin in the current terminal window. You will need to open a new terminal window or tab and navigate to the same location before continuing.
	1. If your wallet was just started, you may need to wait a few minutes for the proposals to sync, otherwise you may not see the full list of proposals. Use the following command to view the proposals:

			./scalaris-cli listproposals

	1. To view proposals since a specific block:

			./scalaris-cli listproposals [BLOCK_NUMBER]

		*Example:*

			./scalaris-cli listproposals 1209600

	1. **Review the proposals and the amount requested.** It's a good idea to consider the total Superblock budget, the other proposals amounts requested, the priorities of the project, and if the proposal aligns with those priorities and greater vision of the project. The link for each proposal should lead to a description of what the proposal is for with some background information and objectives.
	1. The voting system will automatically calculate how many votes you have available according to your balance (1 vote per 2500 SCA) and cast your full vote weight when voting (4999 SCA balance = 1 vote, 49635 SCA balance = 19 votes.
	1. Vote for the proposal using the following command, replacing the variable with the respective values:

			./scalaris-cli vote [PROPOSAL_HASH] [VOTE]

		* `PROPOSAL_HASH`:  The hash listed for the proposal you are voting for
		* `VOTE`:  Your vote (‘yes’ or ‘no’). `yes` means you'd like to vote to fund the proposal and `no` means you'd like to vote against the proposal so it isn't funded.

		*Example:*

			./scalaris-cli vote 06a50c125aa305fbe38fa0fe9a1b39db1b1318838aadaec55f95c7a52101d83f yes

	1. Press the *Enter* key to submit the command and register your vote to the network.
	--8<-- "complete-proposal-voting.md"


??? example "Windows"
	1. Start the [wallet](/wallet/setup). If it's not already running, use the following instructions to start it. 
		1. Navigate to the `bin` folder within your Scalaris wallet installation directory (EG: `C:\Users\[YourUsername]\Downloads\scalaris\bin\`)

			??? tip "Tip: This requires the *scalaris-[version]-win64.zip* download version"
				To interact with the wallet via the command line, the `scalaris-[version]-win64.zip` wallet version is needed.

		1. Type in the following command, replacing `[USERNAME]` and `[PASSWORD]` with the respective `rpcuser=` and `rpcpassword=` values from your `scalaris.infonf` file located in the `C:\Users\[YourUsername]\AppData\Roaming\Scalaris` directory. This directory can be found by opening the file explorer and pasting in `%appdata%\Roaming\Scalaris\` into the file explorer path field.

				scalarisd -rpcuser=[USERNAME] -rpcpassword=[PASSWORD]

			*Example:*

				scalarisd -rpcuser=JohnScalaris -rpcpassword=supersecretpassword

	1. The wallet process will begin in the current terminal window. You will need to open a new terminal window or tab and navigate to the same location before continuing.
	1. If your wallet was just started, you may need to wait a few minutes for the proposals to sync, otherwise you may not see the full list of proposals. Use the following command to view the proposals:

			./scalaris-cli listproposals

	1. To view proposals since a specific block:

			./scalaris-cli listproposals [BLOCK_NUMBER]

		*Example:*

			./scalaris-cli listproposals 1209600

	1. **Review the proposals and the amount requested.** It's a good idea to consider the total Superblock budget, the other proposals amounts requested, the priorities of the project, and if the proposal aligns with those priorities and greater vision of the project. The link for each proposal should lead to a description of what the proposal is for with some background information and objectives.
	1. The voting system will automatically calculate how many votes you have available according to your balance (1 vote per 2500 SCA) and cast your full vote weight when voting (4999 SCA balance = 1 vote, 49635 SCA balance = 19 votes.
	1. Vote for the proposal using the following command, replacing the variable with the respective values:

			./scalaris-cli vote [PROPOSAL_HASH] [VOTE]

		* `PROPOSAL_HASH`:  The hash listed for the proposal you are voting for
		* `VOTE`:  Your vote (‘yes’ or ‘no’). `yes` means you'd like to vote to fund the proposal and `no` means you'd like to vote against the proposal so it isn't funded.

		*Example:*

			./scalaris-cli vote 06a50c125aa305fbe38fa0fe9a1b39db1b1318838aadaec55f95c7a52101d83f yes

	1. Press the *Enter* key to submit the command and register your vote to the network.
	--8<-- "complete-proposal-voting.md"


??? example "MacOS"
	1. Start the [wallet](/wallet/setup). If it's not already running, use the following instructions to start it. 
		1. Navigate to the `bin` folder within your Scalaris wallet installation directory (EG: `~/Downloads/scalaris/bin/`)

			??? tip "Tip: This requires the *scalaris-[version]-osx64.tar.gz* download version."
				To interact with the wallet via the command line, the `scalaris-[version]-osx64.tar.gz` wallet version is needed.

		1. Type in the following command, replacing `[USERNAME]` and `[PASSWORD]` with the respective `rpcuser=` and `rpcpassword=` values from your `scalaris.infonf` file located in your `~/Library/Application Support/Scalaris/` directory. This directory can be found by opening the Finder, in the program menu selecting *Go* > *Go to Folder*, entering `~/Library/Application Support/Scalaris/` in the path, and pressing *Enter*.

				./scalarisd -rpcuser=[USERNAME] -rpcpassword=[PASSWORD] -daemon

			*Example:*

				./scalarisd -rpcuser=JohnScalaris -rpcpassword=supersecretpassword -daemon

	1. The wallet process will begin in the current terminal window. You will need to open a new terminal window or tab and navigate to the same location before continuing.
	1. If your wallet was just started, you may need to wait a few minutes for the proposals to sync, otherwise you may not see the full list of proposals. Use the following command to view the proposals:

			./scalaris-cli listproposals

	1. To view proposals since a specific block:

			./scalaris-cli listproposals [BLOCK_NUMBER]

		*Example:*

			./scalaris-cli listproposals 1209600

	1. **Review the proposals and the amount requested.** It's a good idea to consider the total Superblock budget, the other proposals amounts requested, the priorities of the project, and if the proposal aligns with those priorities and greater vision of the project. The link for each proposal should lead to a description of what the proposal is for with some background information and objectives.
	1. The voting system will automatically calculate how many votes you have available according to your balance (1 vote per 2500 SCA) and cast your full vote weight when voting (4999 SCA balance = 1 vote, 49635 SCA balance = 19 votes.
	1. Vote for the proposal using the following command, replacing the variable with the respective values:

			./scalaris-cli vote [PROPOSAL_HASH] [VOTE]

		* `PROPOSAL_HASH`:  The hash listed for the proposal you are voting for
		* `VOTE`:  Your vote (‘yes’ or ‘no’). `yes` means you'd like to vote to fund the proposal and `no` means you'd like to vote against the proposal so it isn't funded.

		*Example:*

			./scalaris-cli vote 06a50c125aa305fbe38fa0fe9a1b39db1b1318838aadaec55f95c7a52101d83f yes

	1. Press the *Enter* key to submit the command and register your vote to the network.
	--8<-- "complete-proposal-voting.md"











<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinkks = [];
</script>

--8<-- "extras.md"





