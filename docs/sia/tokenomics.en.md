# Tokenomics (SC & SF)
There is a lot of misunderstanding around when it comes to tokens flowing through the Sia network. Most common concern is about its so called “unlimited” supply and inflation. So let’s take a deeper look at it.

>Quick Links: [Siacoin (SC)](#siacoin-(sc)), [Siafund (SF)](#siafund-(sf)), Where to buy?

## Siacoin (SC)
The first and most common mistake we see all the time is people calling the currency **SIA**, the same name as the network. It seems to make sense to them if they only hold it, but is very confusing to anyone actually using it. The network is called **Sia** and the currency enabling us to use it is **Siacoin** with **SC** as the ticker symbol commonly used on exchanges.

Siacoin is a cryptocurrency that was never pre-mined, there was no ICO and it is not a trusted setup. Siacoins are not even securities. In [2019 SEC was looking into Sia](https://sia.tech/settlement2019) and didn’t initiate any action against SC. Only issues they had were with the first and very small $120,000 Sianotes (later converted to Siafunds) offering from 2014, few years before SEC even started providing guidance to projects in 2017.

Siacoin can be divided up tp 10^24 units called **hastings** and is only entering circulation as a result of mining. You can find more details about it in our [Mining Guide](/sia/mining-guide/index.html).

Symbol	| Prefix	    | Full amount	                    | Scientific notation
--------| --------------| ------------------------------| -------------------
H	    | hasting	    | 0.000000000000000000000001 SC	| 10^-24 SC
pS	    | pico	        | 0.000000000001 SC	            | 10^-12 SC
nS	    | nano	        | 0.000000001 SC	                | 10^-9 SC
μS	    | micro	        | 0.000001 SC	                    | 10^-6 SC
mS	    | milli	        | 0.001 SC	                    | 10^-3 SC
SC	    | Siacoin	    | 1 SC                            | 10^1 SC
KS	    | kilo	        | 1000 SC	                        | 10^3 SC
MS	    | mega	        | 1000000 SC	                    | 10^6 SC
GS	    | giga	        | 1000000000 SC	                | 10^9 SC
TS	    | tera	        | 1000000000000 SC	            | 10^12 SC

>**Did you know?** Not many projects can say that they never participated in any paid listings on exchanges. Sia is a rare example of such project that accomplished it purely for its fundamentals.

### How they get made
Those who earn the new coins by mining do it as a paid service. They buy and use expensive hardware with a single purpose  –  mining crypto. It’s a very specific device because it cannot be used for anything else. But it provides an important security layer to the network by powering the transactions that take place.

They earn Siacoin (SC) as their mining reward and then distribute it with profit to the broader community, usually via exchanges. For those who know Bitcoin, this is the same process, but with its own network and Proof of Work algorithm. The only difference is that while Bitcoin has a limit of coins that can be mined, Siacoin doesn’t. And because this is something that makes newcomers to Sia worried, let’s look at it in more detail.

### Is the supply really unlimited?
Many people have concerns about unlimited supply of Siacoin and its inflation. These concerns have roots in lack of understanding and can be easily dismissed.

There is always going to be some block reward to ensure that there are new coins entering circulation. Remember, **this is not just a currency like Bitcoin, this is a data storage network. If it becomes successful, it can happen that a majority of the coins will be locked in storage contracts**. There are also concerns about the other extreme, risk of someone accumulating and holding majority, if not all of the Siacoins. This all has been foreseen and by design the supply has been made “unlimited”.

However, **“unlimited” supply doesn’t mean you can “print” endless amount of coins right now**. It means that there is no limit and coins will keep entering circulation at known rate. As you know the block reward, you can tell how many coins there will be in the existence at any point in time. And you can achieve really infinite supply only if you have infinite time. But the human kind doesn’t have such life expectation. In our lifetimes, the total supply of Siacoin won’t increase much. And that is correct even if Sia Foundation adds extra coins to the block rewards.

>In 2015, **Sia’s block reward started with genesis block at 300,000 SC** and was decreasing by 1 with each new block. The bottom by design was set to 30 000 SC per block and this limit was reached in 2020. Since then the block reward is fixed. In Q1 of 2021 this is changing with Sia Foundation, (you can find more about it in [Introduction to Sia](/sia/introduction/index.html)) but even with block reward doubled to 60 000 SC per block the **inflation will be much lower than for other projects** and actually lower than it wasthen it was a couple years ago. Not just that though, half of these coins will be used for good of the network and if it cannot be reasonably and transparently spent in its support, it will be burnt. Ask yourself, if you knew year ago that 50% of block rewards are going into support of the Sia ecosystem instead of profit taking (where money leave the ecosystem), wouldn’t it be **great news**?

The existence of the block reward guarantees that the network can continue performing smoothly and users always have the option of either buying it on exchange, using some middleman (storage services built on top of Sia and providing fiat payment gates), or mining it themselves. This helps to keep everything working and self-balancing. Another self-balancing technique that the network uses is coin destruction. Some coins are burnt by host announcements and lost in collateral from bad-actor hosts.

### What is a 51% attack and is it a threat or not?
There is one question that is brought up constantly since many other projects were affected by it, especially those allowing GPU mining or algorithms shared by many projects allowing hashrate to be easily rented just for those attacks.

A 51% attack is when a malicious party controls more than 50% of the network’s hashrate. This allows the attacker to rewrite the blockchain history. The most common form of this attack is the “double-spend attack”, where the attacker pays a counterparty, then rewinds the blockchain history to “undo” their payment.

All proof-of-work blockchains are vulnerable to 51% attacks, but **Sia is more secure than most PoW chains because of it's employment of ASICs**. Before ASICs for Sia were released, mining was performed with GPUs. This left the network vulnerable to large GPU mining pools whose total hashrate exceeded 50% of Sia’s hashrate. Recognizing this threat, Nebulous spun off a subsidiary company, Obelisk and started a public fundraising in order to develop and deliver ASIC miners for Sia.

Obelisk was careful to prevent any one entity from controlling too many of these ASICs, but the situation dramatically changed long before their delivery as other manufacturers noticed the public announcement of ASICs being made for Sia and rushed in with inferior, but sooner delivered units. They flooded Sia’s ecosystem with way more than was healthy and even competed with own customers. About half year later, when one such manufacturer got close to 50% of block rewards moving into single wallet address without even trying to hide it, there was no other option and the community unanymously forked anything but Obelisk SC1 away from the network.

Today, there are still many Obelisks on the network but majority of hashrate is from other products that have become available for Sia as well. As a result, Sia’s hashrate is well-distributed. At this point, in order for a 51% attack to be performed, an attacker would need to control multiple mining pools, and/or develop custom ASICs at enormous expense.

>If you want to know more about hardware available for mining and learn more about the history of mining and forks, see our [Mining Hardware guide](/mining/hardware/index.html).

But miners are just where it begins. You probably know that when it comes to decentralized storage, your paper currency is quite useless. Not even the funds on your bank account can help you as there is no payment gateway. Some other projects have them and those gateways are the points of failure, because if they go down, you cannot access your files.

### The importance of Sia having its own currency
And that’s where Siacoins come into play. It is a cryptocurrency specifically designed for this kind of service. Its blockchain supports storage contracts so you can form these with the selected hosts directly. Once the contract is formed, all payments between you and the other side are instant through the payment channel and in the near future there will even be pre-payments possible.

Thanks to this you only pay for what you really use. We believe this is beginning of the internet where you have the option to pay tiny micro-transactions only for content you see instead of blanket subscription fees.

However, this doesn’t mean you won’t have that option. In this new world, it is up to users to decide. Services built with this tech can offer such experience for those who want to use the decentralized internet without worrying about crypto wallet management and just pay with fiat currency. And the recent development with Skynet makes this future look like coming true.

>If you want to know more about Skynet, see our [Introduction to Skynet](/skynet/introduction/index.html).

### What makes hosts to keep and protect my data instead of deleting them?
Hosts also use Siacoin. For them it is not just a reward. Before they get chance to store any of your data, they must provide a collateral. If you met a stranger on the street that would tell you that he will keep and protect your phone if you give it to him, would you trust him without giving you something of at least same value? And would you trust a stranger with your most precious data? We don’t think so. While there are many good people, you would most likely lose your phone and never see your data again as well.

This is why the incentives must be set right, especially in decentralized system that claims to have no point of failure. In a good faith, hosts need to provide collateral which is usually about two times higher than expected earnings for the rented storage. The host will get his collateral back as well as the earnings only if he keeps providing proofs that he still holds your data until the contract duration expires. This is usually called a successful storage contract. On the other side, if it fails, the collateral and expected earnings are burnt. This is why hosting is considered a serious and responsible job, because if you cannot protect user’s data, you are going to lose money. And that makes sense, right?

### Is it a good investment?
Very often people ask if Siacoin (SC) is a good investment. They also remember that developers said they don’t care about the price. While we won’t give you financial advice, we can provide some facts and views that might improve your understanding and enable you to make own judgement and decisions.

The way Sia works, all coins in circulation were mined by community (miners). The developers had less than 1% of coins but accidentaly lost them and since then they have less than 0.1% of entire supply. They don’t participate in speculation, they are probably one of few super rare projects that never paid a single cent for any of the listings on exchanges. And their incentives are the Siafunds (and since 2021 also Skynet business model) which only start generating meaningful income when the network gets more used. And guess what, Siafunds are paying rewards in SC.

Simply said, Sia developers are not in control of the network, markets or price and are very motivated to make Sia succeed in order to generate income in SC. Say what you want, but it is clear that they care about price of SC but what we think they wanted to say is that they are not in control and cannot affect it other way than by their hard work and more people using Sia. The price depends only on supply and demand and markets are tools to help traders discover it.

## Siafund (SF)
Siafund is a supplementary token of the Sia network with only 10,000 SF that will ever be in existence. Unlike Siacoins, which can be divided up, a single SF cannot be split. They are only transferred or held in whole units.

You can hold it in the same wallet, but will never see it mentioned (at least in Sia-UI) unless you have one. These tokens are securities, and you can read more about the landmark [2019 SEC settlement that declared them so](https://sia.tech/settlement2019).

They are used for **revenue sharing** on the Sia network; a **3.9% fee from every storage-related transaction on Sia** is distributed to the holders of Siafunds. The developers (Skynet Labs) currently hold approximately 85% of all Siafunds while the remaining approx. 1,500 SF were distributed to the community in a total of three offerings since 2014.

## Where to buy?
If you are interested in buying Siacoin or Siafund, check our [Trading guide](/discover/trading-guide/index.html). It will lead you through everything you need to to know in order to securely and responsibly manage your assets and execute trade orders.

*Written by: Danger & Covalent, Last Edit: April 14, 2021*
