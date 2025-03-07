# Apache Kafka

Apache Kafka is a high-throughput, fault-tolerant, and scalable distributed streaming platform initially developed at LinkedIn. It is designed to efficiently handle real-time data streams from various sources, including applications, databases, and sensors.

Kafka operates as a **publish-subscribe messaging system**, enabling applications to seamlessly publish and consume data from topics. It is widely used for event-driven architectures, real-time analytics, and data integration due to its reliability, durability, and performance.

## Key Features
- **Scalability**: Seamlessly scales horizontally to accommodate large data volumes.
- **Fault Tolerance**: Ensures high availability through data replication across multiple brokers.
- **Low Latency**: Optimized for real-time data streaming and processing.
- **Durability**: Persistent message storage ensures data integrity and reliability.

## Architecture Overview
Kafka's architecture is built around three core components:

### 1. Producers
Producers are responsible for publishing data to Kafka topics. Messages sent by producers are distributed across partitions within a topic, ensuring load balancing and scalability.

### 2. Brokers
Brokers are Kafka servers that store and manage topics. They handle producer requests, store messages in partitions, and serve consumer read requests. Brokers work collectively to distribute workload efficiently.

### 3. Consumers
Consumers subscribe to topics and retrieve messages from Kafka brokers. They can be grouped into **consumer groups**, allowing parallel processing and efficient load distribution.

## Installation Guide
To install Kafka, ensure you have **Java 8 or later** installed on your system.

1. Download the latest version of Kafka from the [Apache Kafka website](https://kafka.apache.org/downloads).
2. Extract the downloaded package.
3. Navigate to the Kafka directory.

## Getting Started with Kafka
Once installed, you can start a single Kafka broker instance and test its functionality.

### 1. Start the Kafka Broker
Execute the following command to launch a Kafka broker using the default configuration:
```sh
bin/kafka-server-start.sh config/server.properties
```

### 2. Create a Kafka Topic
Run the following command to create a new topic named `my-topic`:
```sh
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic my-topic
```
This creates a topic with a single partition and a replication factor of 1.

### 3. Produce Messages
Start a Kafka producer to send messages to `my-topic`:
```sh
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic my-topic
```
You can now type messages into the console, which will be sent to the Kafka topic.

### 4. Consume Messages
Start a Kafka consumer to read messages from `my-topic`:
```sh
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic my-topic --from-beginning
```
This command displays all messages that have been published to the topic.

## Conclusion
Apache Kafka is a robust platform for building scalable, high-performance data pipelines and real-time streaming applications. Its ability to handle large-scale event-driven architectures makes it an essential tool for modern data-driven enterprises.

---

### 📌 Additional Resources
- [Official Kafka Documentation](https://kafka.apache.org/documentation/)
- [Kafka GitHub Repository](https://github.com/apache/kafka)
- [Kafka Tutorials & Guides](https://kafka.apache.org/documentation/#gettingStarted)



