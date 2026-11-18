IT Infrastructure Monitoring Homelab

A hands-on IT infrastructure monitoring project built using Docker, Prometheus, Grafana, Node Exporter, and Windows Exporter.

Project Overview

Built a containerized monitoring environment to collect, visualize, and analyze system performance metrics from a Windows computer and Docker's Linux environment.

The goal of this project is to develop practical skills in system administration, infrastructure monitoring, troubleshooting, and IT operations.

Technologies Used

- **Docker & Docker Compose** — Container deployment and management
- **Prometheus** — Metrics collection and monitoring
- **Grafana** — Performance dashboards and visualization
- **Node Exporter** — Linux environment monitoring
- **Windows Exporter** — Windows performance monitoring
- **PowerShell** — Service verification and troubleshooting
- **YAML** — Monitoring configuration

Monitoring Architecture

```text
Windows Computer
      |
Windows Exporter (9182)
      |
      v
Prometheus (9090) <--- Node Exporter (9100)
      |
      v
Grafana (3000)
      |
      v
Monitoring Dashboards
```

## Features

- Windows CPU utilization monitoring
- Windows memory utilization monitoring
- Disk capacity monitoring
- Network traffic monitoring
- Linux environment monitoring through Node Exporter
- Prometheus alert-rule configuration
- Grafana dashboards for visualizing system performance

## Troubleshooting Experience

During implementation, I identified and resolved several technical issues:

1. Diagnosed a Docker daemon connection error and restored connectivity.
2. Fixed incorrect PowerShell working-directory issues affecting Docker Compose.
3. Troubleshot YAML syntax errors preventing Prometheus from starting.
4. Verified Prometheus target health and exporter connectivity.
5. Investigated missing Grafana metrics and updated PromQL queries to match Windows Exporter metric names.
6. Created custom Grafana panels to visualize Windows performance data.

## Project Files

- `docker-compose.yml` — Defines the containerized monitoring services.
- `prometheus.yml` — Configures metric collection targets.
- `alerts.yml` — Contains Prometheus alert rules.
- `README.md` — Project documentation.

## Running the Project

1. Install Docker Desktop.
2. Clone this repository.
3. Configure the Grafana administrator password locally using the environment variables referenced by Docker Compose.
4. Start the monitoring stack:

```powershell
docker compose up -d
```

5. Install Windows Exporter on the Windows host for Windows metrics.
6. Open Prometheus at `http://localhost:9090`.
7. Open Grafana at `http://localhost:3000`.
8. Configure Grafana to use `http://prometheus:9090` as its Prometheus data source.

## Future Improvements

- Configure and test high CPU and disk usage alerts.
- Add notification delivery for critical system events.
- Expand monitoring to multiple machines.
- Document recovery and incident-response procedures.

## Skills Demonstrated

Infrastructure Monitoring | Docker | Prometheus | Grafana | Windows Administration | Linux Monitoring | PowerShell | Troubleshooting | PromQL

## Monitoring Dashboard Screenshots

### Windows System Monitoring

Custom Grafana dashboard displaying real-time Windows CPU utilization, RAM usage, and C: drive storage consumption.


### Prometheus Target Health

Prometheus successfully collecting metrics from three monitoring targets: Windows Exporter, Node Exporter, and Prometheus itself.


### Linux Environment Monitoring

Node Exporter Full dashboard displaying CPU, memory, disk, network, and system performance metrics from Docker's Linux environment.

