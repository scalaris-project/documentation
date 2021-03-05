title: Scalaris Superblock Proposal Viewing Guide
description: This guide explains how to view Scalaris's Superblock proposals for funding initiatives and governance management.


# View Proposals
This guide explains how to view Scalaris's [Superblock](/governance/introduction/#superblock) proposals for funding initiatives and governance management. The ability to view proposals is important for the decentralized governance model to function properly, enabling informed discussions and [voting](/governance/proposal-voting).

??? warning "Voting Requirements & Important Information"
	**2500 [SCA](/blockchain/introduction) is required in order to vote.** The [process of voting](/governance/proposal-voting) can take place from a wallet containing at least 2500 SCA, or a Service Node collateral wallet. An active [Service Node](/service-nodes/introduction) is *not* required.

	Additional important information:

	* The UTXO inputs used for the 2500 SCA (to vote) must be 100 SCA or larger.
	* If you spend or stake any of your 2500 SCA inputs after you vote, the vote is marked invalid and you will need to cast your vote(s) again (auto-revote mechanism will do all , if not - revote).
	* Since the votes are recorded on-chain, casting a vote requires you to pay a network fee. It is best practice to have a small UTXO input for each vote to pay for the network fees.
	* Your vote is not counted until the voting transaction fee has 1 confirmation (typically 1 minute), after which your votes will be accounted for when viewing the `listproposals` command.
	* If you vote again you will have to pay another network fee to do so.
	* The voting system will automatically calculate how many votes you have available according to your balance (1 vote per 2500 SCA) and cast your full vote weight when voting (4999 SCA balance = 1 vote, 49635 SCA balance = 19 votes.
	* At least 60 minutes must pass before you can change your vote(s).
	* The deadline for creating proposals is 2000 blocks prior to the Superblock.
	* Voting for proposals ends 106 blocks prior the Superblock.

Proposals should be carefully reviewed along with the amount requested. It's a good idea to consider the total Superblock budget (30,000 SCA), the other proposals amounts requested, the priorities of the project, and if the proposal aligns with those priorities and greater vision of the project. The link for each proposal should lead to a description of what the proposal is for with background information and objectives.

---



??? example "View using wallet"
	![Redesigned Wallet](/img/wallet-redesign/wallet-redesign.png)

	1. Open the [wallet](/wallet/setup) and in the side menu, go to *Proposals*. The wallet does not need to be unlocked.
	1. The Proposals screen shows all the proposals submitted to the network. Above the list of proposals there is an option to filter by *Upcoming*, which displays the proposals that can currently be voted on. Select this filter to view all proposals currently open for voting.

		![Filter Proposals](/img/wallet-redesign/proposals-filter.png)

	1. [Vote on a proposal](/governance/proposal-voting/#voting-from-the-qt-wallet).

---


## Viewing from the Terminal

??? example "Linux"
	1. Start the wallet. If it's not already running, use the following instructions to start it. 
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

	1. [Vote on a proposal](/governance/proposal-voting/#voting-from-the-terminal).


??? example "Windows"
	1. Start the wallet. If it's not already running, use the following instructions to start it. 
		1. Navigate to the `bin` folder within your Scalaris wallet installation directory (EG: `C:\Users\[YourUsername]\Downloads\scalaris\bin\`)

			??? tip "Tip: This requires the *scalaris-[version]-win64.zip* download version."
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

	1. [Vote on a proposal](/governance/proposal-voting/#voting-from-the-terminal).


??? example "MacOS"
	1. Start the wallet. If it's not already running, use the following instructions to start it. 
		1. Navigate to the `bin` folder within your Scalaris wallet installation directory (EG: `~/Downloads/scalaris/bin/`)

			??? tip "Tip: This requires the *scalaris-[version]-osx64.tar.gz* download version"
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

	1. [Vote on a proposal](/governance/proposal-voting/#voting-from-the-terminal).








<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





