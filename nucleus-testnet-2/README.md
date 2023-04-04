# Nucleus Testnet Setup

Nucleus Testnet performs exactly same actions as mainnet specifically for development and testing purposes. Therefore, developers can use this service for development/testing purposes without taking any risk at all.

## Join Nucleus Testnet

- First visit [KomodoPlatform/nucleus](https://github.com/KomodoPlatform/nucleus) and follow the installation and starting instructions.
- Replace your `genesis.json` [with this one](https://raw.githubusercontent.com/KomodoPlatform/nucleus-assets/main/nucleus-testnet-2/genesis.json).
- Add "b31370a90047289fe20cf9a510fd79fd3502c257@65.109.231.159:26656" to `persistent_peers` in `config.toml` 
- Start nucleusd, and wait couple minutes(might take less/long depending on the network conditions) to sync with testnet.

You can also try public testnet node available using:
- grpc endpoint: http://65.109.231.159:9090
- rpc endpoint: http://65.109.231.159:26657
- rest endpoint : http://65.109.231.159:1317

## IBC channel list

**iris**(nyancat-9) to **nucleus**(nucleus-testnet-2)   -> channel-92

**nucleus**(nucleus-testnet-2) to **iris**(nyancat-9)   -> channel-0
