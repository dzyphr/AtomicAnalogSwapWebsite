---
title: "Swap Tools Documentation"
date: 2024-08-18T19:38:36-05:00
draft: true
# weight: 1
# aliases: ["/first"]
tags: ["Security", "Documentation", "Docs"]
author: "Atomic Analog Developers"
# author: ["Me", "You"] # multiple authors
showToc: false
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "AtomicAPI Documentation"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: true
disableHLJS: false
hideSummary: true
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

Tools for interacting with existing atomic swaps

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `checkSwapState`

returns true if the specified swapID's swap state is the expected swap state
#### checkSwapState Signature

```python
def checkSwapState(swapID, state) -> bool :
```
### Parameters

- `swapID` (string)
- `state` (string)
---
### Function: `setSwapState`

Sets the specified swapID's 'SwapState' file to the specified Swap State

#### setSwapState Signature

```python
def setSwapState(swapName, state, setMap) -> bool :
```
### Parameters

- `swapName` (string)
- `state` (string)
- `setMap` (optional: bool) if True will write the state to SwapStateMap json file 

(setMap may be mandatory in future)

---
### Function: `watchSwapLoop`

Takes a SwapID / SwapName and executes any remaining tasks according to swapstate. 
Used for hot reloading.
#### watchSwapLoop Signature

```python
def watchSwapLoop(
    swapName, localChainAccountPassword, crossChainAccountPassword
) -> None :
```
### Parameters

- `swapName` (string)
- `localChainAccountPassword` (optional: string)
- `crossChainAccountPassword` (optional: string) 

---
### List: `PossibleSwapStates`

A list of possible swap states that a swap Responder (Swap Client) will run through.

#### PossibleSwapStates Signature
```python
PossibleSwapStates = [
        "initiated", #0 
        "uploadingResponseContract", #1
        "uploadedResponseContract", #2
        "fundingResponseContract", #3
        "fundedResponseContract",  #4
        "responding", #5
        "responded_unsubmitted", #6
        "responded_submitted", #7
        "finalized", #8
        "verifyingFinalizedContractValues", #9
        "verifiedFinalizedContractValues", #10
        "claiming", #11
        "refunding", #12
        "claimed", #13
        "refunded", #14
        "terminated", #15
        "tbd"#16
]
```
---
### List: `PossibleSwapStatesInitiator`

A list of possible swap states that a swap Initiator (Market Server)  will run through.

#### PossibleSwapStatesInitiator Signature
```python
PossibleSwapStatesInitiator = [
        "initiating", #0 
        "initiated_unsubmitted", #1
        "initiated_submitted", #2
        "responded", #3
        "verifying_response", #4
        "verified_response", #5
        "finalizing", #6
        "finalized_unsubmitted", #7
        "finalized_submitted", #8
        "claiming", #9
        "refunding", #10
        "claimed", #11
        "refunded", #12
        "terminated", #13
        "tbd" #14
]
```
---
