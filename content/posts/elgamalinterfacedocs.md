---
title: "ElGamal Interface Documentation"
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
Interface for interacting with ElGamal encryption / decryption software

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `update_ElGamalPubKeysJSON`

Updates all three ElGamal key related JSON files given a new ElGamal key file index:

- Pubkey Storage: ElGamalPubKeys.json
- QG Channel Storage: ElGamalQGChannels.json
- QG Pubkey Array / Map Storage: QGPubkeyArray.json

#### update_ElGamalPubKeysJSON Signature

```python
def update_ElGamalPubKeysJSON(index) -> None:
```
### Parameters
- `index` (int)

---
### Function: `currentKeysStateCheck`

Checks how many ElGamal Keys currently exist by incrementing through all possible indexes.
Returns first index that doesn't exist yet. 

#### currentKeysStateCheck Signature

```python
def currentKeysStateCheck() -> int :
```
---

### Function: `generateNewElGamalPubKey`

Generates a new ElGamal Key Pair, can use a custom q and g value for compatible key generation. 
Calls currentKeysStateCheck and update_ElGamalPubKeysJSON.

#### update_ElGamalPubKeysJSON Signature

```python
def generateNewElGamalPubKey(q, g) -> None:
```
### Parameters
- `q` (optional: BigInt / int)
- `g` (optional: BigInt / int)
---

### Function: `ElGamal_Encrypt`

Encrypts a message to a specified ElGamalPubkey from a specified local key and saves resulting ciphertext to filepath.

#### ElGamal_Encrypt Signature

```python
def ElGamal_Encrypt(receiverPubKey, userKeyFileName, subject, filePath) -> None:
```
### Parameters
- `receiverPubKey` (string)
- `userKeyFileName` (string)
- `subject` (string)
- `filePath` (string)
---

### Function: `ElGamal_Decrypt`

Decrypts an ElGamal ciphertext from a specific public key using a specific local key and returns the resulting string

#### ElGamal_Decrypt Signature

```python
def ElGamal_Decrypt(subjectFilePath, senderPubKey, userKeyFileName) -> None:
```
### Parameters
- `subjectFilePath` (string) Ciphertext filepath
- `senderPubKey` (string)
- `userKeyFileName` (string)
---


