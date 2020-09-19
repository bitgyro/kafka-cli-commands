# Kakfa CLI Reference
The document provides ready reference to Kakfa CLI commands.
# List existing topics
kafka-topics.sh --zookeeper localhost:2181 --list
# Create new topic

kafka-topics.sh --zookeeper localhost:2181 --topic topic_name --create  --partitions 3 --replication-factor 3

# Create new topic with log compaction
kafka-topics.sh --zookeeper localhost:2181 \
                 --topic favourite_color   \
                 --create  --partitions 3 --replication-factor 3 \
                 --config cleanup.policy=compact \
                 --config segment.ms=10000 \
                 --config min.cleanable.dirty.ratio=0.005 


# Delete topic
kafka-topics.sh --zookeeper localhost:2181 --topic favourite_color --delete

# Create kafka console producer
kafka-console-producer.sh --bootstrap-server localhost:9092 \
                          --topic favourite_color  \
                          --property parse.key=true \
                          --property key.separator=,

# Create kafka console consumer
kafka-console-consumer.sh --bootstrap-server localhost:9092 \
                          --topic favourite_color  \
                          --from-beginning \
                          --property print.timestamp=true --property print.key=true --property print.value=true  --property key.separator=,       
                          
                          
                          



