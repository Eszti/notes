# Prometheus workshop

## Prometheus

- warum
  - info about the system
- archtecture
  - center: application
  - prometheus
    - collects metrics to a DB
      - back to app
      - to an exporter
  - grafana
    - can query the DB
  - alert manager
    - can receive alerts from the DB

- prometheus
  - 2012 by SoundCloud
  - written in Go
  - for storing and querying metrics
  - optimized for multidimensional time series (e.g influx)
    - DB can be changed
  - pull based approach (prometheus asks active for metrics)

- data model
  - time series
  - name of metric
    - labels (key-value)

- configuration
  - yaml file
  - for instance
    - scrape interval
    - retention time

- metrics
  - defaults
    - labels
      - intance & job

- PromQL
  - query
    - specific metrics
      - e.g.: up
    - query labels
      - {job="my-job"}
    - both
      - up{job="test-app"}
    - regegx
  - operators
    - binary
    - matching via labels (all must match!)
    - if matching should be ignored: ignoring(job, instance)
    - aggragations
      - sum, count, topk
      - group by: count by(job)
  - range vectors
    - metric[5m]
    - rate, changes, delta

- secured apps
  - in config
  - only basic auth, bearer, cerificates are supported

## Grafana

- 2012
- written in go
- clicky

- data sources
  - prometheus
  - elastic search
  - postgre
  - cloudwatch

- dashboards
  - visualisation
    - status blocks
    - speedometer
  - query
    - can be PromQL

- configuration
  - /etc/grafana/grafana.ini
  - e.g.
    - provisioning folder
      - standard: /etc/grafana/provisioning
    - logging
    - allowed login
    - database
      - default: sqlite
      - metrics won't be saved in grafana, only dashboards and user data

- data source provisioning
  - /etc/grafana/provisioning/datasources/datasources.yml
- dashboard provisioning
  - can be exported in json format
  - put to /etc/grafana/provisioning/dashboards/dashboards.yml

- templates and variables
- command line interface
  - set password
  - install plugins

- playlists
  - automatically cycle through a list of dashboards
- rest API
  - create readonly users
  - customize welcome screen
- [public dashboards](https://grafana.com/grafana/dashboards)
  - import
- additional panels

## Exporter

- instrumenting
  - official libraries
    - go, java, scala, python, ruby

- blackbox exporter
  - check only response
  - http, https, dns, tcp...

- custom exporter
  - write in python

- push gateway
  - if instances can disappear
  - metrics need to be pushed to a push gateway
  - samples need to be explicitly deleted
  - use rather alternatives
    - e.g. log

## Alterting

- config prometheus
  - rules file
  - alert templates
    - templating language is based on Go

- Alertmanager
  - grouping
  - silencing
  - inhibition
  - forwarding to receiver
    - limited
    - webhook is generic, can be used basically for everything
    - email...

- grafana alert
  - only supported in graph panel

- prometheus alert vs grafana alert
  - prometheus is more flexible

## Advanced

- relabel configs
  - e.g. suffix to label
  - via regex
- recording rules
