# Chapter 10 - [Mastering Go Book](https://packt.link/rUETq)

## Synopsis of Chapter 10: Working with TCP/IP and WebSocket

Chapter 10 delves into network programming, specifically focusing on **TCP/IP** and **WebSocket** communication. This chapter guides developers through the process of building low-level network applications using Go’s networking packages, emphasizing real-time communication and client-server architectures. By the end of the chapter, readers will understand how to establish reliable communication channels using both TCP and WebSocket protocols.

### **TCP/IP Fundamentals**

The chapter begins by explaining the basics of the **TCP/IP protocol**, which is the foundation of network communication. **TCP (Transmission Control Protocol)** provides reliable, ordered, and error-checked delivery of data between applications running on different hosts. Go, with its standard `net` package, simplifies working with TCP, making it straightforward to create both **TCP clients** and **servers**.

The chapter highlights how Go abstracts the complexities of low-level networking, allowing developers to focus on application logic. Readers are introduced to essential functions from the `net` package, such as `net.Listen()`, which sets up a TCP listener on a specific port, and `net.Dial()`, which connects a client to a server.

### **Building a TCP Server**

The first practical example demonstrates how to build a simple **TCP server** in Go. The server listens for incoming connections from clients, processes requests, and sends responses. The chapter explains how to accept multiple connections concurrently using **goroutines**, leveraging Go’s concurrency model for scalable server design.

Here is an example of creating a basic TCP server:

```go
listener, err := net.Listen("tcp", ":8080")
if err != nil {
    log.Fatal(err)
}
for {
    conn, err := listener.Accept()
    if err != nil {
        log.Fatal(err)
    }
    go handleConnection(conn) // Handle each connection in a goroutine
}
```

The server continuously listens for incoming connections, and once a connection is accepted, it spawns a new goroutine to handle the client, allowing the server to manage multiple clients simultaneously.

### **Creating a TCP Client**

The chapter then shows how to build a **TCP client** to connect to the server. The client initiates a connection to the server using `net.Dial()`, sends a request, and receives a response. The interaction between the client and server is based on simple message exchange, with the client sending requests and the server responding with data or acknowledgment.

The client example demonstrates how to write data to the server using `conn.Write()` and how to read the server’s response with `conn.Read()`. Error handling, connection management, and message formats are discussed to ensure robust communication.

### **WebSocket Communication**

After covering TCP, the chapter introduces **WebSocket**, a protocol that allows full-duplex communication between clients and servers over a single, long-lived connection. WebSockets are particularly useful for real-time applications like chat apps, gaming, or live data feeds, where bidirectional communication is needed.

The chapter explains how Go’s `gorilla/websocket` package can be used to create WebSocket clients and servers. WebSockets differ from traditional HTTP because they allow ongoing communication after the initial handshake, making them more suitable for real-time interactions.

The WebSocket server example starts by handling the **WebSocket handshake** and then continuously reading and writing messages between the client and server:

```go
ws, err := upgrader.Upgrade(w, r, nil)
if err != nil {
    log.Println("Upgrade error:", err)
    return
}
defer ws.Close()

for {
    _, message, err := ws.ReadMessage()
    if err != nil {
        log.Println("Read error:", err)
        break
    }
    log.Printf("Received: %s", message)
    err = ws.WriteMessage(websocket.TextMessage, message)
    if err != nil {
        log.Println("Write error:", err)
        break
    }
}
```

In this example, the server reads messages from the client and echoes them back, simulating a basic chat service. This demonstrates the real-time, bidirectional nature of WebSocket communication.

### **TCP vs. WebSocket**

The chapter compares **TCP** and **WebSocket**, explaining when to use each protocol. TCP is ideal for lower-level networking tasks, where you have control over message formats and delivery mechanisms. WebSockets, on the other hand, are better suited for real-time applications with rich client-server interaction, where continuous data exchange is necessary.

### **Practical Use Cases**

The chapter concludes with practical use cases for both TCP and WebSocket protocols, including building real-time chat applications, live notifications, and data streaming services. It emphasizes the importance of choosing the right protocol based on the application's requirements, such as latency, message size, and frequency of communication.