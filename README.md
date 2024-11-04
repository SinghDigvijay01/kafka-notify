# Kafka Notify : Real-Time Notification System

This project is a simple real-time notification system built with **Go**, **Kafka**, and **Gin**. It demonstrates how to send, consume, and retrieve notifications between users using a Kafka producer and consumer architecture.

## Project Overview

This system includes two main components:

1. **Producer** - Sends notifications from one user to another using Kafka.
2. **Consumer** - Listens for notifications, stores them, and provides an API to retrieve notifications for a specific user.

## Technologies Used
- **Go (Golang)**: Main language for building the producer and consumer.
- **Apache Kafka**: Message broker to handle real-time data streaming.
- **Gin**: HTTP web framework for handling requests.
- **Sarama**: Go library for Kafka integration.

## Getting Started

### Prerequisites
- Go (v1.19+)
- Kafka Server running locally on port `9092`
- Gin (for HTTP routing)
- Sarama (Kafka client for Go)

### Running the Project

1. **Clone the Repository**

   ```bash
   git clone https://github.com/SinghDigvijay01/kafka-notify.git
   
2. **Start the Producer**

   Open a terminal, navigate to the `kafka-notify` directory, and run:
   ```bash
   go run cmd/producer/producer.go

3. **Start the Consumer**

   Open a terminal, navigate to the `kafka-notify` directory, and run:
   ```bash
   go run cmd/consumer/consumer.go

4. **Send a Notification**
   
   ```bash
   curl -X POST http://localhost:8080/send \
   -d "fromID=2&toID=1&message=Bruno started following you."
   
5. **Retrieve Notifications**
   
   ```bash
   curl http://localhost:8081/notifications/1
