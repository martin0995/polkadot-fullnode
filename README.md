<h1 align="left">
  <img src="https://cryptologos.cc/logos/polkadot-new-dot-logo.png?v=029" alt="Polkadot Icon" width="50" height="50">
  &nbsp; Westend Fullnode (Polkadot Testnet)
</h1>

Dockerfile to run a westend (Polkadot testnet) fullnode.

## Prerequisites:

Before running the node, please make sure to cover the following recommended requirements:

- 4 CPU
- 16 GB Memory
- 300 GB Storage

Finally, before running the image, go into the Dockerfile and define your node's name in the 5th line.

## Build Image:

```bash
docker build -t image-name .
```

## Run Node:

```bash
docker run -d image-name
```

## Check that your node is successfully running:

Visit Polkadot Telementry website to check that your node is running. Make sure to select the correct chain (westend).

[Visit Polkadot Telementry](https://telemetry.polkadot.io/#/0xe143f23803ac50e8f6f8e62695d1ce9e4e1d68aa36c1cd2cfd15340213f3423e)

## Official Documentation:

[Visit Polkadot Documentation](https://wiki.polkadot.network/docs/maintain-sync)
