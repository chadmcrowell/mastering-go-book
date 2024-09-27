# Chapter 3 - [Mastering Go Book](https://packt.link/rUETq)

## Synopsis of Chapter 3: Composite Data Types

Chapter 3 focuses on **composite data types**, such as **maps**, **structs**, and **regular expressions**, which allow developers to work with more complex data structures and perform pattern matching. The chapter emphasizes how these data types enhance Go’s ability to manage and manipulate data efficiently.

### **Maps in Go**

The chapter begins with an in-depth look at **maps**, a key-value data structure that allows efficient lookups. Maps are highly flexible and are often used when data needs to be stored and retrieved based on keys. The chapter explains how to declare and initialize maps, perform operations like adding, updating, and deleting key-value pairs, and handle cases where a key does not exist in the map. Go’s `comma ok` idiom, which allows you to check if a key exists in the map, is also covered. 

The chapter also addresses potential pitfalls, such as storing values in an uninitialized (nil) map, which can cause runtime panics. Iterating over a map using Go’s `for range` loop is discussed, showing how you can retrieve keys and values.

### **Structs in Go**

The next major focus is on **structs**, Go’s mechanism for grouping data into a composite type. Structs are similar to objects in other languages but are more lightweight and lack object-oriented features like inheritance. The chapter explains how to define and initialize structs, access fields, and how to embed one struct inside another for composition. 

An important concept covered is the use of the **`type` keyword**, which allows developers to define new data types, including struct types, and create methods associated with them. Go’s struct system also supports anonymous fields, where fields can be embedded directly without explicit names, leading to more flexible data structures.

The chapter highlights the distinction between **value types** and **pointer types** for structs, explaining how Go handles memory and how to work with pointers effectively when passing structs to functions. Using the `new` keyword for creating pointers to structs is also discussed, emphasizing Go’s efficient memory management.

### **Regular Expressions and Pattern Matching**

The chapter then moves to **regular expressions**, a powerful tool for pattern matching within text. Go’s `regexp` package is introduced, which supports both `regexp.Compile` for safe compilation of regular expressions and `regexp.MustCompile`, which panics if the expression is invalid. The chapter demonstrates how to use regular expressions to search for patterns in strings, extract specific data, and validate inputs such as email addresses or phone numbers.

Several examples of using regular expressions to match different types of data are provided, from simple string matches to more complex use cases like matching names, surnames, and integers. Go’s use of **raw string literals** for regular expressions, which simplifies working with escape characters, is also covered.

### **CSV Files and Data Persistence**

The chapter finishes by extending the statistics application introduced in earlier chapters. It demonstrates how to add **data persistence** by storing data in CSV files. The `encoding/csv` package is introduced, which allows developers to read from and write to CSV files easily. The chapter explains how to open, read, write, and handle errors while working with CSV data, making it practical for applications that require lightweight data storage.

The updated statistics application now includes the ability to store and retrieve data from CSV files, demonstrating a real-world application of the composite data types discussed throughout the chapter.