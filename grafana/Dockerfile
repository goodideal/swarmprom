FROM grafana/grafana:6.7.1
# https://hub.docker.com/r/grafana/grafana/tags/

COPY datasources /etc/grafana/provisioning/datasources/
COPY swarmprom_dashboards.yml /etc/grafana/provisioning/dashboards/
COPY dashboards /etc/grafana/dashboards/

ENV GF_SECURITY_ADMIN_PASSWORD=admin \
    GF_SECURITY_ADMIN_USER=admin \
    GF_PATHS_PROVISIONING=/etc/grafana/provisioning/

# install plugins 
RUN grafana-cli plugins install grafana-piechart-panel \
    && grafana-cli plugins install grafana-worldmap-panel \
    && grafana-cli plugins install grafana-clock-panel
