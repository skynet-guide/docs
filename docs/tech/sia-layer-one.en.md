# Sia, Decentralized Storage (Layer 1)
Sia has been around for several years, slowly yet constantly growing. You maybe heard about it being decentralized cloud storage and started watching it. You maybe traded or mined Siacoin, or maybe heard about some forks and controversies. And maybe you just discovered it thanks to Skynet...

Whatever brought you here, you are looking for resources to understand what Sia really is and how it works. You want to know how this technology empowers users and how it turned a decentralized internet into reality through Skynet. This entire site is dedicated to guiding you through this exciting journey.

## Decentralized cloud storage platform
Sia is a **decentralized cloud storage platform**.

**Decentralized** means it has no central server or authority that could control the network on its own.

Every single **node** *(computer running the Sia software, for example your Sia-UI wallet)* is equal and has its own verified copy of the **Sia blockchain**. Imagine a blockchain like this: you have some set of information *(transactions)* being sent around, and every 10 minutes that info gets grouped together into something called a block. Then another 10 minutes pass, a new block is made, and is automatically connected *(chained)* to the one before it.

This forms a chain of blocks that is chronologically sorted and cryptographically secured in a way that makes it **immutable** *(cannot be changed)*.

>You can see **blockchain as a transaction history**. That means every single transaction ever made is final, you cannot change or refund it and so you need to be always careful. A good practice is to double or triple check wallet addresses after copy/pasting and check the first and last few characters just to be sure it wasn’t tampered by potentially present malware.

**Cloud storage platform** means that Sia is a platform allowing you to rent and pay for storage space elsewhere in the world for the purpose of having your own private, secure and ever-accessible backups.

The platform is using a **consensus mechanism** *(way of reaching an agreement on a state of the blockchain)* based on **Proof of Work (PoW)**. This protocol was first introduced by Bitcoin in 2009 and brought us a process known as mining.

> If you are worried about PoW, you might want to read <a href="https://blog.sia.tech/fundamentals-of-proof-of-work-beaa68093d2b" target="_blank" rel="noopener noreferrer">Fundamentals of Proof of Work by David Vorick</a>, a very detailed article about this topic.

**Proof of Work means** that miners need to spend significant resources on electricity and specialized *(often single-purpose)* hardware equipment in order to participate in search for a solution to a mathematical problem. This search involves a lot of *“luck”* as miners compete with each other who finds the answer first. Once they do, it is used to sign the new block which is then broadcasted to the network. If the network accepts it, the finder receives a **block reward** in form of **Siacoin (SC)**, the cryptocurrency used on the Sia network. This is how new coins are introduced to the network and further distributed by the miners, usually through the numerous exchanges.

>As many miners don’t want to depend heavily on luck, they are often working together by being connected to a **pool**. When a solution is found by a member of the pool, the reward is fairly shared between all who participated in finding that answer based on amount of work done by each of them.

What this means is that miners are providing service to the network. They are important for it but can be replaced if their intentions become malicious and threaten the network. But this combined with the block reward is a very good incentive for them to act in best interest of the network. To be honest and provide security because they are rewarded for doing so. Doing otherwise would be way more expensive than any potential gain from doing so.

Check our [Mining Guide](/siacoin/mining-guide.html) if you want to learn more.

>If you are interested what would happen if vast majority of miners demanded some changes, make sure to check out the story of Bitcoin’s failed “SegWit2x” fork. Long story short, it was a very important demonstration that the nodes are making and enforcing the rules, not the miners (even if it's a majority of miners, like 95%) even if backed by some of the biggest companies of the crypto world.

## What are the advantages of using Sia?
Sia lets you backup any data in a way that **only allows you to get to it**. No government, no authority, not even the hosts who keep **encrypted** fragments of your data can access it and know what the data is or who it belongs to. They simply can’t. If you are not familiar with **encryption**, it is a method that uses a digital key *(you can imagine it as a password)* to change *(encode)* any data into something unreadable and only way to read *(decode)* it is to have the key and know the method used.

>Since 2020, Sia software allows uploading to **Skynet**, which is a publishing layer utilizing Sia as a storage layer. It allows users to host apps and share content without need for any server or other infrastructure while focusing on **censorship resistance**. This means that if you want to make your data public and let others pin them, you can do so and in such case a host can tell what data you share (since you made it public). Check our [Skynet, Decentralized Internet (Layer 2)](/tech/skynet-layer-two.html) guide to learn more. Also it's worth mentioning that since mid 2021, Skynet code is no longer part of the Sia core software. Instead there is now special client combining the Sia and Skynet known as [Skyd](https://gitlab.com/SkynetLabs/skyd).

This feature is already interesting enough, but there is another factor other than security or privacy. Sia has open marketplace where **anyone can become a host or renter** and set their own conditions and pricing. This ensures that even if demand for Siacoin increases and the price surges, natural competition will normalize the prices so at any given time, you will pay more or less the price that represents the same or similar value in fiat currencies (USD, EUR, etc.).

>You don’t even need any permissions. Sia is **open-source** and **permission-less**. Anyone can start a node and start hosting, renting, and building products and services on top of Sia network. You can find many guides in other sections of this site.

The fact that anyone can become a host and offer his or her unused space to others means that there will not only be data centers with higher pricing for better service quality, but also individual users who will provide other quality service (for example with slower access speed), but for cheap. Since October 2020, hosts also support SkyDB, which is mutable decentralized database that any application can use.

You might now be asking, what guarantees that you won’t lose your data if such a host disappears? Well, **hosts are incentivized to protect your data** by providing collateral that is locked for a duration of your file contracts. If they lose your data, they will lose the collateral that is roughly three times higher than the expected reward. Also, by default Sia is using 3x **redundancy** which means that **when your file is split into 30 fragments, you need only any 10 of them to retrieve the file**. These fragments are stored at different hosts so if a host is down, the redundancy indicator temporarily decreases and fragments are automatically replicated at other hosts to ensure the 3x redundancy.

In practice it means you are paying for three times the size of your files, but it is still way cheaper and more secure than any other solution (most importantly, you need to remember that main feature is the decentralization).

You can also set your own conditions –  for example to have *(even more secure)* 16 out of 40 fragments with 2.5x redundancy, but the default setting is already pretty decent. Over time, as the network gets bigger and quality of hosts increases, it is expected that Sia will move towards 1.5x redundancy, which is sufficient and will make it even more affordable.

>Did you ever wonder **why there is minimum block reward** and are you worried about inflation caused by endless supply? It is so by design as the majority of coins in the future is expected to be locked in contracts. **Minimum block reward will guarantee** that there is always enough new coins entering circulation so **the network can continue working properly** and users will be able to acquire coins to pay for storage.

## Why is Sia important for me?
It’s important because** you care about your data and privacy**. You don’t want to lose your family photos or important data due to the end of some service *(remember Megaupload?)* or get it compromised by leaks, or even inaccessible at times when you need it most during some blackouts. You don’t want to get de-platformed.

With Sia this won’t happen and if 3x redundancy is not letting you sleep at night because of your super important data, set it higher and even whitelist specific hosts in specific regions *(so you can always access your data even if entire countries turn dark)*. Even then it’s **way cheaper than traditional solutions**, but more secure than any and all of them.

**You might also have unused space** on your home server running nonstop. Now you can start hosting and reduce your running costs or even profit from it. If it sounds interesting for you, we recommend to start small and get familiar with it. You can always plug in additional storage capacity when you’re getting near your limit. 

Maybe **you are a developer with some ideas** or just an enthusiast who wants to learn. Sia is opening a world of new possibilities and kinds of apps that were impossible until today, especially with the Skynet letting developers create applications without need for hosting by using simple API. See our other sections to find more information.

## Who is behind Sia and how can I know it will always work?
**Until 2020, Sia was developed by Nebulous, Inc.**, a VC funded company that made this all a reality with **less than $10 million raised** since 2014. Sia was always technically superior and leader in the space while remaining in shadow of less advanced projects that used an opportunity and raised enormous amounts of money during the ICO times.

**Sia never had an ICO or pre-mine. It is not even trusted setup.** All coins were mined by anyone who was interested in doing so, same as did Bitcoin. In 2020, the core team was holding less than 0.1% of all SC. The developers are motivated by possession of network’s supplementary token, Siafund (more about it in [Tokenomics](/siacoin/tokenomics.html)) which pays out part of successful storage contract fees on Sia network to its holders. Where majority of other projects raised a lot of money at beginning, focus on hype and buzz words and have no real incentive to ever introduce a working product while they fake it until they make it, Sia is complete opposite of it. In order for Siafunds to create meaningful source of income, the network has to grow immensely. 

>At time of writing (October 2021) Siafunds are not quite there yet, but the rapidly growing trend is becoming obvious with Sia and its Skynet being increasingly used by developers and very cool decentralized apps being released.

Common concern was that price has stagnated and project must be dead, but price says nothing about the actual progress that was made. Also there are no shortcuts for such tech and for first few years it wasn’t simply production ready. Sia is not just another wallet-only project with main purpose being to make money for the creators and insiders. Sia not only had grand vision in the beginning but also managed to get it done without retail money (not a single Siacoin between 2014-2020 was used to fund development). Where other projects and schemes can just make a token on Ethereum or quickly come with a copy that is "better bitcoin", it took several years to the Sia developers to get where we are now. So no, this is not the end and predicting future by the past performance is foolish because there is no other technology with this set of features. This is just a beginning.

Of course, Sia could go the same way as others and focus on price and marketing, but there would be no working product as a result. For working product, user experience is important and until 2019 it wasn’t possible. Bringing it to masses could cause irreversible damaged becase they tech wasn’t ready. Today it is. There are still things to fix and improve but it is fairly stable and with great things on the horizon - especially Utreexo and Hosting experience improvements.

Finally, it's worth stating that the network is permission-less and open-source, anyone can run it. If the dev team suddenly disappeared, it would continue running and very likely someone would take over its development. Which is actually something that already happened partially. Starting early in 2021, with Sia devs moving their focus to Skynet, Sia development moved under the newly established **non profit organization** named [Sia Foundation](/sia/foundation.html) led by co-founder of Sia, Luke Champine.

---
*Written by: Danger & Covalent, Last Edit: October 26, 2021*
