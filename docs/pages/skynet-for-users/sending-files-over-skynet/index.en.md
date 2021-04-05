# Sending Large Files over Skynet
Sending large files over the internet is a common task. There are safer and faster alternatives to wetransfer.com or FTP. Here’s how to use Skynet and SkySend.

Filesharing is a daily need, be it in business or private. If you need to send large files to a remote colleague or just want to share a video from your last vacation with friends and family, there are common options like the specialized website wetransfer.com or cloud services like Dropbox and Google Drive. But these solutions are centralized and come with a natural twist. You have no guarantee that your files stay online every given second or the services won’t be hacked, giving cybercriminals access to your sensitive business or private files and personal data.

In this tutorial, we will guide you through using Skynet as an alternative, the layer 2-solution of Sia network. If you want to send a file just once or for a limited time, Skynet offers great services without the need of a user registration. Encryption and file-splitting on a trustless decentralized network will ensure, you – and noone else – can obtain power over your data.

We also cover Skynet accounts, with which you can store and share your files forever. At the end, you find a little comparison of the basic features and what to consider, when using any of the mentioned services in this article.

## Option #1: How to send up to 8 GB for free without registration
Skynet offers different ways to easily send large files without registration. We focus on [SiaSky](https://siasky.net) and [SkySend](https://skysend.hns.siasky.net), since they are the first available services for filesharing on Skynet. These are simple solutions to upload your data and share them with anyone you like. For files smaller than 1GB, you can just use siasky.net. But if you need something more, in order to get around the size limitation, you need to use some app that achieves the same result, but differently. Such an app is [SkySend](https://skysend.hns.siasky.net) developed by [redsolver](https://github.com/redsolver) and you can send up to 8GB with it.

But keep in mind: Both SiaSky and SkySend are not final at the time of writing. SiaSky is meant for quick filesharing purposes and doesn’t offer end-2-end encryption at the moment. For SkySend, the encryption still needs to be audited. So consider not to using these services for sensitive data for the time being.

### How to upload and share your files up to 1GB without registration (up to 90 days)
* Visit Siasky(https://siasky.net/) and you’ll find a self-explanatory interface

<img src="/static/assets/sending-files-over-skynet/image-2.jpg">

* click on “Browse“ and choose a file for uploading from your device. If you want to send a bunch of files, which in total are less than 1GB, we recommend to pack them into one archive file, i.e. with 7-Zip. With 7-Zip you can also consider to protect your file or archive with a password to optimize security.
* Depending on your internet connection, the upload will take some time.
* You can also upload folders and then reference the individual files where needed by adding “/folder/index.html” after the skylink.

Once your upload is complete, siasky.net will give you a Skylink. With this link, you or your colleagues, family and friends can download your file. Make sure to save the Skylink for up to 90 days, if you want to share your files again at a later point. After these 90 days, the file is not pinned on Skynet anymore, and thus gets lost.

### How to upload and share files up to 8GB without registration (up to 90 days)
If you are in need of sending single files or archives up to 8GB, we recommend SkySend. Here’s how to use it for free and without any registration process:

* Visit [SkySend](https://skysend.hns.siasky.net/), you find a minimalistic interface which offers everything you need.
* Click on “Browse” and choose your file for upload. Depending on the file-size and your internet connection, it can take a while.

<img src="/static/assets/sending-files-over-skynet/image-3.jpg">

* As you can see, the file is split and encrypted, giving you a maximum of security.
* Once your upload has finished, you will get a link, that – as before – can be shared with anyone you like.
* Make sure to save it for up to 90 days, if you want to share your files again at a later point. After these 90 days, the file is not pinned on Skynet anymore, and thus gets lost.

> Both these approaches are sharing the limited availability for up to 90 days. If you ask why, it is because in both cases we are using the siasky.net portal for the actual upload. Just in the second case, the data is not uploaded by the siasky.net app, but by SkySend that does it differently – splits it into pieces that match the limit and creates a new skyfile with references to the pieces and code necessary to rebuild the file. But since the actual uploaded data goes through the same portal, it shares the same limitations for unregistered users.
>
> However, if you want to upload temporarily, this gives you the ability to use any portal you want. See our list here.

## Option #2: How to upload, store and share your files for lifetime
You can sign-up for free on siasky.net, get 100 GB free cloud storage for lifetime and can share your files online with anyone within seconds – without any cost! For the time being, all you need is an email address and a password to get access to your personal dashboard. The dashboard gives you an overview of every upload and generated skylink that you have created while you were logged in.

### How to setup your Skynet account
* Visit https://siasky.net/ and click on “Sign up now!“
* Provide an email address and choose a password to setup your account

<img src="/static/assets/sending-files-over-skynet/image-4.jpg">

* When you are logged in, any upload going through SiaSky.net will be collected on your dashboard with the appropriate Skylink. This includes not just SiaSky.net itself, but any Skynet app you are accessing through a SiaSky.net portal – like SkyID, Marstorage, SkyFeed, simply everything …

> **Notice:** At the time being, SkySend-links are not visible on the SiaSky dashboard. **Skynet Labs are working on DAC** (Data Access Controller) and details will be revealed soon, which will allow Skapp developers to make it way cooler and easy to use. What does it mean for you right now? **If you use SkySend, make sure to save your SkySend-links separately, until DAC is integrated. Only SiaSky links can be obtained from the dashboard right now.**

Your files are hosted for lifetime without any limit and can be shared for as long as you wish. If you ask how it is possible to get this all for free and for a lifetime, you should learn more about the Skynet monetization model. Best resource available right now is from the developers themselves: [A Deep Dive into Skynet](https://blog.sia.tech/a-deep-dive-into-skynet-a0fa037feea).

> **Did you know?** As a free SiaSky user, you can use 7-Zip or any other similar program to split your own archives bigger than 8GB into pieces, each not bigger than 1GB (or 8GB in the future, after DAC has been deployed). If you want to avoid splitting files, consider to sign-up for one of the paid plans. They will give you even more freedom. Being logged in, you can check the **tiers and Skynet prices** on the appropriate site.
>
> Though keep in mind that the 1GB per-file-limit has not yet been lifted on portals. That should be next in line to change though.

## SiaSky & SkySend vs. WeTransfer, Google Drive and Dropbox
The following table gives you an overview of storage capacities of SiaSky, SkySend and centralized competitors like WeTransfer, Google Drive and Dropbox.

Service	                             | SiaSky.net / SkySend          | wetransfer.com| Google Drive	    | Dropbox
-------------------------------------|-------------------------------|---------------|-----------------|--------
Developer	                         | Skynet Labs / Sia Community	 | WeTransfer	 |Google	       | Dropbox
Technology	                         |decentralized(ish)	         | centralized	 | centralized	   |centralized
Encryption	                         | No / AES256                   | AES256                          | AES128 for storage| 	AES256
Free transfer (without registration) | Yes	                         | Yes (recepient and sender email required) | No      | No
File size limitation	             | 1 / 8GB                       | 2GB           | 15GB            | 2GB (100MB for sending)
Storage (free use after registration)|	100GB                        | 2GB           | 15GB	           | 2GB
Hosting duration (free use)          |	unlimited with registration,90 days without it	7 days (10 downloads)    | –       | –
Download speed                       | unlimited                     | unlimited     | unlimited       | unlimited

## Plans and features for paying users
If you plan to use a storage solution for longterm, it’s worth to look into pricing and the available plans. This is, what the services offer:

* SiaSky plans are simple. You get 100 GB for free. Beginning with $5/month for Skynet Plus, you can use 1TB. You get 4TB for $20/month with Skynet Pro and 20TB for $80/month with Skynet Extreme.
* WeTransfer offers Pro subscription for 12$/month. That will only give you 1TB storage, but you can send files with 20GB in size which can be shared via email 50 times.
* Google Drive has Google One as a paid plan, beginning at 1.99$/month for 100GB. That is a tenth of Skynet Plus’ storage capacity for 40% the price of the same Skynet plan. Further, Google gives you 200GB for 2.99$/month and 2TB for 9.99$/month. Comparing the highest tier of Google to Skynet Extreme in theory, you would have to pay 20% more for Google, to get the same amount of storage.
* Dropbox Plus begins at 9.99$/month without extending your 2TB storage. The limit per transfer is set to 2GB. Concentrating on these numbers alone, the 16.99$/month-family-plan just gives another 5 users access to the same storage capacity.

## Conclusion
SiaSky and SkySend – or in essence Sia’s layer two, Skynet – is your primary choice, if you don’t want your data being stored by a centralized corporation. Comparing storage capacity and price, SiaSky is within a throwing distance of the competitors in terms of price/performance, while allowing a fully open API for skapp devs to take advantage of. Skynet is in active development and new features will be added time after time. Using SiaSky storage, you can easily manage your files on Skynet. Read this guide to understand, [why you need Skynet](). You will find everything else you need to know on our Skynet Wiki.

*Written by MLN284 (March 30, 2021)*

*Last updated by Covalent(April 1, 2021)*
