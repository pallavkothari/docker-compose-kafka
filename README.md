# Docker/Kafka

Run kafka:
```bash
docker-compose up
```

Create a topic:
```bash
docker-compose run --rm kafka kafka-topics.sh --create --topic test --replication-factor 1 --partitions 1 --zookeeper zookeeper:2181
```

List topics:
```bash
docker-compose run --rm kafka kafka-topics.sh --list --zookeeper zookeeper:2181
```

In a separate terminal, run a producer
```bash
docker-compose run --rm kafka  kafka-console-producer.sh --topic test --broker-list kafka:9092
```

In a separate terminal, run a consumer:
```bash
docker-compose run --rm kafka kafka-console-consumer.sh --topic test --from-beginning --bootstrap-server kafka:9092
```
