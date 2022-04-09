4 Types of gRPC

* Unary
* Client streaming => Client sends stream of messages and expects server to send only a single response.
* Server streaming
* Bidirectional streaming

gRPC vs REST
* gRPC much faster with HTTP/2.
* It uses protobuf which is binary and much smaller.
* The API contract is strict and required to be present in the proto file.
* Code generation is built-in in grpc using protoc.
* gPRC supports bidirectional streaming while REST has client -> server request only.
* In terms of securing, both gRPC and REST support TLS/SSL. 
* REST is better in terms of browser support. It is supported in all browsers. gRPC requires a proxy layer gRPC-web to convert b/w HTTP/1 and HTTP/2.

Where is gRPC well suited for?
* Microservices
    * Low latency and high throughput communication.
    * Strong API contract.
* Polyglot environments: Code generation out of the box.
* Point-to-point realtime communication. Excellent support for bidirectional streaming.
* Network constrained environments. Eg. mobile apps.
    * Lightweight message format.