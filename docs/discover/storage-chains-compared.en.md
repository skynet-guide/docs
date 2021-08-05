# Storage Chains Compared
This comparison has been made to let you understand the pros and cons of the “leading” projects in decentralized storage. Don’t expect any scoring or a table – many projects have these made in a way that highlights their own project and misinforms users about the others. We are trying to make the research easier for you and provide you with the technical information in easy to understand way.

## Chains compared: From a Technical Perspective
In this section, I will be breaking down the technical differences between the major players in the “decentralized” storage space (quotes will be explained later). Though, keep in mind that I am prominent in the Sia community so all of my opinions obviously have a bias and should be taken with a grain of salt.

First off, we need to decide which players to consider in the breakdown. I have settled on four competitors.

### Filecoin
When people think “decentralized storage” this is the first thing to come to mind. **They had a massive ICO that raised over $250M** and a darling team from the decentralized community behind the product (Protocol Labs) which have previously developed IPFS (see more [here](https://ipfs.io/)). To say the least, hopes have been very high for Filecoin and they finally reached mainnet after many years of work on new tech in late 2020. So, since they are the big name I’m of course going to include them in this comparison.

### Sia
Started in 2014, Sia was one of the first “decentralized storage” protocols to come to fruition. Not only that, it has been in mainnet for years now which has allowed a small but dedicated group of devs to work on the project. **Total development cost over the years was around $6.6M for Sia and another $3M was raised for the development of Skynet in 2020.**

> It’s also worth mentioning that Sia never had an ICO and is the only of these projects that didn’t fund the development with the network’s own token, Siacoin (SC).

Skynet is an interesting L2 (layer two) solution addressing content distribution that was released in early 2020 (which you may be reading this on right now) that utilizes Sia’s decentralized storage and makes Sia a good point to compare against.

### Storj
Storj was another one of the crypto projects that started in 2014. They released Storj v1 for public beta back right at inception and have aggressively targeted b2b customers by posing themselves as an S3 drop-in replacement. This has recently culminated in the real public release of Storj v3 through [tardigrade](https://tardigrade.io/). **Storj raised $35.4M through multiple funding rounds, though most of it ($30M) was raised during its ICO in 2017.**

### 0Chain
0Chain is a tad different than the other competitors due to its eccentric take on the network architecture. For example, their decision to do all transactions on-chain with sub-second block times is quite the contrast to Sia’s approach of the usual Bitcoin 10 minute block times.

Despite 0chain not actually being in mainnet (which I was considering making a requirement to be in this comparison), I think the tech is advanced and interesting enough to warrant being part of this. **0Chain raised $5.9M during its ICO in 2017.**

## What is to be Compared?
I thought the most important things to consider when comparing the technical sides of these storage chains would be the following:

* Consensus Algorithms
* Block time (and why)
* Enforcement of data retention
* Content distribution
* Sector size
* “Decentralization”

Let us begin.

## Chains compared: Consensus Algorithms
This section is undoubtedly the most complex of all of the sections due to the wild variance between the different chains and how they find quorum. There is a good chance that I mess something up. If you do find anything wrong, feel free to send me a message on discord (I’m ℂ𝕠𝕧𝕒𝕝𝕖𝕟𝕥#5766 btw).

### Filecoin
Filecoin uses an odd variation of PoS (proof of stake) called PoSt (proof of space time). It effectively works by creating a “power table” by testing the usable capacity of the hosts that offer capacity to the network (also used capacity by users provides more power than just plain storage offered to the network). Then a “randomness beacon” is used to select a random host weighted by the power table. So if a miner offers twice the capacity of another miner, it is twice as likely to get chosen as the block leader. This block leader can then use previously grabbed transactions and form a new block-based on them (making sure to pay themselves). Read more [here](https://spec.filecoin.io/systems/filecoin_blockchain/storage_power_consensus/). This method of consensus is unproven and has its own set of issues; namely that the host and the miner (who have separate interests) are now acting as one entity. And due to the cutting-edge nature of the tech, we just don’t know when these motives will clash the hardest and when the algorithm will fall apart. Though, only time will tell how it plays out.

### Sia
Sia uses a near identical consensus algorithm as Bitcoin. I’m not gonna go into too much detail here because the fundamentals are much better explained [here](https://www.youtube.com/watch?v=bBC-nXj3Ng4) by 3blue1brown than I ever could, but the basic idea is as follows:

1. People broadcast transactions into the transaction pool. These transactions include a fee that is an incentive for miners to choose their transaction over others.
2. Every miner looks into the transaction pool and grabs those transactions that’ll make them the most money. Then they create a transaction that will give them the block reward and incorporates the last block into a new one that ensures the immutability of the blockchain.
3. Every miner then repeatedly tries to “hash” their respective newly created block with specialized hardware specific to the task called an ASIC (application specific integrated circuit).
4. Finally, whoever gets a special number from this hash first gets to claim their block reward by broadcasting the block to the network. That makes the block part of blockchain and entire process repeats over and over with a next block.

This is a dramatic over-simplification of PoW and I highly recommend the 3blue1brown video for those who want to understand it in more detail. But the essence is that very expensive and specialized hardware and a huge amount of electricity are used to perform effectively useless computation in order to make money and secure the network. It isn’t particularly efficient, doesn’t scale super well to a huge number of transactions, and requires a long block time to function properly; but it is extremely resilient to any number of attacks and has proved to work very well at its job through the success of Bitcoin which runs since 2009 with 100% uptime.

### Storj
Storj is the only project in this comparison that doesn’t have its own chain; the platform is built on Ethereum (currently built on PoW (proof of work) but exploring ways to change that). As described [here](https://forum.storj.io/t/why-does-storj-use-the-storj-token/2987/38), the reason they decided to build on the Ethereum network is because of the simplicity of using it as a method of exchange. From the start, Storj was never intended to be a true “decentralized storage” network. The idea was more of a ploy for distributed storage (this is further explored later in the “decentralization” section) and when the team looked at their options for paying the storage providers, using something like a coin on top of Ethereum just flat out made more sense.

First, they could mint money to pay for development. Then, more importantly, they could get away from centralized payment providers like Paypal which would have taken a massive chunk of their profits.

In any case, if you’re interested in how Eth consensus works (to get a better grasp of how Storj functions), see [here](https://ethereum.org/en/developers/docs/consensus-mechanisms/pow/).

### 0Chain
0Chain is the only network here that uses PoS (proof of stake). PoS was introduced in 2016 and is at the cutting edge of blockchain tech. Only a few coins have moved to it, namely Dash, Polkadot, and Stellar. The actual details (like everything in crypto) are quite complex, but you can read about it [here](https://drive.google.com/file/d/1KcfkQ1HmtGXvXzZtalNkVHMmIcwOiA7k/view). The short version would look like this:

1. Every miner that wants to take a place in the “active set” of miners and sharders has to lock up some ZCN to the network.
2. Then, at every rotation period, some of the “active set” are rotated out, and the actors with the highest stake (squared) get chosen to join the set.
3. The miners secure the network in return for coin and the sharders aggregate old blocks and serve them to those who request them in return for coin.
4. Because the miners are “centralized” and limited to a set of thirty, transactions can be verified extremely quickly, though this does come at the cost of more trust being necessary to run the network.

The big issue with PoS is the lack of resiliency, the untested nature of new tech, and the focusing of wealth at the top. If a PoS network goes down for a couple of days, it likely won’t come back because the nodes will never be able to settle on the true consensus. This is unlike PoW where it is very easy to verify chain weight and find consensus even after massive downtime by major shares of the network. Then there’s the fact that PoS hasn’t been tested thoroughly, there could be a myriad of issues that are completely unforeseen. Then of course there’s my major issue with the network, the incentivized wealth inequality. In reality, it’s unlikely that the network would ever go down for that long, and it’s not like the code hasn’t been reviewed, but the fact that the entire network’s “Sybil protection” is created in order to funnel wealth to the top just doesn’t sit right with me. Also if you didn’t already know, squared staking is squaring stakes to give the wealthy exponentially more influence over the network.

## Chains compared: Block Time
Block time is how long it takes for a transaction to go through on the network. There can be a myriad of reasons to have different block times depending on what the devs want for the network, but it’s good to keep in mind that the longer the block time is, the more likely it is for the network to be secure and the more ease of supporting nodes that are far apart.

### Filecoin
Filecoin uses a variation of PoS (proof of stake), PoSt (proof of space time) as described above, the block time is thirty seconds on average. This is a bit odd to me because it’s actually quite slow. Payment channels would be necessary but it still poses the issue of malicious miners screwing each other over by propagating outdated chains. Transactions are fast, which is nice for money transfers, but to me at least, this seems like kind of the worst of both worlds. You can read more [here](https://docs.filecoin.io/about-filecoin/network-performance/).

### Sia
Since Sia is very closely based on Bitcoin, the block time is also ten minutes. The network itself is not designed for fast on-chain transactions and is only really meant for three things: transacting money (of course), creating payment channels (allowing instant payments between renters and host), and verifying storage contracts. So the slow block time isn’t really an issue since majority of all transactions happens in payment channels that are settled on-chain when the storage contract expires. *Did anyone say lightning network? 😉*

### Storj
Storj is the only “dstorage” solution to not employ their own chain. As described above, they decided to use the Ethereum network due to the easy deployment of a coin on it. Because of this decision, the block time is twelve seconds and needs to deal with the consequences of sharing blockchain with other projects.

### 0Chain
0Chain is interesting in this regard because it is the only chain that uses a high-frequency block time and “sharders” to handle the significant overhead of a chain that is secured with this method. Blocks occur every second or so on average, and because of this, payment channels aren’t really used to pay blobbers for storage.

Side note, the transaction times can be this low without issues because of the nature of PoS. While I have my qualms with PoS in general, I do recognize this as one upside to the tech.

## Chains compared: Enforcement of Data Retention
There are many different methods that can be used to enforce data retention on data store-ers, all having their individual ups and downs.

### Filecoin
Due to Filecoin using PoSt( proof of space time) the entire network is designed around enforcement of data retention.

1. When uploading a chunk of storage to Filecoin, the renter has to send some money to the host, and the miner has to “seal” this data into something that can be easily used to prove that they continue to store this data. When sealing, some Filecoin (the token of the same name) is also required to be locked up as collateral.
2. Then, every time prompted by the network, the miner puts up proof that it still has the original storage that it was intended to store.
3. If successful, the miner gets to put that amount stored into its own “storage power” (which is equivalent to hash power on a PoW network), and gains block rewards for doing so (as well as the coin sent by the user at the beginning).
4. If the miner fails to provide valid proof, then they lose reputation and get “slashed”. Getting slashed means that they lose the collateral.
> When a miner fails to keep his promise, it means also that only backup of the user’s data was irreversibly lost since Filecoin doesn’t use redundancy.

### Sia
Sia uses a special type of smart contract called a “file contract”. This file contract effectively does two things:

1. It locks up coins from the renter and host until the “proof window” hits and the host can submit proof to the network to prove that they still retain the data that the renter originally uploaded. Unlike something like Storj, there is no trust in either party, and the chain itself is the one that decides if the contract is valid or not.
2. It facilities functions like downloading and uploading through RHPC2 (renter host protocol two) and now RHPC3 (renter host protocol three).

When the contract successfully expires, the host receives both the collateral and reward. The host can set the collateral to anything they want (even to nothing) but any sane host selection algorithm makes sure that the host it’s using has a decent enough collateral multiplier to incentivize the host to keep the data safe and always available.

> If the host fails to keep its promise, all locked up coins are burnt and one fragment of the user’s data is lost. However, thanks to redundancy there are many replacements that allow reconstructions of the fragment and re-upload to different hosts.

### Storj
Unfortunately, the actual enforcement of data retention isn’t super clearly documented, the best resource I’ve come across is [this](https://www.storj.io/blog/2018/12/decentralized-auditing-and-repair-the-low-key-life-of-data-resurrection/). In essence though, each Satellite (the interface between the storage operators and the clients) does the enforcement of data retention all on their own. Each Satellite has its own subset of storage nodes that it knows have a good reputation and it trusts, it uses these hosts to upload data to. Then it, at regular intervals, checks random data segments with something called “Berlekamp-Welch” error correction to make sure that the data is still there. If it is, nothing happens. But if it isn’t there, the reputation of that host gets docked and data is migrated to a new host. It’s quite simple actually.

Unlike the other three options, there isn’t chain-level enforcement for data retention; the Storj token is strictly a means to move value at a massive scale at a low cost. So, this means that the network is relatively trusty when it comes to stuff like payments (the storage operators just have to trust the satellites will pay them).

### 0Chain
0Chain is quite similar to Filecoin in that the network itself ensures data retention by regularly challenging the hosts and requiring proofs. The idea of it is this though:

1. The user and “blobber” (hosting nodes) form an agreement on pricing for bandwidth and storage.
2. The user allocates funds to the “blobber reward pool” to be used for future payment.
3. The user uploads data to “blobbers” and money is moved from the “reward pool” to the “challenge pool”.
4. Then the network regularly challenges the blobber and requires proofs for the data it claims to store.
5. If the blobber provides valid proof, the funds from the challenge pool will incrementally be moved to the host’s wallet where it can use that money as it pleases.
6. If the blobber doesn’t provide valid proofs, it gets punished for its failures and the coin gets burned.

## Chains compared: Content Distribution
Content distribution is a bit of an oddity in the decentralized storage space for one main reason, people that want to watch videos in a browser don’t want to run a full node. Though, because of the nature of the space, full nodes are necessary in order to retrieve files. Different networks take different approaches to adding incentivized middlemen in order to distribute to the layman.

### Filecoin
Filecoin’s content distribution network is kinda odd to say the least. Since data has to be “sealed” to be counted as provable storage to the chain, and since this takes so much computation to do or undo, it really isn’t practical for the Filecoin miners to serve data.

For reference, a 1MiB file can take 5-10 minutes to unseal, and a 32GiB file takes 3 hours to unseal on the minimum hardware requirements (which are 128GB of ram, 8 cores, and an SSD btw). Also, at this point, IPFS (a previous project by Protocol Labs) is effectively dead development-wise due to the lack of incentive structure.

To address this issue, the Filecoin devs introduced a method to store cached and unsealed versions of the data while also storing the same data as sealed in order to provide proofs to the chain. This has the obvious issue of the miner having to store double the amount of data, while also posing the problem that unless this data is frequently accessed, the miners won’t store it because it won’t make them money.

So something like a Google Photo’s equivalent on Filecoin really just isn’t practical because the data is infrequent enough where it doesn’t make sense to cache, while also being something that needs to be low latency (which is impossible if the data has to be sealed/unsealed often). Read more [here](https://docs.filecoin.io/about-filecoin/network-performance/#data-retrieval).

### Sia
The Sia network has had a dedicated content distribution platform for about a year now called Skynet. I delve into more detail about it [here](/sia/introduction.html).

The gist of it though is that there is a “global file space” of things called Skylinks (Skylinks are 46 character long unique identifiers based on the “Merkle Tree Root” of the file). Any node (Skynet nodes are called portals) can access any Skylink by pinging hosts that it is contracted with until it finds the file and can send it off to the user. There is also another layer to this called “SkyDB” which allows for mutable file pointers as well.

The tech is new, there are things to improve and bugs to fix, but in comparison to the rest of the space, it’s very fleshed out. Try out Skynet [here](https://siasky.net/).

### Storj
Content distribution through Storj is actually quite simple. Due to the nature of the data only being accessible through the S3 gateway of centralized data Satellites, any data can be made public, and you can send anyone a link to that data easily. The downside of this is that for network throughput to scale, you have to have Storj Labs add more Satellites to the network because the Satellite software isn’t currently available to the public to set up themselves unlike Skynet Portals or 0Chain block explorer.

Also, something to keep in mind is that due to Storj’s fixed pricing scheme for paying hosts, the hosts have to be paid $10/TB for egress, though different front ends charge different amounts. [Filebase](https://filebase.com/) charges $15/TB and [Tardigrade](https://www.tardigrade.io/) charges $45/TB. So no matter what, egress will always be somewhat expensive because pricing isn’t decided by a free market, unlike the other three competitors.

### 0Chain
0Chain (as of now in the beta net) and Sia have somewhat similar approaches to content distribution. 0Chain has points to interact with the network; in essence, it is a lite wallet and renter combo. A server does all the work, keeping up with the consensus and proxying traffic to the browser.

All files are globally available because they are stored, proven, and maintained by the chain. The eventual goal would be for every client to run a “full node themselves” (which is actually theoretically possible due to sharders dealing with the consensus portion of the network significantly reducing the load on the client), but a js/wasm is yet to see implementation.

## Chains compared: Sector Size
The sector size is often something that is ignored or not considered by someone new to the space. Effectively, sector size is the minimum amount of data you can send to the host and pay for. Different networks call it different things, and different networks have different sizes, but in essence it’s the smallest amount of payable storage.

### Filecoin
Filecoin actually has a fixed 32GiB sector size which is quite unwieldy. Also, for each 256B, 2B are reserved for proofs. Read more [here](https://docs.filecoin.io/store/lotus/very-large-files/#maximizing-storage-per-sector). So what would normally be a 32GiB sector(34,359,738,368B) would actually store 34,091,302,912B. This isn’t a huge cost, but it does mean ~1% of storage paid for is just proofs. Also, another thing to keep in mind is that everything to be sent to a Filecoin miner must be in a [car](https://github.com/ipld/specs/blob/master/block-layer/content-addressable-archives.md) file which can be somewhat compute-heavy on the client-side. This is in contrast to other networks where you just send the host a binary blob and you’re all good.

### Sia
I have talked about Sia’s minimum sector size at length [here](/sia/renting.html), but the gist is this: at a protocol level, the minimum file size is 4MiB. This is done so the metadata doesn’t take up too much space on the renter (for 64B sectors, there would be a 1:2 metadata to data stored ratio). This is planned to be addressed at some point by adding a 64KiB option to sector size, but that has no planned release date. Due to the 4MiB sector size, it is not price efficient to store small files without compressing them first, but it’s fine for anything else (raw photos, videos, archives).

In addition to that, Skynet (Sia’s layer two) allows different handling. While nothing changes for individual files (they take the size of a full chunk if they are smaller), a lot changes for folder uploads. Folders uploaded to Sia hosts through Skynet have their contents automatically packed into the 4 MiB chunks to allow you to store even large collections of tiny files efficiently.

### Storj
Storj is kinda odd when it comes to sector size because of how their network infrastructure works. As described above, Storj uses a set of centralized “Satellites” to aggregate data and ensure up-time of data for you, but because the Satellites (which are the ingress/egress points of the network) are completely in Storj Lab’s control, they can play some tricks to improve their performance in this category.

For example, if the file is < 4KB then it just gets stored on the Satellites in perpetuity it never reaches the hosts. And since the insides of how Storj works aren’t really known, the sector size isn’t clear. What we do know though, is that the object fee is $0.0000022 per file stored. So if you were to store 1TB of 64KB files, it would cost an extra $25 roughly. Nothing spectacular, their storage cost is already $45/TB/mo through Tardigrade. Though, it seems that in their lack of decentralized-ness here they actually incurred massive cost savings. Read more [here](https://forum.storj.io/t/tardigrade-size-of-file-uploads/5976/13).

### 0Chain
As described [here](https://medium.com/@sculptex/distributed-storage-comparison-7c1b46ed480a) in a comparison article by Sculptex, 0chain also has a fixed sector size of 64KiB. This is quite impressive and is small enough to the point where if most people were just to upload all of their personal files to the network, most wouldn’t waste too much storage due to sector size inefficiency.

## Chains compared: Decentralization
I’ve used quotes multiple times when referring to these networks as “decentralized” because some of these networks just have less decentralization than others. I’ll go into more detail on what that means later on.

Filecoin
Something I didn’t touch on earlier in this article (because it wasn’t relevant to the other categories) is the absolute lunacy that is Filecoin’s hardware requirements for hosts. The base hardware requirements are:

1. 8 Core CPU
2. 128GB RAM
3. Beefy GPU
4. 1TB SSD

Read more [here](https://docs.filecoin.io/mine/hardware-requirements/#general-hardware-requirements). In theory, this wouldn’t actually change to what extent the network is decentralized, but you really have to think about who would actually have the resources to run a storage miner. On the other networks, basically anyone can run a storage node (most networks require at least 2 cores, 8GB of RAM and some storage), but on Filecoin, only big companies (or rich people) can run hosts. This significantly reduces the actual spread of the network, and is the reason many people (including myself) refer to Filecoin as a “decentralized marketplace for centralized providers.”

Also, conflating the storage providers and the miners on the network is a serious blow to decentralization because it makes only one type of machine able to participate on the network.

### Sia
Sia, due to the heavy influence of Bitcoin, took a “decentralize at any cost” approach and because of this is as decentralized as it only can be.

Anyone can run any node they’d like on low-end (in the crypto world at least) machines. This comes at the cost of renter having to run Sia at least once every month in order to let the software maintain file health (because trusting anyone but yourself to maintain files would cause a conflict of interest) and keep the hosts on their toes, but for those that want the true decentralization it’s the best option.

Also, the fact that Sia is based on PoW is a good sign for those that respect the tech. It’s very inefficient and wasteful by design and as such it is extremely decentralized, secure, and battle-tested.

> Skynet is not mentioned here because it’s a layer two and isn’t relevant for the underlying protocol. Actually it’s closer to an open-source product built on top of Sia that utilizes Sia’s features to its maximum and that anyone can run.

### Storj
Storj is interesting in the regard of “decentralization” because it really isn’t decentralized. The trust in the Satellites is utmost and the blockchain nature of the Storj coin itself is only really designed for efficient transacting, not decentralized enforcement of data retention. So that really leaves Storj as great “distributed” storage, allowing for greater data durability and the likes, but it’s not really decentralized. Now to be fair to Storj, they really weren’t aiming for “full decentralization” anyway, so it’s not really a big deal. But it is a good thing to keep in mind.

### 0Chain
0Chain is interesting in this regard because they actually did a great job in splitting up every possible role on the network. There are miners for mining coins, blobbers for storing arbitrary data, and sharders for storing consensus; this is a stark contrast to Filecoin where they made all the nodes do all the things, creating conflicts of interest. But at the same time PoS is unproven, squared staking is a funnel of wealth to the already wealthy, and the fact that KYC is required at the launch of their main-net to be a miner should make anyone with knowledge of decentralized systems seriously uncomfortable.

## Okay, so who wins?
Earlier I definitely interwove my opinions into the writing but I tried to stay mostly informative instead of trying to spread my ideals. Here though, I’m just gonna say what I believe (keep in mind that I’m an active Sia community member and what I’m saying is likely highly biased).

**I think that Storj and Filecoin should immediately be eliminated from this running.**

Filecoins issues are:
- **Transfers are egregiously slow** due to the seal/unseal process.
- There are conflicts of interest due to conflating miners and storage providers.
- PoSt is unproven to actually be resilient against attacks
- Hardware requirements are stupidly high.

**Storj just isn’t really a decentralized storage provider**. If you’re in the market for distributed storage though, check out [Filebase](https://filebase.com/) (they’re a storage provider that works both on Sia and Storj for the back end).

Then who wins between Sia and 0Chain? Well, right out of the gate one we have to keep in mind that **0Chain just flat out doesn’t exist yet**. It’s currently rapidly evolving in the beta-net stage and is slated to release in Q1 of 2021. The code is all public of course, but it’s not like you could begin to develop on it right now, it needs more time to mature. The promise of the chain handling contract maintenance sounds super awesome, as well as the idea of having “sharders” handle consensus so full nodes can run on literally any hardware. But my gripes as listed above in the “Decentralization” section are just too great; **anything in crypto that requires KYC to get a priority spot in staking in the network makes me incredibly uncomfortable.**

Now **Sia isn’t perfect in the slightest**, I list a lot of problems with it [here](/renting/before-you-start.html). But in the current decentralized storage space, it is the best option in my eyes.

Also with developments like [Skynet](/skynet/introduction.html), the creation of the [Sia Foundation](/sia/foundation.html), and the possibility of implementing features like Utreexo, the future looks bright for Sia.

To learn more about the insides of it, read an article Danger wrote [here](/sia/introduction.html).

## Honorable mentions
While the only actual usable/promising chains are broken down above, it’s not like they’re the only ones in the space. Some other honorable mentions are as follows.

### Arweave
Arweave gives the interesting proposition of immutable data forever stored on the blockchain.

The only issue is that **data isn’t incentivized to stay on-chain** because the miners don’t get paid more over time for storing the data. They only keep accruing more and more data which will, in all likelihood, lead to a fork in a couple of years to allow miners to ditch data. In my opinion, it’s a bad design and cannot practically hold more than a couple of KB per user and sustain itself.

*Written by: Covalent & Danger, Last Edit: May 3, 2021*
