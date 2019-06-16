# Primecoin Block Hash Fermat Test

- Status: proposed
- Type: protocol
- Related components: block validation
- Start Date: 16-AUG-2013
- Discussion: [thread](https://talk.peercoin.net/t/primecoin-v0-2-proposal/310)
- Supersedes:
- Superseded by:
- Author: Sunny King

## Summary

This document defines the proposed Fermat test on blockhash.

## Conventions
- The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

## Motivation

Currently Primecoin protocol allows searching for a header hash of arbitrary factorization. In fact the initial reference miner finds a block hash divisible by 210, instead of taking random hash values.

Let's recall the formula:

```
origin = blockhash * multiplier
```

If prime chains are pre-generated with highly abundant origins (abundant meaning with large number of factors), in theory you could try to search for a block header hash that divides an abundant origin. This would defeat the non-reusability property of the proof-of-work. With current limit on prime size at 2000 bit this is still thought to be computationally not feasible, but the guesstimate is that instead of 256 bit hard of the secure hash, it might be reduced to 128 bit hard for such brute-force trials on blockhash.

Even though this is not considered a feasible attack vector, but it is tricky to prove its infeasibility. However there is a simple adjustment of the protocol that eliminates such doubt completely. By requiring block header hash to pass Fermat test (thus basically prime), such concerns should be completely eliminated.

## Detailed specification

Reference cpu miner has been updated to reflect the necessary adjustment to be compatible with the additional block validation:  
[commit #22f0237](https://github.com/primecoin/primecoin/commit/22f02370d75be01ec7322914c35960cd123ea1b9)

New protocol has been pre-implemented for miner's testing of future compatibility:  
[commit #b7b034f](https://github.com/primecoin/primecoin/commit/b7b034f39c52c049d63f5abbe8e993983d4d4777)

Protocol activation and switch date has not been determined yet.

The additional block validation is implemented as:

```
bool CheckPrimeProofOfWorkV02Compatibility(uint256 hashBlockHeader)
{
    unsigned int nLength = 0;
    return (FermatProbablePrimalityTest(CBigNum(hashBlockHeader), nLength));
}
```

