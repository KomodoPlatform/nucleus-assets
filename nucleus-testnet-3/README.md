# Nucleus Testnet v3 Setup

Nucleus Testnet v3 performs exactly same actions as mainnet specifically for development and testing purposes. Therefore, developers can use this service for development/testing purposes without taking any risk at all.

## Join Nucleus Testnet v3

- First install [KomodoPlatform/nucleus](https://github.com/KomodoPlatform/nucleus).
- Follow the following instructions:

```sh
nucleusd init <moniker> --chain-id=nucleus-3
nucleusd config keyring-backend test
```

- In `.nucleus/config`
- - Replace `genesis.json` [with this one](./genesis.json).
- - Replace `config.toml` [with this one](./config.toml).
- - Replace `app.json` [with this one](./app.toml).
- Start the node with `nucleusd start` , and wait couple minutes(might take less/long depending on the network conditions) to sync with testnet.

You can start using:
- grpc endpoint: http://127.0.0.1:9090
- rpc endpoint: http://127.0.0.1:26657
- rest endpoint : http://127.0.0.1:1317

Or, you can also try publicly available testnet node using:
- grpc endpoint: http://5.161.55.53:9090
- rpc endpoint: http://5.161.55.53:26657
- rest endpoint : http://5.161.55.53:1317

## Upgrade to Validator Node

To become a validator, you need an account that has nucleus tokens in it.
You can either create an account(`nucleusd keys add <key-name> --keyring-backend=test`) and send some funds into it, or recover(`nucleusd keys add <key-name> --keyring-backend=test --recover`) your account with bip32 mnemonic.

Before creating a validator, make sure `nucleusd` is running and synced with the network.

```sh
nucleusd tx staking create-validator \
    --pubkey=$(nucleusd tendermint show-validator) \
    --moniker=<moniker> \
    --amount=<amount-to-be-delegated, e.g. 10000unucl> \
    --min-self-delegation=1 \
    --commission-max-change-rate=0.10 \
    --commission-max-rate=0.20 \
    --commission-rate=0.1 \
    --gas=200000 \
    --gas-prices=0.0035unucl \
    --chain-id=nucleus-3 \
    --from=<key-name>
```