# Introduction
#Theory/Networks 
Usually systems are desired to be escalated, there is a variety of ways to make the Throughoutput scalate and improve the numbers. In this unit we will revise 3 of them. Vertical, horizontal and Optimization.

# Optimization
This is the process of improving the current service in the algorithms or structures. Going directly were bottlenecks are to try to solve them and make them faster. Some techniques used usually are also Caching in memory some useful data. Perhaps changing the heuristics of the algorithm can also help. Some examples of configurable things are:
- Type and behavior of task scheduler.
- Various resource allocation quotas for processes.
- Behavior of strong random number generator.
- Behavior of networking layer. Especially for TCP/IP protocol.
- Behavior of virtual memory subsystem.

This optimization paths are usually more related to computer architecture. For example deciding which techniques to use to compile the programs or changing the behaviour of the garbage collector.

# Horizontal Scaling
This technique is really tight related to parallelism. Where the task will be done in a parallelistic way to make the program faster. This effects are directly related to **Amdhal's law** and to **Gustafson's law** This two laws defer from each other. The first one is based on parallelizing a task already existing and the other one is focused on parallelizing the pipelines.

There are techniques such as:
- Master/worker Threading
- Parallelism
- Thread pools

This in [[Web services, REST and GRPC]] is handy as it is stateless so they are easy to scalate. However if some information is needed a database should be added which creates a bottleneck that should be studied with optimization. A solution to this is creating replication of the original database but in a read-only way, working with replicas or with partition of the databases.

# Vertical Scaling
This scaling doesnt depend on the software, but changing the components and the hardware making the server and the clients faster. 