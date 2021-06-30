# Docker-Compose
This repository contains the docker-compose.yml and all other files to run the covidpass infrastructure

## Prometheus-Metrics
This docker-compose exports the traefik service to the /traefik-metrics endpoint which is secured using basic-auth.
The metrics endpoint doesn't contain any personal informations like ip-address or user-agent.
It only exports general service-health realted information like how many 404 errors and how many total accesses received the service.

Here's an example output of the prometheus metrics endpoint: https://github.com/covidpass-org/docker-compose/blob/main/prometheus-export-sample.txt
