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
* Well-defined service interfaces and schema
    * Contract-first approach
    * First define the service interfaces and then work on the implementation details afterward.
* Strongly typed
    * Clearly defines the types that will be used for communication between applications.
    * Helps to overcome most of the runtime and interoperability errors.
* Polyglot + Automatic code generation
* Duplex streaming
    * Client-side, server-side, bidirectional streaming.
* Built-in commodity features
    * Authentication
    * Encryption
    * Resiliency(deadlines and timeouts)
    * Metadata exchange
    * Compression
    * Load balancing
    * Service discovery
* Integration with cloud native ecosystems
    * Part of CNCF.
    * Many projects under CNCF use it as a communication protocol.(eg Envoy)
    * Cross-cutting of features. Eg. using Prometheus to monitor gRPC applications.

Disadvantages of gRPC
* May not be suitable for external-facing services.
    * Contract-driven, strongly typed may hinder the flexibility of the services that we expose to the external parties.
    * gRPC gateway is designed to overcome this.
* Ecosystem relatively small compared to REST.

************************************************************************************

gRPC vs Other Protocols

Apache Thrift
* Developed by Facebook.
* gRPC is more opinionated that Thrift and offers first-class support for HTTP/2.
* gRPC natively supports bidirectional streaming.
* gRPC has built a good ecosystem around CNCF projects.
    * Multiple resources like good documentation, external presentations & sample use cases.

GraphQL
* Allows clients to determine what data they want, how they want it and in what format.
* Hence more suitable for user-facing applications where the clients need more control over the data they want to consume from the server.
* Eg. Need only specific information about the products but not the entire set of attributes of a product.

* Do check the courier article: gRPC-based RPC framework: https://dropbox.tech/infrastructure/courier-dropbox-migration-to-grpc

