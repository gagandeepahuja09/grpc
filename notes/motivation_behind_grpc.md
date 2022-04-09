Communication between different languages
* BE, FE ==> Different languages.
* Microservices ==> Different languages.
* They must agree on the API contracts to exchange information:
    * Communication channel: REST, SOAP, message queue.
    * Auth mechanism: Basic, oAuth, JWT.
    * Payload format: JSON, XML, binary.
    * Data model.
    * Error handling.

Communication should be efficient
    * Huge amount of exchange between microservices.
    * Mobile network can be slow with limited bandwidth.

Communication should be simple
    * Client & server should focus on the core logic.
    * Everything else handled by the framework.
