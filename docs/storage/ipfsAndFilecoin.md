---
title: IPFS And Filecoin
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

## Decentralized content based storage

IPFS and Filecoin together are used for decentralized storage for large data files.

IPFS (InterPlanetary File System) is a file sharing protocol.

On IPFS, data is accessed based on a:

      CID (Content Identifier)

In contrast, HTTPS data is accessed based on a location with a:

      Network IP Address (OSI Layer 3)
      Session Port (OSI Layer 5)

Storage space is competitive on IPFS. You can pin your data and have others pin your data.
However, if all pins go down for that data, that data will not be stored anymore on IPFS.

Filecoin is used to keep IPFS content active for simplicity.

## How to upload to IPFS?

Upload to IPFS uisng Spheron:

https://spheron.network/

Easily write to IPFS using Fleek:

https://fleek.co/

## How to download from IPFS?

In the Brave Web Browser, search for this IPFS CID URL:

```
ipfs://Qma1bfuubpepKn7DLDy4NPSKDeT3S4VPCNhu6UmdGrb6YD
```

## Mint an NFT on Shardeum using IPFS and Filecoin

Shardeum logo hosted on IPFS and Filecoin using Fleek:

<img src="https://ipfs.fleek.co/ipfs/bafybeib6zcl5v5ojxkvmxnvpqrypq5yakmu2fd6y6wc3xo4n66pjelu7yq"
alt="shardeumLogo" />

Mint NFT with Shardeum logo using ERC-721 imported OpenZeppelin library.

Note: put the IPFS CID:

    bafybeib6zcl5v5ojxkvmxnvpqrypq5yakmu2fd6y6wc3xo4n66pjelu7yq

instead of the IPFS gateway URL:

    https://ipfs.fleek.co/ipfs/bafybeib6zcl5v5ojxkvmxnvpqrypq5yakmu2fd6y6wc3xo4n66pjelu7yq

since gateways can go down.

<Tabs>
  <TabItem value="solidity" label="Solidity" default>

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.17;

import "@openzeppelin/contracts/token/ERC721/extensions/ERC721URIStorage.sol";

contract ShardeumLogoNFT is ERC721URIStorage {

  constructor() ERC721 ("shardeumLogo", "SL"){
    _safeMint(msg.sender, 1); //Mint NFT with tokenId = 1.
    _setTokenURI(1, "bafybeib6zcl5v5ojxkvmxnvpqrypq5yakmu2fd6y6wc3xo4n66pjelu7yq"); //For tokenId = 1, set IPFS CID for image data.
  }

}
```

  </TabItem>
</Tabs>
