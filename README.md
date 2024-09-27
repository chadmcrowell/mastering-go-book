# mastering-go-book
Notes from the [Mastering Go Book](https://packt.link/rUETq)

1. **[CHAPTER 1](chapter1/README.md): A Quick Introduction to Go**
   - Implement the basic "Hello World" program.
   - Develop a utility to print statistics from user input.

2. **[CHAPTER 2](chapter2/README.md): Basic Go Data Types**
   - Write code to demonstrate how slices are connected to arrays.
   - Implement a Go program that catches out-of-bounds errors.
   - Write a program that generates random numbers and strings.

3. **[CHAPTER 3](chapter3/README.md): Composite Data Types**
   - Create a map and iterate over it.
   - Use regular expressions to match patterns in text files.
   - Extend a CSV file processing program with additional functionalities.

4. **[CHAPTER 4](chapter4/README.md): Go Generics**
   - Develop a function using Go generics that works with slices of any type.
   - Create constraints for a custom data type and apply them to a generic function.

5. **[CHAPTER 5](chapter5/README.md): Reflection and Interfaces**
   - Create a slice of structures, sort them based on a specific field.
   - Use the empty interface and define functions that differentiate between different structures.

6. **[CHAPTER 6](chapter6/README.md): Go Packages and Functions**
   - Develop a Go package and use it to interact with SQLite databases.
   - Implement variadic functions and write test cases for them.

7. **[CHAPTER 7](chapter7/README.md): Telling a UNIX System What to Do**
   - Write a program that reads text files character by character.
   - Create a command-line utility that works with JSON configurations.

8. **[CHAPTER 8](chapter8/README.md): Go Concurrency**
   - Develop a program that creates multiple goroutines and ensures they complete before proceeding.
   - Implement worker pools using channels.

9. **[CHAPTER 9](chapter9/README.md): Building Web Services**
   - Write a simple web server using the `net/http` package.
   - Develop a REST client that communicates with a REST API.

10. **[CHAPTER 10](chapter10/README.md): Working with TCP/IP and WebSocket**
    - Build both a TCP and UDP client and server using Go's networking libraries.
    - Implement a WebSocket server and client.

11. **[CHAPTER 11](chapter11/README.md): Working with REST APIs**
    - Create a REST API server with multiple endpoints and test it using Go's testing package.

12. **[CHAPTER 12](chapter12/README.md): Code Testing and Profiling**
    - Write table-driven tests for various Go functions.
    - Profile an HTTP server and optimize it for performance.

13. **[CHAPTER 13](chapter13/README.md): Fuzz Testing and Observability**
    - Implement fuzz testing for a sample Go function.
    - Create metrics for a Go server and expose them to Prometheus.

14. **[CHAPTER 14](chapter14/README.md): Efficiency and Performance**
    - Create a function that copies binary files, benchmark different implementations to find the fastest one.

15. **[CHAPTER 15](chapter15/README.md): Changes in Recent Go Versions**
    - Experiment with the new features introduced in Go 1.21 and 1.22, such as `sync.OnceFunc()`.

16. **[APPENDIX](Appendix/README.md): The Go Garbage Collector**
    - Several important features that make Garbage collection efficient and reliable.
    - A detailed explanation of the **tri-color algorithm**.
    - How Go’s GC interacts with **maps** and **slices**.