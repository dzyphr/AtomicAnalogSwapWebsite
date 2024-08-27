---
title: "Price Feeds Documentation"
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


Tools for getting price feeds from various APIs

#### Legend:
 !TBD: marks anything To Be Deleted in upcoming update (redundant things that still exist)

---

### Function: `CoinGeckoTickerByID`

Gets a Coin's information based on it's ID, requires CoinGecko API Key, not implemented in default usage at the moment
#### CoinGeckoTickerByID Signature

```python
def CoinGeckoTickerByID(coinname) -> string :
```
### Parameters
- `coinname` (string)

---
### Function: `CoinGeckoAvgPrice`
Gets an 'optimistic' average price from coin gecko feed 

Requires CoinGecko API Key, not implemented in default usage at the moment

#### CoinGeckoAvgPrice Signature

```python
 def CoinGeckoAvgPrice(coinname) -> Decimal :
```
### Parameters

- `coinname` (string)
---
### Function: `CoinGeckoSimplePrice`

Gets simple price from coin gecko feed.

#### CoinGeckoSimplePrice Signature

```python
def CoinGeckoSimplePrice(coinname, rounded) -> Decimal :
```
### Parameters


- `coinname` (string)
- `rounded` (optional: bool)
---
### Function: `BitPandaTicker`

Gets ticker information for a specific coin from Bit Panda feed
#### BitPandaTicker Signature

```python
def BitPandaTicker(ticker) -> dict / json :
```
### Parameters

- `ticker` (string)
---
### Function: `BitPandaPrice`

Gets the price from the Bit Panda feed

#### BitPandaPrice Signature

```python
def BitPandaPrice(ticker, rounded) -> Decimal :
``` 
### Parameters

- `ticker` (string)
- `rounded` (optional: bool)
---
### Function: `KucoinPrice`

Gets the price from the Kucoin feed

#### KucoinPrice Signature

```python
def KucoinPrice(ticker, rounded) -> Decimal :
``` 
### Parameters

- `ticker` (string)
- `rounded` (optional: bool)
---
### Function: `CoinExPriceLast`

Gets the `last` price from the CoinEx feed

#### CoinExPriceLast Signature

```python
def CoinExPriceLast(ticker, rounded) -> Decimal :
```
### Parameters

- `ticker` (string)
- `rounded` (optional: bool)
---
### Function: `CoinExPriceLowHighAvg`

Gets the average of the `low` and `high` prices from the CoinEx feed

#### CoinExPriceLowHighAvg Signature

```python
def CoinExPriceLowHighAvg(ticker, rounded) -> Decimal :
```
### Parameters

- `ticker` (string)
- `rounded` (optional: bool)
---
### Function: `CoinExPriceLow`

Gets the `low` price from the CoinEx feed

#### CoinExPriceLow Signature

```python
def CoinExPriceLow(ticker, rounded) -> Decimal :
```
### Parameters

- `ticker` (string)
- `rounded` (optional: bool)
---
### Function: `CoinExPriceHigh`

Gets the `high` price from the CoinEx feed

#### CoinExPriceHigh Signature

```python
def CoinExPriceHigh(ticker, rounded) -> Decimal :
```
### Parameters

- `ticker` (string)
- `rounded` (optional: bool)
---
### Function: `KrakenPrice`

Gets a price from the Kraken feed

#### KrakenPrice Signature

```python
def KrakenPrice(ticker, kind, rounded) -> Decimal :
```
### Parameters

- `ticker` (string)
- `kind` (optional: string) 
  - accepts: [`ask`, `bid`, `last`, `vwap`, `low`, `high`, `lowhighavg`]
- `rounded` (optional: bool)
---
### Function: `CoinbasePrice`

Gets a price from the Coinbase feed

#### CoinbasePrice Signature

```python
def CoinbasePrice(ticker, kind, rounded) -> Decimal :
```
### Parameters

- `ticker` (string)
- `kind` (optional: string)
  - accepts: [`spot`, `buy`, `sell`]
- `rounded` (optional: bool)
---
### Function: `BinancePrice`

Gets a price from the Binance feed

#### BinancePrice Signature

```python
def BinancePrice(ticker, rounded) -> Decimal :
```
### Parameters

- `ticker` (string)
- `rounded` (optional: bool)
---



