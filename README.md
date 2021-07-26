Mint a new NFT

Once you have the local Ethereum network and IPFS daemon running, minting an NFT is incredibly simple. Just specify what you want to tokenize, the name of the NFT, and a description to tell users what the NFT is for:

minty mint ~/ticket.txt --name "Moon Flight #1" --description "This ticket serves as proof-of-ownership of a first-class seat on a flight to the moon."

> Minted a new NFT:
> Token ID:              1
> Metadata URI:          ipfs://bafybeic3ui4dj5dzsvqeiqbxjgg3fjmfmiinb3iyd2trixj2voe4jtefgq/metadata.json
> Metadata Gateway URL:  http://localhost:8080/ipfs/bafybeic3ui4dj5dzsvqeiqbxjgg3fjmfmiinb3iyd2trixj2voe4jtefgq/metadata.json
> Asset URI:             ipfs://bafybeihhii26gwp4w7b7w7d57nuuqeexau4pnnhrmckikaukjuei2dl3fq/ticket.txt
> Asset Gateway URL:     http://localhost:8080/ipfs/bafybeihhii26gwp4w7b7w7d57nuuqeexau4pnnhrmckikaukjuei2dl3fq/ticket.txt
> NFT Metadata:
> {
>   "name": "Moon Flight #1",
>   "description": "This ticket serves as proof-of-ownership of a first-class seat on a flight to the moon.",
>   "image": "ipfs://bafybeihhii26gwp4w7b7w7d57nuuqeexau4pnnhrmckikaukjuei2dl3fq/ticket.txt"
> }

Show details of an existing NFT

You can view the details of each individual NFT by calling show along with the ID of the NFT:

minty show 1

> Token ID:              1
> Owner Address:         0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266
> Metadata URI:          ipfs://bafybeic3ui4dj5dzsvqeiqbxjgg3fjmfmiinb3iyd2trixj2voe4jtefgq/metadata.json
> ...

Pin IPFS assets for an NFT

The assets for new tokens are stored in a local IPFS repository which is only online while a local IPFS daemon is running. 
The start-local-environment.sh script starts a local daemon for you if you aren't already running and IPFS daemon. 
If you are, then the script just uses the daemon you already have.

To make the data highly available without needing to run a local IPFS daemon 24/7, you can request that a Remote Pinning Service like Pinata or nft.
storage store a copy of your IPFS data on their IPFS nodes.

To pin the data for token, use the minty pin command:

minty pin 1

> Pinning asset data (ipfs://bafybeihhii26gwp4w7b7w7d57nuuqeexau4pnnhrmckikaukjuei2dl3fq/ticket.txt) for token id 1....
> Pinning metadata (ipfs://bafybeic3ui4dj5dzsvqeiqbxjgg3fjmfmiinb3iyd2trixj2voe4jtefgq/metadata.json) for token id 1...
> 🌿 Pinned all data for token id 1

The pin command looks for some configuration info to connect to the remote pinning service. See the Configuration section above for details.
