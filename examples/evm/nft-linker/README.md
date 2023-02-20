# NFT linker

This example sends the NFT that was originally minted at source-chain to destination-chain.

### Deployment

To deploy the NFT Linker, run the following command:

```bash
npm run deploy evm/nft-linker [local|testnet]
```

A single NFT is minted to the deployer (`0xBa86A5719722B02a5D5e388999C25f3333c7A9fb`) on each chain.

## Execution

To execute the NFT Linker example, use the following command:

```bash
npm run execute evm/nft-linker [local|testnet] ${srcChain} ${destChain}
```

**Default Values**:

-   `srcChain` is `Avalanche`. Valid values are Moonbeam, Avalanche, Fantom, Ethereum, and Polygon
-   `destChain` is `Fantom`. Valid values are Moonbeam, Avalanche, Fantom, Ethereum, and Polygon
-   `amount` is `10`

**Note**:

It will fail if an attempt is made to send a duplicate NFT to a chain.

## Example

To deploy the NFT Linker locally and send the NFT originally minted on Avalanche to Polygon:

```bash
npm run deploy evm/nft-linker local
npm run execute evm/nft-linker local "Avalanche" "Polygon"
```

Output:

```
--- Initially ---
Token that was originally minted at Moonbeam is at Moonbeam.
Token that was originally minted at Avalanche is at Avalanche.
Token that was originally minted at Fantom is at Fantom.
Token that was originally minted at Ethereum is at Ethereum.
Token that was originally minted at Polygon is at Polygon.
--- Then ---
Token that was originally minted at Moonbeam is at Moonbeam.
Token that was originally minted at Avalanche is at Polygon.
Token that was originally minted at Fantom is at Fantom.
Token that was originally minted at Ethereum is at Ethereum.
Token that was originally minted at Polygon is at Polygon.
```