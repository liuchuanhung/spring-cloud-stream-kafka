#Spring Cloud Stream Publisher
###Spring Cloud Stream
- This is a Spring framework that enables application developers to write event-driven applications that use the strong foundations of Spring Boot and Spring Integration.
- The underpinning of all these is the binder implementation, which is responsible for communication between the application and the message broker.
- These binders are "MessageChannel"-based implementation.

###Apache Kafka
- This is an open-source distributed even streaming platform used by thousands o companies for high-performance data pipelines, streaming analytics, data integration, and mission-critical applications.

###Zookeeper
- This is an important part of Apache Kafka.  Zookeeper is a cornerstone for so many distributed applications, as it provides fantastic features.
- Zookeeper is used by Kafka to store information regarding the Kafka cluster, as well as user info, in short, we can say Zookeeper store metadata about the kafka cluster.

###How to Run
1. start ZooKeeper server locally from Command Prompt (not Git Bash)
    - *..bin\windows>zookeeper-server-start.bat ..\..\config\zookeeper.properties*
2. start Kafka server locally from Command Prompt (not Git Bash)
    - *..bin\windows>kafka-server-start.bat ..\..\config\server.properties*
3. create Topic
    - *..bin\windows>kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 -topic dummytopic*
4. list all available topics
    - *..bin\windows>kafka-topics.bat --list --zookeeper localhost:2181*
5. Start Spring-Cloud-Stream-Publisher producer microservice
6. Start Spring-Cloud-Stream-Consumer microservice
7. Open up Postman, and hit the /publish endpoint in the producer
    - *POST: http://localhost:8080/publish BODY: {"id":1, "name": "dummy"}*