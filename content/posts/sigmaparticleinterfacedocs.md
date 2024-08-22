---
title: "Sigma Particle Interface Documentation"
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

Interface for interacting with Sigma Particle Ergo Atomic Swap Framework

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `SigmaParticle_newFrame`

Creates a new instance of a Sigma Particle contract / swap directory and it's base files

#### SigmaParticle_newFrame Signature

```python
def SigmaParticle_newFrame(swapName) -> None :
```
### Parameters
- `swapName` (string)
---
### Function: `SigmaParticle_treeToAddr`

Converts an Ergo Tree into an Address

#### SigmaParticle_treeToAddr Signature

```python
def SigmaParticle_treeToAddr(
    tree, swapName, filename, password
) -> str :
```
### Parameters
- `tree` (string)
- `swapName` (string)
- `filename` (string)
- `password` (optional: string)
---
### Function: `SigmaParticle_box_to_addr`

Converts an Ergo Box / UTXO ID into an Address
#### SigmaParticle_box_to_addr Signature

```python
def SigmaParticle_box_to_addr(boxId, swapName, password) -> str :
```
### Parameters
- `boxId` (string)
- `swapName` (string)
- `password` (optional: string)

---
### Function: `SigmaParticle_CheckLockTimeAtomicSchnorr`

Returns the remaining lock time in blocks for a given swap contract

#### SigmaParticle_CheckLockTimeAtomicSchnorr Signature

```python
def SigmaParticle_CheckLockTimeAtomicSchnorr(swapName, boxId, password) -> int :
```
### Parameters
- `swapName` (string)
- `boxId` (string)
- `password` (optional: string)
---
### Function: `BuildAtomicSchnorrContract`

Sets up relevant data and files for Ergo Atomic Schnorr Initiator Contract

#### BuildAtomicSchnorrContract Signature

```python
def BuildAtomicSchnorrContract(
    initiatorMasterJSONPath, refundDuration_BLOCKS, swapName, valueERGO
) -> None :
```
### Parameters
- `initiatorMasterJSONPath` (string)
- `refundDuration_BLOCKS` (int)
- `swapName` (string)
- `valueERGO` (int)

---
### Function: `responderGenerateAtomicSchnorr`

Sets up relevant data for verification and claiming  of Ergo Atomic Schnorr Initiator contract from RESPONDER role side only

#### Atomicity_RemainingLockTimeAtomicMultisig_v_002 Signature

```python
def responderGenerateAtomicSchnorr(
    swapName, DEC_finalizationPATH, responderMasterJSONPATH, boxValue
) -> None:
```
### Parameters
- `swapName` (string)
- `DEC_finalizationPATH` (string)
- `responderMasterJSONPATH` (string)
- `boxValue` (int)
---
### Function: `responderVerifyErgoScript`

Compares expected Ergo Tree with on chain Ergo Tree to check for a match from responder side.

#### responderVerifyErgoScript Signature

```python
def responderVerifyErgoScript(swapName, expectedErgoTree, password) -> bool :
```
### Parameters
- `swapName` (string)
- `expectedErgoTree` (string)
- `password` (optional: string)

---
### Function: `responderClaimAtomicSchnorr`

Claims a specific Ergo Atomic Schnorr swap contract from the responder side. 

#### responderClaimAtomicSchnorr Signature

```python
def responderClaimAtomicSchnorr(swapName, tries, password) -> None :
```
### Parameters
- `swapName` (string)
- `tries` (optional: int)
- `password` (optional: string)
---
### Function: `SigmaParticle_updateKeyEnv`

Updates the specified swap directory with the specified .env key value pairs.

#### SigmaParticle_updateKeyEnv Signature

```python
def SigmaParticle_updateKeyEnv(swapName, targetKeyEnvDirName) -> None :
```
### Parameters
- `swapName` (string)
- `targetKeyEnvDirName` (string)
---
### Function: `SigmaParticle_getTreeFromBox`

Gets an Ergo Tree from a specified Ergo Box / UTXO ID.

#### SigmaParticle_getTreeFromBox Signature

```python
def SigmaParticle_getTreeFromBox(boxID, swapName, password) -> str :
```
### Parameters
- `boxID` (string)
- `swapName` (string)
- `password` (optional: string)
---
### Function: `deployErgoContract`

Deploys any specified Ergo Contract.

#### deployErgoContract Signature

```python
def deployErgoContract(swapName, password) -> None :
```
### Parameters
- `swapName` (string)
- `password` (optional: string)
---
### Function: `getBoxID`

Optimistically returns Ergo Box / UTXO ID from swap file.

#### getBoxID Signature

```python
def getBoxID(swapName) -> str :
```
### Parameters
- `swapName` (string)

---
### Function: `checkBoxValue`

Returns the balance or value in nanoErgs of a Box / UTXO.
Also calls refund functions when discovering errors at the moment, although this functionality will likely be extracted to
a new function and called outside of checkBoxValue's scope in the future.
#### checkBoxValue Signature

```python
def checkBoxValue(
    boxID, boxValPATH, swapName, role, ergopassword, otherchainpassword
) -> int :
```
### Parameters
- `boxID` (string)
- `boxValPATH` (string)
- `swapName` (string)
- `ergopassword` (optional: string)
- `otherchainpassword` (optional: string)
---
### Function: `SigmaParticle_boxFilter`

Checks a specific Ergo Address for any transactions with boxes that are not the given boxID and returns them. 
Only returns first tx found at the moment as that's all that's needed but can handle returning all of them in the future.

#### SigmaParticle_boxFilter Signature

```python
def SigmaParticle_boxFilter(
    address, boxID, swapName, filename, password
) -> json :
```
### Parameters
- `address` (string)
- `boxID` (string)
- `swapName` (string)
- `filename` (string)
- `password` (optional: string)
---
### Function: `checkSchnorrTreeForClaim`

Checks an Atomic Schnorr contract for a claim transaction.
Calls a refund if the timelcok expires and no claim is found. (refund functionality may be extracted to a new function in the future)

#### checkSchnorrTreeForClaim Signature

```python
def checkSchnorrTreeForClaim(
    boxID, swapName, initiatorMasterJSONPath, password
) -> bool :
```
### Parameters
- `boxID` (string)
- `swapName` (string)
- `initiatorMasterJSONPath` (string)
- `password` (optional: string)
---
### Function: `SigmaParticle_valFromHex`

Returns a value based on Ergo Encoded Hexadecimal, only handles int value atm.

#### SigmaParticle_valFromHex Signature

```python
def SigmaParticle_valFromHex(hexval, swapName, filename) -> int :
```
### Parameters
- `hexval` (string)
- `swapName` (string)
- `filename` (string)

---
### Function: `SigmaParticle_ECC_p1Deduce`

Function endpoint to handle basic deduction math call to SigmaParticle/AtomicMultiSigECC

#### SigmaParticle_ECC_p1Deduce Signature

```python
def SigmaParticle_ECC_p1Deduce(sr_, sr) -> int / BigInt :
```
### Parameters
- `sr_` (tuple / ordered pair / coordinates)
- `sr` (int / BigInt)
---
### Function: `deduceX_fromAtomicSchnorrClaim`

Handles all deduction logic including saving results to files.
Calls SigmaParticle_ECC_p1Deduce and SigmaParticle_valFromHex.

#### deduceX_fromAtomicSchnorrClaim Signature

```python
def deduceX_fromAtomicSchnorrClaim(
    initiatorMasterJSONPath, swapName
) -> int / BigInt :
```
### Parameters
- `initiatorMasterJSONPath` (string)
- `swapName` (string)






