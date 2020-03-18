# Primecoin Transaction Fee Model

- Status: proposed
- Type: protocol
- Related components: transaction fee, inflation model
- Start Date: 16-JUN-2019
- Discussion:
- Supersedes:
- Superseded by:
- Author: Sunny King

## Summary

This document defines the proposed transaction fee model and its effects on inflation.

## Conventions
- The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

## Motivation

Primecoin transaction fee was a simplified version of Bitcoin's. It was not initially set to be destroyed like in Peercoin. However this omission may not be what I originally intended.

To better understand this proposal, one must review the crucial differences between Primecoin, Bitcoin, and gold. Bitcoin was designed with a supply cap of 21 million in an attempt to surpass gold in the store-of-value function. However, this compromises network security and made security reliant on transaction fee market and the crypto economy.

Primecoin's design, on the other hand, refuses to compromise security to artificially boost store-of-value function. Like gold, Primecoin has no fixed supply cap. Mining market will sustain itself on inflation indefinitely, assuming Moore's Law's eventual demise.

So Primecoin is closer to gold by design. Does this mean Primecoin must be inferior to Bitcoin in terms of store-of-value? Not exactly.

Transaction fee destruction was first introduced by Peercoin in 2012. It serves several purposes. First, it changes the dynamic of inflation. Second, it eliminates incentive for hostile competition among miners to grab transaction fees for selfish gain.

With transaction fee destruction, the coin economics can potentially be more deflationary than Bitcoin's. When the circulation is fast the monetary system can still be more deflationary than gold.

Keep in mind, the term _deflation_ does not necessarily bear negative meaning as viewed by modern economic theories. Think of consumer goods such as electronics ever getting cheaper and better. Indeed gold can run a whole economy without problem. It just has a disposition favoring equity over debt, discretion over recklessness. Gold financed industrial revolution, Bitcoin financed crypto economy just fine.

With transaction fee destruction Primecoin now also has the potential to eliminate inflation. When the coins are in heavy use and transaction activity is high, the total supply can potentially go down which means a true deflationary period, that even Bitcoin can not have. And also this can potentially happen a lot faster than Bitcoin's fixed halving schedule.

Yet unlike Bitcoin, the prosperity and stability of Primecoin mining market is preserved. The effective inflation rate is allowed to go negative through market action and this makes Primecoin one of the most value-preserving monetary systems favoring the store-of-value function of money.

## Design specification

* Transaction fee destroyed rather than collected by miners.

* Transaction minimum fee rate raised to 1mXPM/Byte.

## Design considerations

Primecoin's fee system was originally designed to be simple and easy to understand by users. A minimum fee rate is enforced by network protocol. This proposal continues this tradition.

New minimum fee rate is raised and accounted on bytes instead of kilobytes. This increases the cost of transaction and saves resource on blockchain.

Bitcoin's methodology of attempting to serve both as base money and high volume transaction processor does not work well. Primecoin on the other hand is designed to excel as base money.

Then transaction fee should not be too cheap. At the new minimum rate, the economics will turn deflationary when average block utilization reaches around 8kB per block. Because Primecoin's block interval is 1/10 of Bitcoin's, this compares to about 80kB block utilization in case of Bitcoin, or 4GB blockchain growth annually, which Bitcoin reached a couple years ago.

The minimum fee rate is intended for the long term and not meant to be reviewed and changed by developers constantly. It should be viewed as a market based mechanism both economically and monetarily. When the fee is considered high by market, transactions tend to move off-chain thus on-chain activity drops. This facilitates inflation, increases supply and effectively lowers fee value. Conversely when the fee is considered low by market, transactions tend to move on-chain thus inflation is reduced. The new fixed minimum rate reflexes the optimal balance with respect to blockchain resource capacity and monetary utility.
