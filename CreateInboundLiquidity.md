## Create inbound liquidity

To make outbound liquidity (to be able to send payments) is easy, you just need to open a channel to a well connected, stable node. 

To make inbound liquidity (to be able to receive payments on a channel you opened) a payment can be sent to a merchant or exchange accepting Lightning and receive the product or receive the sats back on-chain.

### Non-custodial wallets
Run a separate LN node on your phone or desktop where you can move some funds, so remote balance/ inbound liquidity is created
* [Breez](https://breez.technology/)  
A mobile wallet which creates a 1 million sats incoming channel automatically, so funds can be moved over in minutes after setting up.  
Sending the funds out to a bitcoin address on-chain costs 0.5% with [Boltz](https://boltz.exchange/)
* [Zap](https://zap.jackmallers.com/)   
Run a Lightning Node on Android, iOS or desktop. Channels are managed manually or by the autopilot.
* [Lightning App by Lightning Labs](https://github.com/lightninglabs/lightning-app)  
An easy-to-use cross platform lightning wallet
### Custodial wallets
Tip yourself via LN and benefit from the inbound liquidity created.
The drawback is that you don`t control the seed of your custodial wallet.  
Examples:  
* [Tippin.me](https://tippin.me/)
* [Wallet of Satoshi](https://www.walletofsatoshi.com/)
* [Bluewallet](https://bluewallet.io/)

### [Lightning Loop](https://github.com/lightninglabs/loop)
Lightning Loop is a non-custodial service offered by Lightning Labs to bridge on-chain and off-chain Bitcoin using submarine swaps.

In the current iteration of the Loop software, two swap types are supported:

* Loop Out: off-chain to on-chain. The Loop client sends funds paid on Lightning to a Bitcoin address.

* Loop In: on-chain to off-chain. The Loop client sends funds paid on-chain to a Lightning channel.

* Max swap amount: 4 200 000 sats

* Example usage for lowest cost (leads to longer confirmation time (estimation for 25 blocks) and higher failure rate (max routing fee 500 sats) - adjust the numbers accordingly):  
`loop out --conf_target 25 --max_swap_routing_fee 500 4200000 [optional external address]`

    ```
     loop out [command options] amt [addr]

    # --channel value               the 8-byte compact channel ID of the channel to loop out (default: 0)
    # --addr value                  the optional address that the looped out funds should be sent to, if let blank the funds will go to lnd's wallet
    # --amt value                   the amount in satoshis to loop out (default: 0)
    # --conf_target value           the number of blocks from the swap initiation height that the on-chain HTLC should be swept within (default: 6)
    # --max_swap_routing_fee value  the max off-chain swap routing fee in satoshis, if let blank a default max fee will be used (default: 0)
    # --fast                        Indicate you want to swap immediately, paying potentially a higher fee. If not set the swap server might choose to wait up to 30 minutes before publishing the swap HTLC on-chain, to save on chain fees. Not setting this flag might result in a lower swap fee.
    ```
    <https://lightning.engineering/loopapi>

### [ChainMarket](https://chainmarket.etleneum.com/)
A Lightning to onchain swap market with batched transactions.
Fee: 0.5%

### [Sats4Likes](https://kriptode.com/satsforlikes/index.html)
Post an advert and pay satoshis for incoming channels.

### [t.me/LNswapBot - A Telegram bot](https://t.me/LNswapBot)
Swap on-chain coins to Lightning Network and vice versa! For less then $0.01 fee! 

### [Boltz](https://boltz.exchange/)
Fee: 0.5% both ways

### [FixedFloat](https://fixedfloat.com/)
Lightning cryptocurrency exchange
Fee: 0.5 - 1% both ways

### [ZigZag.io](https://zigzag.io/#/)
An exchange that accepts Lightning payments.
Max 4M sats
Commission ~ 2% 

### [LightningTo.me](https://lightningto.me/)
Opens a channel for free funded with 2 000 000 satoshis. Need to have 10 channels open already to use this service.  
Add their node as a peer if connecting from behind Tor:  
`$ lncli connect 03bb88ccc444534da7b5b64b4f7b15e1eccb18e102db0e400d4b9cfe93763aa26d@138.68.14.104:9735`

### [LightningPowerUsers.com](https://lightningpowerusers.com/home/)
Request inbound capacity for a small fee
Recommended channel size: Between 500 000 and 16 500 000 satoshis.

### [Thor: Lightning Channel-Opening Service by Bitrefill.com](https://www.bitrefill.com/thor-lightning-network-channels/?hl=en)
Pay with Lightning for an inbound channel of up to 16 000 000 satoshis.

### [LNBIG.com](https://lnbig.com/#/open-channel)
Free incoming channel with up to 5 000 000 sats from <https://twitter.com/lnbig_com>

Once there is higher balance on the side of your node an other incoming channel can be requested.

the service is paid in routing fees:  
![lnbig_fees](/images/lnbig_fees.png)

### [github.com/bitcoin-software/ln-liquidity](https://github.com/bitcoin-software/ln-liquidity)
List of exchange services to make coin swaps LN <-> onchain & more

### Nodes which connect back:
* **stackingsats [TFTC] [NODL] [TOR]**  
<https://1ml.com/node/02d419c9af624d0eg7a7c90a60b9ffa35f4934973a9d7d3b4175cc3cc28b7ffcde1>  
Will reciprocate channels over 2 000 000 sats.  
Keep in mind that channels fees can be changed by the peer arbitrarily.   
Check the latest state in a Lightning Explorer:  
https://1ml.com/node/02d419c9af624d0e7a7c90a60b9ffa35f4934973a9d7d3b4175cc3cc28b7ffcde1/channels

## To top up the Lightning balance

### [RedShift](https://ion.radar.tech/redshift)
Trustless transfers between the Lightning Network, the Bitcoin blockchain, and any supported digital asset (BTC and ETH so far).
Send funds on-chain and receive on Lightning.

### [Lightning Loop](https://github.com/lightninglabs/loop)
* Loop In: on-chain to off-chain, where the Loop client sends funds paid on-chain to an off-chain channel.

### [golightning.club](https://golightning.club/)
Send on-chain and receive bitcoin over Lightning!
Up to 1000000 satoshi / 0.01 BTC.