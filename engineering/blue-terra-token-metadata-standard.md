---
description: Proposing A New Standard For SPL Tokens With Legal Contracts
---

# 💾 Blue Terra Token Metadata Standard

## Introduction

The vision of scalable decentralized real estate on the blockchain has yet to fully come to fruition. Tied to this, is the lack of formal schema or data standard in which legal contracts can be recorded. As a result, the Solana ecosystem has yet to converge on a metadata standard for legal contracts. We must take it into our own hands to define and spread a sensible specification.&#x20;

Blue Terra proposes a new SPL token metadata standard, coined the `Blue Terra Token Metadata Standard` by extending the Metaplex token metadata standard to include the realization of decentralized real estate. All Blue Terra NFT Metadata is written in the `Blue Terra Token Metadata Standard`. We should note that this new standard does not override any original Metaplex on-chain program data but makes additions to the JSON payload `uri` field in the on-chain metadata.

We make no claims about the viability of the `Blue Terra Token Metadata` standard for an arbitrary country or freehold structure. It is our contention though, that wherever necessary the `Blue Terra Token Metadata` standard can be expanded to facilitate the regulatory requirements in other jurisdictions.&#x20;

## Requirements

We do not seek to replace the Metaplex Token Metadata Standard but extend it to facilitate all other Land-As-NFT projects on Solana. Given this, we had two basic requirements for our standard.&#x20;

1\) The `Blue Terra Token Metadata Standard` must not interfere with, limit or override any already existing Metaplex Token Metadata Standard JSON fields.

2\) The `Blue Terra Token Metadata Standard` must fully encapsulate the necessary fields so as to fulfill the operational requirements of Blue Terra in the Bahamas.&#x20;

## Token Metadata Program

The on-chain metadata for the `Blue Terra Token Metadata Standard` contains the same fields as the Metaplex Metadata Standard.&#x20;

Therefore, your NFT should have the following information as on-chain metadata:

| Field                      | Type   | Description                                                    |
| -------------------------- | ------ | -------------------------------------------------------------- |
| name                       | string | name of asset                                                  |
| symbol                     | string | symbol of the asset                                            |
| uri                        | string | URI to the external JSON representing the asset                |
| creators                   | array  | public key of each creator                                     |
| update\_authority          | string | public key of the metadata owner                               |
| primary\_sale\_happened    | string | flag describing whether the primary sale of the token happened |
| seller\_fee\_basis\_points | number | royalties percentage awarded to creators                       |

The program also specifies optional structs used for the creation of `Master Editions` and `Editions`.

## URI JSON Schema

The JSON Schema for the `Blue Terra Token Metadata Standard` (or in other words the off chain JSON payload in the on-chain `uri` field ) is where all of our additions will live. Here is an example in pseudo json schema:&#x20;

```
{
  "name": String,
  "symbol": String,
  "description": String,
  "seller_fee_basis_points": Int,
  "image": String,
  "animation_url": String,
  "external_url": String,
  "attributes": List[{
    "trait_type": String, 
    "value": String
  }],
  "collection": {
     "name": String,
     "family": String
  },
  "properties": {
    "files": List[{
      "uri": String, 
      "type": String
    }],
    "category" String,
    "creators": List[{
      "address": String,
      "share": Int
    }],
    "contract": {
      "name": String
      "uri": String
      "type": String
      "description": String
      "period": String
      "created": DateTime | String
    }
  },
}
```

We resist describing every key but the `contract` key within `properties` . More information on off-chain metadata can be found [here](https://docs.metaplex.com/token-metadata/Versions/v1.0.0/nft-standard) in the Metaplex documentation. The contract field definitions are not prescriptive but we offer the following in terms of instructions:

| Name        | Type    | Description                                                                                 |
| ----------- | ------- | ------------------------------------------------------------------------------------------- |
| name        | string  | Human readable name of contract. Ideally, this should match the name of the legal contract. |
| uri         | string  | URI linked to a webapp or pdf containing legal contract.                                    |
| type        | string  | Human readable type of the contract. For example: `Perpetual Lease`.                        |
| description | string  | Human readable short description of the contract.                                           |
| period      | string  | Period of contract enforceability, as an absolute TimeDelta or DateTime range as a string.  |
| created     | string  | DateTime of contract creation as a string.                                                  |

&#x20;
