---
title: "Responder Interface Documentation"
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

Function Interace for Swap Responder Role / Swap Client Role

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `process_initiation`

Decrypts am encrypted atomic swap initiation json and saves it to DEC_filepath

#### process_initiation Signature

```python
def process_initiation(
    ENC_filepath, DEC_filepath, SenderPubKey, UserKeyFileName
) -> None :
```
### Parameters
- `ENC_filepath` (string)
- `DEC_filepath` (string)
- `SenderPubKey` (string)
- `UserKeyFileName` (string)

---
### Function: `response`

Generates an atomic swap response according to an initiation, saves response data into responder.json

#### response Signature

```python
def response(
    DEC_initiation_filepath, responderMasterJSONPATH, 
    response_filepath, SenderPubKey
) -> None :
```
### Parameters
- `DEC_initiation_filepath` (string)
- `responderMasterJSONPATH` (string)
- `response_filepath` (string)
- `SenderPubKey` (string)

---
### Function: `GeneralizeENC_ResponseSubroutine`

Generalized function to handle everything involved with responding (responder / swap client role)
to a swap initiation including deploying and funding the response contract.
Calls response. 
#### response Signature

```python
def GeneralizeENC_ResponseSubroutine(
        swapName, responderCrossChainAccountName, responderLocalChainAccountName, 
        ElGamalKey, ElGamalKeyPath, InitiatorChain, ResponderChain, swapAmount, 
        localChainAccountPassword, crossChainAccountPassword, reloadSwapState
) - > None :
```
### Parameters
- `swapName` (string)
- `responderCrossChainAccountName` (string)
- `responderLocalChainAccountName` (string)
- `ElGamalKey` (string)
- `ElGamalKeyPath` (string)
- `InitiatorChain` (string)
- `ResponderChain` (string)
- `swapAmount` (string)
- `localChainAccountPassword` (optional: string)
- `crossChainAccountPassword` (optional: string)
- `reloadSwapState` (optional: string)

---
### Function: `GeneralizedENC_ResponderClaimSubroutine`

Generalized function to claim from an atomic swap from responder / swap client role.

#### GeneralizedENC_ResponderClaimSubroutine Signature

```python
def GeneralizedENC_ResponderClaimSubroutine(
    responderJSONPath, localChainAccountPassword, 
    crossChainAccountPassword, reloadSwapState
) -> None :
```
### Parameters
- `responderJSONPath` (string)
- `localChainAccountPassword` (optional: string)
- `crossChainAccountPassword` (optional: string)
- `reloadSwapState` (optional: string)

---
### Function: `Responder_CheckLockTimeRefund`

Generalized function to refund an atomic swap from responder / swap client role if the lock time is expired.

#### GeneralizedENC_ResponderClaimSubroutine Signature

```python
def Responder_CheckLockTimeRefund(swapName, password) -> None :
```
### Parameters
- `swapName` (string)
- `password` (optional: string)
---

