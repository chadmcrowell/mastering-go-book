# Chapter 7 - [Mastering Go Book](https://packt.link/rUETq)

## Synopsis of Chapter 7: Telling a UNIX System What to Do

Chapter 7 focuses on interacting with the **UNIX system**, specifically using Go to execute system commands, work with files, directories, and manage processes. This chapter demonstrates how Go can be leveraged for tasks traditionally performed by shell scripts, offering more flexibility and control with Go's type safety and concurrency model.

### **Executing Commands in Go**

The chapter starts by explaining how to use the `os/exec` package to execute external commands from a Go program. It introduces the **`exec.Command()`** function, which allows you to run any command that you would typically execute in the UNIX shell. The chapter provides examples where commands like `ls`, `cat`, and `grep` are executed directly from a Go program. This approach enables developers to integrate system utilities into their Go applications.

The chapter emphasizes handling output from these commands using `CombinedOutput()` and `Output()` methods, allowing the program to capture and process the results of the executed commands. It also discusses how to pass arguments to commands and how to handle errors if the command fails or returns non-zero exit codes.

### **Working with Files and Directories**

Next, the chapter dives into **file and directory manipulation**, one of the most common tasks in system programming. Go’s `os` and `io/ioutil` packages provide functions for interacting with the file system. The chapter explains how to create, read, write, and delete files using `os.Open()`, `os.Create()`, and `os.Remove()`.

Directory manipulation is covered in detail, with examples on how to create and remove directories using `os.Mkdir()` and `os.RemoveAll()`. Listing the contents of a directory is demonstrated using the `ioutil.ReadDir()` function, which returns the files and directories within a given directory path.

A special emphasis is placed on handling **file permissions**, as UNIX systems rely heavily on permission settings to secure files. The chapter explains how to use Go’s file mode constants (e.g., `os.FileMode`) to set and modify permissions when creating or modifying files and directories.

### **Pipes and Redirection**

The chapter also explains **pipes** and **I/O redirection**, which are fundamental concepts in UNIX-like systems. Pipes allow the output of one command to be used as the input of another command, enabling complex workflows. In Go, pipes are implemented using the `io.Pipe()` function.

The chapter demonstrates how to set up pipes between commands, allowing the output of one command to be passed directly to another without storing it in an intermediate file. This is useful for tasks such as chaining commands like `ls | grep`. It also covers redirecting input and output streams, showing how to redirect output to files using `os.Stdout` and `os.Stderr`.

### **Managing Processes**

The chapter moves on to process management, introducing Go’s capabilities to create and manage **child processes**. The `exec` package allows forking a new process using `Command()` and provides the ability to control process execution, wait for a process to finish, and capture exit codes. Examples are provided where Go creates child processes and synchronizes their execution with the main program.

A section on **signals** covers how to send and receive UNIX signals like `SIGINT` and `SIGKILL`, which are used to manage running processes. The chapter explains how Go’s `os.Signal` and `signal.Notify()` can be used to handle signals gracefully, ensuring that processes are terminated or restarted properly.

### **Environment Variables**

The chapter also touches on **environment variables**, which are a key part of UNIX system configuration. It shows how to access, modify, and set environment variables using `os.Getenv()`, `os.Setenv()`, and `os.Unsetenv()`. These examples demonstrate how Go programs can interact with their environment, making them more configurable and adaptable.

### **Building Command-Line Utilities**

Towards the end, the chapter combines all the previous concepts to build a simple **command-line utility** in Go. The utility uses command execution, file manipulation, and environment variables to perform system tasks like monitoring files or processing logs. This practical example reinforces the chapter’s key points and shows how Go can be used to automate system administration tasks.