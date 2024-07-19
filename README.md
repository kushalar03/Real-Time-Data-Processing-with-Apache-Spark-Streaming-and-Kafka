Real-time data processing pipeline using Apache Spark Streaming and Kafka. The pipeline involves consuming data from Kafka topics and performing windowed computations on the streaming data.
The dataset "Heart rate time series / MIT-BIH Database" is sourced from the MIT-BIH Database Distribution.
This dataset contains evenly-spaced measurements of instantaneous heart rate from 4 people.
Kafka and Spark are utilized for stream processing, where data from a CSV file serves as the input for a Kafka producer. Each column in the CSV file corresponds to a distinct Kafka topic, resulting in three topics named topic1, topic2, and topic3, respectively. Subsequently, three consumers are employed to receive data relevant to the topic they are subscribed to.

In the consumer file, a Spark session is established to facilitate the processing of the received data using Spark Streaming. Consumer1, subscribed to topic1, calculates the maximum heart rate observed for a person. Consumer2, assigned to topic2, determines the count of occurrences where the heart rate exceeds 90 beats per minute. Finally, the consumer dedicated to topic3 computes the minimum heart rate recorded.

Spark Version 3.5.1
Kafka Version 3.6.25

Steps to run
1. Install Spark
2. Install Kafka
3. Start Kafka
4. Start producer
   python3 producer.py
6. Start Consumers
   python3 consumer1.py topic1 topic2 topic3
   python3 consumer2.py topic1 topic2 topic3
   python3 consumer3.py topic1 topic2 topic3
   
