# Impermanent Loss Exercise

> DeFi exercise to experiment with the idea of impermanent loss

## TLDR

Write a node.js script that takes the Etherum address of a Uniswap *liquidity provider* and returns the *impermanent loss* for this account.

## The long version

### What's the purpose of this execise?

To see how fast you can learn new concepts by yourself and apply newly learned technologies. We hope that the TLDR sentence above is completely meaningless to you - that you have no idea what's *Uniswap* and you have never heard the term *impermanent loss*. Google is your friend. If you have no experience with blockchain/Ethereum, even better! No need to become an expert on any of these things, just pick up a few tutorials and combine the bits and pieces into something working-ish. We want to see how you learn something new and figure it out by yourself.

Here are some pointers to get you started in the right direction:

### What is Ethereum?

Ethereum is a globally shared cloud service where anyone can deploy code (these pieces of code are called *smart contracts*) and anyone can call the methods of this code (calling a method that writes data to persistent state is called *executing a transaction*). One of the popular applications of this technology is to write code that deals with decentralized money - money that is fully democratic and transparent and isn't being controlled by a small minority.

A popular web-based explorer that lets you query the Ethereum network, the smart contracts on it and their state is [etherscan.io](etherscan.io). Don't be afraid to Google to learn more, but be careful not to drown yourself in information.

### How can you write scripts that query Ethereum?

There's JavaScript API that's very easy to use in a popular library called [web3](https://web3js.readthedocs.io/en/v1.3.0/). Its github repo is [here](https://github.com/ChainSafe/web3.js). You can use node.js to run these scripts on your machine.

Don't be afraid to Google to find simple tutorials that show a working example you can fiddle with in 10 minutes.

### What is Uniswap?

Uniswap is a product that is implemented over Ethereum. Its website is [here](https://uniswap.org/). Basically, somebody wrote some code that implements a way to trade assets (for example convert USD to ILS). After they deployed it, many people now use it to trade different types of assets back and forth. It's worth to mention that nobody really operates this system, it's running on its own in a completely "decentralized" way.

You can see the assets being traded [here](https://info.uniswap.org/tokens). Note that it is possible to "digitize" assets that represent pretty much anything, from cryptocurrencies like Bitcoin, to stocks like Tesla and commodities like Gold. For example, the pair that trades between ETH (Ether, a cryptocurrency similar to Bitcoin, which is the native currency of the Ethereum network) and USD is seen [here](https://info.uniswap.org/pair/0xb4e16d0168e52d35cacd2c6185b44281ec28c9dc). If you're feeling adventurous, you can take a look at the smart contract source code on [etherscan.io](https://etherscan.io/address/0xb4e16d0168e52d35cacd2c6185b44281ec28c9dc#code).

### What is a liquidity provider?

The term *liquidity provider* is one of the roles of the Uniswap product. People can either be *swappers* - where they have one of the sides (just ETH **or** just USD) and they want to swap/trade for the other. Or they can be *liquidity providers* - meaning they have both ETH **and** USD and they allow others (the swappers) to trade between the two in exchange for fees.

Don't be afraid to Google to learn more. There are some cool animated YouTube videos that explain these concepts quickly. Some of the relevant keywords are DEX (decentralized exchange), AMM (automated market maker) and DeFi (decentralized finance).

### What is impermanent loss?

When a *liquidity provider* provides liquidity, they basically take a bunch of ETH (let's say X1) and a bunch of USD (let's say Y1) and give it to the Uniswap contract on Ethereum. After many swappers use this pool to swap back and forth between ETH and USD, the amounts X and Y change slightly. So eventually, when the liquidity provider wants to exit and take their money back, they would receive back X2 and Y2 instead of the original X1 and Y1. The difference in value between X1+Y1 and X2+Y2 is called *impermanent loss*.

Don't be afraid to Google to learn more. Again, many animated YouTube videos for this term.

### What tool do we want to build in this exercise?

People's accounts (wallets) on Ethereum are represented using a hex address. Here is one for example - [0xFcd300AaFE1fDB3166cd1A3B46463144fc2D46ad](https://etherscan.io/address/0xFcd300AaFE1fDB3166cd1A3B46463144fc2D46ad). This wallet is a liquidity provider that added $100 worth of USD (100 USDC tokens) and about $100 worth of ETH (0.062 ETH tokens at the time) as liquidity - you can see the transaction where this happened [here](https://etherscan.io/tx/0x9ff9f4837bc468f8b6b321f0d9a69739e1c39093f844835258d863c75d68f123). Now, our fearless liquidity provider wants to know if they are making more money due to the fees or losing money due to the impermanent loss. How can they tell??

Your simple node.js script will print out the answer. It should use the web3 JavaScript library to interact with the relevant Uniswap smart contract on Ethereum to calculate the answer (don't worry, there isn't any complex math involved).

### Questions? Anything is unclear?

We hope that *everything is unclear* and you have a million questions. Google is your friend, good luck.
