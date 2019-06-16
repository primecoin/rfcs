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

This document defines the proposed transaction fee model and its effect on Primecoin inflation.

## Conventions
- The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

## Motivation

Primecoin transaction fee was a simplified version of Bitcoin's. It was not initially set to be destroyed like in Peercoin. However this omission may not be what it originally intended.

Destruction of transaction fees serves several purposes. First, it changes the dynamic of inflation. Second, it eliminates incentive for hostile competition among miners to grab transaction fees for selfish gain. Arguably, with transaction fee destruction, the coin economics can be even more deflationary than Bitcoin's. This means, when the circulation is fast the economic is more deflationary than gold. Keep in mind, here the term 'deflationary' does not bear negative meaning as in the modern economic theories. Think of consumer goods such as electronics ever getting cheaper and better, it can and does bring benefit to the economy. But it does disfavor debt systems when the economic enters a period of deflation.

Let's recall that Primecoin's economics was designed to favor a stable and subsidized mining economy. At similar capitalization, primecoin would have a more prosperous and stable mining economy than Bitcoin. This requires the elimination of supply cap, which some consider the coin more inflationary than Bitcoin. This may be true if transaction fee is not destroyed. But with transaction fee destruction the dynamic completely changes.

The mining subsidy remains the same but transaction fee destruction has a chance to completely negate any inflation and some. So in such case the total supply can go down which means a true deflationary period, that Bitcoin will not have.

Thus the prosperity and stability of mining market is preserved. Yet the inflation rate is allowed to go negative through market action and produce one of the most value-preserving monetary systems favoring store of value property of money.

## Detailed specification

* Transaction fee destroyed rather than collected by miners.

* Transaction base fee rate raised to 1mXPM/B. This serves to increase the cost of transaction and reduce traffic to blockchain. Clearly Bitcoin's methodology of attempting to be both base money and high volume transaction processor does not work well. Primecoin on the other hand is designed to excel as base money. Transaction fee should not be too cheap. At this new rate, the economics will turn deflationary when average block utilization reaches around 8kB per block. Because Primecoin's block interval is 1/10 of Bitcoin's, this compares to about 80kB block utilization in case of Bitcoin, or 4GB blockchain growth annually, which Bitcoin reached a couple years ago.
