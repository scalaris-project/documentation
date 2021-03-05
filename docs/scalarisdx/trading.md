title: Scalaris DX Trading Guide
description: These Scalaris DX trading guides explain how to check your balances, select your market, make orders, take orders, check order status, and view order history.


# Scalaris DX Trading
[Scalaris DX](/scalarisdx/introduction) is the  one of fastest, most secure, most reliable, and most decentralized exchange (DEX), built on the [Blocknet Protocol](/project/introduction). Follow the guides below to learn how to check your balances, select your market, make orders, take orders, check order status, and view order history. If Scalaris DX has not been setup yet, please follow the [setup guide](/scalarisdx/setup).


??? example "Balances"
	The first thing you want to do when starting Scalaris DX is to check your balances. *Balances* displays the connected wallets along with the *available* balance. A connected wallet is one that has been configured and is currently open and unlocked. The *available* balance is the balance of the funds in a wallet that are not locked up.

	![Balances](/img/scalarisdx/balances-unequal.png)

	The *Available* balance may show a value different than what's displayed in the wallet if:

	* The wallet is locked.
	* You have already made a trade that has locked up funds. You will want to create smaller inputs so that a single trade won't lock up more funds than needed.
	* Funds aren't in a legacy address. Right now only legacy addresses are compatible. If you are using a Segwit address, please create a new address to send the funds to. If the wallet has been configured via Scalaris DX, then a legacy address will automatically be created when generating a new address.
	* The wallet was not [configured](/scalarisdx/configuration).
	* The wallet was not restarted after the configuration.
	* If inputs have been locked via Coin Control.


??? example "Select Market"
	1. The market selection tool can be found in the upper-left corned.

		![Select Market](/img/scalarisdx/select-market-1.png)

	1. Click the *Select market pair* button.
	1. A downdown will appear with two lists: the assets of the wallets you have connected and all assets listed on Scalaris DX.

		![Select Market](/img/scalarisdx/select-market-2.png)

	1. From *Connected Tokens*, select the asset you would like to trade.
	1. Select the asset you would like to trade the first asset with. The first asset will be priced in terms of this asset. This asset must have a wallet configured.

		![Select Market](/img/scalarisdx/select-market-3.png)

	1. Select *Select* to view the chosen market.
		
		![Select Market](/img/scalarisdx/select-market-4.png)


??? example "Market Information"
	??? warning "Warning: When opening ScalarisDX for the first time it can take up to 3 minutes for all currently active orders to display on the screen."
		This is simply the nature of a fully decentralized, peer-to-peer network. If your
		XBridge client is connected to very few peers, it can even
		take slightly longer than 3 minutes.

		??? tip "Hint: Check your peer count."
			- Redesign Wallet:
 
				![Peers Status](/img/wallet-redesign/status-peers.png)


	Within ScalarisDX, each market has a price chart, depth chart, and market stats available.

	![Market Data](/img/scalarisdx/market-data.png)

	The market stats are above the price chart and show the last trade price, percent in price change over the last 24 hour rolling period, and volume over the last 24 hour rolling period.

	![Stats](/img/scalarisdx/navbar-stats.png)

	The chart has the ability to zoom. To zoom in, click and drag the pointer over the are you want to zoom in on.

	![Price Chart Zoom](/img/scalarisdx/price-chart-zoom.png)

	You can hover over the candles to show the information of each data point in the legend.

	![Price Chart Zoomed](/img/scalarisdx/price-chart-zoomed.png)

	To reset the chart, select the *Show All* button in the upper-right corner of the chart.

	![Show All](/img/scalarisdx/price-chart-show-all.png)

	To the right of the price chart there's also a depth chart. The depth chart shows how much market depth there is of orders at certain prices.

	![Depth Chart](/img/scalarisdx/depth-chart.png)

	Hover order the depth chart to view the data values.

	![Depth Chart Hover](/img/scalarisdx/depth-chart-hover.png)


??? example "Make Order"
	
	![Make Order](/img/scalarisdx/make-order.png)

	1. Review the [trading fees](/scalarisdx/fees/#maker-fee) for making orders.
	1. At the left side of Scalaris DX you will find an order form.
	1. Select either the buy or sell tab.
	1. For *Amount* (the first input), enter the amount you would like to buy or sell.

		??? info "Note: There are no limit, market, or partial orders."
			At the moment there are just *Exact* orders, meaning that orders must be taken for the exact amounts. Due to this setup, if trading a large amount it may be best to instead break the order into a few smaller separate orders.

	1. For *Price* (the second input), enter the price (rate) for
       which you would like to trade the first asset. Note, there is
       also an option to enter *Price* in terms of BTC.
	1. *Total* shows the total amount of the 2nd asset that will be traded for the first asset.
	1. In the *Address* fields, enter the addresses the funds will be
       going to for each asset. In the above example, buying SCA
       with BTC, the *SCA Address* is the address where the SCA
       you buy will be sent, and the *BTC Address* is the
       [change address](/resources/glossary/#change-address) where BTC
       change from the transaction will be sent. If you don't mind having funds sent to new/empty addresses in your
       SCA and BTC wallets, you can just click the *Generate New SCA/BTC
       Address* options to fill in both of these *Address* fields
       automatically. However, if you
       want the asset you're acquiring or the change from the transaction to go
       to specific addresses in your wallet, you'll
       need to copy/paste those specific addresses from your wallets into
       these fields. (For now, these *Address* fields must be legacy addresses,
       not Segwit addresses.) Note, the address from which
       the trade is funded is chosen automatically by ScalarisDX. ScalarisDX
       funds the trade from the address with the smallest [UTXO](/resources/glossary/#utxo)
       which can cover the expense of the trade.
	1. Ignore *Order ID*, that should be blank when creating an order.
	1. Review your order.
	1. Select the place order button.
	1. The trade will now be visible as *Open* under *Active Orders*.

		![Active](/img/scalarisdx/orders-active.png)

	The Scalaris wallet and the wallets that are being traded out of must remain open and unlocked during trading. If the Scalaris wallet is closed, any open orders will automatically be cancelled.


??? example "Take Order"
	1. Review the [trading fees](/scalarisdx/fees/#taker-fee) for taking orders.
	1. On the right side of Scalaris DX you will find the order book.

	    ![Order Book](/img/scalarisdx/order-book.png)

	1. Click on the order you would like to take.

		??? info "Note: There are no limit, market, or partial orders."
			At the moment there are just *Exact* orders, meaning that orders must be taken for the exact amounts. Due to this setup, you must have enough funds to cover the entire sell amount of the order selected.

	1. The order form on the left side of Scalaris DX will auto-populate.

		![Take Order](/img/scalarisdx/take-order.png)

	1. Make sure *Balances* shows enough funds in the *Available* column to cover the order.
	1.  In the *Address* fields, enter the addresses the funds will be
       going to for each asset. In the above example, selling SCA
       for BTC, the *SCA Address* is the
       [change address](/resources/glossary/#change-address) where SCA
       change from the transaction will be sent, and the *BTC Address* is the address where the BTC
       you acquire from the sale will be sent. If you don't mind having funds sent to new/empty addresses in your
       SCA and BTC wallets, you can just click the *Generate New SCA/BTC
       Address* options to fill in both of these *Address* fields
       automatically. However, if you
       want the asset you're acquiring or the change from the transaction to go
       to specific addresses in your wallet, you'll
       need to copy/paste those specific addresses from your wallets into
       these fields. (For now, these address fields must be legacy addresses,
       not Segwit addresses.) Note, the address from which
       the trade is funded is chosen automatically by ScalarisDX. ScalarisDX
       funds the trade from the address with the smallest [UTXO](/resources/glossary/#utxo)
       which can cover the expense of the trade.
	1. Review your order.
	1. Select the place order button.
	1. The trade will now be visible under *Active Orders*.
	1. The trade should complete in about 20-30 seconds.

	The Scalaris wallet and the wallets that are being traded out of must remain open and unlocked during trading. If the Scalaris wallet is closed, any open orders will automatically be cancelled.


??? example "Order Status"
	Any orders that are open or in progress can be found in *Active Orders*.

	![Active](/img/scalarisdx/orders-active.png)

	You can hover over the order to read the order state.

	![Active](/img/scalarisdx/orders-active-open.png)

	Any orders that are cancelled, completed, or failed can be found in *Inactive Orders*

	![Inactive](/img/scalarisdx/orders-inactive.png)

	Again, you can hover over the order to read the order state. There are different icons to represent each order state.

	![Inactive Complete](/img/scalarisdx/orders-inactive-complete.png)
	![Inactive Cancelled](/img/scalarisdx/orders-inactive-cancelled.png)

	If you have created an order, it will be indicated in the order book with a white dot.

	![Order Book](/img/scalarisdx/order-book-own-order.png)

	The Scalaris wallet and the wallets that are being traded out of must remain open and unlocked during trading. If the Scalaris wallet is closed, any open orders will automatically be cancelled.


??? example "Order History"
	At the bottom-right corner of Scalaris DX you can find the trade history. The trade history information is gathered only for the wallets that are configured. Therefore, the trade history will only show the orders that have been completed since Scalaris wallet and wallets for the currently viewed market have been opened and unlocked. If the Scalaris wallet is restarted, this information will be cleared and no longer visible.

	![Trade History](/img/scalarisdx/trade-history.png)











<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





