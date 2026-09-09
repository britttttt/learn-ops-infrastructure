# System Map (AI)

## 1. System Diagram

```mermaid
%%{init: {'theme':'dark'}}%%
graph LR
    client[learn-ops-client] -->|HTTP :8000| api[learn-ops-api]
    api -->|SQL :5432| db[(database)]
    api -->|"PUBLISH pub/sub :6379"| valkey[(valkey)]
    api -->|HTTPS REST| github[GitHub REST API]
    api -->|HTTPS REST| slack[Slack Web API]
    monarch[service-monarch] -->|"SUBSCRIBE pub/sub :6379"| valkey
    monarch -->|HTTPS REST| github
    valkeymon[valkey-monitor] -->|"MONITOR :6379"| valkey
    pgexp[postgres_exporter] -->|SQL :5432| db
    prometheus[prometheus] -->|"HTTP scrape :8000"| api
    prometheus -->|"HTTP scrape :9187"| pgexp
    grafana[grafana] -->|"HTTP query :9090"| prometheus
```