title: Scalaris Service Node Setup Guide
description: This guide explains step-by-step how to setup a Service Node, which earns block rewards and 100% of fees from Scalaris's services (XBridge, XRouter, XCloud).


# Service Node Setup
This guide explains step-by-step how to setup a [Service Node](/service-nodes/introduction). Operating a Service Node requires 2500 SCA collateral. This 2500 SCA collateral will still be in your wallet and in your control, but must not be moved or spent in order for the Service Node to remain valid and active. However, you may still use this collateral to participate in staking.

Operating as a Service Node requires two computers:

* __Collateral Computer__ - The computer will contain the 2500 SCA collateral and does *NOT* need to remain on with the wallet open unless the 2500 SCA is being staked or you are [voting on a proposal](/governane/proposal-voting).
* __SNode Server Computer__ - This computer will act as the Service Node and must remain on with the wallet open.

To setup your Service Node, complete the following guides in order:

1. [Collateral Computer Setup](/service-nodes/setup/#collateral-computer-setup)
1. [SNode Server Computer Setup](/service-nodes/setup/#snode-server-computer-setup)
1. [Additional Setup](/service-nodes/setup/#additional-configuration)
1. [Service Node Deployment](/service-nodes/setup/#service-node-deployment)

---

## Collateral Computer Setup

??? example "Setup using wallet"
	![Redesign Wallet](/img/service-nodes/redesign-wallet.png)

	1. [Install the Scalaris wallet](/wallet/installation).
	1. [Fully sync the wallet](/wallet/syncing).
	1. [Encrypt the wallet](/wallet/encrypting).

		!!! info "Note"
			If your SCA funds are located on a different wallet, you will need to first send the 2500 SCA to this collateral Scalaris wallet. Make sure to include a little extra (1 SCA) to have enough to cover transaction fees when continuing this step.

	1. Select *Tools* from the left menu, then the *Debug Console* tab. The input field at the bottom is where you will type commands.
	1. Create a new public address for the Service Node. A unique name for this address will need to be provided as an alias. To do this, type `getnewaddress [ALIAS]` into the debug console with `[ALIAS]` replaced with the alias you will be using for this address. Example:
		```
		getnewaddress snode1
		```

		![Create Address](/img/service-nodes/redesign-getnewaddress-command.png)

	1. Press the *Enter* or *Return* key. The command will appear in the console window followed by a response with the created address.

		![Address](/img/service-nodes/redesign-getnewaddress-response.png)

	1. Retrieve your private key for the newly created address for backup purposes. Type `dumpprivkey [ADDRESS]` using the new address and press the *Enter* or *Return* key. Example:
		```
		dumpprivkey SZ6CHFUomGnuZxm18EQUvTstxxujJZbk1Q
		```

		--8<-- "privkey-warning.md"

	1. Create the input(s) needed for the Service Node collateral using the following command structure (**Note:** If you already have your inputs created for your Service Node(s) you can skip this step *and* the next step):
		```
		servicenodecreateinputs [NODE_ADDRESS] [NODE_COUNT] [INPUT_SIZE]
		```

		* `NODE_ADDRESS` = The address returned in the previous step.
		* `NODE_COUNT` = The number of Service Nodes to create. 

			* Requires a minimum of 2501 SCA per Service Node (1 SCA extra for transaction fee).
			* If left blank, it defaults to `1`.
			* Example: 10,001 SCA will be needed to create 4 Service Nodes

		* `INPUT_SIZE` = The amount of SCA for each collateral input. 

			* Must be >= `500` and <= `2500`.
			* If left blank, it defaults to `500`.
			* Example: `1250` will create 2 inputs of 1250 SCA each per Service Node

	1. Type the above command replacing the variables with the respective values in place. See examples below:

		* Single Service Node: `servicenodecreateinputs SZ6CHFUomGnuZxm18EQUvTstxxujJZbk1Q`
		* Single Service Node (2 inputs): `servicenodecreateinputs SZ6CHFUomGnuZxm18EQUvTstxxujJZbk1Q 1 1250`
		* Multiple Service Nodes (5k SCA): `servicenodecreateinputs SZ6CHFUomGnuZxm18EQUvTstxxujJZbk1Q 2 2500`

		![Create Inputs](/img/service-nodes/redesign-servicenodecreateinputs-response.png)

	1. Create a `servicenode.conf` configuration file. Type `servicenodesetup [NODE_ADDRESS] [ALIAS]`. An entry will be created in the `servicenode.conf` for the Service Node(s). Example:
		```
		servicenodesetup SZ6CHFUomGnuZxm18EQUvTstxxujJZbk1Q snode01
		```

		![Config Setup](/img/service-nodes/redesign-servicenodesetup-response.png)

	1. Export the `servicenode.conf` configuration file. Type `servicenodeexport [ALIAS] [ENCRYPTION_PASSWORD]`. The password is used to encrypt the export data. Example:
		```
		servicenodeexport snode01 supersecretpassword
		```

		![Config Setup](/img/service-nodes/redesign-servicenodeexport-response.png)

	1. Copy this output hash for later use.
	1. Restart the Scalaris wallet.
	1. Continue on to [SNode Server Computer Setup](/service-nodes/setup/#snode-server-computer-setup).


---

## SNode Server Computer Setup

??? example "Setup using wallet"
	![Redesign Wallet](/img/service-nodes/redesign-wallet.png)

	1. [Install the Scalaris wallet](/wallet/installation).
	1. [Fully sync the wallet](/wallet/syncing). Encryption is not needed on this wallet since it will not be holding funds.

	--8<-- "data-directories-1.md"

	1. Open the `scalaris.conf` configuration file.
	1. A file will be opened with your default text editor. Add the following information on new lines:
		```
		server=1
		listen=1
		rpcuser=
		rpcpassword=
		rpcallowip=127.0.0.1
		port=42500
		rpcport=42510
		txindex=1

		enableexchange=1
		servicenode=1
		rpcthreads=8
		```
	1. Enter a username and password for `rpcuser=` and `rpcpassword=`. These should be difficult and secure credentials.
	1. Here the SNode Computer wallet is used to connect to the Scalaris blockchain with the `rpcallowip=127.0.0.1` setting (localhost). If you would like to setup a different computer to host the Scalaris blockchain, update the `rpcallowip=` setting to the IP of that computer.
	1. For best performance, a `maxconnections=` setting should **NOT** be specified.
	1. Save and close the `scalaris.conf` file.
	1. Open the `xbridge.conf` configuration file (also in the Scalaris data directory).
	1. A file will be opened with your default text editor. Add the following information on new lines:
		```
		[Main]
		ExchangeWallets=SCA
		FullLog=true
		LogPath=
		ExchangeTax=300

		[SCA]
		Title=Scalaris
		Ip=127.0.0.1
		Username=
		Password=
		Port=42510
		AddressPrefix=63
		ScriptPrefix=23
		SecretPrefix=154
		COIN=100000000
		MinimumAmount=0
		TxVersion=1
		DustAmount=0
		CreateTxMethod=BTC
		GetNewKeySupported=true
		ImportWithNoScanSupported=true
		MinTxFee=10000
		BlockTime=60
		FeePerByte=20
		Confirmations=0
		Address=
		TxWithTimeField=false
		LockCoinsSupported=false
		JSONVersion=
		ContentType=
		```
	1. Set `Username=` to the same value as `rpcuser=` from your `scalaris.conf`.
	1. Set `Password=` to the same value as `rpcpassword=` from your `scalaris.conf`.
	1. Set `Ip=` to the same value as `rpcallowip=` from your `scalaris.conf`.
	1. Save and close the `xbridge.conf` file.
	1. Select *Tools* from the left menu, then the *Debug Console* tab. The input field at the bottom is where you will type commands.
	1. Import the `servicenode.conf` configuration file. Type `servicenodeimport [EXPORTED_HASH] [ENCRYPTION_PASSWORD]` with `[ENCRYPTION_PASSWORD]` replaced with the encryption password used to export your *servicenode.conf* on your collateral computer and `[EXPORTED_HASH]` replaced with the hash that was returned in that response. Example:
		```
		servicenodeimport 0554a26adbfbb710bc7fde6c66cd9e07cd4ed84d2fb6121ccc3036255912ee7e1bfd7b88e4d586f64a81edd4406403bbaa3179b241a98d9f7ee93e7a4d10db5896311496ee2fee1f3c7aa832e0827bf81e66274f7617c19c3cd6a4846b2ac674da3cf2fa1a63baf75ca6036ad644d2ab532e6a93ec31866d1c06fca0018336f40716fce3f875768da3a9b694e1f0cbf7201c9f150b76204431ea1560f24cf858 supersecretpassword
		```

		![Config Setup](/img/service-nodes/redesign-servicenodeimport-response.png)

	1. You should receive a `true` response, which means a `servicenode.conf` file was automatically created and saved.
	1. Restart the Scalaris wallet.

---

## Additional Configuration
At this point you have completed the basic setup for a Service Node. The Service Node can operate but will not be supporting any service. Now what you need to do is setup the Service Node to support services on the network where 100% of fees are distributed to Service Nodes:

* With [XBridge](/protocol/xbridge/introduction), the decentralized exchange component of the Blocknet Protocol, 100% of [trading fees](/protocol/xbridge/fees) are distributed to Service Nodes for hosting full blockchain nodes and providing verification checks for trustless exchange between digital assets. For setup, see the [XBridge Configuration Guide](/service-nodes/xbridge-configuration).
* With [XRouter](/protocol/xrouter/introduction)\*\*, the decentralized inter-chain communication component of the Blocknet Protocol, 100% of fees are paid to Service Nodes for hosting full blockchain nodes that support SPV calls. For setup, see the [XRouter Configuration Guide](/service-nodes/xrouter-configuration).
* With [XCloud](/protocol/xcloud/introduction)\*\*, a decentralized microservice oracle network built on XRouter, allows you to monetize any microservice, blockchain call, API, or cloud tech on your own hardware, in many cases without having to write any code. For setup, see the [XCloud Configuration Guide](/service-nodes/xcloud-configuration).

\*\* **For XRouter and XCloud services**, your Service Node Computer IP address must remain unchanged (static). If using a VPN with an IP that changes, it will impact your ability to provide these services.

---

## Deploying Service Node

??? example "Setup using wallet"

	> **Preparation**

	1. On the SNode Server computer:
		1. Start the Scalaris wallet (or restart if you haven't already or have made changes).
			* Make sure this contains the previously configured `scalaris.conf` file and the `servicenode.conf` with the Service Node credentials.
		1. Fully sync the wallet.
		1. This wallet must stay running. If the SNode Server wallet is closed, you will need to re-register the Service Node from the Collateral Computer wallet if you have staked a block in that time period.
	1. On the Collateral computer:
		1. Start the Scalaris wallet (or restart if you haven't already or have made changes).
		1. Fully sync the wallet.


	> **Register the Service Node**

	1. Make sure all your inputs have at least 2 confirmations (about 2 minutes since `servicenodecreateinputs`).
	1. On the Collateral Computer wallet, open the debug console and type `servicenoderegister [ALIAS]` with `[ALIAS]` replaced with the alias of the Service Node you want to register. If `[ALIAS]` isn't specified, all known Service Nodes will be registered. You will see a response similar to this:

		![Register](/img/service-nodes/redesign-servicenoderegister-response.png)

	1. The `snodekey` will remain unchanged as long as the contents of your `servicenode.conf` remains unchanged and you haven't used the `servicenodesetup` command.


	> **Send Service Node Ping to the Network**

	1. On the SNode Server wallet, open the debug console and type `servicenodesendping`. You should see that the Service Node status is now `"status": "running"` along with a list of the services being hosted.

		![Send Ping](/img/service-nodes/redesign-servicenodesendping-response.png)


	> **Check Service Node Status**

	1. On the SNode Server wallet, open the debug console and type `servicenodestatus`. You should still see a `running` status and the services being hosted.

		![Check Status](/img/service-nodes/redesign-servicenodestatus-response.png)


	> **Check Service Node Is Available on the Network**

	1. On a client *other than* the SNode Server wallet (such as the Collateral Computer wallet), open the debug console and type `servicenodelist`. You should see your newly created Service Node in the returned list with the status as `"status": "running"`. Your Service Node is the one with the `"snodekey"` that matches the ones returned when registering your node.

		![Network Status](/img/service-nodes/redesign-servicenodelist-response.png)

	1. At this point the Collateral Computer wallet can be closed if you are not voting or staking.

---

## Operation

View the [Operations](/service-nodes/operation) for reference on how to go about common Service Node operations such as staking, voting, updating, restarting, and checking your Service Node configs.

---

## Troubleshooting
* Ensure you have the latest wallet and that it's fully synced.
* Ensure the SNode Computer wallet is open and synced before using the `servicenoderegister` from the Collateral Computer wallet.
* Ensure that you have at least 2500 SCA per Service Node in your designated `[NODE_ADDRESS]`.
* Ensure that your 2500 SCA accidentally didn???t send to a change address (if creating inputs manually).
* Ensure all your inputs have at least 2 confirmations before registering.
* Ensure you didn't include the `[` or `]` when typing commands and replacing the variables. Example:
	* Correct: `getnewaddress snode1`
	* Incorrect: `getnewaddress [snode1]`
* If you manually setup your Service Node (this guide shows the automatic procedure):
	* Ensure your `servicenode.conf` information is correct to your settings. 
	* Ensure that the `servicenode.conf` matches on both the Collateral and SNode Server computers.
	* Ensure your configuration file is `servicenode.conf` and **NOT** `servicenode.conf.txt`.

--8<-- "troubleshooting.md"



<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





