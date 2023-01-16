
# Which are the parts of a Service
#Theory/Networks 

```ad-info
A Service is a set of actions that a service provider performs on a request of a service consumer
```
In programming a service provider is called ==server== and a service consumer is called a ==client==.
The set of operations available in a request from the client is called a ==service contract==. The conceptual view of such is:
![[Pasted image 20221229194118.png]]
# Conceptualizing a Network Service
There are 3 main way s of conceptualizing a network service varying the functionality of such and using different technologies.
## Set of Related Operations
This is the most common case, in fact it was shown as an example. This is seen as a way of communicating regarding a common domain problem.
![[Pasted image 20221229194118.png]]
## Set of Document Exchanges
As the name itself explains this service understanding it's found mostly in document centric systems.
![[Pasted image 20221229194731.png]]
## Set of Resources
This understanding is more kind of a mix between the two original ones. It's mostly found in the  RESTfull services.
![[Pasted image 20221229195022.png]]
# How services communicate
Services communicate using Communication channels, that is the communication between remote components. In **Network Services** context it can be abstracted as
![[Pasted image 20221229195216.png]]
Where this properties are:
- **Protocol:** Defines the features and limitations of the CommChannel
- **Bandwith:** This limits the amount of data that can be shared in one unit of time
- **Latency:** This limits the amount of synchronous req-res pairs transferable through communication.
- **Interruptability:** Decides whether the loss of data is an error or a normal part of the process