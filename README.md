# Quickstart for Thanos

![CI badge](https://github.com/dbluxo/quickstart-thanos/workflows/build-and-test/badge.svg)

Get up and running with Thanos, Prometheus, Grafana, Alertmanager, cAdvisor and Node Exporter with a `docker-compose.yaml` file in less than 5 minutes.

## Running the example

```bash
git clone https://github.com/dbluxo/quickstart-thanos
cd quickstart-thanos
docker-compose up -d
```

The following services will be installed (and some are accessible via browser):

| Component                     | Description                                                               | URL                           |
| -----------------------       | ------------------------------------------------------                    | ----------------------------- |
| prometheus-1                  | Prometheus Server 1 (labels: cluster=chicago, replica=r1)                 | <http://localhost:9081/>      |
| prometheus-2                  | Prometheus Server 2 (labels: cluster=chicago, replica=r2)                 | <http://localhost:9082/>      |
| prometheus-3                  | Prometheus Server 3 (labels: cluster=seattle, replica=r1)                 | <http://localhost:9083/>      |
| prometheus-4                  | Prometheus Server 4 (labels: cluster=seattle, replica=r2)                 | <http://localhost:9084/>      |
| thanos-sidecar-1              | Thanos Sidecar for Prometheus Server 1                                    | not accessible via browser    |
| thanos-sidecar-2              | Thanos Sidecar for Prometheus Server 2                                    | not accessible via browser    |
| thanos-sidecar-3              | Thanos Sidecar for Prometheus Server 3                                    | not accessible via browser    |
| thanos-sidecar-4              | Thanos Sidecar for Prometheus Server 4                                    | not accessible via browser    |
| thanos-query-frontend         | Thanos Query Frontend                                                     | <http://localhost:10901/>     |
| thanos-querier                | Thanos Querier                                                            | <http://localhost:10902/>     |
| thanos-ruler                  | Thanos Ruler                                                              | <http://localhost:10903/>     |
| thanos-bucket-web             | Thanos Bucket Web                                                         | <http://localhost:10904/>     |
| thanos-store-gateway          | Thanos Store Gateway                                                      | not accessible via browser    |
| thanos-compactor              | Thanos Compactor                                                          | not accessible via browser    |
| minio                         | Minio - Amazon S3 Compatible Object Storage                               | <http://localhost:9000/>      |
| alertmanager                  | Alertmanager                                                              | <http://localhost:9093/>      |
| grafana                       | Grafana                                                                   | <http://localhost:3000/>      |
| cadvisor                      | cAdvisor                                                                  | <http://localhost:8080/>      |
| node-exporter                 | Node Exporter                                                             | <http://localhost:9100/>      |

## Credentials

Grafana:

```bash
username - admin
password - foobar (Password is stored in the `/grafana/config monitoring` env file)
```
  
Minio:

```bash
Access Key - smth
Secret Key - Need8Chars (Keys are stored in the `docker-compose.yaml` file)
```

## Explore metrics

* Explore metrics via Grafana <http://localhost:3000/explore> or the Thanos Query Frontend <http://localhost:10901>

## Notes

This project is intended to be a quick-start to get up and running with Thanos. Security has not been implemented in this project.
It is inspired by:

- <https://github.com/vegasbrianc/prometheus> (forked from this project)
- <https://github.com/alexellis/quickstart-prometheus>
