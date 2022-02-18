---
title: Necc - The latest in ponzinomics experiments
date: 2022-01-02 
draft: false
author: Peter Horton
description: <a href="https://twitter.com/ph0rt0n">By Peter Horton</a>
dropcap: false
---
<meta property="og:image" content="https://bcblockchain.org/posts/necc/Picture3.png"></meta>
<meta property='twitter:image' content='https://bcblockchain.org/posts/necc/Picture3.png'></meta>
<meta name="twitter:image" content="https://bcblockchain.org/posts/necc/Picture3.png"></meta>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Every day, wake up, drink coffee, brush teeth, necc. That is the mantra of Necc, a new protocol on Aurora that defines itself as a “decentralized interest bearing inverse perpetual swap protocol.” If that sounds like a medley of various existing DeFi protocols, well it is. DeFi 2.0 is all about composability and interaction between dApps, and Necc takes this ethos to the max. Necc combines three sub-protocols (leveraged trading, stablecoin minting, and Olympus bonding/staking), intertwining their mechanics and assets under one mega protocol. Its team is led by Eric Juta, a former ConsenSys developer who also happens to have a rather <a href="https://twitter.com/c0syboi/status/1475230970743857159">thick necc</a>. With its innovative blend of protocols and strong memeability, Necc has developed a small cult following and attracted the interest of several notable CT figures.

<div class="container">
<div class="gallery">
  <style>
  *,
  *::after,
  *::before {
    margin: 0;
    padding: 0;
    box-sizing: inherit;
  }
  .gallery {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: repeat(1, 25vw);
      grid-gap: 0.5rem;
  }
  .gallery__img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    display:block;
  }
  .container{
    width:100%
    margin: 2rem auto;
  }
  </style>

  <figure class="gallery__item gallery__item--1">
    <a href="https://twitter.com/blknoiz06/status/1475543794405810180">
    <img src="/posts/necc/Picture1.png" class = "gallery__img" alt="Twitter Link">
    </a>
  </figure>
  <figure class="gallery__item gallery__item--2">
    <a href="https://twitter.com/mattysino/status/1475656968001839107">
    <img src="/posts/necc/Picture2.png" class = "gallery__img" alt="Twitter Link">
    </a>
  </figure>
</div>
</div>

&nbsp;
&nbsp;
&nbsp;

But before diving deeper into Necc, let's first take a look at Aurora.

#### What is Aurora?
<b> Tech </b>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In short, Aurora provides an Ethereum L2 experience on NEAR. NEAR is a sharded proof-of-stake blockchain, but at the moment contracts are written in either Rust or TypeScript. This presents developers with a trade-off if they want to build on NEAR. Enter Aurora. Aurora is an EVM machine built on NEAR by former NEAR team members. Aurora Labs CEO Alex Shevchenko likes to describe Aurora as taking a great old car that is now inefficient and pollutant (i.e. Ethereum) and replacing its engine with a faster, more eco-friendly version (i.e. NEAR). In efforts to not change anything except the engine, gas fees are paid in ETH on Aurora, a stark contrast to other EVM compatible L1s and even Ethereum L2s. Why would NEAR want a protocol built on top of it that accrues value to ETH, not NEAR? Well, gas fees technically aren’t paid in ETH, that’s just how it appears to the user. Since Aurora is a NEAR smart contract, all transactions still have to be paid using NEAR, which the RPC pays and is then reimbursed for with the user’s ETH. This allows a seamless transition from Ethereum (and other EVM compatible L1s) to Aurora for users and developers while still benefiting the underlying ecosystem. At the time, all of this is somewhat a moot point because users currently do not have to pay any gas fees. Yes, Aurora has free gas! Fees are being subsidized for the next month or so, until Aurora launches a secret project that will “revolutionize” gas fees and how dApps are built, according to Shevchenko (from around the eight minute mark of <a href="https://www.youtube.com/watch?v=hekE-jR3dFs"> this video.</a>)

<b> Ecosystem </b>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The combination of free and quick transactions, a familiar UX, and an $800m NEAR ecosystem fund has recently spurred activity on Aurora. With only a handful of dApps, Aurora’s TVL has surged from around $100m to almost $600m in the past month. A majority of Aurora’s TVL comes from Trisolaris, your friendly neighborhood DEX. Rose serves as Aurora’s liquidity protocol (think Curve) and was the first project launched on Nearpad, an IDO launchpad (think Avalaunch). With a dog/meme coin (AuroraShibaMoon), an OHM fork (Empyrean DAO), and multiple rugs, Aurora ticks all the boxes of the “EVM starter ecosystem” checklist. Joining these native protocols are cross-chain protocols and tools such as Aave, Curve, Sushiswap, 1inch, The Graph, Connext Network, Flux, and Etherscan, which have already deployed on Aurora or soon will. While Aurora’s so-called “holy trinity” ($tri $pad $rose) could certainly stand to benefit if more users migrate to Aurora, as standalone protocols they largely do not offer anything new to the DeFi landscape. In steps Necc.

#### How does Necc work? 
<img src="/posts/necc/Picture3.png"/>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The simplest way I’ve seen Necc described is from a twitter thread by Diamond Cock DAO (a group consisting of those especially keen on the Aurora ecosystem) member <a href="https://twitter.com/AnonUser_404/status/1475180202326167562">0x1337.near</a> who sums up the protocol as “bitmex x maker x ohm.” Let’s break these down.

<b> Necc as Bitmex: Trade </b>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Necc users can long or short assets using inverse perpetual contracts, a product first introduced by Bitmex in 2016. For those unfamiliar, perps are similar to futures except they have no expiration date and with inverse perps profit is taken in the speculated asset rather than in USD. Necc currently offers ETH, BTC, and NEAR inverse perps with up to 30x leverage. As a whole these positions are delta-neutral, meaning that the protocol does not have a directional market view. Necc provides assets for traders to borrow as leverage from its pools of liquidity. But how does Necc attract liquidity and grow its assets under management (AUM)?

<b> Necc as Maker: Mint </b>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Just like Maker, Necc has both a native asset (NECC) and an asset soft-pegged to the USD (NDOL). In order to mint NDOL, users sell whitelisted collateral to the protocol. 1 NDOL is minted for every $1 of collateral supplied (minus fees). NDOL can be redeemed back for any of the collateral assets at a rate of (collateral in pool) / (NDOL amount minted from that collateral). Thus, NDOL is technically an index weighted stablecoin, since it reflects the value of the underlying basket of collateral. Ok, so if users mint NDOL, then the protocol can lend the supplied collateral to leveraged traders, but why would a user want to mint NDOL?

<b> Necc as Olympus: Bond </b>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Necc incentivizes NDOL minting through the ever popular Olympus model. Users that mint NDOL can either stake it or sell it for vested NECC. Necc’s bonds have the same design as Olympus, which you can see the equations for <a href="https://docs.olympusdao.finance/main/references/equations">here</a> if interested. NDOL stakers receive a 1% bond fee rate in the form of nNECC (yes nNECC, not NECC). nNECC is simply the staked version of NECC and its price equals NECC’s price * the current index. As more bonds are purchased, nNECC accumulates more NECC with hourly rebases, generating yield for NECC stakers (aka nNECC holders). Bonds are not only purchased by users, but also by the protocol itself, using the fees generated from its trading and minting sub-protocols. NDOL and LP bonds allow Necc to own its collateral and liquidity, increasing the amount that leveraged traders can borrow and overall growing and stabilizing the protocol through strategic deployment of its treasury. 

<b> Putting it all together </b>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Necc’s docs provide <a href="https://docs.necc.io/liquidity-flow-diagrams">eight diagrams</a> which help illustrate how liquidity flows during its various mechanisms. Additionally, we can construct a diagram that shows generally how the three sub-protocols interact with and benefit each other.
 
<img src="/posts/necc/Picture4.png"/>

-	(Blue) Users sell whitelisted collateral to the protocol in return for minted NDOL. Traders can then borrow this collateral for leveraged trading.
-	(Green) NDOL holders can either stake their NDOL or sell it for vested NECC. Bonding generates yield for NDOL stakers in the form of nNECC, at a 1% bond fee rate. 
-	(Purple) Bonders redeem their NECC and can stake it in the form of nNECC, receiving yield from further bonding. 
-	(Orange) High yield for NECC stakers is partially sustained by the protocol’s fees. Fees from minting, burning, borrowing, and trading are strategically swapped to one of the whitelisted collateral (depending on current collateral pool ratios) through an external AMM. The collateral is sold for NDOL which is used to purchase bonds. Redeemed NECC is staked for nNECC which allows the protocol to afford rebases and reward nNECC holders.
-	(Red) Bonds in the form of NDOL and LP tokens raise the supply of NECC, distributing yield to NECC stakers. It also gives the protocol ownership over its collateral and liquidity. This allows for more trading and for the protocol to deploy its treasury for other uses when necessary. For example it could deploy treasury funds to stabilize the minting sub-protocol if NDOL’s redemption rate falls below 1.
-	We can see how this creates a cycle where more trading -> more fees -> higher yield -> more liquidity -> more trading. As this cycle continues to repeat, the protocol will become more and more stable. 

#### Outlook
<b> Stats </b>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In less than a week, Necc’s AUM has grown to $5 million and the protocol has generated almost $800k in fees! For most of the time, the utilization rates for the protocol’s ETH, NEAR, and BTC have been very close to 100%, indicating a strong demand for leveraged trading that will continue accruing fees for the protocol and NECC stakers as more liquidity flows in. After bouncing between $300-$1000, nNECC’s price quickly rose first to $4000 and then to almost $11,000 within 48 hours of launch. nNECC has currently been sitting in the $3000-$4000 range, with a market cap of over $10,000,000. APY for staking NECC has ranged from around 1,000-4,000%, but this has partially been suppressed because the team’s tokens are currently staked. Eric has voiced plans to unstake these tokens and lock them somewhere (they would burn them but that would reduce the amount of bonds that could be purchased), which will help increase the APY.

<b> Risks </b>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Due to its experimental nature and many moving parts, Necc is inherently a risky play. Composability between protocols is great but it also enhances smart contract risk and design flaws – if one part of the protocol fails, it can all come crashing down. As was expected, Necc experienced some early hurdles. The protocol’s debt ratio rose to over 2,000,000% due to nNECC’s dramatic price appreciation, which prevented any further bonding at the time. Additionally, ETH’s price depreciation since Necc’s launch combined with a relatively small amount of liquidity in the protocol has driven the redemption rate for NDOL to under 1. Lastly, initially launching without LP bonding (due to some Aurora network imposed limits) limited the effectiveness of the protocol. In response to these issues, Necc’s team has responded exactly how you’d want. Eric has been extremely transparent throughout the whole process, open-sourcing the Github after launch, hosting an impromptu AMA, and constantly inviting discussion and contributions to further the protocol.

<b> Roadmap </b>

In the short term, Eric’s focus will be on smoothing out problems that arise and stabilizing the protocol. But the team has also teased future improvements to the protocol. One of its most exciting plans features leveraging Connext Network once it integrates with Aurora to allow for cross-chain interactions. As Necc’s <a href="https://neccdao.medium.com/necc-protocol-project-partners-1b8dcc2c4cb0">first blog post</a> puts it: “Imagine opening a $NEAR inverse perpetual position on Aurora by putting down $AVAX collateral on Avalanche.” Other plans include allowing NDOL to be used as collateral for trading, formalizing community involvement through a DAO, and adding more LP pairs for bonding.

<b> Closing Thoughts </b>

If Necc continues to generate $800k in fees per week then its current $10m market cap seems far too low. But in order to do so Necc will have to continue improving its algorithm and game theory. Of most concern at the moment is the inability for users to burn their NDOL at a good price. The redemption rate from NDOL to ETH has been around .75 for the past several days, and users cannot redeem for NEAR or BTC because those pools are fully utilized. However, I’m confident that Eric, who’s as much of a based dev as I’ve seen, and the community, through conversation and decentralized governance, will be able to find solutions. If you’re looking to bet on the Aurora ecosystem, Necc is certainly a more degen play. However, due to its innovative qualities and strong community I can see Necc being a protocol that attracts new users to Aurora, in a similar vein as to what DeFi Kingdoms has done for Harmony (although likely not to the same extent). Whether it fails or succeeds, we can applaud Necc for being an ambitious and interesting project, and it'll be fun to watch in the coming year.

Resources:
-	<a href="https://www.necc.io/">Necc protocol</a>, <a href="https://discord.gg/U7hnpvzR">discord</a>, and <a href="https://twitter.com/neccdao">twitter</a>
-	Follow nNECC’s price <a href="https://dexscreener.com/aurora/0xad5779da21408e70973ac56ab91dbf201b45b652">here</a> (make sure to toggle to switch to price in NDOL, not USD - and ignore the market cap figure here)
-	If interested in bridging to Aurora (or any network), check out <a href="https://docs.google.com/spreadsheets/d/1jYZOfU2R3PdzRmnY9Nfc4pzerX_YSInNdyhtSj_3oWY/edit#gid=0">this guide</a> by Necc mod <a href="https://twitter.com/XLBao">Kuro</a>
-	To stay up to date with the Aurora ecosystem, check out this (very incomplete) <a href="https://twitter.com/i/lists/1475642232338358275?s=20">twitter list</a>

#### <a href="https://twitter.com/ph0rt0n"> By Peter Horton <img src="/cleartwitter.png" width=50vm height=50vm style="display: inline-block; margin:0; vertical-align:-15px" /> </a>

Januray 2 2022

*Disclaimer: This report is for educational purposes and should not be construed as investment advice. Additionally, the author may hold any of the assets mentioned.*
