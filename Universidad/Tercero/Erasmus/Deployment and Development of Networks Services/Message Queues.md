#Theory/Networks 
A _message_ is simply a piece of data produced by some _message producer_ and intended to be consumed by some _message consumer_. 

A ==message queue ==is as itself s written a FIFO queue, from producters to consumers. The message queues are stored in servers called ==message brokers==. Both producers and consumers connect to this server to access the different message queues. Sometimes message brokers can work together to help with high availability systems.

==Message queues== can be broadcasting or not. In non braodcasting the messages are created and sent to only one consumer. Whereas in the broadcasting all the messages are sent to all the consumers. Bradcasting MQ can be done by unifying a system of non broadcasting MQs

MQs can be durable or non durable. Which means whether the MQ exists even when there are non consumers or producers, or not.

In some cases the MQ uses exchanges with routers that allow communication accesing those routes.

