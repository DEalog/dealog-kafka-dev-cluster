# DEalog Kafka Development Cluster

**This is a development cluster, do not use in production.**

The origin docker-compose file is from the
"QUARKUS - USING APACHE KAFKA WITH REACTIVE MESSAGING" Guide [1]

## Requirements

- [Docker](https://docker.io)
- [Docker Compose](https://docs.docker.com/compose)

## Development

### Prerequisites

- Download the `docker-compose.yaml` or clone the repository and run
  `docker-compose`
- If not already there create the `dealog_dev` network:
  `docker network create dealog_dev`

```
docker-compose up [-d]
```

### Available listeners

To be able to use the cluster locally as well as Docker there are two listeners
available:

- `localhost:9092` for local (external) access
- `kafka:29092` for Docker (internal) access

### Run commands

Use `docker-compose exec kafka ls bin/` to see the top level scripts.

### Manually produce messages

```
docker-compose exec kafka bin/kafka-console-producer.sh --broker-list kafka:29092 --topic messages
```

### Kafka WebView

The Docker Compose setup comes bundled with the
[Kafka WebView](https://github.com/SourceLabOrg/kafka-webview)

This is started and exposed on port `8081`.

Open http://localhost:8081 in your web browser.

First you need to setup the cluster (`kafka:29092`). Next you need to create a
view. Then you can either browse or stream the messages.

The initial username is `admin@example.org`, the default password is `admin`.

## Sources

[[1] QUARKUS - USING APACHE KAFKA WITH REACTIVE MESSAGING](https://quarkus.io/guides/kafka)
