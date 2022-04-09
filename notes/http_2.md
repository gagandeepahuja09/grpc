* HTTP/2 is what makes gRPC efficient.
* https://developers.google.com/web/fundamentals/performance/http2
* gRPC uses HTTP/2 as its transfer protocol.
* Binary framing layer:
    * More performant, robust.
    * Lighter to transport, safer to decode.
    * Great combo with protobufs.

* HTTP/2 features
    * One TCP connection.
    * Request -> stream
        * Streams are multiplexed.
        * Streams are prioritized.
    * Binary framing layer.
        * Prioritization
        * Flow control
        * Server push

* Binary framing: 
    * HTTP messages are decomposed into one of more frames(how does this help?):
        HEADER for meta-data, DATA for payload, RST_STREAM to cancel, SETTINGS, PRIORITY.
    * Each frame has a common header
        * 9-byte, length prefixed
        * Easy and efficient to parse

* HPACK header compression
    * There is a static + dynamic table from which values are optionally indexed.
        eg "METHOD: GET" ==> 2
        "user-agent: Mozilla/5.0" ==> 62
    * Literal values are optionally encoded with static huffman encoding.

* Multiplexing
    * Send multiple requests and response in parallel over a single TCP connection.

* Server push
    * One client request, multiple responses.
    * Reduce round-trip latency.


* How HTTP/2 works under the hood.
    * Single TCP connection carries multiple bidirectional streams.
    * Each stream has a unique ID and carries multiple birectional messages.
    * Each message(request / response) is broken down into multiple binary frames.
    * Frame is the smallest unit that carries different type of data: HEADERS, SETTINGS, PRIORITY, DATA, etc.
    * Frames from different streams are interleaved and then reassembled on the other side.


* HTTP 2 vs HTTP 1.1
* Transfer protocol: 2 Binary, 1.1 Text
* Headers: 2 Compressed, 1.1 Plain text
* Multiplexing: 2 Yes, 1.1 No
* Requests per connection: 2 Muliple, 1.1 Only one(We'll need to create multiple separate TCP connections to send multiple requests).
* Server push: 2 Yes, 1.1 No