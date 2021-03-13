## To run docker compose yaml
## docker-compose up

## one partition for a topic can only be read by one consumer in a consumer group

## One consumer in a consumer group can read messages from more than one partitions for a given topic  

##/opt/kafka_2.13-2.7.0 # pwd
  > /opt/kafka

## create topic
> ./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic my-topic-3

## List Topics
> ./bin/kafka-topics.sh --list --zookeeper zookeeper:2181

## describe topic
> ./bin/kafka-topics.sh --topic my-topic --describe --zookeeper zookeeper:2181

## describe all topics
> ./bin/kafka-topics.sh --describe --zookeeper zookeeper:2181

## produce a message
> ./kafka-console-producer.sh --topic my-topic --bootstrap-server localhost:9092 
  >first message 1
  >second message 2

## consume message
> /opt/kafka_2.13-2.7.0/bin # ./kafka-console-consumer.sh --topic my-topic --bootstrap-server localhost:9092 --from-beginning
>first message 1
>second message 2
### --from-beginning will get all messages

## create consumer group
> /opt/kafka_2.13-2.7.0/bin # ./kafka-console-consumer.sh --topic my-topic --bootstrap-server localhost:9092 --from-beginning --group cg1

## describe group 
> /opt/kafka_2.13-2.7.0/bin # ./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --describe --group cg1
