---
title: "Market Pricing Documentation"
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


Functions to automatically set market server prices

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `UpdateMarketOrderTypeUUIDsList`

Updates OrderTypes.json according to given marketConfig.json input data

#### UpdateMarketOrderTypeUUIDsList Signature

```python
def UpdateMarketOrderTypeUUIDsList(
    coins, marketConfigJSON, marketFeePercentage, coinAVolumeMinMax, rounded
) -> None :
```
### Parameters
- `coins` (list of strings)
- `marketConfigJSON` (string)
- `marketFeePercentage` (int or Decimal) 
- `coinAVolumeMinMax` (list where index 0 is min and 1 is max)
- `rounded` (bool)

---
### Function: `marketPricingLoop`

Eternal loop that runs UpdateMarketOrderTypeUUIDsList at a given interval

#### marketPricingLoop Signature

```python
def marketPricingLoop(frequency) -> None :
```
### Parameters

- `frequency` (optional: int) Market Pricing Update Frequency. Default is 15.

---

