Kafka Notification System
This project demonstrates a real-time notification system using Kafka, Golang, and Gin framework. The system consists of a producer and consumer for sending and retrieving notifications between users. The producer publishes notifications to a Kafka topic, and the consumer reads and stores these notifications for retrieval via an API.

Features
Real-time Notifications: Users can send notifications to each other.
Kafka Integration: The project uses Kafka for message brokering to ensure reliable communication between the producer and consumer.
REST API: Exposes endpoints to send and retrieve notifications.
Example Users: Sample user data is provided for testing purposes.
Setup Instructions
Start the Kafka Server: Ensure Kafka is running locally on port 9092.
Run the Producer:
sh
Copy code
go run cmd/producer/producer.go
Run the Consumer:
sh
Copy code
go run cmd/consumer/consumer.go
API Endpoints
Send a Notification
To send a notification from one user to another, use the following curl command:

sh
Copy code
curl -X POST http://localhost:8080/send \
-d "fromID=2&toID=1&message=Bruno started following you."
Retrieve Notifications
To retrieve notifications for a specific user, use:

sh
Copy code
curl http://localhost:8081/notifications/1
Sample JSON Response
json
Copy code
{
    "notifications": [
        {
            "from": {"id": 2, "name": "Bruno"},
            "to": {"id": 1, "name": "Emma"},
            "message": "Bruno started following you."
        }
    ]
}
In this response:

from: Contains the user ID and name of the sender.
to: Contains the user ID and name of the recipient.
message: Shows the notification message.
Project Structure
Producer: Publishes notifications to the Kafka topic.
Consumer: Consumes messages from the Kafka topic, stores them, and serves them via an API.
Models: Contains data structures, such as User and Notification.
Tech Stack
Golang: Used for backend services.
Kafka: Handles messaging between producer and consumer.
Gin: Web framework for building the REST API.
