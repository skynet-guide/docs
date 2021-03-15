# Sia Foundation & Fork 2021
The Sia network is hardforking to implement the Sia Foundation: a new non-profit entity led by Luke Champine that builds and supports distributed cloud storage infrastructure, with a specific focus on the Sia storage platform. 
<details>
<summary>
<b> The Sia Foundation proposal </b> 
</summary>
<blockquote class="reddit-card" data-card-created="1615816216"><a href="https://www.reddit.com/r/siacoin/comments/iox6ly/proposal_the_sia_foundation/">Proposal: The Sia Foundation</a> from <a href="http://www.reddit.com/r/siacoin">r/siacoin</a></blockquote>
<script async src="//embed.redditmedia.com/widgets/platform.js" charset="UTF-8"></script>
</details>

Official way to communicate with The Sia Foundation is through the [Sia Forum](https://forum.sia.tech/). Not discord, reddit or twitter. The Sia Forum is the right place to post your suggestions and be sure that they will be considered and receive an official response. You can also find Luke’s launch post [here](https://blog.sia.tech/launching-the-sia-foundation-ee47dfab4d2c).

<details>
<br>
<summary>
<b>How does this fork affect the Siacoins in circulation?</b>
</summary>
You can see it on this SiaStats chart. The inflation is going to be about 10% in 2021 and then will decrease to roughly 5% per year. We noticed some people being concerned about exit scam so it is fair to explain who the developers of Sia are. They are the same peoples who worked for years with different model than anyone else. Where other projects went with ICO, pre-mines, airdrops, trusted setups and other more or less centralized solutions that allowed them to literally print money and keep a lot for themselves without ever risking anything, since they were paid ahead, Sia developers did this all with zero SC investment from the community, no ICO or pre-mine.

But let’s look at the inflation a bit closer. In 2019 not so long time ago the inflation was much higher. And even today, majority of crypto projects have higher inflation than this one. Huge difference with Sia is that all of the new coins added on top of original block reward will be transparently used for good of the Sia network.

How can we so be sure? Well, there is a law for it, Sia Foundation is registered as non-profit and needs to be transparent with its expenses and funding.

Developers didn’t use the Siacoin to fund the development in any way, but there was isolated offering of network’s supplementary token called Siafund that raised $120,000 (initially called Sianotes). See the link for more information.

Another thing to explain is that many people got used that when some project launches mainnet, it is immediately usable and should go for adoption. But that is because majority of these projects are trying to replace Bitcoin, act as money. Sia could be used as money back since 2015, but was it ready to provide decentralized storage? No. It got there with 1.4.0 update in April 2019. But even that was just a beginning, it is getting much closer to that state today in 2021 when Skynet and first real products are just getting finished and launched. And now, finally, developers around the world can finally react and build exciting apps with it. Will it be fast? No, as with every new technology, it takes time to be adopted.
</details>
<br>
<details>
<summary>
<b>How does it compare with other projects?</b>
</summary>
There are many projects that claim decentralization. Many are not truly decentralized but benefit from people thinking they are. And others are, but in very limited way, absolutely unusable for anything but tiny quantities of data. And some others are decentralized, but not in the same vein as Sia. There is also another cucial distinction that people often miss; there is a difference between a decentralized app and decentralized storage network. For example, Sia is a decentralized storage network (layer 1), that can be used by Skynet, a decentralized internet (layer 2). And then there are decentralized apps that can be built on top of decentralized internet, Skynet.

Another facet to consider is inflation; a good comparison to draw would be Sia to Filecoin. Simple fact is that Filecoin has several hundred times higher inflation and if you are watching coinmarketcap, the supply is frozen and showing 45 million FIL, while there is already over 110 million in existence. And there will be over 1 billion in its first 2 years. It’s fully diluted market cap is about 250x that of Sia (this value can be different due to markets never sleeping) higher than Sia and Filecoin is a living proof that projects with questionable approaches, heavily experimental tech and unsustainable methods of growth can easily get away with anything.
</details>
<br>
What about Sia’s own unlimited supply?
In the end it’s all about supply and demand. Over time, it could happen that majority of circulating supply ends up locked in storage contracts and/or held by people. This could make it very difficult for people using to pay for their storage. That’s why Sia is always going to have a block reward so there is always a way to get SC. You can read more about it in Introduction to Sia.

Since we know the block reward, we can tell how many SC there will be at any point in future. And we can tell that while supply is maybe theoretically infinite, it is truly infinite only if our lifes were infinite. The fact is that in our lifetimes, the supply will double maybe in next 8 years. But for Filecoin, it will double in next few weeks.

So what should you do? Zoom out. Also don’t trust, verify – make your own research. And if you still doubt Sia and Skynet, go and try all of the alternatives. Then go to Siasky.net, upload picture, video or an entire website. And send a link to your friend:)

What is the hard fork?
Hard fork is event when new version of software is released and it has different “rules”. It results in two blockchains, where one is being used by those who do not update and continue using old version. And the new blockchain that is using the new version. In this case, Sia is introducing changes to the block reward.

Up to the point in time before its activation, both blockchains have identical history. It is as if someone duplicated it. If you held for example 1000 SC before, you will now have 1000 SC (which are actually 1000 SCC) on legacy blockchain and 1000 SC on the new one. But they are not the same, community usually gives them different tickers to distinguish them, like SC and SCC.

Does it mean you will have double the amount of SC? No. This is wrong assumption. Let’s look at one good example from Sia’s own history. The fork in 2018 resulted in two chains: Sia (after update, used by versions 1.3.7 and higher, let’s call it SC after its currency) and the legacy one (used by those who didn’t update, let’s call it SCC).

If you had SC before the fork, when the network split happened, you had same history (seed, blocks, addresses, transactions) on both blockchains, but after that moment, each blockchain went own way. That means you had same amount of different coins that weren’t compatible with each other – if you made transaction with SCC after the fork or mined coins on SCC chain, they would only exist on SCC blockchain, not on Sia. And vice versa.

Since this fork is welcome by vast majority of the community (if you don’t understand what it means, check out History of Sia, the Proposal or Sia Foundation), there is no legacy chain expected to survive. You can still access your legacy coins if you use the old wallet software at any point in future, but there will be no one who continues using it. In other words, it will be worthless.

What does it mean for me? Help me!
This fork will activate at a block height 298,000 which is expected to be on February 3rd.

Update to version 1.5.4 is necessary to spend coins, receive coins, rent, or host after the fork. If you don’t upgrade in time (or at least before next time you run Sia), you will get your consensus.db file stuck to the legacy blockchain.

consensus.db is the file that syncs the blockchain to your computer, and if you don’t update now, you will have to eventually re-sync it which is very time consuming operation.

If you rent or host on Sia
Renters and hosts need to upgrade to 1.5.4 by February 3rd. Doing so ensures that renters will continue to upload data to hosts also on the new fork. Hosts who fail to upgrade in time will no longer form contracts with renters who upgrade. Long story short, you need to be on the same version as everyone else or you aren’t part of the same network.

If you hold Siacoins in own wallet (Sia-UI)
If you have Siacoins stored in official Sia-UI wallet, all you need to do is to update to 1.5.4. You control the seed (private key) and you will have instant access to your SC on the new Sia chain.

If you hold Siacoins in own wallet (Sia Central)
Ledger Nano S users will have to update their apps. Those not using Ledger don’t have to do anything, the site will update the node it connects to so you won’t have to. You control the seed (private key) and you will have instant access to your SC on the new Sia chain.

If you hold Siacoins on exchange
You don’t have to do anything, the exchange will update the node it connects to so you won’t have to. Also, the exchange controls the seed (private key) so it’s not your issue at all. Your Siacoin balance is the balance you have in their exchange’s internal database and it will be the same after the fork as it was before.

It is good idea to never keep your coins on Exchange unless you are trading actively and you know what you are doing. It is rather rare today but many exchanges in the past ended up with users losing their assets. When you have coins on Exchange, they are not really yours since you don’t have the seed (private key). It is very similar to your bank account, the money are not yours. It is the bank that keeps them and allows you access it through its system. If that system goes down, what will you do? You can prevent this scenario by keeping coins in your own wallet out of exchanges.

If you mine Siacoin
Nothing changes. Only ones who need to update are the mining pools. We already updated our list of Mining Pools, so all that you find there confirmed the update.

Written by Danger (Updated: Jan 15, 2021)