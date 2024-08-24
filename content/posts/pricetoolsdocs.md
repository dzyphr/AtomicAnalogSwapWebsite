---
title: "Price Tools Documentation"
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


Tools for handling price conversions and percision handling

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `getPriceConversions`

Convert a coin amount into another coin amount, handles both directions.

#### getPriceConversions Signature

```python
def getPriceConversions(amountMod, CoinA_Price, CoinB_Price) -> list :
```
### Parameters
- `amountMod` (int)
- `CoinA_Price` (Decimal)
- `CoinB_Price` (Decimal) 

---
### Function: `EthToWei`

Converts Eth value to Wei

#### EthToWei Signature

```python
def EthToWei(Eth) -> int :
```
### Parameters

- `Eth` (int)

---
### Function: `weiToEth`

Converts Wei value to Eth

#### weiToEth Signature

```python
def weiToEth(wei) -> int :
```
### Parameters

- `wei` (int)

---
### Function: `ErgToNanoErg`

Converts Ergo value to Nano Ergo value

#### ErgToNanoErg Signature

```python
def ErgToNanoErg(Erg) -> int :
```
### Parameters

- `Erg` (int)
---
### Function: `NanoErgToErg`

Converts nano Erg value to Ergo value

#### NanoErgToErg Signature

```python
def NanoErgToErg(NanoErg) -> int :
``` 
### Parameters

- `NanoErg` (int)
---
