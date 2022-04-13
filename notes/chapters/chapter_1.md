Limitations of RESTful services that hinders them to be used as the messaging protocol for modern microservices-based applications:

Inefficient text-based message protocols
* HTTP 1.x are text-based protocols. They leverage human-readable textual formats such as JSON.
* This is very inefficient for service based communications as both the parties don't need to read a human-readable format.
* This leads to unnecessary conversion: binary -> text -> binary.

Lacks strongly typed interfaces between apps
* OpenAPI/Swagger are only afterthoughts and not tightly integrated with the messaging protocol.
* No framework that generates the core of server and client-side code for polyglot technologies. 

REST Architectural style is hard to enforce
* REST has a lot of "good practices" to be followed. But these aren't enforced.
* Dev teams have to spend a lot of time maintaining the consistency and purity of a RESTful service.

************************************************************************************

Advantages of gRPC

* Efficient for inter-process communication
    * Protocol buffer based binary protocol.
    * HTTP/2.
* 