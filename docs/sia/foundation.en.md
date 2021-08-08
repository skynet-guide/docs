<!-- Intro section -->
# Sia Foundation
The Sia network hardforked at beginning of 2021 to implement the Sia Foundation: a new non-profit entity led by Luke Champine that builds and supports distributed cloud storage infrastructure, with a specific focus on the Sia storage platform.
## Common points of interest
---
<!-- Section speaking about where to converse about the foudation -->
Official way to communicate with The Sia Foundation is through the <a href="https://forum.sia.tech/" target="_blank" rel="noopener noreferrer">Sia Forum</a>. Not discord, reddit or twitter. The Sia Forum is the right place to post your suggestions and be sure that they will be considered and receive an official response. You can also find Luke’s launch post <a href="https://blog.sia.tech/launching-the-sia-foundation-ee47dfab4d2c" target="_blank" rel="noopener noreferrer">here</a>.

<!-- Section that links to the proposal -->
<details>
<summary>
<b> The Sia Foundation proposal</b>
</summary>
<blockquote class="reddit-card" data-card-created="1615816216"><a href="https://www.reddit.com/r/siacoin/comments/iox6ly/proposal_the_sia_foundation/">Proposal: The Sia Foundation</a> from <a href="http://www.reddit.com/r/siacoin">r/siacoin</a></blockquote>
<script async src="//embed.redditmedia.com/widgets/platform.js" charset="UTF-8"></script>
</details>
<br>

<!-- Second dropdown about the circulating supply -->
<details>
<summary>
<b>How did this fork affect the Siacoins in circulation?</b>
</summary>
You can see it on this <a href="https://siastats.info/macroeconomics">SiaStats</a> chart. The inflation increased in 2021 by roughly 10%, but that's only because of 1.57 GS that the Sia Foundation directly received as you can see <a href="https://foundation-tracker.siacentral.com">here</a> and because of the 30KS per block that are being paid out monthly. This means it will be around 5% in the following years and slowly decrease.

Sia Foundation is non-profit, so it must follow laws and as you can see in the tracker above, we can transparently see its fund management.

Due to legal reasons and requirements, Sia Foundation also paid 800M SC to the Skynet Labs for the Sia IP ownership (at the time this was decided and approved by community, it was worth of $1,000,000 - for comparison, about 15% of total development cost of Sia). That said, both teams are closely co-operating with the same goals as ever, making Sia the backbone of future internet. Sia Foundation focuses on the core tech and Skynet Labs work on the Skynet, bringing mainstream adoption to Sia.

We are putting effort to explain it because it's very common in crypto world that whenever any dev team receives a lot of coins, it's seen as exit scam. Also, splits are usually seen as bad thing.

But not for Sia and Skynet, both projects helping each other. And not when it comes to these devs. They are the same peoples who worked for years with different model than anyone else. Where other projects went with ICO, pre-mines, airdrops, trusted setups and no risk since they were paid ahead, Sia developers did this all with zero SC contribution from the community, no ICO or pre-mine. Until now.

It's quite ironic that only thanks to birth of Sia Foundation receiving SC from the blockchain, all the previous "investments" from people who bought SC can be finally seen as investments into the network and the non-profit entity working developing it.

<h2>
What about Sia’s own unlimited supply?
</h2>
In the end it’s all about supply and demand. Over time, it could happen that majority of circulating supply ends up locked in storage contracts and/or held by people. This could make it very difficult for people using to pay for their storage. That’s why Sia is always going to have a block reward so there is always a way to get SC. You can read more about it in our Introduction to Sia.

Since we know the block reward, we can tell how many SC there will be at any point in future. And we can tell that while supply is maybe theoretically infinite, it is truly infinite only if our lifes were infinite. The fact is that in our lifetimes, the supply will double maybe in next 8 years. But for Filecoin, it will double in next few weeks.

So what should you do? Zoom out. Also don’t trust, verify – make your own research. And if you still doubt Sia and Skynet, go and try all of the alternatives. Then go to Siasky.net, upload picture, video or an entire website. And send a link to your friend:)
</details>
<br>

<!-- Section about what the hardfork is -->
<details>
<summary>
<b>What is the hard fork?</b>
</summary>
<b>Hard fork is event when new version of software is released and it has different “rules”</b>. It results in two <i>seperate</i> blockchains, where one is being used by those who do not update and continue using old version. And the new blockchain that is using the new version. In this case, Sia is forking to introduce changes to the block reward.

Up to the point in time before its activation, both blockchains have identical history. It is as if someone duplicated it. If you held for example 1000 SC before, you will now have 1000 SC (which are actually 1000 SCC) on legacy blockchain and 1000 SC on the new one. But they are not the same, community usually gives them different tickers to distinguish them, like SC and SCC.

<b>Does it mean you will have double the amount of SC?</b> No. You <i>will</i> have twice the coins, but each set of coins is on a seperate network and all new transactions can only be on one chain. Let’s look at one good example from Sia’s own history. The fork in 2018 resulted in two chains: Sia (after update, used by versions 1.3.7 and higher, let’s call it SC after its currency) and the legacy one (used by those who didn’t update, which was called SCC(there were also other forks, but they're not important here)).

If you had SC before the fork, when the network split happened, you had same history (seed, blocks, addresses, transactions) on both blockchains, but after that moment, each blockchain went own way. That means you had same amount of different coins that weren’t compatible with each other – if you made transaction with SCC after the fork or mined coins on SCC chain, they would only exist on SCC blockchain, not on Sia. And vice versa.
<blockquote>
Since this fork was well accepted by vast majority of the community<i>there is no legacy chain expected to survive</i>. You can still access your legacy coins if you use the old wallet software at any point in future, but there will be no one who continues using it. In other words, it will(in all likelyhood) be worthless.
</blockquote>
</details>
<br>

---
<!--Final section about the forks implications -->
## What does it mean for me? Help me!
This fork will activate at a block height 298,000 which is expected to be on **February 3rd**.

Update to version **1.5.4 is necessary to spend coins, receive coins, rent, or host after the fork**. If you don’t upgrade in time (or at least before next time you run Sia), you will get your `consensus.db` file stuck to the legacy blockchain.

>`consensus.db` is the file that syncs the blockchain to your computer, and if you don’t update now, you will have to eventually re-sync it which is very time consuming operation.

### If you rent or host on Sia
Renters and hosts need to **upgrade to 1.5.4 by February 3rd**. Doing so ensures that renters will continue to upload data to hosts also on the new fork. Hosts who fail to upgrade in time will no longer form contracts with renters who upgrade. Long story short, you need to be on the same version as everyone else or you aren’t part of the same network.

### If you hold Siacoins in own wallet (Sia-UI)
If you have Siacoins stored in official Sia-UI wallet, all you need to do is to **update to 1.5.4**. You control the seed (private key) and you will have instant access to your SC on the new Sia chain.

### If you hold Siacoins in own wallet (Sia Central)
**Ledger Nano S users will have to update their apps**. Those not using Ledger don’t have to do anything, the site will update the node it connects to so you won’t have to. You control the seed (private key) and you will have instant access to your SC on the new Sia chain.

### If you hold Siacoins on exchange
You don’t have to do anything, the exchange will update the node it connects to so you won’t have to. Also, the exchange controls the seed (private key) so it’s not your issue at all. Your Siacoin balance is the balance you have in their exchange’s internal database and it will be the same after the fork as it was before.

>It is good idea to **never keep your coins on Exchange** unless you are trading actively and you know what you are doing. It is rather rare today but many exchanges in the past ended up with users losing their assets. When you have coins on Exchange, they are not really yours since you don’t have the seed (private key). It is very similar to your bank account, the money are not yours. It is the bank that keeps them and allows you access it through its system. If that system goes down, what will you do? You can prevent this scenario by keeping coins in your [own wallet](/sia/wallet.html) out of exchanges.

### If you mine Siacoin
Nothing changes. Only ones who need to update are the **mining pools**. We already updated our list of Mining Pools, so all that you find there confirmed the update.

*Written by: Danger & Covalent, Last Edit: April 14, 2021*
