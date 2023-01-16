#Theory/Networks 
# What is a transaction
A transaction  is a process which can be done or fully undone, no way in the middle. A transaction has the following 4 states:
- running
- completed
- commited: complete transaction preserves the result made by the transaction
- rolled back: The sytem undoes the progress and loads as it was before calling it

The transactions must follow ==**ACID**==(atomicity,consistency,isolation and durability) properties

# Distributed transactions
A _distributed transaction_ is a transaction that is performed across several components interacting over computer network. A component that initiates a transaction is called _coordinator_, other components are called _participants_. A transaction manager runs either inside a coordinator or as an independent piece of middleware.

The distributed transactions have som elimitations and a model of two general problems is applied. However no errors can be suppresed they can only be lowered their probability.

There are cases where distributed transactions cannot be implemented, therefore they create a pseudo distributed transaction In these cases,it might be solved by using _undo-list_. An undo list is simply a list that stores a sequence of actions executed, where each action is paired with a corresponding reverting action. In order to this the actions must be reversible
## Protocols and Algorithms
There are lots of frameworks and protocols for distributed transactions such as XA. It is desirable that the portocols tend to be the same else in a heterogeneus system it's going to provoke many problems as managers will need lots of adaptations. Right now the most used protocol is the two phase commit. A widely implementation algorithm of this is the PAXOS algorithm.

Two phase commit algorithm becomes unreliable if any of transaction participants or coordinator or communication channel between participants and coordinator are unreliable. There is a _three phase commit_ algorithm that add timeouts to coordinator-participant interactions. Depending on which step the participant is in, a communications timeout is assumed to indicate either success or failure of an overall transaction. 

