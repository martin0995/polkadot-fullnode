<h1 align="left">
  <img src="https://cryptologos.cc/logos/polkadot-new-dot-logo.png?v=029" alt="Polkadot Icon" width="50" height="50">
  &nbsp; Polkadot Fullnode (Mainnet and Testnet)
</h1>

Dockerfile to run a fullnode in the Polkadot ecosystem. You will find below all the steps on how to run your own fullnode (mainnet and testnet).

## Prerequisites:

Before running the node, please make sure to cover the following recommended requirements:

#### Westend (testnet):

- 4 CPU
- 16 GB Memory
- 300 GB Storage

#### Polkadot (mainnet):

- 4 CPU
- 32 GB Memory
- 500 GB Storage

## Build Image:

```bash
docker build -t image-name .
```

## Run Node:

Please specify the node's name in the below command.

#### Run fullnode on Westend:

```bash
docker run -d image-name --name your-node-name --chain=westend --sync=warp
```

#### Run fullnode on Polkadot:

```bash
docker run -d image-name --name your-node-name
```

## Check that your node is successfully running:

Visit Polkadot Telementry website to check that your node is running. Make sure to select the correct chain.

[Westend Telementry](https://telemetry.polkadot.io/#/0xe143f23803ac50e8f6f8e62695d1ce9e4e1d68aa36c1cd2cfd15340213f3423e)

[Polkadot Telementry](https://telemetry.polkadot.io/#list/0x91b171bb158e2d3848fa23a9f1c25182fb8e20313b2c1eb49219da7a70ce90c3)

## Official Documentation:

[Polkadot Documentation](https://wiki.polkadot.network/docs/maintain-sync)
