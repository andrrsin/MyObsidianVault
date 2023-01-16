#extra/Theory/Networks 
RPC can be multithreaded to avoid some synchronous work. Usually the server will do some background work which can allow to some problems. This is a activity diagram of a sequential RPC.
![[Pasted image 20221230124107.png]]

In order to avoid the beforehand mentioned problems, the background of the server can be moved to a separate thread and each request of a client can be separated to a thread based on a ==Thread pool==. In our activity diagram this pool is called Request Processor.

![[Pasted image 20221230124332.png]]
