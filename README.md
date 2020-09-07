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

### Run commands

Use `docker-compose exec kafka ls bin/` to see the top level scripts.

### Manually produce messages

```
docker-compose exec kafka bin/kafka-console-producer.sh --broker-list kafka:9092 --topic messages
```

### Kafka WebView

The Docker Compose setup comes bundled with the
[Kafka WebView](https://github.com/SourceLabOrg/kafka-webview)

This is started and exposed on port `8080`.

Open http://localhost:8080 in your web browser. You need to create a view
initally. Then you can either browse or stream the messages.

## Sources

[[1] QUARKUS - USING APACHE KAFKA WITH REACTIVE MESSAGING](https://quarkus.io/guides/kafka)
