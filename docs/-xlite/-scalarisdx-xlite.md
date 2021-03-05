title: Using ScalarisDX w/ XLite
description: This page gives hints on how to use ScalarisDX with XLite.

## Configure ScalarisDX for XLite
After you have [configured ScalarisDX to connect to XLite](/scalarisdx/configuration/), you are now ready to trade XLite assets in ScalarisDX. Below are a few hints you may find helpful.

---
## Expand XLite Window Size
When XLite is open to the Dashboard in a large enough window, it should look something
like this:
![XLite Dashboard](/img/xlite/dashboard.png)
If you don't see the circular *Portfolio* graph and the *Latest
Transactions* listed below it, you can expand the size of the XLite window
until they appear.

---
## Filling in address fields in ScalarisDX from XLite

ScalarisDX requires you to fill in two addresses in the ORDER FORM before
you are can place a trade. One is the address to which the
asset you're acquiring will be sent. The other is the
[change address](/resources/glossary/#change-address) to which the
leftover change from the transaction will be sent.

For Example, an ORDER FORM to *Buy SCA*, paying for it with *LTC*, looks like this:

![Order Form](/img/scalarisdx/make-order.png)

In this example, the *SCA Address* is the address where the SCA
       you'll buy will be sent, and the *LTC Address* is the
       [change address](/resources/glossary/#change-address) where LTC
       change from the transaction will be sent. Lets also assume in
       this example that both your SCA and LTC wallets are
       within XLite. If you don't mind having funds sent to new/empty addresses in your
       SCA and LTC wallets, you can just click the *Generate New SCA/LTC
       Address* options in the ORDER FORM to fill in both of these *Address* fields
       automatically. However, if you
       want the SCA you're buying or the LTC change from the transaction to go
       to specific addresses in your wallet, you'll
       need to copy/paste those specific addresses from your wallets into
       these *Address* fields. If you want to send both the SCA you're buying,
       and the LTC change from the transaction to addresses which
       already have funds in them, here's how to find those funded
       addresses in XLite:

??? example "Find Funded SCA address within XLite"

	1. Open XLite wallet to reveal a screen like this:
	![XLite Dashboard](/img/xlite/dashboard.png)
	1. Click *Transactions* in the upper left area of the screen to reveal this screen:
	![XLite Transactions](/img/xlite/transactions.png)
	1. Click *Unspent* in the upper right area of the screen to reveal this screen:
	![XLite Unspent Scalaris](/img/xlite/unspent-blocknet.png)
	1. On this screen you can see if you already have some funded SCA addresses in XLite. (Note, you can limit the assets displayed
	on this screen to  __*only*__ Scalaris (SCA) by selecting *Scalaris* in
	the lower left area of the screen.)
	1. If you don't see any funded SCA addresses here, click *Generate New SCA Address* in the ORDER FORM and you're done.
	1. If you do find a funded SCA address to which you'd like to
    send the SCA you're about to purchase,
		1. Select the SCA address (see image above).
		1. Copy the SCA address you just selected into the clipboard (Ctrl-C Windows, Command-C Mac).
		1. Paste the SCA address into the *SCA Address* field of
           the ORDER FORM in ScalarisDX.  (Ctrl/Cmd-V)

??? example "Find Funded LTC address within XLite"

	1. Open XLite wallet to reveal a screen like this:
	![XLite Dashboard](/img/xlite/dashboard.png)
	1. Click *Transactions* in the upper left area of the screen to reveal this screen:
	![XLite Transactions](/img/xlite/transactions.png)
	1. Click *Unspent* in the upper right area of the screen to reveal this screen:
	![XLite Unspent](/img/xlite/unspent.png)
	1. On this screen you can see if you already have  some funded LTC
	addresses in XLite. (Note, you can limit the assets displayed
	on this screen to  __*only*__ Litecoin (LTC) by selecting *Litecoin* in
	the lower left area of the screen.)
	1. If you don't see any funded LTC addresses here, click *Generate New LTC Address* in the ORDER FORM and you're done.
	1. If you do find a funded LTC address to which you'd like to
    send the LTC change from the transaction,
		1. Select the LTC address (see image above).
		1. Copy the LTC address you just selected into the clipboard (Ctrl-C Windows, Command-C Mac).
		1. Paste the LTC address into the *LTC Address* field of the
           ORDER FORM in ScalarisDX.  (Ctrl/Cmd-V)


??? bug "Bug: If you used *Generate New Address* in ScalarisDX to generate the address to which the asset you just acquired should be sent, and the trade completed successfully but the asset didn't arrive in XLite as expected, click here for instructions what to do."
	1. Click on *Receive* in the upper right corner of XLite.
	1. Select the asset which did not arrive in XLite.
	1. Click *Generate new address* until the address to which the
       missing asset was sent appears in the *Your address* box.







<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





