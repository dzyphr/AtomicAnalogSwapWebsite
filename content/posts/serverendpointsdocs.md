---
title: "Server Endpoints Documentation"
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

Python endpoints for calling Server REST API requests

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `logInToPasswordEncryptedAccount_ServerEndpoint`

log in to a password encrypted swap account

#### logInToPasswordEncryptedAccount_ServerEndpoint Signature

```python
def logInToPasswordEncryptedAccount_ServerEndpoint(Chain, AccountName, Password, auth) -> None :
```
### Parameters
- `Chain` (string)
- `AccountName` (string)
- `Password` (string)
- `auth` (string)

---
### Function: `publishNewOrderType_ServerEndpoint`

Publishes a new swap order type (needs updating)

#### publishNewOrderType_ServerEndpoint Signature

```python
def publishNewOrderType_ServerEndpoint(
    url, CoinA, CoinB, CoinA_price, CoinB_price, MaxVolCoinA, MinVolCoinA, auth
) -> None :
```
### Parameters

- `url` (string)
- `CoinA` (string)
- `CoinB` (string)
- `CoinA_price` (Decimal)
- `CoinB_price` (Decimal)
- `MaxVolCoinA` (Decimal)
- `MinVolCoinA` (Decimal)
- `auth` (string)

---

