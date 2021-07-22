
Java 8
Kafka
MongoDB
Java compatible IDE

__Environment Setup__


To get help with Kafka setup visit https://kafka.apache.org/quickstart

For mongo setup , refer to https://docs.mongodb.com/manual/installation/


___Kafka Setup:___

Start Zookeeper and Kafka Broker server. If you are using service offering from your enterprise, make sure you are connected to the appropriate instances.
Create a topic named ‘rsvpTopic’ on your kafka cluster. (following command for local zookeeper and kafka broker)
./bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic rsvpTopic

___Mongo Setup___
* Creat a mongo database named 'rsvpDB' and create ‘capped’ collection named ‘meetups’ in  rsvpDB.


It consists of three projects.


__CollectSendToKafka:__
This program acts as a collector. It reads the input stream from the MeetupRSVP and send it to Kafka.

__SparkKafkaToMongo:__
Reads the message from Kafka queue, processes it and inserts the final output in to MongoDB.

__MongoReactiveWebSSE:__
It consists of a web page that uses a server sent event to display contents of MongoDB on MAP UI as they become available.

