#Theory/Networks 
# Introduction to Web Services
A **web service** is any kind of service which is based on open commnuication protocls and open data encoding formats. It is also required that data is encoded in human readable format

# RESTfull Web Services
RESTfull web services are web services built by using HTTP protocol and _REST principles_. They have a minimal ammount of principles which will be seen in this unit:
1. The message must have the HTTP Structure
	1. Translating to http://server/service/operationX calls
	2. They can have CRUD operators such as POST,GET,UPDATE...
2. All the data encoded must have a readable format
	1. For this there are two main options, XML and JSON
	2. Currently JSON is the most common as it's the simplest
3. HTTP request should be according to their naming
4. If possible, the web service should be statless in client, (Base pilar of  REST)

# GRPC
is a version of web services that can often be encountered in environments where it is desirable to have something similar to RESTfull web services, but OpenAPI related libraries and tools are either unavailable or seen as too heavy.

Main difference from standart modern RESTfull web services is in the message encoding format and lack of integrated documentation support. ==GRPC is however widely supported and is suitable for interaction with low resource devices.==