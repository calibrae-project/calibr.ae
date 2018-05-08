# Calibrae White Paper Outline
This is a bullet-point based outline of all the elements of Calibrae set forth in the work-order that they need to be implemented in.

## Spawn - GPU resistant PoW coin with 1 minute blocks, linear supply growth and zero fees

- Calibrae is a homophone for the Russian word Kolibri, meaning hummingbird, and Spawn refers to eggs. The Calibrae logo reflects this in a direct or indirect visual resemblance to a hummingbird in flight and the logo for Spawn will have a dominant image of an egg, and the initial primary CLI/GUI wallet will be called Nest.
 
- Initial solver for Hummingbird Proof of work exploits data cache locality for the reference, using the BAST (Bifurcation Array Search Tree) (cat logo) B-heap inspired search and sort algorithm, to discover solutions for a PoW based loosely on the Cuckoo Cycle but designed to require a much larger working memory requirement in order to minimise any advantage possible from non-general computing processors and expensive fast memory bus and high speed GDDR memory cells. 

  It is probable that with efficient flash storage caching systems that even very low cost SoC and ARM/Atom based platforms will be competitive on price-performance ratio.
  
- The first released miner application will be a closed source application based on BAST that will have a 1% hard wired developer contribution to the author(s) of the miner and the cryptocurrency node.
  

  This will function similarly to the way that Gold has a relatively stable annual percentage of supply expansion, that contributes to its utility as a primary settlement mechanism, though gold lacks the portability of cryptocurrency.

- Based on Piotr Narewski's [Gocoin](https://github.com/piotrnar/gocoin) - an extremely fast and featureful implementation of the Bitcoin daemon in Golang. It includes a very informative, realtime web interface for monitoring that even allows GUI based operations with the wallet.

### Blockchain Parameters

- 1 minute block time - Because why should a blockchain be any slower than it can be?

- 8Mb initial block size cap but blocks can be as small as the number of transactions in the one minute period.

- Block rewards are calculated instead of using a bi-annual halving sequence, by an exponential decay algorithm that results in a constant expansion of supply of 5% per year. The token denomination is encoded with 128 bit fixed precision integer based numbers and mining for issuance never stops, though in first year 95% is issued, and then 95% of the remainder in year two, and so on indefinitely, for which reason there is no need for transaction fees.
  

## Kriya - Privacy focused GPU resistant PoW coin

- Name is from the Bulgarian word for hidden.

- Using the same parameters as Spawn, except with 5 minute blocks (due to higher processing cost for block validation), but built out from the Monero codebase to use Ring Signatures by default and Confidential Transactions to mask account balances and transaction sizes.

- Has a greater processing load so is better suited to secure storage of assets and especially large transactions.

### Why PoW?

- Spawn and Kriya are both Proof of Work coins because as the primary interface to outside markets requires strong security against censorship and provides also a benefit of creating a miner userbase who have skin in the game.

- Hummingbird PoW is designed to eliminate the use of economies of scale and large capital outlays to significantly advantage those already established from being able to outcompete and cause the centralisation of validation of these two base currencies to impact the project.

- The rest of the system works on a Proof of Service principle and is regulated by a reputation system rooted in the public forum system to prevent malicious actors to censor or unduly influence the direction of development.

## Spore BFT Database Replication Replication with multi-format store for other protocols

- This replication protocol will be derived from the SporeDB BFT database replication protocol.

- Blockchains make several assumptions about the types of data and their uses that are not always relevant to use cases. Complete global consensus and perfect auditability are not necessary for all types of data, especially for chat and email systems.

- Most systems use a single type of storage strategy but different types of data do not suit this for performance reasons. Notably, Graph databases are very poor at coping with large data objects,  NoSQL and Key/Value are not as bad but better suit small data payloads.

  Therefore there will be 5 primary backends that can be used depending on the type of data (data sizes are related to hardware block sizes for memory and nonvolatile storage):

  - 512 byte blocks for short messages like microblogs and instant messaging.

  - 4Kb blocks for email and forum posts

  - 1Mb blocks for still image and audio content

  - 8Mb blocks for video content

  - Graph database system for breadth first searches into content, where Graph databases have the advantage over other types by their nonlinear structure.

- Infrastructure providers have the option of deciding exactly which protocols they want to participate in, depending on their capital and existing available infrastructure.

- Calibrae Spore servers also allow route cost and geographic proximity propagation strategies in order to further reduce latency, depending on the need of the application.

  This will allow transaction clearance times with high confidence to be as low as 100ms in metropolitan and regional networks for the use of the platform to run interactive action games as well as forming the basis of the messaging system.

## Decentralised Exchange and Per-Protocol tokens for monetisation

- Liquidity providers operate bridges between the Spawn, Scriya token, and potentially any other cryptocurrency, and the internal Calibrae Spore based application protocols tokens and networks.

- Decentralised Exchange order books are distributed using the Spore server system allowing extremely low latency trade execution.

- Every application built on Calibrae issues tokens that are able to be traded through the decentralised exchange in order to allow market price discovery of the value of the activity occurring inside each protocol.

## Spore - Interest bearing token

- In order to generate interest in participating in the Calibrae network and buying Spawn tokens, through the DEX users will be able to trade Spawn for Spore tokens, and to earn rewards on Spore users run a full node that verifies transactions, and their record of verifications enables a consensus to calculate a daily percentage reward for helping run the network.

- Most existing staking currency systems have payout protocols that pay stakers too infrequently once the supply gets beyond a certain size, so a token that pays daily interest will be a strong motivation for users to run a full node for this in order to profit from HODLing one of Calibrae’s subtokens. This also helps to generate demand for purchasing Spawn tokens for those who want a simple, predictable yield on their investment.

## Decentralised Exchange Margin Lending Market

- In cryptocurrency exchanges such as Bitfinex, it is possible to stake part of your holdings in your accounts to be lent out to facilitate margin trading. 

- This feature will also be added to the distributed exchange so that any token that can be held on the DEX can be staked as being available for lending at a user-specified interest rate, and secured by automated closure of losing trades before the interest payment cannot be paid out of the balance on margin trades.

## Reputation based Crowdsourced Monetisation and Security
  
- Skin in the game - preventing the externalisation of negative consequences from bad behaviour and poor leadership.
  
- Reputation system is based on a simple currency based system with a flat percentage supply with only the effect of assigning rewards to posts in the various formats.
  
- In the social and media distribution protocols, negative votes can be applied that place a hold on both the voter and the target content, or account, the negative votes are bilateral in their effect to counter malicious use of them. 

- Users running infrastructure for the network can lose reputation when their services are unreliable, unstable or unfaithful, and peers will automatically report this.

- The automated fault reporting by infrastructure nodes also is bilateral in its effect, to prevent malicious abuse of this mechanism for promoting reliable, available nodes for the network.

- Infrastructure providers trust levels in the spore network are tied directly to reputation in the forum, as these trusted third parties must be communicative with the users, and thus benefit from philanthropic types of behaviour in having their nodes favoured by users.

- By making it possible to upvote or downvote content and users, the social discourse is self-regulating and with the cost of downvoting being bilateral, peaceful interaction is promoted while enabling the suppression of bad behaviour on the network without centralised moderation.
  
- Monetisation of Spore nodes is based on their provision of access into the network from clients, by delivering either RPC service or Node/Angular based web application.
  
- Using a system of cosigning, similar to Beneficiaries, on the Steem platform, every post propagated into the Forum and Git Repository system has a commission paid to the infrastructure providers, which functions as proof of service and a means to fund the infrastructure. 
  
- When infrastructure operators upset the community their frequency of being used for these services will be generally diminished (users can manually override but random selection of a nearby node for access to the  network will be weighted by reputation by default), acting as a regulator to prevent the abuse of this service provision to acquire an undue share of token distribution.
  
- Also, the web applications delivered by nodes will be audited via the P2P VPN system by other nodes and inconsistencies can be flagged through downvotes against the account tagged as such.

## Forum/News and Media distribution and monetisation system

- The most simple application for the Calibrae Spore network is the forum.

- The forum will have multiple protocols that cover each different type of social media:

  - Microblogging, with 512 byte maximum post size for Twitter-like posts

  - News and commentary format with 4Kb sized blocks for storage for Facebook style posts, and Microblog comments attached to them.

  - Still image and Audio post formats stored with the 1Mb blocks, with Microblog comments.

  - Video posts with 8Mb block storage and Microblog comments

  - The forum is the primary way and most accessible to all users for acquiring basic reputation scores and communicating with the public. The reputation system ensures that the most visible and rewarded content is broadly accepted and undesirable and malicious content is reduced in visibility and unrewarded.

- Reputation acquired in the forum is the primary basis upon which network clients will select the nodes through which they will interact with the network.

## Software Repository System

- Through similar mechanisms as used in the Forum/News system, the software that the Calibrae network operates on itself is hosted within the platform, which is called **Self Hosting**.

- Software development contributors have a distinct and separate reputation score system that is used to promote and reward productive contributors and suppress malicious detractors.

- Voting systems based on the reputation system determine the right for contributions to the codebase, using a quorum requirement, to flow upstream to testing and then eventually to the production/live system.

- All nodes in the network will automatically update themselves when the change sets that have been approved in the testing branches are migrated to the production branch.

- The system will not only provide hosting for the system itself, but also allow any software content to be established, though generally this content will be related as the idea is this serves as an incubator and system to remunerate contributions to the network system and applications that interact with it.

- The Software Repository System functions as a governance system for the regulation of the software that runs on live, potentially sensitive and valuable transactions between users.

- Once this system is built the Calibrae network becomes a fully autonomous organisation and its users effectively citizens of a new, non-geographical State.

## Secure Instant Messaging, Voice and Video Conferencing and Email

- Both open public and cleartext messages as well as peer to peer encrypted and moderated transparent and encrypted chatroom formats enable communication between users.

- Unmoderated messaging systems have the ability to block receiving of content from users the recipient does not want to see, and moderated messaging systems are based on a centralised propagation of messages that messaging infrastructure providers operate that enable private groups whether the content is encrypted to users or not.

- Messaging system optimises traffic paths to minimise the latency of signal transmission and reduce the number of nodes that may act as middlemen in transmissions.

  In cryptography, any signal that is passed through an intermediary exposes the risk of various kinds of network attacks and surveillance, so for this reason it is better if there is less. However, as users can use the VPN services this can further reduce the location visibility of users.

## Peer to Peer VPN services

- Similar in principle to Tor and I2P networks, but using a system of service vouchers to provide anonymised payments for infrastructure provision, and a protocol for secure escrow based swapping of vouchers between nodes to further obfuscate connections between users and traffic and the use of the Scriya token for payment to make it impossible to track the traffic while limiting use of the anonymisation routing services for malicious behavior through a cost for using the services, which also serves to fund the providers of infrastructure for this.

- Modular, programmable client-side routing systems that use both multi-hop onion routing as well as Secret Shares based parallel multi-path onion routing for lower latency transmission.

- Uses forward error correction to reduce retransmission and signal drops and attempts to cut communication channels for users in hostile environments.

## Peer to Peer Marketplaces

- Simple classifieds, various types of auction structures, and crowdfunding systems will be developed and regulated also through a protocol specific reputation score which is used to both provide a reward for positive feedback in the form of protocol specific tokens as well as suppress the rewards and visibility of malicious traders.

## Computation Services

- Infrastructure operators will also have the option of providing general purpose computation, both CPU, GPU, FPGA and ASIC compute systems and monetised through a proof of service signature based system.

- This system can also be used to implement network gaming engines and collaborative work platforms as well as selling large scale infrastructure services such as rendering farms, compute farms for deep learning, simulations and modelling, and anything that can be parallelised and function over a higher latency network.
# Roadmap

First steps, already in progress are all about developing the Hummingbird Proof of Work:

- BAST sort and search algorithm

- Hummingbird graph theoretical proof of work

- Forking Gocoin bitcoin daemon to make Spawn currency, to use Hummingbird, setting parameters such as block time, block reward formula, changing the currency denomination precision calculations to 64 bit fixed point.

- Creating the database system to handle Calibrae accounts, including frameworks to include external identity verification bindings, and building the base account system with spaces for storing ledgers relating to reputation

- Forking SporeDB to add a full dynamic peer discovery system and connecting it to the reputation system of the accounts

- Building the database store backends required for the various data types stored in Calibrae node databases

- Creating the forum database system and designing the voting and rewards system and computing reputation scores created by voting behaviours

- Build the web application that is served by Spore nodes to users, as well as the website based redirector that farms out application service to users, as well as the monetisation system built into the RPC that allows node operators to be paid for their services

- Extending from the forum system, build the repository system, first with a wiki, and then to the Git repository system, adding the voting and rewards calculations, and the quorum for automating pushing commit sets up into testing and then from testing into the live system

- Extending Spore to enable locality and latency aware propagation patterns in order to implement the Chat, Email and basic collaborative document working systems

- Building the routing function into the Spore node system and creating the modular routing programming framework to enable location obfuscation and monetisation of routing services

- Forking Monero to Kriya to use Hummingbird and the same supply and data replication parameters.

- Creating the marketplace system, first with classifieds, then add auctions and crowdfunding systems

- Building a base protocol for negotiating contracts for computation service provision.
