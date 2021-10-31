# History of Sia
Sia initially started as an idea by David Vorick in 2013 that he was discussing over email with Luke Champine, calling it “*the Nimbus network*”. After writing the first draft of the whitepaper in September (called “*Bytecoin*”), David shared it with college friends who together with Luke began programming a prototype. The project was then renamed once more to `Sia`*(the Egyptian god of perception, pronounced [sigh-uh])*.

It met with positive response on BitcoinTalk, and so David decided to work on Sia full-time as a startup. Together with Luke they applied for Y Combinator, a startup accelerator, and got through the initial screen but were ultimately rejected as the project would take much longer to build than anticipated.

They didn’t have to wait for their chance much longer. After one BitcoinTalk user abused David’s hand-drawn diagrams in order to fraudulently raise money, it was clear that there is enough interest to raise money via crowdfunding.

Not only was the crowdfunding successful, it also helped them with raising contacts and getting introduced to **Jim Pallota** and their first traditional investment funding. They formally incorporated `Nebulous, Inc.`, and soon after sold `Sianotes`, later convertible to `Siafunds` (*a supplementary token of the Sia network, see more in [Tokenomics guide](/how-does-it-work/sia-guides/tokenomics.html)*).


But Sia was a very different project back then. It used Proof of Storage consensus instead of the current Proof of Work (*explained in [Introduction to Sia](/how-does-it-work/introduction-to-sia-and-skynet.html)*), hosts were grouped into “*quorum*” that were responsible for storing users’ files, and the wallet was also fully scriptable.

Ultimately, David discovered issues in the Proof of Storage algorithm that forced them to start over, but thanks to David’s participation in the Bitcoin core developer community around that time, he became able to understand the unique challenges of cryptocurrencies and use this knowledge to lay a path towards the efficient and well-designed Sia platform as we know it today.

The re-created Sia was heavily inspired by Bitcoin, but improving some of its known deficiencies and using a transaction type that enables `storage contracts` *(digital contracts between those providing storage and paying for storage*). It became formalized in the second whitepaper titled *“Sia: Simple Decentralized Storage”* in November 2014 and the beta version was publicly released six months later with the `genesis block` being created on June 6th, 2015 at 10:13 EST.

The development continued over the years and steady progress was made through the **1.3.x** series. Despite many required workarounds, around that time some companies started working on first products using Sia. Today, you can see some of them in our Discover section. In 2018, many other interesting events happened. There was another Siafund offering and also development of ASICs being announced to the Sia network in form of the Obelisk project during summer 2017. This was in order to move on from GPU mining and provide better security to it and had heavy support from entire community.

>**Important part of Sia’s mining history**
>
>There were some hints late in 2017 but majority of the Sia community was surprised when early in 2018 Bitmain announced its Sia ASIC, Antminer A3 shipping in January. While inferior to the expected Obelisk SC1 miner, Bitmain probably wanted to be the dominant player in ASIC industry and as soon as Sia publicly announced its Obelisk plans, they rushed in using their facilities and knowledge and managed to ship inefficient but working ASIC as first to market. Community discussed the potential fork right away but we didn’t know the truth back then, so these miners were allowed to the network. However, just few months later thanks to research of the community it was clear what happened. Bitmain created many times more units than was healthy and killed everyone’s ROI (Return Of Investment) and by everyone I mean their own customers. Later it was discovered that Bitmain was mining for months on these units before dumping them to the customers. Sadly enough, there was only winner, Bitmain.
>
>Few months later, another manufacturer appeared with way stronger Innosilicon S11 miner and even if many miners still think today that Sia bricked their A3 with the following fork, the reality is simple – Innosilicon’s miners turned A3 into unprofitable devices long time before the fork even happened. In any case, even these miners were allowed to participate until it became clear during the summer that nearly 50% of all block rewards is going into single wallet address that doesn’t even try to hide it. What did it mean? This manuafacturer was not only selling expensive hardware to its customers, it cheated them second time by competing with them by running majority of network’s hashrate themselves. When the community realized what is going on, the decision to fork the network was inevitable. The community wrote a proposal that was well accepted, however different users had different ideas and the final look of fork was in hands of Sia core team. It was them who enabled Obelisk SC1 to be able of algorithm switch and while this change was pretty simple, it was enough to invalidate all other ASICs on the Sia network while still having at least one ASIC running to provide strong security.
>
>This fork happened on November 1, 2018 and was clear message from the community to the manufacturers to focus on manufacturing and selling, not competing with own customers. Also to provide sales numbers and be more transparent so miners can make educated decisions. Today (in 2021) there are devices from multiple companies mining on the network.

In 2019, Sia released version is **1.4.0** with codename `Draco` that was an important milestone in the history and probably the biggest release since 2015. Everyone could notice the complete visual redesign of Sia-UI, but even more happened under the hood, making Sia faster, more robust and ready for the features we’ve been waiting so long for.

The most important feature was introduced in version **1.4.2** that followed soon after. This feature was seed-based file recovery and allowed renters to take a snapshot of their backups and then recover from these backups on any computer just by using their seed.

Luke Champine also introduced `us` framework, a low level alternative API for Sia. While requiring more work from third party developers, it gives them way more freedom how to use Sia.

>A question we occasionally see is: **why Siacoin is not an Ethereum token?** It is because Sia was actually created before Ethereum existed. But even if it did exist, Sia is a very complex project and has specific requirements that only own unique blockchain and cryptocurrency can meet. It’s also a way to avoid dependency on some outside project or influence, or another network that can be bogged down by a thousand other projects.

At the beginning of 2020, version **1.4.3** brought us `Skynet`, first building blocks of decentralized internet letting us to upload and easily share any content – static web pages and data to start with. While the most of the development through the year was focused at it, Sia also went through a lot of performance and stability improvements including some important bug fixes. **1.4.4** then added support for uploading directories, encrypting skylinks, unpinning and deletion of skynet files and this trend continued in next versions.

Next major version was **1.5.0** known as `Equinox`.

`SiaMux` was added (multiplexer of connections that reduces the latencies of the communications between hosts and renters), also `Handshake` was integrated (decentralized domains allowing you to access Skynet content by human-readable links instead of hashes) and `Ephemeral Accounts` (payment channel technology allowing low latency and higher bandwidth for data transfers between hosts and renters).

This release was massive increase for scalability of Skynet, allowing Skynet Portals to handle 100x more traffic. It also activated `Renter-Host Protocol v3 (RHP3)` which allows faster and more efficient data transfers and is a foundation of many features of the Sia network. One of such features is the ability to host dynamic content.

In November 2020, Sia **1.5.1** introduced `the Skynet Registry`, a database layer on hosts that powers `SkyDB`, a mutable decentralized database that any app can use.

In early 2021 **1.5.3** with various improvements and fixes to recently added features. **1.5.4** is currently in testing with more fixes on the way as well as new features. This is also leading up to **1.5.5** where the Foundation fork will occur; Sia development will be directed by changes in two directions: Sia Foundation will continue improving Sia core tech in directions most requested by the Sia community as host stability, small file support or reduction of blockchain requirements with Utreexo. Skynet Labs will focus on Skynet and getting more developers and users.

In middle of 2021 **1.5.6** was released splitting the Foundation `siad` codebase away from the Skynet `skyd` codebase, followed by **1.5.7** in September that brought some important host fixes and updated list of bootstrap peers.

The team is currently focusing on two major things. Integration of **Utreexo** and **Hosting** experience improvements (hosting should eventually become easy enough that you don't need to study technical details deeply in order to avoid mistakes). These two are expected to render Sia-UI obsolete so part of it should also be a **new user interface**. It's for sure that next major update (1.7.0?) will be one of the biggest since 1.4.0, if not the biggest update ever.

---
*Written by: Danger & Covalent, Last Edit: October 26, 2021*
