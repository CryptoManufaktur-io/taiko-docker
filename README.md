# Overview

Docker Compose for Taiko Layer 2 Node

Meant to be used with [central-proxy-docker](https://github.com/CryptoManufaktur-io/central-proxy-docker) for traefik
and Prometheus remote write; use `:ext-network.yml` in `COMPOSE_FILE` inside `.env` in that case.

If you want the RPC ports exposed locally, use `rpc-shared.yml` in `COMPOSE_FILE` inside `.env`.

## Upstream repo
https://github.com/taikoxyz/simple-taiko-node

## Quick Start

The `./taiko` script can be used as a quick-start:

`./taiko install` brings in docker-ce, if you don't have Docker installed already.

`cp default.env .env`

`nano .env` and adjust variables as needed, particularly L1_ENDPOINT_WS, L1_BEACON_HTTP, and P2P_SYNC_URL

`./taiko up`

## Software update

To update the software, run `./taiko update` and then `./taiko up`

## Customization

`custom.yml` is not tracked by git and can be used to override anything in the provided yml files. If you use it,
add it to `COMPOSE_FILE` in `.env`

## Components

This repository includes:

1. **L2 Execution Engine**: A modified Geth client for Taiko (taiko-geth)
2. **Taiko Client Driver**: The driver that synchronizes the L2 chain with L1 data

## Required Configuration

Before starting, ensure you have:
- An Ethereum L1 WebSocket endpoint (L1_ENDPOINT_WS)
- An Ethereum L1 Beacon API endpoint (L1_BEACON_HTTP)
- (Optional) Adjust P2P_SYNC_URL for checkpoint sync

## Version

Taiko Docker uses a semver scheme.

This is Taiko Docker v1.0.0
