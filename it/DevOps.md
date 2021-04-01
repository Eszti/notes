# DevOps

## Containers

### Docker

- PaaS (Platform as a Service)
- OS level virtualization
- deliver software in packages, called containers
- run by OS kernel, less resources than VM
- low level tasks
  - `start`
  - `stop`
  - `delete`

### docker-compose

- defining & running multi-container docker applications

### Kubernetes (k8s)

- container orchestration tool
- high level tasks
  - automatic deployment
  - scaling & management of containerized apps
- came out of Google
- conductor
  - K8s Control Pane
- node (cloud or on-premise)
  - container runtime + k8s software (agent)

## AWS

- [localstack](https://github.com/localstack/localstack)
- CodePipeline: CI
- SFTP as managed service

## Automated checks

- [clair](https://github.com/quay/clair)
  - static analysis of vulnerabilities
- dependency update checks
  - [renovate](https://github.com/renovatebot/renovate)
  - [dependabot](https://dependabot.com/)
- dependency vulnerability checks
  - [dependency-check-maven](https://jeremylong.github.io/DependencyCheck/dependency-check-maven/index.html)

## Monitoring

- [Prometheus](https://prometheus.io/)
  - stores real time monitoring in a time series database
- [Grafana](https://grafana.com/)
  - for creating monitoring dashboards
  - query, visualize, alert on metrics
  - can query Prometheus

## Profiling

- [Apache JMeter](https://jmeter.apache.org/)
  - load testing tool
- [Visual VM](https://visualvm.github.io/)
  - get detailed info about Java applications running on a JVM
