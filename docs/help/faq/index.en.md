# Frequently Asked Questions
If you know about any other questions that should be here, check out the [Contributors page](/help/contributors/index.html) and contact us.

Last update: March 31, 2021 | Sia 1.5.5

## Wallet
<!-- storing sc -->
<details>
<summary>
Where can I store SC?
</summary>
We have a dedicated guide for that <a href="">here</a>.
</details>
<br>

<!-- issues sending and recieving -->
<details>
<summary>
    Cannot send or receive Siacoin (SC)
</summary>
Since there is no centralized server you can ask for current balance in the decentralized network like Sia, each user has their own copy of the blockchain that he must sync with and verify. This means your wallet can show and work only with results based on the data you already have and synced.

<b>If you cannot see incoming transaction</b> but it is visible in blockchain explorer like <a href="https://siastats.info">siastats</a>, it means the transaction is already yours, you are just not synced to the Sia blockchain. You are synced to wrong blockchain, which is common issue for returning users who missed the 2018 fork and launched version older than 1.3.7 before checking for update. That got you to a situation where you synced past the point of automatic resolution and are trying to sync blocks from incompatible blockchain, which new versions of Sia won’t accept. You will see correct balance once you re-sync to Sia blockchain. See <a href="">instructions</a> how to re-sync.

<b>If you sent transaction but it never arrived in the other wallet</b>, you also most likely cannot see it in the blockchain explorer like <a href="https://siastats.info">siastats</a>. If this is the case, you didn’t send Siacoin (SC). You are synced to wrong blockchain for same reason as explained above. Instead of SC you sent the coins on the legacy blockchain and that’s why other Sia users and exchanges cannot detect it. This transaction never happened on Sia network which means that once you re-sync, you will still find the coins in your wallet. You can follow these <a href="">instructions</a> to re-sync.

<b>If you cannot send a transaction</b> and it shows nothing after clicking the “Send” button, you are maybe trying to send full balance. Try it again but send 0.5 SC less. This is needed since the wallet is not counting transaction fees in the transaction. The fees are paid from the remaining SC inn your wallet so it is good idea to always leave some tiny amount (1 SC or less) instead of sending it all. If this doesn’t help, try <a href="">cleaning up your transaction pool</a>.

<blockquote>
You might want to know that Sia Foundation is going to work on Utreexo this year (2021), a feature that will dramatically reduce blockchain requirements, so you will be able to sync nearly instantly and without gigabytes of data. This will open way towards easy to use lite wallets and apps accessing Sia directly from a node running on any of your devices.
</blockquote>
</details>
<br>

<!-- resync -->
<details>
<summary>
How do I re-sync the Sia blockchain?
</summary>
If you find yourself on wrong blockchain (most commonly you notice because of wrong balance or any issue with sending/receiving coins), all you need to do is:

<blockquote>
Windows: %UserProfile%\AppData\Roaming\Sia-UI\sia\<br>
Linux: ~/.config/Sia-UI/sia/<br>
Mac: ~/Library/Application Support/Sia-UI/sia/<br>
</blockquote>

1. Open Sia Data Folder (either manually using location above or from the `About` section accessed by `i` button).
2. Make sure Sia is not running and then delete `consensus` and `transactionpool`.
3. Re-launch Sia and wait until you are 100% synced before trying to send anything. This is especially important if you have any recent missing transactions. They are at the end of blockchain and you won’t see them until nearly 100% synced.
</details>
<br>

<!-- clear the tpool -->
<details>
<summary>
How do I clean the transaction pool?
</summary>

<blockquote>
Windows: %UserProfile%\AppData\Roaming\Sia-UI\sia<br>
Linux: ~/.config/Sia-UI/sia/<br>
Mac: ~/Library/Application Support/Sia-UI/sia/<br>
</blockquote>

1. Open Sia Data Folder (either manually using location above or from the `About` section accessed by `i` button.
2. Make sure Sia is not running and then delete `transactionpool` folder.
3. Re-launch Sia and give it some time to rebuild it. It can take few minutes or a bit longer depending on if you whave SSD or HDD.
</details>
<br>

<!-- clean install -->
<details>
<summary>
How do I perform clean installation of Sia?
</summary>
<blockquote>
Windows: %UserProfile%\AppData\Roaming\Sia-UI\sia<br>
Linux: ~/.config/Sia-UI/sia/<br>
Mac: ~/Library/Application Support/Sia-UI/sia/<br>
</blockquote>

1. Open Sia Data Folder (either manually using location above or from the About section accessed by i button.
2. Make sure Sia is not running and then rename entire the sia folder to sia_backup for example.
3. Make sure you are running latest version. If not, update.
4. Re-launch Sia and wait until you are 100% synced before trying anything.
5. Load wallet from a seed (or create new wallet, depending on what you want). Once you are done, remember that in order to unlock the wallet you need to enter your seed again.
6. Give it some time. On some computers it can sometimes take up to an hour to display correct balance.

<blockquote>
Your 29-word seed is the default password and you need to enter it into password field after each recovery. You can change your password then but remember, the custom password is always just local one – protecting the wallet data in this specific computer.
<br>
If you lose your seed, your only chance to get it again is if you still have the wallet data and used a custom password. If you know it, you can unlock the wallet and let it display your seed again. However, it’s better to be careful and remember that seed is the only thing you will ever need for recovery.
</blockquote>
</details>
<br>

<!-- speed up syncing -->
<details>
<summary>
How can I sync faster?
</summary>
This is not recommended, since you rely on third party’s consensus, but if you don’t have SSD, you would wait up to a week just to get through the initial sync (further syncing will be fast) because you have several years of transactions to catch up.
<br>
In such case you can follow <a href="https://siastats.info/consensus">these instructions</a> to bootstrap consensus.
</details>
<br>

<!-- change sia data dir -->
<details>
<summary>
How to move Sia data folder to different location?
</summary>
<blockquote>
Windows: %UserProfile%\AppData\Roaming\Sia-UI\sia
Linux: ~/.config/Sia-UI/sia/
Mac: ~/Library/Application Support/Sia-UI/sia/
</blockquote>

This is useful when you need to move from HDD to SSD in order to make syncing faster.
<br>
1. Go to the folder above and copy entire `sia/` folder to a new location on your SSD
2. Launch Sia-UI, go to the settings and change the Sia Data folder location to the new one.
3. App will restart and if you did everything correctly, it will display the same stuff as before, but using new location. After that you can safely remove the original folder (only the `sia/` that you moved, do not delete anything else higher in the hierarchy) to save up some space.

<blockquote>
If it doesn’t work, check the location and make sure it is correct.
</blockquote>
</details>
<br>

<!-- hardware wallet integration -->
<details>
<summary>
Is there any HW Wallet integration?
</summary>
Yes, there is official one using `Ledger Nano S`, but we do not recommend to use it since it is for advanced users only.
<br>
Instead, we recommend you to check out the <a href="https://wallet.siacentral.com">Sia Central Lite wallet</a>. Works with any browser and allows you to use your `Ledger Nano S`. We see it as currently best possible experience for anyone looking to hold SC.

<blockquote>
If you want to do more, rent or host, you will need to run full node and download Sia-UI.
</blockquote>

Unfortunately, there is no support that developers could use to integrate it with other options as newer Ledger, Trezor and other HW Wallets.
</details>
<br>

<!-- tiny outgoing txn -->
<details>
<summary>
Why do I see tiny outgoing transactions?
</summary>
These are around 0.1 SC and usually appear when you had many incoming transactions, which is common when renting, hosting or mining. Sia-UI automatically consolidates these in order to make future transactions more efficient. It makes sense, using one output is much more efficient than using hundreds. There is nothing to be concerned about and no way to avoid it.
</details>
<br>

## Fundamentals
<!-- sia v skynet -->
<details>
<summary>
What is the difference between Sia and Skynet?
</summary>
Sia and Skynet are part of the same software, but with different goals.
<br>
<br>
You can see <b>Sia</b> as a `decentralized cloud storage layer`. Its complex solution that allows us to access data storage without any need for trust. It gives control back to user and individuals.
<br>
<br>
<b>Skynet</b> is different. It is a `censorship-resistant publishing platform`. It is like decentralized internet that fully utilizes everything that Sia makes possible and uses it as its storage layer. Since it is using the same tools, the data are stored on the same hosts, but in a different way that allows content pinning, easy sharing, even entire app/site hosting without need for server. And it also allows access to SkyDB, decentralized mutable database. Anything uploaded has own Skylink that you can share.
</details>
<br>

<!-- sia whitepaper -->
<details>
<summary>
Where can I find Sia whitepaper?
</summary>
You can find it right <a href="https://sia.tech/sia.pdf">here</a>. However, keep in mind that Sia did a lot of progress since invention and if you want to better understand how it works, check out our up to date guides like <a href="">Introduction to Sia</a>.
</details>
<br>

<!-- where is the roadmap -->
<details>
<summary>
Where is the Sia roadmap?
</summary>
After the establishment of Sia Foundation in January 2021, the place to go to view, discuss and propose new and planned features is the <a href="https://forum.sia.tech">Sia Forum</a>.
<br>
<br>
If you are interested in what’s planned for Skynet. Best places to watch are <a href="https://discord.com/invite/sia">Sia discord</a>, <a href="https://siasky.net>siasky</a> and of course our <a href="https://skynetwiki.tech>SkynetWiki</a>. We are going to work hard to always bring you the latest news and apps from Skynet.
</details>
<br>

## Troubleshooting
<!-- misbehaving renter -->
<details>
<summary>
The renter is misbehaving?
</summary>
If not maintained, the renter module can be quite a pain to deal with, and the most common issue is the allowance running out. So, when you create a renter node, you set an “allowance” that basically says, “renter, you can do whatever you want besides go over this allotted amount of money(in SC). Small issue with that though, the user generally doesn’t know the best number to put in here. Put the allowance too high, the renter node will frivolously spend and waste money on big contracts. Too low? The node will run out of funds and lock up. A good ballpark can to put in 3x the monthly price that is listed on <a href="https://siastats.info">Siastats</a>, but even that is a estimate and can become inaccurate within weeks due to the “marketplace” nature of Sia. So what are the side-effects of a mismanaged allowance?
<br><br>

<li>Downloads will cease to work properly
<li>Contract count will drop
<li>As it dwindles, siad will struggle with host churn as it trys to form contracts with cheaper and cheaper hosts.
<br><br>
Okay, so how do you diagnose this issue?

<blockquote>
I’m going to be using Sia-UI to show this example, but it’s applicable to the cli interface btw.
</blockquote>

So go to the “terminal” button:<br><br>
<img src="/static/assets/FAQ/image-1.png">

Then type in `siac renter -v`. You’ll get something that looks like this at the top of the long output:<br><br>
<img src="/static/assets/FAQ/image-1.png">

<br>
So let me break down the 3 main catigories:
<br><br>
<li>Spent funds
<li>Unspent funds-Allocated
<li>Unspent funds-Unallocated


<h3>Spent funds</h3>
Spent funds are funds that have already been signed off in the payment channel with the host(see <a href="">renting</a>). These are funds that have been spent and the host now effectively has, assuming they can provide a storage proof in the proof window.

<h3>Unspent funds-Allocated</h3>
These funds are funds that have been locked into a contract and have been not been spent yet. These are put here because you needs funds to use on the fly when adding more storage or paying for download bandwidth. But if these aren’t ever spent, they will get returned at the end of the contract period.

<h3>Unspent funds-Unallocated</h3>
This is where the issues mostly arise. If this section goes unfunded, new contracts cannot be formed and heavily used contracts cannot be refilled. This causes a myriad of issues with the renter so make sure to keep the unallocated category topped off by routinely checking it and upping the allowance as need be.

One more thing to keep in mind is that it may say that you have “700 H” or whatever, but H means hasting which is actually 1e-24 SC. To learn more about how the token works and the different denominations, look <a href="">here</a>.
</details>&nbsp;

*Written by: Danger & Covalent, Last Edit: April 14, 2021*
