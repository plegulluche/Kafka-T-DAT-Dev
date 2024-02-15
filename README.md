# Usefull commands

- **see a list of all topics :**

#### using docker :

docker run --network=host --rm confluentinc/cp-kafka kafka-topics --bootstrap-server localhost:9092 --list

#### using kafka :

kafka-topics --bootstrap-server localhost:9092 --list

- **see approximate number of messages in a topic  :**
  Getting the exact number of messages in a Kafka topic can be complex due to Kafka's distributed nature and how it handles message offsets. However, you can get an approximation of the number of messages in a topic by checking the offsets.

Use the kafka-run-class command with kafka.tools.GetOffsetShell to get the earliest and latest offsets for each partition of a topic, which can help you estimate the number of messages.

#### using docker :

docker run --network=host --rm confluentinc/cp-kafka kafka-run-class kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic your-topic-name --time -1

#### using kafka :

kafka-run-class kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic your-topic-name --time -1
