# Interacting with Meter Mainnet Using MetaMask

Meter mainnet now supports two transaction \(tx\) formats: 

1. The native Meter tx, which is more expansive and supports staking, on-chain auctions, validator transactions, and future multiple chains/shards. This tx format is used by the Meter mainnet wallet which is a PC/Mac application [downloadable](https://www.meter.io/wallets/) from the Meter website or [Github](https://github.com/meterio/meter-wallet). 
2. Ethereum tx. This is designed for backward compatibility with existing Ethereum dApps and ecosystem including wallets like [Metamask](https://metamask.io/).

Metamask communicates with the Meter mainnet through a RPC \(Remote Procedure Call\) emulation layer.  The user will have to configure a custom RPC network inside MetaMask. Here is how to do so.

**For the browser plugin version of Metamask:**

1. Select the network drop down menu, and then click on the custom RPC at the bottom.

![](../.gitbook/assets/image.png)

If you are using the mobile app version of Metamask, the custom RPC setup is under "Settings" and then "Networks".

![](../.gitbook/assets/image%20%286%29.png)



2. Enter the following information for the Custom RPC and click "Save":

![](../.gitbook/assets/image%20%284%29.png)

In Meter, both MTR and MTRG are native network coins. However, Metamask can only display one native coin \(ETH in Ethereum's case\). We configured the gas token MTR to replace the default ETH in the wallet. To properly display and transact MTRG, we created ERC-20 wrappers for MTRG and MTR so MetaMask and dApps could treat them as ERC-20 tokens as well. Please add the following ERC20 contract addresses as custom tokens in MetaMask:

-MTRG: 0x228ebBeE999c6a7ad74A6130E81b12f9Fe237Ba3

-MTR \(Optional\): 0x687A6294D0D6d63e751A059bf1ca68E4AE7B13E2

These two ERC-20 contracts will only be effective after block 4.9M on the Meter mainnet.

![](../.gitbook/assets/image%20%281%29.png)

One potential confusing issue is that the minimum gas price is 500 gwei in Meter.  Metamask will typically estimate the transaction fees too low unless the user set custom gas price 500 gwei.  Meter also doesn't use the gas limit passed from Metamask.

Please be aware there is no nonce concept in Meter.  Therefore, **you should NOT click on the "Speed up" or "Cancel" button for the transaction**.  This will cause the same transaction to be issued multiple times.  Any transactions that are not processed within 320 seconds are automatically cancelled in Meter.

Finally, since Metamask interacts with the Ethereum network by default, it adds wait and delay time for sending transactions. Therefore, it may take up to 30 seconds for Metamask to show that a Meter transaction is confirmed, although it may already be confirmed on the Meter mainnet. 











