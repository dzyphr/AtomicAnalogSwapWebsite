---
title: "Security Information"
date: 2023-12-03T23:47:54-06:00
draft: true
# weight: 1
# aliases: ["/first"]
tags: ["Security"]
author: "Atomic Analog Developers"
# author: ["Me", "You"] # multiple authors
showToc: false
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Atomic Swap Protocol / Implementation Security Details"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: true
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: false
#cover:
#    image: "https://cdn.iconscout.com/icon/free/png-512/free-atom-31-117013.png?f=avif&w=512&h=512" # image path/url
#    alt: "<alt text>" # alt text
#    caption: "<text>" # display caption under cover
#    relative: false # when using page bundles set this to true
#    hidden: false # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link

---

# High Level Security:

### What is an Atomic Swap?

An atomic swap is a cryptographic protocol that allows multiple unique users to exchange secret data without needing to trust eachother.
For example a swap between two different "coins" that exist on separate [blockchains](https://en.bitcoin.it/wiki/Block_chain).

### How can this not require trust?

The elements of the protocol that are security prone are entirely transparent and can be verified by each user.
In our protocol Clients and Servers are programmed to automatically check security parameters everyime a swap is made.
Users can optionally increase their Client's security parameters if they feel the need to.

### What happens if a swap fails?

In the case of failure both the Client and Server will be able to get a refund from their own contract.
As soon as the lock time you agreed to when funding the contract expires, the Client or Server you are running will automate a refund.
Minimizing these lock times is a large security / UX tradeoff, we are doing testing to see what optimal cross chain lock times look like.
Until we gather more data about cross chain lock time security, we will employ conservative assumptions as a standard.


# Mid Level Security:

### What contracts are involved in an Atomic Swap?

Atomic Swaps require three basic contracts, two of which are on-chain and one which is handled entirely off chain. 
There is only one onchain contract per chain. 
Each peer publishes a contract from the chain that they are starting out on, they will end up claiming funds from the other peer's contract if the swap is successful. 

These contracts contain cryptographic curve point commitments, which basically means they are locked to very large securely randomly generated values. 
Though the values are randomly generated they are not arbitrary, they're generated through the setup of the offchain swap contract. 
Each peer has a copy of this contract locally, and uses it to set up the cryptographic commitments from the start to the end of the swap whenever needed.
 
This offchain contract influences the output of the onchain contract's cryptographic curve point commitments, allowing for both peers to verifiably interact with the contracts as expected. 
The offchain contract also handles things like the math behind extracting the secret value from an on chain claim commitment made by one of the peers, allowing the other peer to claim their side of the atomic swap. 

The setup for the onchain contracts will vary per chain since different chains require different implementations of these contracts.
However, currently we have implemented an Atomic Schnorr "Initiator" contract on Ergo, and an Atomic 256 bit preimage "Responder" contract on EVM. 
This allows us to facillitate a Pedersen-Schnorr-Atomic-Swap between an Ergo Initiator and EVM Responder.
We also have tested the contracts for the reverse setup, with the Schnorr contract on EVM and the 256 bit preimage contract on Ergo but that is awaiting API and UI implementation still as of right now.

### How does the Lock Time part of the contracts work?

Each onchain contract contains a locktime spending condition for "emergency" circumstances. 
From a client's perspective an "emergency" could consist of: swap server goes down mid swap, swap server gives you unsafe contract of any sort, swap server doesnt fund contract with minimum expected value, etc...

In these circumstances, the contract has a clause which says that if your intended recipient (the server in this case) does not claim the swap by block x (currently determined using current height + lockTimeInBlocks, might be updated to use timestamp for more accuracy against reorgs in the future) then you can call the refund branch using null / public data and reclaim your funds from the contract. 
The server's contract also has the same "emergency" spending condition branch / clause for similar "emergencies" that might be signaled by one of it's clients.

Since block times are different on different chains, precautions have to be made to prevent "double spending" from swap contracts from poorly set lock time parameters. One solution in the future might be to utilize timestamps only within explicitly valid parameters that would prevent this regardless of blocktime variation. 
However until that is implemented, we need to overestimate the amount of blocks it will take for both chains to wait the same amount of time.

For example if you want a ~1hr lock, calculate the expected blocks per 30mins per chain, then add a buffer of 10-20 mins worth of blocks on top of that to be safe. 
If one of the chains happens to run into low variance during that period the buffer should account for that difference. 
In extremely paranoid circumstances one could set an extremely long lock time, but has to keep in mind this is the time they are committing their funds into a lock to as well. 
So it has major UX impact to consider when setting, making timestamp based locking way more appealing.

### What Security Assumptions are made about communication between Client and Server?

The Server is expected to have high uptime, and will have a public API endpoint that the Client can add via their UI generally speaking. 
The Client can check what ElGamal public keys the Server has available, generate a compatible one if needed, then request an encrypted initiation from the Server. 

The Server encrypts the initiation to the public key specified by the client establishing the encrypted communication channel. 
When the Client has a response they encrypt it to the Server's ElGamal public key.
The ElGamal encryption prevents any middlemen between the client and the server from spying on the swap data, this can help prevent things like frontrunning.

The Server has public REST API Keys used for starting communications, at the moment these are all that is needed for communication but this will not suffice for a secure public mainnet setup. 
It's currently still in the plans to establish a REST API key security protocol.

At the moment the client is being designed so it wont ever need to open any ports, this means all REST API interactions happen completely privately between the Client's UI and the REST API exclusively. It mainly functions as communication between the localhost browser and atomicAPI.

