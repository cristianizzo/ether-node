# Ethereum Node Monitoring with Grafana, Prometheus, and Prysm Beacon Chain

This repository provides the configuration files and instructions to set up an Ethereum node, monitor it using Grafana and Prometheus, and integrate the Prysm Beacon Chain for Ethereum 2.0 validation. The project is designed to run on an AWS instance using Ubuntu.

## Prerequisites

- Docker and Docker Compose installed on your AWS Ubuntu instance.
- Basic understanding of Docker and containerization concepts.

## Getting Started

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/cristianizzo/ether-node.git
   cd ether-node
   ```

2. Generate JWT Secret:

   Generate a JWT secret using OpenSSL and store it in a file named `jwt.hex` inside the `data` directory:

   ```bash
   openssl rand -hex 32 > data/jwt.hex
   ```

   This JWT secret is used for authentication and authorization purposes in the Ethereum node.

3. Configure Prometheus:

    - Edit the `./prometheus/prometheus.yml` file to customize scraping targets according to your services.

4. Configure Beacon Chain and Validator:

    - Edit the `./config/beacon.yaml` and `./config/validator.yaml` files to configure Ethereum 2.0 Beacon Chain and Validator settings.

5. Start the Monitoring Stack:

   Run the following command to start all services defined in the Docker Compose file:

   ```bash
   docker-compose up -d
   ```

   This command will create and start containers for the following services:

    - **Ethereum Geth**: Ethereum node for blockchain synchronization and JSON-RPC/WebSocket communication.
    - **Prysm Beacon Chain**: Ethereum 2.0 Beacon Chain for validator operations.
    - **Prysm Validator**: Validator service integrated with the Beacon Chain.
    - **Prysm Slasher**: Slasher service to manage and monitor Ethereum 2.0 slashing events.
    - **Prometheus**: Metrics collection and storage service for monitoring.
    - **Grafana**: Visualization and dashboarding tool for monitoring data.
    - **Grafana Image Renderer**: Tool to render Grafana dashboards as images.
    - **Node Exporter**: System metrics exporter for Prometheus.

6. Access Services:

    - Ethereum Geth: Access the Ethereum node at `http://localhost:8545` for JSON-RPC and `ws://localhost:8546` for WebSocket communication.

    - Prysm Beacon Chain: Access the Beacon Chain service at `http://localhost:4000`.

    - Grafana: Access the Grafana web UI at `http://localhost:3000`. Use the default credentials `admin/admin` to log in.

    - Prometheus: Access the Prometheus web UI at `http://localhost:9090`.

7. Grafana Configuration:

    - Log in to Grafana using the default credentials.
    - Import dashboards from the community or create custom dashboards to visualize Ethereum and Prysm metrics.
    - Configure data sources to integrate Prometheus with Grafana.

## Customization and Further Steps

- You can modify configurations for Ethereum Geth, Prysm Beacon Chain, and Validator services as per your requirements.

- Customize dashboards in Grafana to visualize specific metrics and data important for your monitoring needs.

## Troubleshooting

- If you encounter issues during setup, consult the logs of individual containers using `docker-compose logs <container-name>`.

## Disclaimer

This setup is intended for development and learning purposes. Ensure you have proper security measures in place before deploying it in a production environment.

## Contributions

Contributions are welcome! Feel free to contribute improvements, bug fixes, or additional features to this repository.

