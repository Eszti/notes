# Containers

## Docker

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

## Kubernetes (k8s)

- container orchestration tool
- high level tasks
  - automatic deployment
  - scaling & management of containerized apps
- came out of Google
- conductor
  - K8s Control Pane
- node (cloud or on-premise)
  - container runtime + k8s software (agent)