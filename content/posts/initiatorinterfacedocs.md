---
title: "Initiator Interface Documentation"
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

Function Interace for Swap Initiator Role / Market Server Role

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `initiation`

Returns an atomic swap initiation JSON object

#### initiation Signature

```python
def initiation(crossChainPubKey, initiatorChain, crossChain) -> json :
```
### Parameters
- `crossChainPubKey` (string)
- `initiatorChain` (string)
- `crossChain` (string)

---

### Function: `sanitizeInitiation`

Removes private values from the given atomic swap initiation, returns 'public' version of the json. 

#### sanitizeInitiation Signature

```python
def sanitizeInitiation(initiationJSON) -> json :
```
### Parameters
- `initiationJSON` (string)
---

### Function: `inspectResponse`
Takes a decrypted atomic swap response filepath, checks the contract from the response for timelock and funding values.
Returns timelock and funding values in json format. 

#### inspectResponse Signature

```python
def inspectResponse(DEC_response_filepath, swapName, password) -> json :
```
### Parameters
- `DEC_response_filepath` (string)
- `swapName` (string)
- `password` (optional: string)
---

### Function: `finalizeSwap`
Returns an atomic swap finalization json object according to the existing Initiator JSON data

#### finalizeSwap Signature
  
```python
def finalizeSwap(initiatorMasterJSONPath) -> json :
```
### Parameters
- `initiatorMasterJSONPath` (string)
---

### Function: `GeneralizedENC_InitiationSubroutine`

Generalized function to create atomic swap initiation commitments, interactions, and store relevant data

#### GeneralizedENC_InitiationSubroutine Signature

```python
def GeneralizedENC_InitiationSubroutine(
    swapName, LocalChainAccountName, CrossChainAccountName, 
    ElGamalKey, ElGamalKeyPath, InitiatorChain, ResponderChain,
    localChainAccountPassword, crossChainAccountPassword
) -> None :
```
### Parameters
- `swapName` (string)
- `LocalChainAccountName` (string)
- `CrossChainAccountName` (string)
- `ElGamalKey` (string)
- `ElGamalKeyPath` (string)
- `InitiatorChain` (string)
- `ResponderChain` (string)
- `localChainAccountPassword` (optional: string)
- `crossChainAccountPassword` (optional: string)
---

### Function: `GeneralizedENC_FinalizationSubroutine`

Generalized function to create atomic swap finalization commitments, interactions, and store relevant data

#### GeneralizedENC_FinalizationSubroutine Signature

```python
def GeneralizedENC_FinalizationSubroutine( 
    initiatorJSONPath, CoinA_Price, CoinB_Price,
    localchainpassword, crosschainpassword, swapStateReload
) -> None :
```
### Parameters
- `initiatorJSONPath` (string)
- `CoinA_Price` (string)
- `CoinB_Price` (string)
- `localchainpassword` (optional: string)
- `crosschainpassword` (optional: string)
---

### Function: `GeneralizedENC_InitiatorClaimSubroutine`

Generalized function to claim or refund an atomic swap as an initiator / market server

#### GeneralizedENC_InitiatorClaimSubroutine Signature

```python
def GeneralizedENC_InitiatorClaimSubroutine(
    initiatorJSONPath, localchainpassword, crosschainpassword
) -> None : 
```
### Parameters
- `initiatorJSONPath` (string)
- `localchainpassword` (optional: string)
- `crosschainpassword` (optional: string)







