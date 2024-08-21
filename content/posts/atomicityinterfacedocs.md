---
title: "Atomicity Interface Documentation"
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

Interface for interacting with Atomicity EVM Atomic Swap Framework

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `Atomicity_ContractFilesBuilt`

Function that optimistically checks whether or not a contract/swap directory and subsequent files have been generated.

#### Atomicity_ContractFilesBuilt Signature

```python
def Atomicity_ContractFilesBuilt(swapName) -> bool :
```
### Parameters
- `swapName` (string)
---
### Function: `Atomicity_CheckContractFunds`

Checks the balance of a contract (or any address technically) and returns it.

#### Atomicity_CheckContractFunds Signature

```python
def Atomicity_CheckContractFunds(swapName, j_response, password) -> int :
```
### Parameters

- `swapName` (string)
- `j_response` (json)
- `password` (optional: string)
---
### Function: `Atomicity_SendFunds`

Sends specified amount of wei to specified EVM address

#### Atomicity_SendFunds Signature

```python
def Atomicity_SendFunds(
    addr, amount_wei, swapName, gas, gasMod, password
) -> None :
```
### Parameters

- `addr` (string)
- `amount_wei` (int)
- `swapName` (string)
- `gas` (optional: string)
- `gasMod` (optional: string)
- `password` (optional: string)
---
### Function: `Atomicity_newFrame`

Creates a new Atomicity instance / swap directory and base files

#### Atomicity_newFrame Signature

```python
def Atomicity_newFrame(swapName, chain, multiFile, constructorArgs) -> None :
```
### Parameters

- `swapName` (string)
- `chain` (string) Specifies which EVM chain to use
- `multiFile` (optional: bool)
- `constructorArgs` (optional: bool)

---
### Function: `Atomicity_Refund`

Calls the refund branch on the atomic swap contract

#### Atomicity_Refund Signature

```python
def Atomicity_Refund(swapName, role, gas, gasMod, password) -> None :
```
### Parameters

- `swapName` (string)
- `role` (string)
- `gas` (optional: string)
- `gasMod` (optional: string)
- `password` (optional: string)

---
### Function: `Atomicity_RemainingLockTimeAtomicMultisig_v_002`

Checks the blocks remaining in the atomic swap contract's lock time and returns it

#### Atomicity_RemainingLockTimeAtomicMultisig_v_002 Signature

```python
def Atomicity_RemainingLockTimeAtomicMultisig_v_002(
    j_response, swapName, password
) -> int :
```
### Parameters
- `j_response` (json)
- `swapName` (string)
- `password` (optional: string)
---
### Function: `Atomicity_buildScalarContract`

Builds the scalar lock atomic swap contract files.

#### Atomicity_buildScalarContract Signature

```python
def Atomicity_buildScalarContract(
    chain, counterpartyChainPub, xG, locktimeDuration, swapName
) -> None :
```
### Parameters
- `chain` (string)
- `counterpartyChainPub` (string)
- `xG` (string)
- `locktimeDuration` (int)
- `swapName` (string)

---
### Function: `Atomicity_deployEVMContract`

Deploys a given EVM contract / atomic swap contract

#### Atomicity_deployEVMContract Signature

```python
def Atomicity_deployEVMContract(
    swapName, customGas, customGasMod, password
) -> None :
```
### Parameters
- `swapName` (string)
- `customGas` (optional: string)
- `customGasMod` (optional: string)
- `password` (optional: string)
---
### Function: `Atomicity_compareScalarContractCoords`

Compares onchain coordinates of a contract with expected coordinates to verify a match.

#### Atomicity_compareScalarContractCoords Signature

```python
def Atomicity_compareScalarContractCoords(
    swapName, contractAddr, expectedX, expectedY, password
) -> bool :
```
### Parameters
- `swapName` (string)
- `contractAddr` (string)
- `expectedX` (string)
- `expectedY` (string)
- `password` (optional: string)
---
### Function: `Atomicity_claimScalarContract`

Call the claim branch of a scalar lock atomic swap contract with secret `x` value

#### Atomicity_claimScalarContract Signature

```python
def Atomicity_claimScalarContract(
    initiatorMasterJSONPath, swapName, gas, gasMod, password
) -> None :
```
### Parameters
- `initiatorMasterJSONPath` (string)
- `swapName` (string)
- `gas` (optional: string)
- `gasMod` (optional: string)
- `password` (optional: string)
---
### Function: `Atomicity_updateKeyEnv`

Updates the specified EVM swap folder with the specified account's .env data

#### Atomicity_updateKeyEnv Signature

```python
def Atomicity_updateKeyEnv(swapName, targetKeyEnvDirName) -> None :
```
### Parameters
- `swapName` (string)
- `targetKeyEnvDirName` (string)


