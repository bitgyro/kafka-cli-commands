# Kakfa CLI Reference
The document provides ready reference to Kakfa CLI commands.
# List existing topics
kafka-topics.sh --zookeeper localhost:2181 --list
# Create new topic

kafka-topics.sh --zookeeper localhost:2181 --topic topic_name --create  --partitions 3 --replication-factor 3

