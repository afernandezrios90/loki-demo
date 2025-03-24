# Loki Demo

Repository for deploying a simple Loki installation along with an application to generate logs

## Description

> [!TIP]  
> You are in the `virtual-store` branch. Other active branches with slightly different funcionality are:
> - `main` --> Loki + Alloy deployment with a simple app called "Carnivorous Garden" that logs some activity (to have samples). Those samples are ingested by Alloy and stored by Loki.

This project is just a simple simulation of a Loki installations to test basic functionality. It is based on 'what-is-loki' branch of [loki-fundamentals](https://github.com/grafana/loki-fundamentals) official repository.

## Considerations
This branch does not include a Grafana instance, since the original idea was to use an existing Grafana container. Therefore all the components use the "grafana-network".

## Installation
1. Clone the repository
```bash
git clone https://github.com/afernandezrios90/loki-demo.git
```
2. Switch to the desired branch
3. Adjust the configuration if desired to change log path, processing features, etc, if desired
4. Run using Docker compose
```bash
docker-compose up -d
```
5. Open the "Virtual Store" app in your browser (`http://localhost:5000`) and interact to start generating interesting log content. If you haven't deployed the Virtual Store App yet, check: https://github.com/afernandezrios90/virtual-store
6. Add Loki installation as datasource in Grafana and start reviewing logs.

## Troubleshooing
### Test logs ingestion
Check the Loki logs (`docker logs -f loki`) and search some lines like this one:

`level=info ts=2025-02-26T18:45:30.123456Z caller=ingester.go:150 msg="received new log entry"`