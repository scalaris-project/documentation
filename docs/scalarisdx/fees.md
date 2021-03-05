title: Scalaris DX Fee Structure
description: Scalaris DX is a decentralized exchange dApp powered by the Blocknet Protocol that has lower fees and no deposit, withdrawal, or maker fees.


# Scalaris DX Fee Structure
[Scalaris DX](/scalarisdx/introduction) is a decentralized exchange dApp powered by the Blocknet Protocol. Unlike centralized exchanges, Scalaris DX has no deposit, withdrawal, or maker fees other than network fees of the asset being traded.

---

## Maker Fee
When creating an order on Scalaris DX, there is no fee other than the transaction fee for the network of the asset being sold. This is the same type of fee you would incur if sending this asset to another party.

Having no fee to place an order encourages market makers to add liquidity. This also makes it possible for a user to acquire the [SCA](/blockchain/introduction) needed to take orders.

---

## Taker Fee
When accepting an order on Scalaris DX, a static fee of 0.01 [SCA](/blockchain/introduction) is charged at the time the order is taken. This fee is charged even if a trade is canceled or fails and is meant to discourage malicious behavior on the network. 

In addition to the 0.01 SCA fee, there is also the transaction fee for the network of the asset being sold. This is the same type of fee you would incur if sending this asset to another party.

If the taker asset is SCA, there needs to be *at least* two [UTXOs](/resources/glossary/#utxo) - one or more to cover the 0.01 SCA fee and one or more to cover the traded amount. 

In a future update, there will be a percent-based fee that’s charged when accepting an order, but the details of this are not yet finalized.


---

## Fees Distribution
100% of trade fees are distributed to [Service Node](/service-nodes/introduction) operators for supporting the network.













<script type="text/javascript">
// read instructions for related links in ../snippets/extras.md
var relatedLinks = [];
</script>

--8<-- "extras.md"





