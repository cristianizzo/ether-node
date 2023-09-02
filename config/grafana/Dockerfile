# Use the official Grafana image as a base image
FROM grafana/grafana:latest

# Switch to the root user to install plugins
USER root

# Install the Worldmap Panel and Pie Chart Panel plugins
RUN grafana-cli plugins install grafana-worldmap-panel && \
    grafana-cli plugins install grafana-piechart-panel

# Switch back to the grafana user
USER grafana

COPY config.ini /etc/grafana/grafana.ini
COPY provisioning /etc/grafana/provisioning
