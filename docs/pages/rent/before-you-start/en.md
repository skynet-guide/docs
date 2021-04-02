# Before you start
While the Sia network is great in many ways in comparison to traditional storage providers (mainly censorship resistance and speed through parallelism, read more here), there are several things that you should be familiar with before you spend any money or time setting up your own renter, portal, or host.

> This article will make you aware of these issues while also offering another view. One, where many developers and community members are working hard to make our decentralized dream into reality. One, where there are not always the resources needed to get it done as soon as we would hope. But to be fair, other projects in the “decentralized” space have much worse issues, very often not only being technically wrong, but fundamentally. And it seems that even with many times higher funding, it’s not about the money. It is about how it works… and in this matter, Sia keeps moving unstoppably forward.

## Renting
Below are a couple of things to consider before renting.

### Minimum File Size
The minimum file size is **40MB**. This is due to erasure coding and the minimum sector size on Sia.

> If you are trying to store a bunch of small files like a photos, songs or documents, either archive them together or don’t use Sia to store/back them up. If you were to store a bunch of 4KB files, you’d be over spending by over 1000x. To learn more about why, read here.

### Only One Computer at a Time
A Sia node can only be used on one computer at a time due to how file contracts work, so don’t expect a full dropbox-esque experience of having it on every device at once.

### Blockchain vs. Smaller Devices
In order to sync the blockchain, you must download and maintain a ~22GB consensus file which makes a full Sia node completely impractical to run on anything but a mid-to-high tier desktop computer. This means **you won’t be running a Sia node on your phone anytime soon**.

> One way around this issue is to use Luke Champine’s `us` (see [here](https://github.com/lukechampine/us)). It allows you to use something called a `shard` node which can run the consensus on a remote server for many clients at the same time, thus shifting the load away from the edge clients. In such case you have to depend on centralized server, even if it’s yours.

> Another future option is the planned implementation of [Utreexo](https://dci.mit.edu/utreexo), which would effectively allow you to run a full node but instead of having to store the whole chain history, you’d only have to store the chain state (which would be around 50 KB). This would be great, but due to the [Sia Foundation]() being in its infancy, I wouldn’t expect Utreexo to be complete till at earliest 2022.

### Backups are Unreliable
If you are to run your node continuously and you never run into any bugs (which actually aren’t too common in `siad`), you likely will never lose a single file over any period of time when renting on Sia. Only issue is, it isn’t exactly practical to constantly run something like a Sia renter node and this is where backups come into play. The renter node can be backed up in two ways:

1. **Back up the `renter` folder.**
Backups of the `renter/` folder become completely useless if any of the contracts are updated. That means uploading a file, downloading a file, etc will make your backup meaningless. This is due to the nature of the host and renter having to have synced contracts, so if they fall out of sync, you can’t do anything with the contracts anymore.

2. **Take a contract snapshot to take advantage of seed based file recovery.**
Seed based file recovery is currently unreliable. It is quoted as 95% reliable by the devs, but some users can less lucky experience. Though even if it does work, it only saves a contract snapshot and cannot be deleted. So if you upload a file after the snapshot, it cannot be recovered.

> Covalent: “I cannot speak on others experiences, but in my personal experience seed based file recovery has a reliability of 50% at best. It SHOULD NOT be relied upon for important data, treat it as a nice to have, not a foundation to rely on.”

While Sia Foundation is expected to address this, it might take some time. Until then, if you are looking for something more reliable, one such way is to use Skynet or some of the [apps built with it]().

### Development of Sia-UI
The community understands that developers started this all with good intentions but also for profit. Investors backing up development expect some results which made it difficult to justify development of features that do not directly bring results as for example Skynet can. This is the main reason why the team didn’t have much time for Sia-UI in 2020 and why some things were seen as a priority over things mentioned above.

In order to change this unfortunate state of the community and the devs being at odds, as well as give Sia-UI and other participants of Sia’s ecosystem some love and features they deserve, Sia Foundation was created.

The Skynet Team doesn’t have much time for anything but Skynet, but luckily the head of the Foundation, Luke Champine, is quoted saying that they will be hiring a UI dev within the year to work on applications like Sia-UI, so that's exciting. There are other option to store your data in the meantime though, namely: [Skynet](https://siasky.net/), [Filebase](https://filebase.com/), [Storewise](https://storewise.tech/). Though, you have to keep in mind that they are effectively centralized service providers with a dash of decentralization, not the same fully-permissionless-ness of Sia-UI.


### Storing Less Than 1TB isn’t practical
Due to the contract formation fees of contracting hosts, if you’re storing less than 1TB of data, you will end up spending the pricing is inflated greatly. This is becase you need to form some number of contracts no matter how much you plan to store and the more you store, the smaller part of your overall expenses will be spent on contract forming.

Now if you understand all that and still wish to rent on Sia, feel free! Check out the [Renting Guide]().

## Before You Host:
It’s good idea to start small, get familiar with it and then add more storage when it makes sense for you.

To be continued...

## Before You Mine:
Coming soon

*Last Updated by Covalent (March 29, 2021)*
