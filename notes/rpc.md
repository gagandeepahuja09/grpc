* Protocol that allows a program to: 
    * Execute a procedure of another program located in another computer.
    * Without the dev explicitly coding the details of the remote interaction.
* The client and server can be written in different languages.
* In client code, it looks like we are just calling a function of the server code directly.

* How does the remote call happen? The client has a stub(automatically generated) that provides the same methods as the server.
* The stub/code are generated with the help of protocol buffer.