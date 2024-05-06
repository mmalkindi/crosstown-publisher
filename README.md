# Tutorial 8 - Publisher

## Reflection

> How many data your publlsher program will send to the message broker in one run?  

A: Publisher sends data 5 times in one run as there are five invocation of `publish_event()`.
Every event is named `user_created`, with varying `user_id` and `user_name` on each invocation.

> The url of: `amqp://guest:guest@localhost:5672` is the same as in the subscriber program, what does it mean?

A: Publisher targets the same URL as the subscriber, which means it will be able to connect and communicate with each other.

Running RabbitMQ instance:  
![RabbitMQ first run](/img/rabbitmq_firstrun.png)

Sending event from Publisher to Subscriber:  
![Subscriber receiving from Publisher](img/publisher_subscriber_run.png)

Monitoring chart based on Publisher:  
![RabbitMQ monitoring](img/rabbitmq_monitor_run.png)

The spikes that happened in the chart above is caused by Publisher sending events into the queue.
One point of the chart is higher than the other because the Publisher is run repeatedly (thus queueing more events) in a short amount of time.
