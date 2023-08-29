# Ethereum Node Monitoring with Grafana, Prometheus, and Prysm Beacon Chain

This repository contains the necessary configuration files to set up an Ethereum node and monitor it using Grafana and Prometheus. It also includes the Prysm beacon chain.

## Directory Structure

- `./docker-compose.yml`: Docker Compose configuration file
- `./prometheus/prometheus.yml`: Prometheus configuration file
- `./node/Dockerfile`: Dockerfile for Ethereum node
- `./grafana/Dockerfile`: Dockerfile for Grafana
- `./grafana/config.ini`: Grafana configuration file

## Endpoints

- **Ethereum Node**: Accessible at `http://localhost:8545` for HTTP and `ws://localhost:8546` for WebSockets.
- **Grafana**: Accessible at `http://localhost:3000`. Default login is `admin/admin`.
- **Prometheus**: Accessible at `http://localhost:9090`.
- **Prysm Beacon Chain**: Accessible at `http://localhost:4000`.

## How to Run

1. Clone the repository.
2. Navigate to the repository directory.
3. Run `docker-compose up -d` to start all services.
4. Open Grafana at `http://localhost:3000` and log in with the admin credentials.

