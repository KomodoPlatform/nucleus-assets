# Nucleus Testnet Setup

Nucleus Testnet performs exactly same actions as mainnet specifically for development and testing purposes. Therefore, developers can use this service for development/testing purposes without taking any risk at all.

## Join Nucleus Testnet

- First visit [KomodoPlatform/nucleus](https://github.com/KomodoPlatform/nucleus) and follow the installation and starting instructions.
- Replace your `genesis.json` [with this one](https://raw.githubusercontent.com/KomodoPlatform/nucleus-assets/main/nucleus-testnet-1/genesis.json).
- Add "c7f78e7ba5c7db4000770bbdbfb47db427aec20a@65.109.231.159:26656" to `persistent_peers` in `config.toml` 
- Start nucleusd, and wait couple minutes(might take less/long depending on the network conditions) to sync with testnet.

You can also try public testnet node available using:
- grpc endpoint: http://65.109.231.159:9090
- rpc endpoint: http://65.109.231.159:26657
- rest endpoint : http://65.109.231.159:1317

## IBC channel list

**iris**(nyancat-9) to **nucleus**(nucleus-testnet-1)   -> channel-88

**nucleus**(nucleus-testnet-1) to **iris**(nyancat-9)   -> channel-2
