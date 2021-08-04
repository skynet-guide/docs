# Renting
As gone over in the introduction to Sia article, Sia is `decentralized storage platform`. It is composed mainly of three parties, renters, miners, and hosts. In this article, I will be going over the renter module; so I will be going over what it is, how it works, and how you can set one up today.

## What is renting?
In essence, a Sia renter nodes only do a couple of things. They pay hosts to store data for them as well as paying the host to download that data once uploaded. They do that in tandem with fancy math and a dedicated cryptocurrency to make sure the data is safe and highly available. Now, of course, in practice it’s a tad more complicated than that. But that’s all you really have to know in order to use it. So if you don’t particularly care about the technical side to it but want to store data on the Sia network, just skip to the [Setting up a renter](/rent/renting-on-sia/index.html) section.

## How does it work?
Before reading this it is probably best if you read the [Introduction to Sia](/sia/introduction/index.html) article written by Danger so I don’t have to re-explain everything.

Okay, now that you have read that, how does a renter node actually work assuming there is an established network of hosts and miners already doing their jobs? Well the main components/aspects that make a functional renter are following in no particular order:

- Host selection algorithm
- Redundancy
- Storage contracts
- Erasure coding
- Encryption

### Host selection algorithm
The host selection algorithm in `siad` is relatively simple. It effectively polls all hosts that are accepting new renters, checks their prices and response time, then chooses hosts based on those parameters and arbitrary weights the devs put on certain aspects of the hosts. For example, the devs may think that performance is more important than download price, so even if a host has a very cheap download price, `siad` may choose a host with lower latency to give a better experience to the user.

> Note, `siad` is the main module that pretty much everything Sia based is built upon. It contains the basic renter, host, miner, wallet, etc functionality necessary to use the Sia network. There are minimal clients available like [Luke Champine’s `us`](https://github.com/lukechampine/us), but none are actually usable to an average user, they require custom built tooling to actually function unlike `siad`.

> Also the name is derived from Sia + daemon, so `siad`.

Due to the decentralized nature of Sia, fresh renter nodes have no idea what hosts are reliable, fast, or really any metric that isn’t being advertised by the hosts(so basically anything but price). So often when new nodes are created, the renter has to “churn” a bunch of bad hosts before it can reach a set of hosts that is reliable enough to use. This can make storing < 1TB of data seem inexplicably high in comparison to what is advertised on the [Sia website](https://sia.tech/) or [Hakkane’s Siastats](https://siastats.info/storage_pricing).

### Redundancy
This is kind of a basic component to the renter node, but the whole idea of Sia hinges on this to be price competitive; hosts don’t have to be reliable. Generally, for high availability, the amount of nine’s of uptime counted is the most important factor, so 99.9999% uptime would be good, but not incredible. The whole idea is flipped on it’s head with Sia, if a host is above 95%(that’s a week or so of downtime a year) uptime, it’s probably fine. One may say that this would make renting prohibitively expensive because you have to pay for the data multiple times, but this is contradicted by the fact that if you don’t have to have incredible uptime hardware costs are lower. You can cut costs by just not paying for a lot of the “traditional server” setup. To have a storage server traditionally, you’d have to pay for stable power, buy UPSes, purchase good dedicated internet, *pay for the facilities*, etc. But with Sia you can have a bunch of 8GB raspberry pis, with a couple of 12TB hard drives connected to each one in your basement and that’s it. Costs can be greatly reduced through cheap hosts, throughput can greatly increase due to parallelism, and reliability can greatly increase just by paying multiple hosts to store the data.

> By default, the Sia renter uploads each file 3 times, so 3x redundancy. Though it is a tad more complex than that because it also uses **erasure coding** to increase reliability.

>Also Skynet uses 10x redundancy because 3x wasn’t fast enough when it was initially created. Learn more in [Introduction to Skynet](/skynet/introduction/index.html). Though this is actually changing. Basically, the base sector(used to find the file on the hosts) is going to stay at 10x redundancy, but for anthing over that it will be stored in a 3x(10 of 30) redundancy scheme to lower costs. For something like video streaming, the origional 4MB sector should store a couple seconds worth of video(5 seconds at  8mbps) which should give `siad` plenty of time to find the location of the rest of the sectors.

### Storage contracts
Storage contracts are the magic that make Sia a truly permissionless storage network. On a high level, a storage contract is a payment channel between the renter and host with some metadata on top of it; for more info on payment channels listen to this [talk](https://www.youtube.com/watch?v=Hzv9WuqIzA0).

>For those that don’t feel like watching that, but want the gist of payment channels, effectively one party puts in a certain amount of crypto into a “smart contract.” This money is unavailable until the arbitrary end date of this contract when it will be resolved. Whenever the sender(in this case the renter node), wants to send money, instead of sending a transaction over the network and having to wait an hour for multiple confirmations, the sender just adds some coin to the “sent” section of the payment contract, then signs it. The other party(in this case the host) sees this signed contract, and knows that it can safely broadcast this later to get the money inside the channel. The sender cannot revoke this money sent because it has already signed it, and it cannot be iterated downwards, because the receiver could always just broadcast the transaction with more money to make more money. So this is safe way to send money with latency in milliseconds instead of hours.

Anyhow, storage contracts have one other thing built in that makes them special in comparison to plain payment channels. This is the storage proof. What this means is that the host doesn’t only have to have the signature of the renter in order to take the money from the channel, but they have to prove that they still have the data from the renter by submitting a Merkle tree root that combines a hash of the data and some entropy to make sure that they cannot prove it in advance.

I’m gonna stop here because it can get incredibly complex and nuanced, and you can learn more about it [here](https://bitcoin.stackexchange.com/questions/10479/what-is-the-merkle-root). But, basically, just know that the storage contract is the thing that allows the Sia network to function without trust.

> One more thing to note. It is often brought up how the minimum sector size with Sia is 4 MiB. And the reason the team originally made this decision is actually because of the limitations of the storage contract. You can read more about it from Luke [here](https://forum.sia.tech/t/core-development-small-sector-support/77/5). The basic idea was that Sia was originally based on 64B “segments”, but since storing one Merkle root is 32B, this made it so if you were storing 2TB of data, you’d have to store 1TB of metadata. They quickly saw this for what it was, a big issue. So in order to solve this problem, they tried to take a middle ground in “sector” size and take the root of that instead of the “segment.” They chose 4MiB as a nice middle ground between metadata size and performance arbitrarily. So if you now upload any file, it’ll be padded to 4MiB no matter the size in order to fit inside that sector. This is being actively worked on to be reduced.

### Erasure coding
Erasure coding is the second trick Sia uses to increase the availability of data. For a technical explanation, read [this](https://oceanstore.cs.berkeley.edu/publications/papers/pdf/erasure_iptps.pdf). If you didn’t read that the basic idea is this, fragmentation of data provides a far greater amount of reliability than redundancy does. So in order to take advantage of that, a normal Sia renter node uses a 10 of 30 scheme. So basically, instead of just uploading each sector to a different node 3 times, it does fancy math to zip-tie 10 sectors together make it so any 10 of the 30 uploaded sectors can retrieve the data of what was originally put in. Unfortunately, this does come at the cost of increasing the minimum file size to 40MB, but the devs thought it okay to do that because it made the renter node much more reliable.

>Side note, Skynet does not use erasure coding because it wasn’t fast enough on release, learn more in [Introduction to Skynet](/skynet/introduction/index.html). Again, as stated earlier, this is somewhat changing.

### Encryption
Encryption is effectively just fancy math that allows you to take data and a “password”(also knows as a private key), then turn that into another piece of data that can only be viewed if you have the corresponding private key. To get a better explanation with nice visuals, check out this [3blue1brown video](https://www.youtube.com/watch?v=S9JGmA5_unY).

Technical details aside, the use of encryption makes it so you can safely send sensitive data to hosts without worry of them being able to view it. You never send the private key of your data to the host, so to them it’s just random jibber-jabber that they get paid to store. Security wise, it’s the same as just using a hard-drive you own.

### Setting up a renter
To set up a renter, follow the steps in [Renting on Sia](/rent/renting-on-sia/index.html).

*Written by: Covalent, Last Edit: April 14, 2021*
