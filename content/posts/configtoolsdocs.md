---
title: "Config Tools Documentation"
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


Tools for various configuration interactions

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `firstRunCheck`

CLI level function that makes sure accounts are configured for every chain chosen.
Can be used to setup market servers entirely from CLI with no external wallet dependencies.
Currently mandatory, to be made optional and removed from default build script.

#### firstRunCheck Signature

```python
def firstRunCheck() -> None:
```
---
### Function: `updateMainEnv`

Updates the local base .env file with the given key value pair.
This env file holds configurations for things like lock times. 

#### updateMainEnv Signature

```python
def updateMainEnv(Key, Val) -> None :
    return set_key('.env', Key, Val, quote_mode='never')
```
### Parameters

- `Key` (string)
- `Val` (string,int)

---
### Function: `compareListsFindOutliers`

Takes two lists, compares the actual list against the expected list.
Returns a list of actual outliers and a list of expected outliers
#### compareListsFindOutliers Signature

```python
def compareListsFindOutliers(actual, expected) -> list, list :
    return list(actualOutliers), list(expectedOutliers)
```
### Parameters

- `actual` (list): The list to check.
- `expected` (list): The list to check the `actual` list against.

---
### Function: `is_uuid`

Checks if the given string is formatted like a uuidv4

#### is_uuid Signature

```python
def is_uuid(string) -> bool :
```
### Parameters

- `string` (string)
---
### Function: `remove_uuids_from_list`

Checks if the given List contains member strings formatted like a uuidv4 and removes them if so

#### remove_uuids_from_list Signature

```python
def remove_uuids_from_list(list) -> list :
``` 
### Parameters

- `list` (list)
---
### Function: `is_EVM_swap_dir`

Checks if the given string is formatted like a EVM swap directory name

#### is_EVM_swap_dir Signature

```python
def is_EVM_swap_dir(string) -> bool :
``` 
### Parameters

- `string` (string)
---
### Function: `remove_EVM_swap_dirs_from_list`

Checks if the given List contains member strings formatted like an EVM swap dir name and removes them if so

#### remove_EVM_swap_dirs_from_list Signature

```python
def remove_EVM_swap_dirs_from_list(list) -> list :
```
### Parameters

- `list` (list)
---
### Function: `createNonInteractive`

'Chain agnostic' Account file building function, for local accounts (non 3rd party wallets)

#### createNonInteractive Signature

```python
def createNonInteractive(
    fulldirpath, fullenvpath, envFormat, enc, password
) -> bool :
```
### Parameters

- `fulldirpath` (string) !TBD
- `fullenvpath` (string)
- `envFormat` (string)
- `enc` (bool)
- `password` (optional: string)

---
### Function: `initSepoliaAccountNonInteractive`

Sepolia EVM Account file building function, for local accounts (non 3rd party wallets)

Calls createNonInteractive

#### initSepoliaAccountNonInteractive Signature

```python
def initSepoliaAccountNonInteractive(
    SepoliaSenderAddr, SepoliaPrivKey, Sepolia, SepoliaID, SepoliaScan,
    SolidityCompilerVersion, fulldirpath, fullenvpath, enc, password
) -> None :
```
### Parameters

- `SepoliaSenderAddr` (string)
- `SepoliaPrivKey` (string)
- `Sepolia` (string)
- `SepoliaID` (int) !TBD
- `SepoliaScan` (string) !TBD
- `SolidityCompilerVersion` (string) !TBD
- `fulldirpath` (string) TBD
- `fullenvpath` (string)
- `enc` (bool)
- `password` (optional: string)
---
### Function: `initErgoAccountNonInteractive`

Ergo Account file building function, for local accounts (non 3rd party wallets)

Calls createNonInteractive

#### initErgoAccountNonInteractive Signature

```python
def initErgoAccountNonInteractive(
    testnetNode, mnemonic, mnemonicPass, senderEIP3Secret, senderPubKey,
    apiURL, fulldirpath, fullenvpath, enc, password
) -> None :
```
### Parameters

- `testnetNode` (string)
- `mnemonic` (string)
- `mnemonicPass` (string / empty string if none)
- `senderEIP3Secret` (int) 
- `senderPubKey` (string) !TBD
- `apiURL` (string) 
- `fulldirpath` (string) !TBD
- `fullenvpath` (string)
- `enc` (bool)
- `password` (optional: string)
---
### Function: `initializeAccount`

CLI Account Initialization Dialogue function

Called by firstRunCheck

#### initializeAccount Signature

```python
def initializeAccount(accountName, chain) -> None:
```
### Parameters

- `accountName` (string)
- `chain` (string)
---
