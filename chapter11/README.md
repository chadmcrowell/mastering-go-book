# Chapter 11 - [Mastering Go Book](https://packt.link/rUETq)

## Synopsis of Chapter 11: Working with REST APIs

Chapter 11 focuses on **building and consuming REST APIs** using Go. RESTful APIs have become a fundamental part of modern web development, enabling applications to communicate over HTTP using standard methods like GET, POST, PUT, and DELETE. This chapter covers how to create REST APIs in Go and how to interact with external APIs, offering practical examples and best practices for API development.

### **REST API Basics**

The chapter starts by explaining the fundamentals of **REST (Representational State Transfer)** architecture. REST is a stateless, client-server protocol that uses HTTP for communication, where resources are identified by URLs and manipulated using HTTP methods. REST APIs are widely used in web and mobile applications to expose data and services over the web.

Go’s standard `net/http` package is introduced as the core tool for building REST APIs. This package simplifies the process of setting up an HTTP server, handling routes, and responding to client requests, making it a powerful yet lightweight choice for API development.

### **Setting Up a RESTful API**

The first example in the chapter demonstrates how to build a basic RESTful API in Go. A simple web server is set up using the `http.HandleFunc()` function, which maps URL paths to handler functions. The handler functions implement the standard HTTP methods (GET, POST, PUT, DELETE) to perform CRUD (Create, Read, Update, Delete) operations on a resource, such as a list of users or items.

Here’s an example of setting up a basic API that handles GET and POST requests:

```go
http.HandleFunc("/users", func(w http.ResponseWriter, r *http.Request) {
    switch r.Method {
    case "GET":
        // Handle GET request (retrieve users)
    case "POST":
        // Handle POST request (create new user)
    default:
        w.WriteHeader(http.StatusMethodNotAllowed)
    }
})
```

In this example, the server distinguishes between HTTP methods to perform different actions. It responds with a **status code** based on the outcome of the request, which is a critical part of REST API design.

### **Handling JSON Data**

Working with **JSON** is an integral part of building REST APIs, as JSON is the most commonly used format for data exchange over the web. The chapter explains how to serialize Go data structures into JSON using the `json.Marshal()` function and deserialize JSON into Go structs using `json.Unmarshal()`.

Practical examples show how to read incoming JSON data from client requests and send JSON responses back. Error handling for JSON parsing is emphasized, ensuring that invalid data is handled gracefully. Here's an example of decoding a JSON request body:

```go
decoder := json.NewDecoder(r.Body)
var user User
err := decoder.Decode(&user)
if err != nil {
    http.Error(w, err.Error(), http.StatusBadRequest)
    return
}
```

This pattern is used for creating new resources, where the client sends JSON data in a POST request, and the server decodes it into a Go struct for further processing.

### **Routing and URL Parameters**

The chapter covers **routing** in greater detail, explaining how to extract parameters from URLs and query strings. For instance, when retrieving a specific user by ID, the API might use a route like `/users/{id}`, where `{id}` is a dynamic parameter. Go’s `http.ServeMux` or third-party routing libraries like `gorilla/mux` are introduced for handling more complex routing scenarios.

Using **query parameters** is another key topic, as many APIs allow filtering or sorting based on parameters passed in the URL. The chapter demonstrates how to retrieve and use these query parameters in Go to provide more flexible API endpoints.

### **Creating and Consuming External APIs**

In addition to building APIs, the chapter explores **consuming external APIs**. Go’s `net/http` package is also used for making HTTP requests to third-party services. Examples show how to send GET and POST requests, handle HTTP responses, and parse JSON data from external APIs. Here's how to make a simple GET request:

```go
resp, err := http.Get("https://api.example.com/users")
if err != nil {
    log.Fatal(err)
}
defer resp.Body.Close()

var users []User
json.NewDecoder(resp.Body).Decode(&users)
```

This process allows Go programs to integrate with external services, such as weather APIs, payment gateways, or social media platforms, enabling rich interactions between distributed systems.

### **Error Handling and Best Practices**

Error handling is a critical aspect of API development, and the chapter discusses how to return appropriate HTTP status codes and error messages based on the outcome of the client’s request. Best practices for designing REST APIs, including versioning, security (e.g., authentication and authorization), and documentation, are also emphasized.