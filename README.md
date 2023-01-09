# About this Project : 

Here is the architecture of the project : 
![Ar](https://user-images.githubusercontent.com/47195793/198752037-c13b6bc6-6594-4b97-89e3-dd4774dabbc6.JPG)

# Meetup RSVP Stream Kafka Producer

This project streams data from the [Meetup RSVP Stream API](https://www.meetup.com/meetup_api/docs/stream/2/rsvps/) and sends it to a Kafka topic using a Kafka producer.

The Kafka producer code is implemented in `kafka_producer.py`. It starts by importing the required libraries and defining some constants, such as the URL of the Meetup RSVP Stream API and the name of the Kafka topic to which the data will be sent.

The producer is created using the `KafkaProducer` class, which is configured with the address of the Kafka broker and a value serializer function that converts the data to a format that Kafka can understand.

The producer then enters an infinite loop, in which it makes a GET request to the Meetup RSVP Stream API and iterates over the received messages. For each message, it converts it to a Python dictionary using `json.loads`, prints it to the console, and sends it to the Kafka topic using the `send` method of the `KafkaProducer` object. If an exception occurs during the request to the Meetup Stream API, a message is printed to the console indicating that the connection could not be established.

## Prerequisites

- Python 3.6 or later
- Kafka 2.6 or later

## Components

The project consists of a single Python script, `kafka_producer_demo.py`, which contains the Kafka producer code.

## Setup and installation

1. Install Kafka on your machine. See the [Kafka documentation](https://kafka.apache.org/quickstart) for instructions.
2. Start the Kafka broker by running `bin/kafka-server-start.sh config/server.properties` in the Kafka installation directory.
3. Clone or download this repository.
4. Install the required Python packages by running `pip install -r requirements.txt`.

## Usage

To run the Kafka producer, use the following command:
`python kafka_producer.py`


The producer will start streaming data from the Meetup RSVP Stream API and sending it to the Kafka topic specified in the `kafka_topic_name` variable.

## Documentation and resources

- [Meetup RSVP Stream API documentation](https://www.meetup.com/api/general)
- [Kafka documentation](https://kafka.apache.org/documentation/)

