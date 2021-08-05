# Siacoin Wallets
This guide will introduce you to different ways how to store your SC. Of course, you can always keep it on exchange, but why doing so? We don’t think you care about decentralization so much to come here and start researching it only to end up leaving your precious coins then on centralized exchange where you can never be sure what happens to it.

Don’t hesitate, don’t be afraid of getting it under your own control. We are here to help you and you will be glad of making this step rather sooner than late.

>Quick Links: How to store Siacoin? ([Sia-UI](), [Sia Central]()), [How to receive SC?](), [How to send SC]()?

## How to store Siacoin?
### Sia-UI
**Available for**: Windows, MacOS, Linux

`Sia-UI` is the official and recommended way of accessing you Sia Wallet. It is the visual layer *(also known as UI, or User Interace)* on top of `Siad` *(Sia Daemon)*, software that is operated by many users around the globe and pumping life to the constantly running Sia network.

>If you are looking for CLI (Command Line Interface) instead, check our Mastering Sia with CLI guide.

1. First thing to do is to visit the [website](https://sia.tech) and **download latest version of Sia-UI** for your `OS (Operating System)`. This guide is written for 1.4.0 or higher at the time of 1.5.3 being the latest version available.
2. **Launch Sia-UI** and once you see the options to create wallet or recover it from a seed, select the option to **Create Wallet**. It will present you with 29-word seed and force you to write it down. This 29-word seed is the only information you will ever need to regain access to your wallet.
3. **Save your 29-word seed** in a `password manager` of your choice to make sure it's secure and available after a possible system faliure (see [Secure Seed Management guide](/sia/seed-management.html)). You can also include any notes like where to download it or copy/paste content or link of this article.
4. **Backup your `password manager‘s` database**. Once you save this new item in your database under name like “Sia Wallet [Seed]”, what I usually do is to duplicate that item and name it “Sia Wallet [Seed Backup]”. Just in case you ever accidentally deleted any of these two. Then save the database, update it’s timestamp like “KeePass_01_05_19” and save it to all the places and devices you decided to. Two are absolute minimum, 3–4 work best.
5. Unlock your wallet by entering the seed into the password field. Once you do so, you can click more and then **change your password**. Just remember that it will work only locally on this specific computer and only until you load any wallet from the seed again. If you ever get into situation when your password is not accepted and you are 100% sure it was your password, just enter your seed in format `word1 word2 word3 … word27 word28 word29`.
6. Congratulations, you’ve successfully created Sia wallet and are ready to receive your first Siacoins (SC).

Right now you can already generate wallet address by clicking **Receive** but you will still need to be 100% synced in order to see any incoming transaction and be able to send some.

>Let’s say **you want to know what to do if you lose your custom password** . That’s easy, just load your wallet from your seed and then enter your seed again when asked for password. Because the seed is your default password after loading a wallet from a seed. You can find answers in our detailed [FAQ](/help/faq.html).

>**If you already had an earlier Sia-UI version installed on your computer**, you might run into some issues with synchronization due to past hard forks. In such case, remember that your seed is the key and Sia-UI just a tool that can work only when it has correctly synchronized data. You can always re-sync to correct blockchain and get access to your wallet just by clearing it’s data, installing latest version, letting it sync and then using it to load wallet from a seed. It is called clean installation and you can find instructions in our [FAQ](/help/faq.html).

>**If you want to have multiple wallets** and switch between them time from time, these two commands will be useful for you: `wallet init --force` instantly creates new wallet and shows you new seed, while `wallet init-seed --force` lets you load your existing wallet from a seed. You can use these from Terminal inside Sia-UI and remember that the expected password then is going to be the same as your seed. It is not recommended to try to run same wallet on multiple computers at once, especially if you are hosting or renting.

>Blockchain can usually hold just one currency and cannot be mixed with another one or even separate forks (having own unique currency since that point). But in case of Sia there is one exception. It is the supplementary token known as **Siafund** (SF) and Sia wallet can hold both SC and SF. You can read more about Siafund in [Tokenomics](/sia/tokenomics.html).

### Sia Central
**Available for**: Any platform with Web Browser

Sia Central Lite Wallet was introduced in 2020 by Community member **Nate**, author of Sia Host Manager. It is the most user friendly way of sending and receiving Siacoins.

It lets you use it straight away from your browser without syncing anything. You just enter your seed or create new one and that’s it. While it is secure and your seed never leaves your computer, it is only as secure as your computer is.

Fortunately, it has a feature that lets every user enjoy top tier security. It supports Ledger Nano S so your seed never leaves you hardware wallet and you can use it securely even if you’re not friendly with technologies.

You can find detailed guide including pictures here: [Sending Siacoins with Ledger Nano S](https://medium.com/sia-central-blog/sending-siacoins-with-the-ledger-nano-s-ea6d87711a3e).

### Other Wallets
If you found a Sia wallet not mentioned in this list, you should pay increased attention. While there were some working wallets in the past (there was/is one for Android that even allowed you to sync blockchain), there were also some scams. Even if it’s not so comfortable as getting such third party wallet on platform of your preference, it is recommended to use one of the options above.

With Sia Foundation taking over further development of Sia starting in 2020, it is expected that in the next year Sia will get `Utreexo` introduced, a feature dramatically reducing blockchain requirements and making sync times nearly instant. It is seen as pre-requisite for turning every single device including your phone into Sia node and opening of new world of possibilities.

## How to receive Siacoin?
### Receiving at Exchange
Find `Wallet` or `Deposit` section and select coin you want to receive (`deposit`). You will know you did it right when it shows you wallet address and by double checking it you can confirm that the coin is really Siacoin (SC). Copy this address into `clipboard` and remember few of its first and last characters. Then provide this `wallet address` to person or wallet you want to receive coins from.

>If you are the recipient and you are just sending coins between your different wallets, continue with the following section [How to send Siacoin?]() and copy/paste (and then check if it is correct) this value into `wallet address` (sometimes called `recipient's address`) field.

>**It is good idea to never keep your coins on Exchange** unless you are trading actively and you know what you are doing. It is rather rare today but many exchanges in the past ended up with users losing their assets. When you have coins on Exchange, they are not really yours since you don’t have the seed (private key). It is very similar to your bank account, the money are not yours. It is the bank that keeps them and allows you access it through its system. If that system goes down, what will you do? You can prevent this scenario by keeping coins in your own wallet out of exchanges.

### Receiving with Sia-UI or Sia Central
When your wallet is unlocked, just find the `Receive` button (in Sia-UI it is under Wallet section) and see the wallet address generated. Then provide this `wallet address` to person or wallet you want to receive coins from.

>This wallet address was generated with your seed (private key) and any transaction sent to it will belong to it. It means that if you recover your wallet on other computer from seed, you will see your coins again. You don’t need anything but your seed. Losing your seed means loss of access to your coins and no one can help you so make sure to store it securely. Feel free to check our guide about [Secure Seed Management](/sia/seed-management.html).

>If you use Sia-UI, you won’t see the incoming transaction until 100% synced. This process can take a lot of time, even up to a week if you don’t have SSD drive. If it’s your case, check our [FAQ](/help/faq.html) for **How can I get synced faster**?

## How to send Siacoin?
### Sending from Exchange
Even if every exchange is different and buttons can have different labels, basics are all the same. You need to find `Wallet` or `Withdrawal` section and select a coin you want to send (`withdraw`). Once you do so, you need to enter recipient’s Siacoin `wallet address`. Remember always to double or triple check the address that it matches the one you want to send it to. Fast way to do so is to check first and last characters so you know for sure you didn’t miss any.

### Sending from Sia-UI
Click `Wallet` tab on the left side and then `Send` in the middle area that opens. **Make sure you are 100% synchronized**, otherwise it won’t work. Also make sure you are running latest version of Sia-UI since there was a fork at version 1.5.4.

>If you had Sia-UI previously installed, didn’t update before February 2020 and launched any older version first, you are most likely on wrong blockchain and experiencing issues with transactions. You will need to re-sync in order to fix it. In such case continue check **How to re-sync Sia-UI in** our [FAQ](/help/faq.html).

If everything is ok, you can send Siacoin easily by specifying `amount` of SC you want to send and `wallet address` you want to send it to. Just make sure to not send full balance. You need to leave tiny amount of SC so there is enough left to cover transaction fees. Easiest way to do so is to send 0.5 – 1 SC less than full balance.

### Sending from Sia Central
This option is great since it allows you near instant access. No need to sync blockchain and you can quickly load any seed.

Once your wallet is unlocked, just click Send and specify `recipient's address` and `amount` you want to send. Sia Central will let you know about transaction fee and remaining balance. Once satisfied, just confirm transaction by clicking on `Send` button.

*Written by: Danger & Covalent, Last Edit: April 14, 2021*
