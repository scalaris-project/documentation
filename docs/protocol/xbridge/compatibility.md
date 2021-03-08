title: Scalaris Protocol - XBridge Asset Compatibility
description: Scalaris has over 100 digital assets tested and confirmed to be supported by XBridge, with the number continuously growing as more are integrated. 


# XBridge Digital Asset Compatibility

Any digital asset that supports lock time checks and has a JSON RPC interface will be compatible with Scalaris's XBridge. As a result, most digital assets in existence today are compatible. 

Currently Scalaris has over 90 [digital assets](/resources/glossary/#digital-asset) tested and confirmed to be supported by XBridge, with the number continuously growing as more are integrated. 

---

## Integration
Being integrated with Scalaris holds many benefits. Not only does it allow an asset to be traded using Scalaris DX, a decentralized exchange built on XBridge, but it allows other services to be built utilizing the asset. This extends the demand, utility, and accessibility of the asset to the rest of the ecosystem.

Integration of assets is a free and open process, without permission required. All configuration files are located in Scalaris's [blockchain-configuration-files](https://github.com/scalaris-project/blockchain-configuration-files/) Github repository.

If you would like to have a digital asset supported, please ask a member of that project to create a pull request or ask someone from community at [Discord](https://discord.gg/ZeUMV2kcaQ) in listing chanel to help you.

#### Blockchain Requirements
In order for for a blockchain to be compatible it must support JSON RPC, CLTV atomic swaps, and the following calls:

* createrawtransaction
* decoderawtransaction
* getblock
* getblockchaininfo (fallback getnetworkinfo, getinfo)
* getblockhash
* getnewaddress
* getrawmempool
* getrawtransaction
* gettransaction
* gettxout
* listunspent
* sendrawtransaction
* signmessage
* signrawtransaction (or signrawtransactionwithwallet)
* verifymessage

---

## Supported Digital Assets
**Note**: XBridge is not yet compatible with hardware wallets such as Ledger, web wallets such as MyEtherWallet (MEW), or lite wallets such as Jaxx. Desktop Qt/cli wallets must be used. Below is a list of compatible assets and respective wallet versions. 

--8<-- "xbridge-compatibility.md"








<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





