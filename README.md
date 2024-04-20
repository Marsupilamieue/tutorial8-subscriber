a. what is amqp?
AMQP stands for Advanced Message Queuing Protocol. It is an open standard application layer protocol for message-oriented middleware, designed for exchanging messages between applications or services in a distributed system. AMQP enables communication between systems that can be decoupled, flexible, and scalable.

what it means? guest:guest@localhost:5672 , what is the first quest, and what is the second guest, and what is localhost:5672 is for? 

"guest" is the username.
"guest" (again) is the password.
"localhost:5672" refers to the hostname and port number.
In this configuration:

"guest" is the default username and password often used for testing or initial setup purposes in AMQP brokers like RabbitMQ.
"localhost" refers to the local machine, indicating that the AMQP broker is running on the same machine as the client.
"5672" is the default port number for AMQP communication.
So, "guest:guest@localhost:5672" represents the credentials (username and password) used to connect to the local AMQP broker running on port 5672.