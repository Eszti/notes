# Elasticsearch

- [Doku](https://www.elastic.co/guide/en/elasticsearch/reference/current/elasticsearch-intro.html)

- a distributed document store
- serialized as JSON
- document: key-value pairs
- data structure
	- text: inverted index: 
		- list of every unique word with all the documents they occur in
	- numeric & GEO fields
		- BKD trees: a k-dimansional B+ tree (balanced search tree)
- schema
	- can be schema-less
	- dynamic mapping
		- default automatic mapping (boolean, floating point...)
	- defining your own mapping
		- custom formats
		- geo_point & geo_shape cannto be detected automatically
	- often useful to index the same field in different ways
- full-text field
	- query text undergoes the same analysis as the text field
- search built on Apache Lucene search engine library

## Interface

- REST API
	- managing the cluster
	- indexing data
	- searching data
- testing
	- command line
	- Kibana: Developer Console
	- Elasticsearch client (e.g. python)

## Search

- structured queries
	- SQL-like
- full text queries
	- return all matching and sorting by relevance
- complex queries
	- combination
- query vs filter
	- query: uses scoring from Lucene
	- filter: does not compute scores, faster

## Architecture

- distributed by nature
- nodes
	- servers
	- data & queries are automatically distributed
- cluster
	- contains multiple nodes
- shards
	- physical
	- a self-contained index
	- primary
		- each document belogs to one
		- number is fixed at the time when the index is created
	- replicas
		- copy of a primary shard
		- number can be changed any time
- redundancy
	- documents are distributed in an index across multiple shards
	- shards are distributed across multiple nodes

## Concepts

- index ~ database in SQL
- mapping
	- defining how a documents and its fields are stored and indexed
- indexing = storing a document in an index
- searching = retrieven a document

## Start

```bash
# To start on system boot up
sudo systemctl daemon-reload
sudo systemctl enable elasticsearch.service

# Start
sudo systemctl start elasticsearch.service
# Stop
sudo systemctl stop elasticsearch.service

# Check if running
curl --cacert /etc/elasticsearch/certs/http_ca.crt -u elastic https://localhost:9200

# 
```

## Configuration

- systemd service file: `/usr/lib/systemd/system/elasticsearch.service`
- [config docs](https://www.elastic.co/guide/en/elasticsearch/reference/current/settings.html)
- config files
	- `/etc/elasticsearch/elasticsearch.yml`: to configure Elasticsearch

	- `path.data: /var/lib/elasticsearch`: data we index
	- `path.logs: /var/log/elasticsearch`: own application logs

## Index

- number of shards: every index can contain up to 2^32 docs, shard size 20-25GB
- number of replicas: how many times your data is replicated in your cluster
- after creating the index all the shards are ready to accept data
- open/close index
- freeze index
- create a mapping ~ tables/schema for SQL
- reindexing
	- instead of deleteing an existing mapping (not possible)
	- source & dest
- refreshing
	- data is not searchable directly after sending it (fixed time interval) - can be enforced
- flushing: move from memory to disk (done periodically)
- merge
- shrink
- aliases: group multiple indices
- bulk operations
	- bulk insert
	- multi-get

## Install

Follow [this](https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html) guide to install elasticsearch. 

```bash
# Download and install the public signing key:
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg

# Install apt-transport-https (in case it's not already on your computer):
sudo apt-get install apt-transport-https

# Save the repository definition to /etc/apt/sources.list.d/elastic-8.x.list:
echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list

# Install the Elasticsearch Debian package:
sudo apt-get update && sudo apt-get install elasticsearch
```

### Disable security

Open `elasticsearch.yml` for editing, e.g. with `vi`:
```bash
sudo vi /etc/elasticsearch/elasticsearch.yml
```

Set `xpack.security.enabled` to `false`:
```bash
xpack.security.enabled: false
```

Add `xpack.license.self_generated.type` field with value `basic`:
```bash
xpack.license.self_generated.type: basic
```

## Uninstall

```bash
sudo rm -rf /var/lib/elasticsearch
sudo rm -rf /usr/share/elasticsearch
sudo apt-get purge elasticsearch
```

## Troubleshooting

`curl: (77) error setting certificate file: /etc/elasticsearch/certs/http_ca.crt`

1. Check whether the cert file exist by calling `sudo cat /etc/elasticsearch/certs/http_ca.crt`.
2. If you do not have one, you can create it by calling `sudo /usr/share/elasticsearch/bin/elasticsearch-certutil ca`.
3. Add read permission for others by calling `sudo chmod a+rx /etc/elasticsearch/ /etc/elasticsearch/certs` and `sudo chmod a+r /etc/elasticsearch/certs/http_ca.crt `.
