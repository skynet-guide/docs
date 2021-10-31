# FAQs
If you know about any other questions that should be here, check out the [Contributors page](/about/contributors.html) and contact us.

Last update: October 26, 2021 | Sia 1.5.7

## Wallet
<!-- storing sc -->
<details>
  <summary>
    Where can I store SC?
  </summary>
  We have a dedicated guide for that <a href="/how-does-it-work/sia-guides/wallet.html">here</a>.
</details>

<!-- issues sending and recieving -->
<details>
  <summary>
      Cannot send or receive Siacoin (SC)
  </summary>
  Since there is no centralized server you can ask for current balance in the decentralized network like Sia, each user has their own copy of the blockchain that they must sync with and verify. This means your wallet can show and work only with results based on the data you already have and synced.
  <br><br>
  <b>If you cannot see incoming transaction</b> but it is visible in blockchain explorer like <a target="_blank" rel="noopener noreferrer" href="htthttps://siastats.info">siastats</a>, it means the transaction is already yours, you are just not synced to the Sia blockchain and need to wait for 100% sync (if a new user) or you are synced to wrong blockchain, which is common issue for returning users who missed the 2018 and/or 2021 fork and launched legacy version before checking for update. That got you to a situation where you synced past the point of automatic resolution and are trying to sync blocks from incompatible blockchain, which new versions of Sia won’t accept. You will see correct balance once you re-sync to Sia blockchain. See <a href="">instructions</a> how to re-sync.
  <br><br>
  <b>If you sent transaction but it never arrived in the other wallet</b>, you also most likely cannot see it in the blockchain explorer like <a target="_blank" rel="noopener noreferrer" href="htthttps://siastats.info">siastats</a>. If this is the case, you didn’t send Siacoin (SC). You are synced to wrong blockchain for same reason as explained above. Instead of SC you sent the coins on the legacy blockchain and that’s why other Sia users and exchanges cannot detect it. This transaction never happened on Sia network which means that once you re-sync, you will still find the coins in your wallet. You can follow these <a href="">instructions</a> to re-sync.
  <br><br>
  <b>If you cannot send a transaction</b> and it shows nothing after clicking the “Send” button, you are maybe trying to send full balance. Try it again but send 0.5 SC less. This is needed since the wallet is not counting transaction fees in the transaction. The fees are paid from the remaining SC inn your wallet so it is good idea to always leave some tiny amount (1 SC or less) instead of sending it all. If this doesn’t help, try <a href="">cleaning up your transaction pool</a>.

  <blockquote>
  You might want to know that Sia Foundation is currently working on Utreexo with "expected" release by end of 2021 or early in 2022, a feature that will dramatically reduce blockchain requirements, so you will be able to sync nearly instantly and with kilobytes instead of gigabytes of data. This will open way towards easy to use lite wallets and apps accessing Sia directly from a node running on any of your devices.
  </blockquote>
</details>

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

<br>
Make sure you have your 29-word seed before you start.
<br><br>

  1. Open Sia Data Folder (either manually using location above or from the About section accessed by i button.
  2. Make sure Sia is not running and then rename entire the sia folder to sia_backup for example.
  3. Make sure you are running latest version. If not, update first.
  4. Re-launch Sia and wait until you are 100% synced before trying anything.
  5. Load wallet from a seed (or create new wallet, depending on what you want). Once you are done, remember that in order to unlock the wallet you need to enter your seed again.
  6. Give it some time. On some computers it can sometimes take up to an hour to display correct balance. It is normal to see no transactions and zero balance as transactions are being scanned and appear over time.
  7. If everything is ok, you can delete the sia_backup folder to free unused space.

  <blockquote>
  Your 29-word seed is the default password and you need to enter it into password field after each recovery. You can change your password then but remember, the custom password is always just local one – protecting the wallet data in this specific computer.
  <br>
  If you lose your seed, your only chance to get it again is if you still have the wallet data and used a custom password. If you know it, you can unlock the wallet and let it display your seed again. However, it’s better to be careful and remember that seed is the only thing you will ever need for recovery.
  </blockquote>
</details>

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

<!-- hardware wallet integration -->
<details>
  <summary>
    Does Sia support hardware wallets?
  </summary>

 Sia supports the `Ledger Nano S` and `Ledger Nano X` hardware wallets. You can install the Sia app from Ledger Live by enabling "Development Mode" under "Settings". 
  <br/><br/>
 There are currently two methods to access Siacoin stored on a Ledger device. The official command line client or Sia Central's lite wallet. We do not recommend the command line client since it is for advanced users only; instead we recommend you use the <a target="_blank" rel="noopener noreferrer" href="htthttps://wallet.siacentral.com">Sia Central Lite wallet</a>. Ledger USB support works on desktop Chrome, Brave, Edge, and Opera. Ledger Bluetooth is only supported on Chrome desktop. We see it as currently best possible experience for anyone looking to hold SC.
  <blockquote>
  If you are worried to use a wallet link from third party site, you can access it by visiting the `official Sia site`, clicking `download` and scrolling down to the `list of recommended apps` where Sia Central Lite Wallet is mentioned by the Sia developers. You might also want to know that Nate, its author, officially joined Sia Foundation as a developer in Q2 2021.
  </blockquote>  
  <blockquote>
  If you want to do more, rent or host, you will need to run full node and download Sia-UI.<br>
  Unfortunately, there is no support that developers could use to integrate it with other options as Trezor and other HW Wallets.
  </blockquote>
</details>

<!-- tiny outgoing txn -->
<details>
  <summary>
    Why do I see tiny outgoing transactions?
  </summary>
  These are around 0.1 SC and usually appear when you had many incoming transactions, which is common when renting, hosting or mining. Sia-UI automatically consolidates these in order to make future transactions more efficient. It makes sense, using one output is much more efficient than using hundreds. There is nothing to be concerned about and no way to avoid it.
</details>

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

<!-- sia foundation vs skynet labs -->
<details>
  <summary>
    What is the difference between Sia Foundation and Skynet Labs?
  </summary>
  <b>Sia Foundation (Core Tech Upgrades)</b>
  <br><br>
  Sia Foundation's purpose is to maintain and upgrade the core Sia technology and support the ecosystem in transparent manner as a non-profit org. Sia's core tech is working, but there are many things to improve and it would be otherwise impossible due to their high development costs without further funding.
  <br><br>
  Unlike other projects that raised enormous amounts of money through ICO, Sia was not funded by the Siacoin (SC). Team never received any coins in the way as other projects do. It was funded through series of fundraising from VCs.
  <br><br>
  While sticking true to the same principles, Sia is entering a new age with Luke Champine (Sia co-founder known as @nemo) as its leader. Planned features are small file support, host module improvements and utreexo.
  <br><br>
  <b>Skynet Labs (Mainstream Adoption)</b>
  <br><br>
  It is a for-profit company that was developing Sia so far under the Nebulous brand and continues assisting Sia Foundation for some transition period until the foundation becomes fully independent.
  <br><br>
  Main product of Skynet Labs is Skynet, released in 2020 and receiving frequent updates since then. If Sia is layer 1, a decentralized storage, Skynet is layer 2, a decentralized internet. It is beginning of what you can call Web 3.0. A new paradigm.
  <br><br>
  Skynet is built on top of Sia and being powered by the same currency, Siacoin (SC) since the data are all stored on the Sia network's hosts. It allows censorship-resistant hosting and access of any content, including decentralized mutable database (SkyDB) and easy sharing with anyone. As long as anyone is willing to pay for the data, they cannot be taken down from the network and you can always access it through access points called Skynet Portals. Public, private, or your own. Your data will no longer be stored in thousands of data silos. Your data belong to you and other apps need your permission to access them.
</details>

<!-- how are files stored -->
<details>
  <summary>
    How are files stored on Sia and Skynet? Are my files safe?
  </summary>
  When you upload a file to the Sia network using Sia itself (wallet, siad, etc) the client first takes your file and creates associated "chunks" based on your redundancy. Sia currently uses 3x as the default redundancy, which is then multiplied by a constant "10", giving 30 different pieces. If you increase your redundancy to 5x, 50 files will be created. 1.7x, 17 files will be created, etc. This means that for every 1GB you upload, the amount rented will be multiplied by your redundancy (3GB, for example)
  <br><br>
  Using a complex Solomon-Reed algorithm all chunks are created simultaneously such that any 10 of the original 30 (or whatever your redundancy is set to) can be used to recreate the original file. For Sia each chunk is then encrypted, while Skynet skips this step when uploading to a public portal. MySky will offer future options for data privatization on Skynet.
  <br><br>
  Lastly, after all chunks are created and encrypted as previously described, each chunk is then distributed to a host on the Sia network by way of a contract agreed on between both the host and the renter. The host is required to lock up collateral during the contract period and if the host is unable to submit proof of storing the file, or becomes unavailable for too long, the collateral is burnt.
  <br><br>
  The Sia client periodically monitors the health of each file and the number of chunks currently available across it's contracted hosts. If the number of chunks drops, the client will automatically download any necessary chunks and recreate the missing pieces and form new contracts as-needed. For Skynet portals, as they are a sort of "always-on" service, this happens continuously.
  <i>For more info, see <a href="/private-backups-with-sia/introduction-to-renting.html">here</a></i>
</details>

<!-- What is the registry? -->
<details>
  <summary>
    What is the registry?
  </summary>
  It is explained in detail <a href="/how-does-it-work/skynet-layer-2.html#what-about-the-registry">here</a>.
</details>

<!-- What is SkyDB? -->
<details>
  <summary>
    What is the SkyDB?
  </summary>
  SkyDB is shorthand for a registry entry that contains a <a href="/how-does-it-work/skynet-layer-2.html#how-does-skynet-work-in-theory">Skylink</a>. This means that the link itself is mutable(can be changed at any time by anyone with they keys).  
</details>

<!-- sia whitepaper -->
<details>
  <summary>
    Where can I find Sia's whitepaper?
  </summary>
  You can find it right <a target="_blank" rel="noopener noreferrer" href="htthttps://sia.tech/sia.pdf">here</a>. However, keep in mind that Sia did a lot of progress since invention and if you want to better understand how it works, check out our up to date guides like <a href="/how-does-it-work/sia-layer-1.html">Introduction to Sia</a>.
</details>

<!-- where is the roadmap -->
<details>
  <summary>
    Where is the Sia roadmap?
  </summary>
  After the establishment of Sia Foundation in January 2021, the place to go to view, discuss and propose new and planned features is the <a target="_blank" rel="noopener noreferrer" href="htthttps://forum.sia.tech">Sia Forum</a>.

  If you are interested in what’s planned for Skynet. Best places to watch are <a target="_blank" rel="noopener noreferrer" href="https://discord.com/invite/sia">Sia discord</a>, <a target="_blank" rel="noopener noreferrer" href="https://siasky.net">SiaSky.net</a> and of course our **Sky Guide**. We are going to work hard to always bring you the latest news and apps from Skynet.
  <br>
  <br>
  If you are interested in what’s planned for Skynet. Best places to watch are <a target="_blank" rel="noopener noreferrer" href="https://discord.com/invite/sia">Sia discord</a>, <a target="_blank" rel="noopener noreferrer" href="https://siasky.net">siasky</a> and of course our <a target="_blank" rel="noopener noreferrer" href="https://sky-guide.hns.siasky.net">Skynet Guide</a>. We are going to work hard to always bring you the latest news and apps from Skynet.
</details>

<!-- storage comparisons  -->
<details>
  <summary>
    What's better? Sia, Filecoin or Storj?
  </summary>
  Don't ask others. Don't trust, verify. While it's impossible for anyone involved to take the bias away completely, <a href="/how-does-it-work/sia-guides/storage-chains-compared.html">this</a> is as roughly objective and (deeply) technical comparison and it shouldn't be an issue for you to verify these claims yourself.
  <br><br>
  </summary>
</details>

<!-- utreexo  -->
<details>
  <summary>
    What is Utreexo?
  </summary>
  Original Proposal on <a target="_blank" rel="noopener noreferrer" href="https://forum.sia.tech/t/core-development-utreexo/54">Sia Forum</a>.<br>
  Last update (<a target="_blank" rel="noopener noreferrer" href="https://sia.tech/transparency/2021-q1.pdf">Q1 2021 Report</a>)
</details>


## Troubleshooting
<!-- misbehaving renter -->
<details>
  <summary>
    The renter is misbehaving?
  </summary>
  If not maintained, the renter module can be quite a pain to deal with, and the most common issue is the allowance running out. So, when you create a renter node, you set an “allowance” that basically says, “renter, you can do whatever you want besides go over this allotted amount of money(in SC). Small issue with that though, the user generally doesn’t know the best number to put in here. Put the allowance too high, the renter node will frivolously spend and waste money on big contracts. Too low? The node will run out of funds and lock up. A good ballpark can to put in 3x the monthly price that is listed on <a target="_blank" rel="noopener noreferrer" href="https://siastats.info">Siastats</a>, but even that is a estimate and can become inaccurate within weeks due to the “marketplace” nature of Sia. So what are the side-effects of a mismanaged allowance?
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
  Spent funds are funds that have already been signed off in the payment channel with the host(see <a href="/private-backups-with-sia/introduction-to-renting.html">renting</a>). These are funds that have been spent and the host now effectively has, assuming they can provide a storage proof in the proof window.

  <h3>Unspent funds-Allocated</h3>
  These funds are funds that have been locked into a contract and have been not been spent yet. These are put here because you needs funds to use on the fly when adding more storage or paying for download bandwidth. But if these aren’t ever spent, they will get returned at the end of the contract period.

  <h3>Unspent funds-Unallocated</h3>
  This is where the issues mostly arise. If this section goes unfunded, new contracts cannot be formed and heavily used contracts cannot be refilled. This causes a myriad of issues with the renter so make sure to keep the unallocated category topped off by routinely checking it and upping the allowance as need be.

  One more thing to keep in mind is that it may say that you have “700 H” or whatever, but H means hasting which is actually 1e-24 SC. To learn more about how the token works and the different denominations, look <a href="/how-does-it-work/sia-guides/tokenomics.html#siacoin-sc">here</a>.
</details>

<!-- balance is 0 -->
<details>
  <summary>
    I can't see any transactions and my balance is 0. Where are my coins?
  </summary>
  If you are using latest <a target="_blank" rel="noopener noreferrer" href="https://sia.tech/get-started">version</a> and are 100% synced, don't worry if you see no transactions at all. It sometimes takes few minutes, especially for older wallets, to finish scanning your transactions before they appear.
  <br><br>
  Unfortunately there is no indicator for it as it wasn't much issue in the past, but the blockchain is growing. This is expected to change with Utreexo which is something the team is working on (more details in <a target="_blank" rel="noopener noreferrer" href="https://sia.tech/transparency/2021-q1.pdf">Q1 2021 report</a>).
</details>

<!-- daemon unreachable  -->
<details>
  <summary>
    Sia Daemon Unreachable
  </summary>
  Try to check the running processes for Sia-UI and siad and terminate them all. If you don't know how to do it, just restart your computer, it will have same effect. Then try to launch it again.
  <br><br>
  - If the error is not going away, you most likely recently updated. If you check logs in the Sia Data Folder, you will probably notice errors like "incompatible version" or issues with consensus. In such case you will need to re-sync your consensus and make sure you are running latest version and delete all old versions and shortcuts. More details and instructions <a target="_blank" rel="noopener noreferrer" href="https://support.sia.tech/forks/so-you-didnt-update-in-time">here</a>.
  <br><br>
  - (Windows only) If nothing helps and you remember that you tried to uninstall Sia-UI previously, it's also possible you messed up your registry. Based on community feedback, CCleaner is often recommended as an app to use in order to clean up Sia stuff. Once you do, download and install <a target="_blank" rel="noopener noreferrer" href="https://sia.tech/get-started">latest version</a> again.
</details>

<!-- my seed doesn't work -->
<details>
  <summary>
  My seed doesn't work, what can I do?
  </summary>
  <b>Possible issues:</b>
  <br>
  <li>
  <b>You're not synced</b>: You need to be 100% synced. You can only start scanning your wallet for transactions that belong to you if you know all transactions that ever happened.
  </li>
  <li>
  <b>Missing or Extra Spaces</b>: Make sure there are no leading or trailing spaces and there is exactly one space between the words. Like this: "word1 word2 word3 ... word27 word28 word29"
  </li>
  <li>
  <b>Wrong words</b>: Seed is composed only from english words. Check them carefully. If you are unable to spot the mistake, <a target="_blank" rel="noopener noreferrer" href="https://wallet.siacentral.com/">Sia Central Lite Wallet</a> is not just a good alternative to Sia-UI, but it can also quickly help you fix such wrong words because it tells you exactly which one is invalid.
  </li>
  <li>
  <b>Missing words</b>: If you are missing 1 word (didn't test it with more), there is around 50 000 of combinations it needs to check and you can use these instructions to brute force it using <a target="_blank" rel="noopener noreferrer" href="https://support.sia.tech/your-sia-wallet/wallet-troubleshooting/find-or-fix-your-seed">siac</a>.
  </li>
</details>

<!-- sync process -->
<details>
  <summary>
  Sync process - how long does it take and how to sync faster?
  </summary>
  In decentralized systems, there is no one you can ask for your balance and you don't have to trust anyone to get it. In order to know and see your balance, you need to synchronize the blockchain, which is the decentralized ledger, complete transaction history of the network. During the syncing process you download it from other network participants you connect to and thanks to cryptography verify that everything matches. Once you know all transactions (100% synced), your wallet can scan it all for transactions that belong to your seed (your wallet can do this only because it knows the seed) and remember their list. What you see in the list of transactions in the wallet is exactly result of this scan and your balance is just a simple sum of all your incoming and outgoing transactions.
  <br><br>
  <li>
  If you have SSD, it takes up to 2/3 of day.
  </li><li>
  If you don't have SSD, it can take up to a week or even more on very old computers.
  </li>
  <br>
  One way to sync faster is to get external SSD drive and change the Sia Data Folder location in Sia-UI Settings (it's available once you get to your dashboard). When you change it, expect Sia-UI to restart and start completely over. If you want it to continue with the previous data and your wallet, you will need to manually move it to new location and re-launch.
  <br><br>
  Other way is less secure as you are relying on someone else's consensus. It can decrease your sync time by about 90%. In case of HDD, you will probably still end up waiting for maybe a half of day or longer. If you want to proceed, check this <a target="_blank" rel="noopener noreferrer" href="https://siastats.info/consensus">community site</a> for more details.
</details>

<!-- I am stuck at Block Height 0 -->
<details>
  <summary>
    Sync process - I am stuck at Block Height 0
  </summary>

  You might run into an issue that your node is not syncing because it cannot find other nodes to connect to. The list that is hard-coded in the app is several years old and needs an update. Meanwhile, you can fix this issue easily by adding nodes manually.
  <blockquote>
    siac gateway connect 88.98.208.124:9981<br>
    siac gateway connect 88.131.107.45:9981<br>
    siac gateway connect 167.86.109.162:9981<br>
    siac gateway connect 63.141.234.114:9981<br>
    siac gateway connect 199.195.252.152:9981<br>
    siac gateway connect 72.69.188.134:9981<br>
    siac gateway connect 188.83.8.209:9981<br>
    siac gateway connect 65.21.79.100:9981<br>
    siac gateway connect 80.101.32.17:9981<br>
  </blockquote>
  Enter these commands (one line at a time) in the Sia-UI's terminal or in your own terminal if you're using the CLI.
</details>

<!-- wallet choice -->
<details>
  <summary>
    How can I store Siacoin (SC) securely? What wallets are available?
  </summary>
  Official Wallet: <a target="_blank" rel="noopener noreferrer" href="https://support.sia.tech/your-sia-wallet/wallet-overview">Sia-UI</a>
  <br>
  Community Resources: Our <a href="/how-does-it-work/sia-guides/wallet.html">Wallet</a> and
  <a href="/how-does-it-work/sia-guides/seed-management.html">Secure seed management</a> guides.
</details>

## Trading

<!-- max supply -->
<details>
  <summary>
    Does Sia have unlimited supply?
  </summary>
  There is no hard limit on the supply, but we are limited by the time. Since we know the block reward, we can say how many SC there will be at any point in the future. And while the supply is maybe "theoretically infinite", our lifespan is not. In the time that matters to us, inflation is quite low and with exception of 2021 (Sia Foundation established) it's going <a target="_blank" rel="noopener noreferrer" href="https://siastats.info/macroeconomics">steadily down</a>.
  <br><br>
  Also there is a very good reason for no hard limit. Over time, it could happen that majority of circulating supply ends up locked in storage contracts and/or held by people. It could also be literally scooped by some entity, presenting a serious attack vector. This could make it very difficult for those who are using SC to pay for their storage. That’s why Sia is always going to have a block reward to guarantee new coins entering the ecosystem.
</details>

<!-- stablecoin -->
<details>
  <summary>
    Is Siacoin (SC) meant as a stablecoin? Because if it goes up, storage would cost more, right?
  </summary>
  <b>Wrong</b>. There is no way to guarantee the price of SC. There are open markets and simplified it to the core mechanics, there are two forces clashing constantly, helping SC to find current price. Supply and demand.
  <br><br>
  Another important fact is that there is also Sia's own open storage marketplace. Hosts and renters come to the network, providing or looking for storage and setting own conditions and pricing. Hosts are adjusting (majority does this automatically with some tools, like Sia Host Manager) their pricing to reflect the continuously changing price of SC. So while it may look to you that prices are always paid in SC (yes, they are), they are not fixed for all. They are fixed only for the contract duration (3 months by default), but every single day, new contracts are formed at adjusted pricing.
  <br><br>
  If you won't adjust your prices as a host, renters will simply prioritise other hosts with more competitive pricing. This simple mechanic is ensuring that storage won't be overpriced, at least not for long even during big SC price spikes. Good profitability attracts more hosts who will keep their prices lower and you will have to do the same. Because if you won't make any contracts, you won't make any profit. And hosts are here for the profit.
  <br><br>
  <b>Example</b>: Renters buy SC worth of 1 year of storage, but the price suddenly goes higher
  <blockquote>
    They will pay what they expected for the first contracts. If they were trading, they might worry that if they held longer, those SC would have higher value now. But these users are not here for an investment, they bought them because they have data storage needs and at the time the contracts are formed, the price is exactly what they expected. However, the future contracts formed will be different. Since hosts adjusted the price to stay competitive in $, they will pay much less SC, making your SC last much longer than expected.
  </blockquote>
</details>

## Mining
<details>
  <summary>
    Can I mine Siacoin with my GPU? How do I mine Siacoin?
  </summary>
  Siacoin should not be mined via GPU anymore. While Siacoin use to be a GPU-minable coin, ASICs took over the mining scene in 2017 and GPUs became rapidly underpowered. Siacoin currently uses the Blake2B-Sia variant, importantly noting that Blake2B miners are not compatible such as the Antminer A3 or Innosilicon S11.
  <pre>
    <code>
      Currently compatible Siacoin ASIC miners are:
      Obelisk SC1
      ePIC SC200
      Goldshell HS3/HS3-SE/HS5
    </code>
  </pre>
  You can check their estimated earnings <a target="_blank" rel="noopener noreferrer" href="https://www.blakemining.com/">here</a>.
  <br><br>
  The original GPU mining software "Marlin", coincidentally, was updated to be compatible with the Blake2B-Sia variant and can be downloaded from the <a target="_blank" rel="noopener noreferrer" href="https://github.com/SiaMining/marlin/releases/tag/v1.1.0">Github source</a>. However, please keep in mind that even an RTX 2080Ti will only generate less than 2SC per-day at the current difficulty level and is continuing to drop lower.
  <br><br>
  If you would like to earn Siacoin by mining with your GPU, we recommend mining another coin or using a service like NiceHash and converting from a more profitable coin to Siacoin
</details>

<br>

---
*Written by: Danger & Covalent, Last Edit: October 29, 2021*
