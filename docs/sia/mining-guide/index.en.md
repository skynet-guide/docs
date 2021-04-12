# Mining Guide
First of all, you should know that mining is one of the most competitive activitites one can do. Miners are using expensive hardware (ASIC – Application-Specific Integrated Circuit) in order to race to find a special sequence of characters (called hash) purely by luck. Of course, you can get the luck on your side or join forces with others and split the reward each time your group (called Mining Pool) is successful. Let’s look at it in more detail.

## What is blockchain?
Blockchain is nothing special, it is just kind of database where data are contained in structures called blocks and they are added on top of each other in a way that makes it impossible to change any block without changing all of the following blocks.

What is making blockchain unique and amazing technology is decentralization. Blockchains like Bitcoin or Sia are decentralized which means that if you want to change anything, you need to get all computers participating in the network to agree with the change, which is practically impossible. That’s why it is called immutable.

When it comes to new blocks, they need to be validated by the network as well. Each node validates it separately and if it finds ok, it adds it to own copy of blockchain.

## How are blocks created?
Whenever a transaction happens on the network, it is added to a transaction pool. That’s a special place a miner looks into and adds the transactions to a block. And at the same time he constantly attempts to find a matching hash – one that will work as signature for block’s content. This involves a lot of luck and is a reason why it sometimes takes a minute to find a block and sometimes 30 minutes or rarely more.

This process is called Proof of Work (PoW) and is one of the best consensus mechanics since it guarantees that in order to find the blocks, a lot of computation (hashrate) needs to be happen.

Let’s introduce a constant now, block time = 10 minutes. You might think “But the blocks are never found every 10 minutes!” and you are right. This time is used to keep track of mining schedule. If a lot of hashrate connects to the network suddenly (it is common each time new ASIC is manufacturer), miners will start finding blocks in very fast succession.

But if you are worried this means that with more hashrate you can make too many coins quickly, you are wrong. This is where difficulty and the schedule comes into play. Difficulty is special kind of value that increases when blocks are found ahead of the schedule and decreases when it’s behind. This change happens every single block (unlike for Bitcoin where it happens in specific intervals) and means that if a lot of blocks was found quickly (for example 1-3 minutes), next blocks will take much longer (can be 20-60 minutes). And that’s all thanks to the difficulty value that directly affects the chance that valid hash is found in relation to the available hashrate.

And the most important part is… only the one miner that found the hash, signed the block and broadcasted the block to network gets the block reward.

After that, process repeats with new block. Over and over.

## What are you telling me? That I need to find the block myself?
> No, Neo. I’m trying to tell you that when you’re ready, you won’t have to.

That’s one option. Some miners run their ASICs as kind of lottery. If you know that network hashrate (can find in [Network Metrics](/discover/network-metrics/index.en.html)) is 8,600 TH/s and you have one miner with 2.2 THS hashrate, it means you are 1 / 3909 of the total hashrate. In other words, you should find roughly 1 block per 3909 blocks, which can be translated to 27 days. Of course, due to the luck factor, you can find 3 blocks in a week or no block in 3 months. But usually over longer period of time this gets quite accurate. Especially if you run more miners than one.

And that gets us to the [Mining Pools](/mining/mining-pools/index.en.html). These are special sites where you get the address of the server and then use it in configuration of your miner. Each computation (share) of your miner is sent to the pool and this allows many miners to co-operate. It is very fair since the mining pool knows exactly how many shares who sent (miners with higher hashrate will contribute more) and the rewards are then distributed fairly according to the number of shares submitted by you in relation to the total number of shares submitted by everyone using the same pool.

Now that we covered the principles, let’s look at what should you do.

## Should I start mining?
This really depends on what is your **goal**.

**If you want to help the ecosystem to be more secure and hashrate better distributed**, just go on. You should make sure you don’t do it at a loss since your electricity is likely more expensive at home than for those who run it in colocation centers. And if you do, then at least try to find secondary use to it. Since ASICs generate a lot of heat, many miners use single or multiple units for heating of their homes and garages. In that case always take safety measures and don’t hesitate to ask others for help. Also you should know that ASICs are making A LOT of noise.

**If you want to do it for profit**, you need to do a lot of research, preparation and calculation. There is cost to everything – Hardware, Hosting / Location, Electricity. Since miners can relocate (they are heavy but can be moved) quite easily, you need to select right location and that will allow you to get cheap electricity and renting cost. You can also go for renewable sources of energy. Those have higher initial cost but allow you to run the miners for their entire lifetime (until they break). Popular choices are hydropower or solar power plants.

> There is one special term that every miner knows well – `Return of Investment (ROI)`. You should always keep in ming in how much time you can recover your initial investment.

Also keep in mind it’s all very risky. Some manufacturing companies in the past didn’t hesitate to kill the ROI of own customers by over-producing units so much that only the manufacturer ever did any profit. There were also many miners that were promised and accepted pre-orders but never delivered. You should always verify that what you pay for is a real thing and that manufacturer doesn’t play against you.

If you decided that you want to start mining, continue with our [Hardware](/mining/hardware/en.md) guide to learn how to buy and setup a miner and what to be careful about.

*Written by Danger (Jan 14, 2021)*  
*Updated by Covalent(April 5, 2021)*
