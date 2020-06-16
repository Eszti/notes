# Database

## RDBMS (Relational Database Management System)

- well defined schema
- tables & colums

- Examples
  - [H2](https://www.h2database.com/html/main.html)
    - written in java
    - can be embedded in java applications in client-server mode
  - [AWS RDS](https://aws.amazon.com/rds/)

### API

- JDBC (towards relational)
- ODBC (not only for relational)

## NoSQL

- not only SQL

### Key-value store

- ~ dictionary or hash table

- Examples
  - [redis](https://redis.io/)

### Document-based

- subclass of key-value store
- store object in a single instance
- assume some kind of encoding (xml, yaml, json, bson)

- Examples
  - [MongoDB](https://www.mongodb.com/)
  - [AWS DocmentDB](https://aws.amazon.com/documentdb/)

### Wide-column store

- has rows & columns but the column format varies from row to row
- ~ two dimensional key-value store

- Examples
  - [Cassandra](https://cassandra.apache.org/)
  - [AWS DynamoDB](https://aws.amazon.com/dynamodb/)
