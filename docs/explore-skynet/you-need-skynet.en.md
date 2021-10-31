# Why do I need Skynet?
This is surely the question in your mind right now. Maybe you discovered someone talking about it on the internet, or your friend is convincing you why Sia and Skynet are the future of the internet. Or you are just someone looking for decentralized alternatives to activities you’re performing every single day.

Before we dig into the use cases, let’s take a look at the current internet and compare it with Skynet.

## Restart the internet
I won’t lie to you. Skynet is new. And even a year or two later it will still be new – the same as the internet was still a new thing to many people in the early 2000s. Back then, most of the apps you are using today didn’t exist. It took a lot of time for the internet to become what it is today… and in many ways, become something we are disgusted at since we can’t really do anything to change it.

Today your data is stored across millions of servers and databases in isolated silos owned by the companies holding your data and selling it to anyone for profit. The Internet is not free, you’re paying with your privacy that gets monetized. Also, each new service needs to build its own user base and network effect from zero. It doesn’t matter if it’s 1000 times better with a more user friendly model – it won’t survive in this merciless competition. Innovation is being supressed. Rules are defined by giants (Apple, Google and others). Content creators are being de-platformed and silenced. There are even way more ridiculous things happening and you know this is just the tip of the iceberg.

What can we do about it? Well, we can restart the internet.

## Get in control of your data and privacy… easily
Skynet is presenting a new kind of internet, a decentralized one. Built with open-source software on top of the fully decentralized cloud storage platform known as Sia. If you want to learn more, check our other guides. But most important thing is that you don’t need to know much to start.

**You don’t need any special software.**
**You don’t need to run any server.**
**You don’t need any Siacoin (SC).**

All you need is an account on a portal of your choice. All these guides will be using siasky.net as the official Skynet portal operated by the developers of Skynet. But it’s open source, so anyone can start a business and become a player in the decentralized cloud storage market or run an own portal just for the own needs, family or friends. You can always migrate to any other portal if you’re not happy, simply telling another portal to start pinning all your data. But we will leave that for a separate guide later.

There are resources that explain it much better. If you want to learn more about Skynet’s vision which is close to a roadmap, check this <a href="https://blog.sia.tech/a-deep-dive-into-skynet-a0fa037feea" target="_blank" rel="noopener noreferrer">“ADeep Dive into Skynet”</a> article on the official Sia blog.

Let’s look at a bit condensed version.

## What is the minimum I need to know to begin?
### Skynet apps are running client-side.
When you are accessing some Skynet app, you download its entire code. It doesn’t have to connect anywhere (at least not those apps that claim to be fully decentralized), it has everything it needs and connects to Skynet directly through the portal you use.

### Skynet is not encrypted by default, encryption is defined on the app level.
For these reasons, siasky.net uploads should only be used if you’re fine that what you upload will be available without any encryption. It’s not good for personal data. But there is no limit on what users can accomplish using other apps – some allow just non-encrypted upload, some offer also encrypted upload and some do a mix of both approaches for different types of data.

### Your data is always stored redundantly.
All files up to the base sector size are stored with 10x redundancy. This applies to all smaller files (let’s say up to the size of an mp3 song). Bigger files are stored with 3x redundancy. This means your files or fragments of files exist multiple times on the network and are automatically re-uploaded to another host in order to maintain good health of your files in case of some host holding pieces of your data disappears.

### Anyone can run a Skynet portal with own rules and integrate new features. It’s open-source.
Let’s say your favorite portal has a limit for a maximum upload of 1GB. If you need more, you have two options. To use some Skynet app that works around that limit, for example as SkySend ([see our guide here](/guides/skynet/sending-files.html)).

Or, if you’re not happy with some portal, you can always move to another one or run your own. This is what makes the difference from the centralized internet. When some site goes offline, you lose all your data. But on Skynet, the data is stored on the underlaying Sia network that is deeply integrated with Skynet. All you have to do is to tell your portal (or just a Sia renter node in “portal mode”) to start pinning the list of all your Skylinks.

### You can use any Skynet portal to access any Skylink.
Just change the domain name in the skylink to something else. Find a list (may be incomplete) [here](/tech/portals.html).

### Skynet is decentralized internet.
It’s not a single app, it is a way to access and utilize the decentralized storage network in a way that lets you upload anything you want and host it without need of a server. It can be a document, song, video, or entire complex application, like SkyFeed (decentralized twitter), Marstorage (decentralized dropbox) and others. All Skynet portals let you access the same files at the same hosts on Sia network through Skylinks (way of addressing specific content on decentralized network) so you’re not depending on single point of access.

### Built-in monetization and natural app cross-operability.
As you can read in the article mentioned above (“A Deep Dive to Skynet”), Skynet has monetization deeply integrated in its veins. Skynet portals are paying Sia hosts with SC so the users don’t have to worry about running a node or a wallet. And this goes way beyond with recursive monetization being worked on allowing limitless innovations. Imagine making an image, setting a fee to it and anyone can use it in the own app and you get paid each time it is displayed, automatically. Or getting paid for curating, filtering content for other users who follow you. Or getting paid for answering questions, or even asking them on a skynet powered forum.

And if you think this is all, you’re wrong. Applications can use same data, if a user allows that. Apps do not need to build their own network effect, they can build on top of the network effect of all other apps. Imagine using a decentralized facebook and then discovering a better interface, letting you work with the same data plus way more. You can start using it without your friends even noticing, since they will still see your activity.

### Skylinks are content based.
You can read more about this in other linked resources but shortly said, you don’t need to upload the file to know its Skylink. You can do so before it, because identical file (content and name) will always result in the same Skylink. This is especially useful if you have some favorite app. When you access it through the Skylink, you can be always sure it was not modified and no one added any malicious code.

## Where to go from here?
I know, you want to use it already. We are currently working on more guides that will lead you through account creation and various Skynet apps (shortly Skapps) to use. Expect this section to grow fast.

> [How To: Sending Large Files over Skynet](/guides/skynet/sending-files.html)

---
*Written by: Danger & Covalent, Last Edit: April 14, 2021*
