#Theory/Networks 

# What is an RPC
```ad-tldr
RPC(Remote Procedure Call) is a generic name for the mechanisms that allow the client call functions in the remote server by using the same set as the ones existing in local operations
```

To be more specific this is how the RPC conceptual model would look like, eventough from actual implementations this could change.
![[Pasted image 20221230123136.png]]

# How do RPC communicate
RPC mostly communicates with network sockets in modern systems, with the following general schema.

```ad-note
A **network socket** is a software structure within a network node of a computer network that serves as an endpoint for sending and receiving data across the network.
```

![[Pasted image 20221230123423.png]]

This communication sometimes can be too complicated to do it in a sequential mode, therefore RPC can be implemented to avoid synchronous work in [[RPC multhreaded]]

# Patterns of Service Provisioning
There are three main patterns for service provisioning in RPC
- Singleton
- Instance per Request
- Instance per Request per Client Session
Note that this can hae different names depending on the frameworks. It is just needed one of the patterns to implement the other three, however not all RPCs will include the three of them.

## Singleton pattern
**SIngleton**  means that all the client operations will be the same no matter which client it is. They all have a unified set of operations. This is multithreaded but must add some synchronous streategies when dealing in server side.

The **singleton** can be translated into **instance-per-request** by creating and using a new instance of service logic and related state inside every service operation.

The **singleton** can be translated into **instance-per-client-session** by adding special service operations to use tokens for each client. Such as create token, check token, and end token session.
## Instance per Request pattern
In **Instance per Request** an instance is created for every client operation call, then theoperation is runed and after the instance is automatically discarded. This action provokes that there are no states shared between client invocations, therefore accesing shared instances must be synchronized

To transform it to **singleton** we just have to hold the service instead of destroying it every time. And for **instance per request per client session** we use the tokens in a way that a token refers to a specific state operation.

## Instance per Request per Client Session
In this case each client has a separate service instance wich is automatically created and disconnected when the client is ending the usage. In this case there are no shared states between clients so to access shared resources syncronous actions must be made by the server. When this pattern is chosen RPC must have multithreading or limitations of usage around the operation calls.

There is no need to explain how to transform from this to the others as it is exactly the inverse way of how it was said before.