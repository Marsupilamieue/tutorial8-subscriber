- what is amqp?
    - AMQP stands for Advanced Message Queuing Protocol. It is an open standard application layer protocol for message-oriented middleware, designed for exchanging messages between applications or services in a distributed system. AMQP enables communication between systems that can be decoupled, flexible, and scalable.

- what it means? guest:guest@localhost:5672 , what is the first quest, and what is the second guest, and what is localhost:5672 is for? 

    - "guest" is the username.
        "guest" (again) is the password.
        "localhost:5672" refers to the hostname and port number.
        In this configuration:

        "guest" is the default username and password often used for testing or initial setup purposes in AMQP brokers like RabbitMQ.
        "localhost" refers to the local machine, indicating that the AMQP broker is running on the same machine as the client.
        "5672" is the default port number for AMQP communication.
        So, "guest:guest@localhost:5672" represents the credentials (username and password) used to connect to the local AMQP broker running on port 5672.

![Slow Subscirber](/assets/slowsubs.png)

In the queue message graph, there were approximately 35 messages queued. This occurs due to the subscriber requiring more time to process each event in the message queue. Consequently, a backlog of messages accumulates because the publisher can publish messages faster than the subscriber can handle them.

- First subscriber 
![1](/assets/1.png)
- Second subscriber
![2](/assets/2.png)
- Third subscriber
![3](/assets/3.png)
![rabbit](/assets/rabbitmq.png)

The sudden increase in the message queue probably because we added a sleep function (thread::sleep(ten_millis);) in the subscriber's main.rs file. This function waits for 1000 milliseconds (1 second) before printing each message. So, messages get more time to be handled one after the other, which helps clear out the backlog in the queue.

My suggestion is to apply an asynchronous processing
