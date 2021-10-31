# Skynet, Decentralized Internet (Layer 2)
Before reading this article, it is recommended to check [Sia, Decentralized Storage (Layer 1)](/tech/sia-layer-one.html) first in order to have a better bearing of how everything works, and who is behind the project. While the top level ideas can be grasped pretty easily, the design behind Sia can be pretty complex, so keep that in mind.

>Since the introduction of Skynet a lot of time passes already, but if you want to read the document that introduced us to the full vision of Skynet for first time, don’t miss <a href="https://blog.sia.tech/a-deep-dive-into-skynet-a0fa037feea" target="_blank" rel="noopener noreferrer">A Deep Dive into Skynet</a> on the Sia blog (published in Feb 2021). Also keep in mind that the monetization part described there is outdated and a whitepaper with a better take on monetization is expected by end of 2021.

## What is Skynet?
Skynet is a first party layer two solution to a decentralized file space that was built on top of the existing Sia network. So basically it allows file sharing. But combined with what can be created with it there is way more fitting words to describe what Skynet is - the decentralized internet**.

> You can find official Siasky.net support site and guides <a href="https://support.siasky.net" target="_blank" rel="noopener noreferrer">here</a>.

## How does Skynet work in theory?
I’m going to get a little bit more technical here, so make sure to read the renting article first.

So the base level for how Skynet works is it that every node that wants to be able to access `Skyfiles` forms contracts with as many hosts as possible on the network. Then, when a node wants to upload a file, it sends the data off to a subset of that massive host pool and generates something called a `Skylink`.

>A `Skylink` is a 46 character string of base64 encoded data. This data represents a couple things, but for the most part, this link is storing the Merkle root of the file. Merkle roots are complicated and you can dive more into them in this paper written by the head of the Sia Foundation, Luke Champine. But basically, `Skylinks` are just unique file identifiers; every single combination of data (think video file) and metadata (think file size) has a unique `Merkle tree root`.

Then when you want to query a specific `Skylink` (think if you’re requesting a video on Skyfeed), your Skynet node make a bunch of requests to hosts it has contracted with to see if they have the `Skylink` in question. The first host to respond with the data chunk then sends over the file to the renter node, and gets paid. In practice, fetch latency can be incredibly small, rivaling that of the centralized internet.

## How does Skynet work in practice?
Unfortunately, as of today you cannot just run a Skynet portal in your browser. Due to the many limitations of running a Sia full node talked about in [this article](/guides/sia/renting/introduction.html), running a renter node is hard on your system. The main hard parts are:

- Consensus is 22GB+
- It requires high up-time to maintain files
- Requires a lot of RAM
- High CPU load (would kill battery life)

But to be fair, this all is known and expected to be resolved by [Sia Foundation](/sia/foundation.html) with <a href="https://forum.sia.tech/t/core-development-utreexo/54/14" target="_blank" rel="noopener noreferrer">Utreexo</a> support early in 2022. Proof of concept for Utreexo was released mid 2021 and since then the team is integrating it into Sia.

So how did the team work around this? Well the idea is to use something called a **Skynet Portal**.

## Skynet Portals
A Skynet portal is a simple concept in practice. It effectively is an entry point to using the Sia network without having to run a node yourself. So someone else runs a dedicated server running a Sia node with Skynet turned on, and there’s a front end in front of that that allows users to interact with it. For example, check out <a href="https://siasky.net" target="_blank" rel="noopener noreferrer">siasky</a>, Skynet Lab’s official portal.

But what separates this from any other centralized file sharing platform out there like Dropbox or Mediafire? Well the main differentiator is that since the portals use the Sia network as a backend instead of their own servers, every file is available on every portal. For example Big Buck Bunny (an old Blender open source video file) is fully available at <a href="https://siasky.net/CACqf4NlIMlA0CCCieYGjpViPGyfyJ4v1x3bmuCKZX8FKA" target="_blank" rel="noopener noreferrer">siasky.net</a>, <a href="https://skyportal.xyz/CACqf4NlIMlA0CCCieYGjpViPGyfyJ4v1x3bmuCKZX8FKA" target="_blank" rel="noopener noreferrer">skyportal.xyz</a> and every other Skynet Portal at this Sia link: sia://CACqf4NlIMlA0CCCieYGjpViPGyfyJ4v1x3bmuCKZX8FKA. But these are not a duplicates of the file. You always access the same file, just through different portals. This is the next level up from federated, it’s decentralized!

>Note, some people claim that Skynet isn’t decentralized because the ingress/egress points are centralized. This is a fair point. But currently it isn’t possible to make something with a higher level of decentralization. It is being worked on, as stated above, but having site interoperability is pretty awesome in itself. Any file can be accessed from any portal, no matter who pins it or where they are. Now, each portal respectively can block any file they would like(for example, Skynet Labs won’t be paying for you to access content that’s illegal in their jurisdiction), but since anyone can set up their own portal, it’s not a huge issue. Also setting up your own Skynet portal isn’t easy, per say, but it is do-able if you have technical chops. For a guide on how to do this, look <a href="https://github.com/NebulousLabs/skynet-webportal/tree/master/setup-scripts" target="_blank" rel="noopener noreferrer">here</a>.

## What about the registry?
I haven’t talked about this so far because I didn’t want to overwhelm the reader with new stuff. But the registry, in essence, is a mutable file pointer built on top of the Sia network. Okay, but what does that mean? Each registry entry itself is only 256B on the hosts storage(usually on the main SSD) and it contains a couple things, though the only one I’m gonna be focusing on is the data field. In that data field, you can store up to 128B of whatever data you would like (though this is generally used to store a single `Skylink`).

The registry works by effectively generating a private-public key pair and publishing the public key out there for everyone to access. Then stored inside this entry is the data field which can be changed at any time. But since the original creator is the only one who can sign the data with the private key, anyone accessing the entry knows this version of it was generated by the original user with the private key, public entries are not a thing as of now.

>Now, technically, you could store whatever data you’d like in this “data” field, so you’d wonder why people wouldn’t store data directly in a registry instead of just a pointer to a `Skyfile` (like a photo for example). Well the main reason is cost. In order to upload that 256B file, you pay 50 hosts for 64KB off contract. So in total, for that 128B field, you end up paying for 3.2MB of space! Now, since it’s off contract, you don’t have to deal with the minimum file size, but you would have to pay for 25600x overhead so it’s no super practical. Also, another fun thing is that you pay one time to form a registry entry for 10 years in advance and don’t pay upkeep for the registry entry, so once it’s up, it’ll stay up in perpetuity (though it’ll slowly degrade in redundancy over time because hosts don’t have to put up collateral for registry entries). Updating the entry with new information will refresh the host count.

>Side note, the registry is a database, it’s called SkyDB after all. But it is not a relational database like SQL, it’s a key-value store architecture. This can be somewhat limiting for some applications.

## What can I do with Skynet?

> **Important - Update by Danger (October 26, 2021):**  This section is a bit outdated since it describes state before more than 6 months. A lot changed since then and if you want to know what Skynet lets you do today, check out our new dedicated section `Explore Skynet`. This section is kept around only to show how much progress has been done just in last few months and how many more apps were made since then.

---

*(Outdated)* As listed above, currently, Skynet has two real features; those being `Skyfiles`, which are accessible from any portal, and the registry(which when accessed through the SDK is referred to as `SkyDB`), which are mutable pointers that can be accessed or updated from any portal.

Currently the biggest things on Skynet are Skyfeed and content distribution by using Skynet as a CDN on sites like <a href="https://d.tube/" target="_blank" rel="noopener noreferrer">DTube</a>.

#### <a href="https://skyfeed.hns.siasky.net" target="_blank" rel="noopener noreferrer">Skyfeed</a>.hns.siasky.net
Skyfeed is a first Facebook-esque social media built on top of Skynet by community member Redsolver. It’s flagship features are mainly that if you run your own portal no one can limit your speech, and that there are no ads or tracking to speak of.

#### CDN Capabilities
The first thing that Skynet was advertised as was a CDN with decentralized frills, and it is still pretty good at that. Though, because of the traditional web architecture that web portals are built on, they completely rely on horizontal load balancing to scale. Also due to the nature of Sia, speeds cap at about 1GBPS per node, so a huge amount of nodes and load balancing is required to accomplish something like a large live event. For example, if you wanted to have a streaming platform with 100k concurrent viewers, you would need 1k-2k nodes at a minimum (depending on quality of the stream). This will be fixed once Utreexo is implemented(or host→user websockets), but for the time being, it’s a lot of work just like any other CDN. Though, unlike traditional web architectures, the actual pool of data itself can be massive per portal node because they have access to every `Skyfile` and `SkyDB` entry.

>Discover more [Skynet Apps](/explore-skynet/4-popular-apps.html).

## Moving forward
Skynet is still under heavy development by Skynet Labs and a breadth of features are in the pipeline. For example, upcoming features include:

- Utreexo
- Beefed up `SkyDB` pipeline with web sockets
- Content monetization
- Direct host → user web sockets
- Massive performance improvements per node
- Node scalability improvements
- And much more

---
*Written by: Covalent & Danger, Last Edit: October 29, 2021*
