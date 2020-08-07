# DEalog Kafka Development Cluster
**This is a development cluster, do not use in production.**

The origin docker-compose file is from the "QUARKUS - USING APACHE KAFKA WITH REACTIVE MESSAGING" Guide [1]

## Requirements
- [Docker](https://docker.io)
- [Docker compose](https://docs.docker.com/compose/compose-file)

## Development
Download the `docker-compose.yaml` or clone the repository and run `docker-compose`
```
docker-compose up
```

### Manually produce messages
Get your container id and execute bash ...
```
docker exec -it [CONTAINER] bash
```

... read data from standard input and publish it to Kafka
```
./bin/kafka-console-producer.sh --broker-list kafka:9092 --topic messages
```

## Sources
[[1] QUARKUS - USING APACHE KAFKA WITH REACTIVE MESSAGING](https://quarkus.io/guides/kafka)