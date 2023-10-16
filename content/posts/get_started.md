---
title: "Get Started"
date: 2023-10-02T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["GetStarted"]
author: "Atomic Analog Developers"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "How to use Atomic Analog Swap"
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
UseHugoToc: true
cover:
    image: "https://cdn.iconscout.com/icon/free/png-512/free-atom-31-117013.png?f=avif&w=2048&h=2048" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: false # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

Atomic Analog Swap is a platform for cross-chain [Atomic Swaps](https://bitcointalk.org/index.php?topic=193281.msg2224949#msg2224949).
Atomic Swap is a cryptographic protocol that enables multiple parties to exchange without trusting eachother.
The protocol relies on off-chain AND on-chain scripting conditions. 

Read more about our specific Atomic Swap implementation here: [TBD](/TBD)

About the Application:


On our end we host a REST-API end point, this gives users with a public APIKEY the ability to query information about swaps. 
On the user's end, they will self-host a client that runs important cryptographic and RNG functions in accordance with the atomic swap protocol.

It is vital that the user's hardware is generating it's own cryptographic secrets and seed randomness, otherwise we could not guarentee the security of the protocol.
Using the client we are developing, a user can set parameters for a swap and have it carried out via automation. Therefore the user does not need to understand the difference between an atomic swap and any other kind of swap in order to use the platform. 

Our goal is to achieve a platform that has a similar feeling that other platforms provide, except running in a self-hosted environment for security purposes. We are constantly looking for feedback on improving this experience, to leave us suggestions please visit our Discord community: https://discord.gg/fWTVdvgep2 and go to the #feedback channel!

How to Start:

**NOTE: WE ARE CURRENTLY IN ALPHA / TESTNET-ONLY PHASE**

**DOCS ARE SUBJECT TO CHANGE**


Requirements for building and usage:

- OS: Linux

- Langs/Compilers: Rust, Python, C++, JavaScript

1. Clone a copy of AtomicAPI from GitHub: https://github.com/dzyphr/atomicAPI  
2. Run the setup script
3. Launch AtomicAPIFullClient (Includes client REST-API and webUI)
4. Navigate to [http://localhost:1313/AtomicClientUI](/TBD) Connect to [https://AtomicAnalogSwap.com/marketAPI](/TBD)
5. Browse swap offer information and make a swap!










