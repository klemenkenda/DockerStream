# Installation

## Prerequisites

* Ubuntu 17.10, server, with OpenSSH, tmux.

## Docker

```
sudo apt install docker
```

## Docker Machine

```
curl -L https://github.com/docker/machine/releases/download/v0.13.0/docker-machine-`uname -s`-`uname -m` >/tmp/docker-machine &&
chmod +x /tmp/docker-machine &&
sudo cp /tmp/docker-machine /usr/local/bin/docker-machine
```

## Kafka

Repository: [[https://github.com/spotify/docker-kafka]].

```
sudo docker run -d -p 2181:2181 -p 9092:9092 --env ADVERTISED_HOST=`docker-machine ip \`docker-machine active\`` --env ADVERTISED_PORT=9092 --name kafka spotify/kafka
sudo docker run -it --name kafkaClient spotify/kafka bash
```

### Quick-start console tools for Kafka
https://kafka.apache.org/quickstart

Create topic
```
$KAFKA_HOME/bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
```

Start console producer
```
$KAFKA_HOME/bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test
```

Start a consumer
```
$KAFKA_HOME/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```