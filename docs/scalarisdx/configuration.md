title: Scalaris DX Configuration Guide
description: This guide explains how to configure wallets for trading on Scalaris DX for decentralized peer-to-peer exchange directly from your own wallet.


# Scalaris DX Configuration
[Scalaris DX](/scalarisdx/introduction) is a truly decentralized exchange that enables peer-to-peer trading. Since trading with Scalaris DX is performed directly from the wallet of the assets being traded, these wallets must be properly configured. This guide will walk you through the configuration process, all performed through a few simple screens within Scalaris DX. For the full setup process, see the [Scalaris DX Setup Guide](/scalarisdx/setup).


## Written Guide

1. [Install the Scalaris wallet](/wallet/setup). The Scalaris wallet is **required** to facilitate peer-to-peer trading on Scalaris DX.
1. Install the wallets of the [digital assets](/resources/glossary/#digital-asset) you will be trading. These wallets are **required** to store your funds since Scalaris DX is non-custodial. [View the list compatible digital assets and wallet versions](/scalarisdx/listings).

	??? info "Note: Lite wallets in general, and Electrum wallets, are not supported."
		Due to the interactions the wallet needs to make to ensure secure trading, lite wallets and Electrum wallets are not currently supported. However, Scalaris's XRouter allows for the development of decentralized, noncustodial SPV wallets
	??? tip "Tip for Goldcoin (GLC) traders"
		1. Make sure you have [installed the latest ScalarisDX (v1.9.0 or greater)](/scalarisdx/installation/#install-scalaris-dx)
		1. Make sure you have [installed the latest version of Goldcoin wallet (v0.14.7 or above)](https://www.goldcoinproject.org)
		1. If you created your Goldcoin wallet using an earlier version of the Goldcoin wallet app, you may have a Goldcoin data directory named, `GoldCoin (GLD)`.  You can check this by navigating in a File Explorer (Windows) or Finder (Mac) to this location:
			- Windows: ` %appdata%\Roaming`
			- Mac: ` ~/Library/Application Support/`
			- Linux: ` ~/`
		1. If you see a directory here named, `GoldCoin (GLD)`, close your Goldcoin wallet and rename `GoldCoin (GLD)`  to `Goldcoin`  (note the small *c* in *coin*). In the case of Linux, rename it to `.goldcoin`.
		1. Restart your Goldcoin wallet and verify it shows the correct balance.
		1. If the Goldcoin app asks you to specify the data directory, select the default directory, which should be the new Goldcoin data directory you just made by renaming the old data directory.
		
1. [Install Scalaris DX](/scalarisdx/installation). This is a desktop dApp and not supported in-browser.
	
???+ warning "Warning"
    You *__must__* have the Scalaris wallet and the wallets of the assets you will be trading installed  *before* continuing.

## 2 Step Configuration

??? example "Step 1 - This step is required for everyone. __*This step must be performed before Step 2*__"

    When you first open ScalarisDX, you should see the __FRESH SETUP__ screen below. (If you don't see this screen, choose the __Fresh Setup__ option when it's presented, or arrive at the __Fresh Setup__ option through *Menu->Add & Update Wallets*.):

	![Configuration](/img/scalarisdx/config-fresh-setup.png) 

    * It is recommended you use the *Quick Setup* option, but if you use custom data directories for your wallets then you'll need to use the *Expert Setup* option.

	![Configuration](/img/scalarisdx/select-native-wallets.png) 

	![Configuration](/img/scalarisdx/restart.png) 

	* When you arrive at the __CONFIGURATION COMPLETE__ screen, be sure to carefully read and follow steps 1 & 2 __*BEFORE*__ clicking *RESTART*

	![Configuration](/img/scalarisdx/menu.png) 

    * After configuration is complete, you can add new wallets or reconfigure existing wallets at any time under *MENU->Add & Update Wallets*. 

--8<-- "complete-scalarisdx-configuration.md"















<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





