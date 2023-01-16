#Theory/Networks 

# Types of Communication Channels
As mentioned in the past unit [[Integrated RPC]] the interaction is made with communication channels. In this unit the main types of communication channels will be discussed.
## Shared Memory
If there is some data that is desired to be used by two different processes this can be mapped into virtual addresses, this process is called **Shared Memory**. (It could be seen as an and operator) This technique itself could be used only in the same state machine however, using **distributed shared memory** implementations they can be solved.

The most common technique of such is **memory mapped files**, A file in this case serves as a backing storage (optionally) and as an address of connection point. In order to avoid completion problems,  a completion flag is created which needs to be verified.
## Files based message passing
File based message passing can be used to connect components running both on the same machine and on different machines. The components being connected must have read/write access to the same location in some _file system_.

File systems can be local and remote. Examples of remote file systems are: FTP (File Transfer Protocol), SFTP (SSH File Transfer Protocol)

It is quite important that this tecnique allows locking of files else the process becomes quite tedious, Here is an example of how it would look.
![[Pasted image 20221230184536.png]]


## Database based message passing
If the network has already a communicating database,  the message can be passed actually between components creating a communication channel,.

In relational databases, if message fits into a single database row and a single SQL statement is used to create it, this statement will be atomic. Howver in non-relational databses this should be checked in the documentation.

## Sockets
As mentioned in [[Integrated RPC]] this is the most common case in modern programming and It's found in RPC systems.

## Standard I/O Streams
A stream is a communication created between a client and a Server, it has the main three default streams, I/O and error as seen in the picture.
![[Pasted image 20221230185035.png]]
Note that this message raises an issue to treat wheter the message begins or ends. For that delimiters such as the length of the message or things like that should be raised 