---
title: "Client Endpoints Documentation"
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

Python endpoints for calling Client REST API requests

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `checkElGQGChannelCorrectness`

Locally checks that ElGamal `QG` communication channel is safe to use

#### checkElGQGChannelCorrectness Signature

```python
def checkElGQGChannelCorrectness(QG, privateAPIKey) -> string :
```
### Parameters
- `QG` (string)
- `privateAPIKey` (string)

---
### Function: `logInToPasswordEncryptedAccount_ClientEndpoint`

Log in to a password encrypted account chain specific

#### logInToPasswordEncryptedAccount_ClientEndpoint Signature

```python
def logInToPasswordEncryptedAccount_ClientEndpoint(Chain, AccountName, Password, auth) -> None :
```
### Parameters

- `Chain` (string)
- `AccountName` (string)
- `Password` (string)
- `auth` (string)

---
### Function: `requestEncryptedInitiation_ClientEndpoint`

Request an encrypted initiation from a swap server from client 

#### requestEncryptedInitiation_ClientEndpoint Signature

```python
def requestEncryptedInitiation_ClientEndpoint(url, OrderTypeUUID, ElGamalPubkey) -> None :
```
### Parameters

- `url` (string)
- `OrderTypeUUID` (string)
- `ElGamalPubkey` (string)

---
### Function: `submitEncryptedResponse_ClientEndpoint`

Submit and encrypted response to the swap server from client

#### submitEncryptedResponse_ClientEndpoint Signature

```python
def submitEncryptedResponse_ClientEndpoint(swapID, marketPublicRequestsURL, ENC_response, auth) -> string :
```
### Parameters

- `swapID` (string)
- `marketPublicRequestsURL` (string)
- `ENC_response` (string)
- `auth` (string)
---

