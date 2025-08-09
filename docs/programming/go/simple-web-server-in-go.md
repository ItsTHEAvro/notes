# Building a Simple Web Server in Go: Complete Tutorial

In this tutorial, you'll learn how to build a complete web server in Go from scratch. By the end of this guide, you'll have a working web server that can serve static files, handle forms, and respond to custom API endpoints.

## 🔗 Source Code

Complete source code for this tutorial is available on **[Github](https://github.com/ItsTHEAvro/LearnGoLang/tree/main/01.%20Simple%20Web%20Server)**

## What You'll Build

By following this tutorial, you'll create a web server with the following features:

- **Static File Serving**: Serve HTML static files
- **Custom API Endpoints**: Handle specific routes with custom logic
- **Form Processing**: Accept and process HTML form submissions
- **Error Handling**: Proper HTTP error responses
- **Request Validation**: Method and path validation

## Prerequisites

Before starting this tutorial, make sure you have:

- Go installed on your system (version 1.16 or later)
- Basic understanding of Go syntax
- A text editor or IDE
- Basic knowledge of HTTP concepts

## Step 1: Project Setup

First, let's create our project structure:

```
simple-web-server/
├── main.go          # Main server implementation
├── static/          # Static files directory
│   ├── index.html   # Home page
│   └── form.html    # Form page
└── go.mod           # Go module file
```

### 1.1 Create the Project Directory

```cmd
mkdir simple-web-server
cd simple-web-server
```

### 1.2 Create Static Files Directory

```cmd
mkdir static
```

## Step 2: Create Static HTML Files

Let's create the HTML files that our server will serve.

### 2.1 Create `static/index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Web Server</title>
</head>
<body>
    <h1>Welcome to the Simple Web Server</h1>
    <p>This is a basic web server setup using Go.</p>
    <a href="/hello">Click here to say hello</a>
    <br>
    <a href="/form.html">Here is a form</a>
</body>
</html>
```

### 2.2 Create `static/form.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Web Server - Form</title>
</head>
<body>
    <h1>Submit Your Information</h1>
    <form action="/submit" method="POST">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>
        <br>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        <br>
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

## Step 3: Building the Go Web Server

Now let's build our web server step by step.

### 3.1 Create `main.go` with Basic Structure

Start by creating the basic file structure:

```go
package main

import (
	"fmt"
	"log"
	"net/http"
)

func main() {
	// We'll add our code here step by step
}
```

### 3.2 Add the Hello Handler

Let's create our first custom endpoint that responds with "Hello World!":

```go
func helloHandler(w http.ResponseWriter, r *http.Request) {
	// Validate the URL path
	if r.URL.Path != "/hello" {
		http.Error(w, "404 Not Found", http.StatusNotFound)
		return
	}

	// Validate the HTTP method
	if r.Method != "GET" {
		http.Error(w, "Method is not supported", http.StatusNotFound)
		return
	}

	// Send response
	fmt.Fprint(w, "Hello World!")
}
```

**Understanding the Handler Function:**

- **Function Signature**: All HTTP handlers in Go must have the signature `func(http.ResponseWriter, *http.Request)`
- **ResponseWriter**: Used to write the HTTP response back to the client
- **Request**: Contains all information about the incoming HTTP request
- **Path Validation**: We check if the request is for the exact path `/hello`
- **Method Validation**: We only allow GET requests
- **Error Responses**: We use `http.Error()` to send proper HTTP error codes

### 3.3 Add the Form Handler

Now let's create a handler that can process form submissions:

```go
func formHandler(w http.ResponseWriter, r *http.Request) {
	// Parse the form data from the request
	if err := r.ParseForm(); err != nil {
		fmt.Fprintf(w, "ParseForm error: %v", err)
		return
	}

	// Send success message
	fmt.Fprintf(w, "POST request successful!\n")

	// Extract form values
	name := r.FormValue("name")
	email := r.FormValue("email")

	// Display the submitted data
	fmt.Fprintf(w, "Name = %s\n", name)
	fmt.Fprintf(w, "Email = %s\n", email)
}
```

**Understanding Form Processing:**

- **ParseForm()**: This method parses the form data from the request body
- **Error Handling**: We check for parsing errors and display them if they occur
- **FormValue()**: Extracts specific form field values by their `name` attribute
- **Formatted Output**: We use `fmt.Fprintf()` to send formatted responses

### 3.4 Complete the Main Function

Now let's update our main function to set up all routes and start the server:

```go
func main() {
	// Create a file server for static files
	fileServer := http.FileServer(http.Dir("./static/"))
	
	// Register route handlers
	http.Handle("/", fileServer)                    // Serve static files from root
	http.HandleFunc("/submit", formHandler)         // Handle form submissions
	http.HandleFunc("/hello", helloHandler)         // Handle hello endpoint

	// Start the server
	fmt.Println("Starting server at port 8080")
	if err := http.ListenAndServe(":8080", nil); err != nil {
		log.Fatal(err)
	}
}
```

**Understanding Server Setup:**

- **FileServer**: `http.FileServer()` creates a handler that serves static files from a directory
- **Route Registration**: We use `http.Handle()` for handler objects and `http.HandleFunc()` for handler functions
- **Server Start**: `http.ListenAndServe()` starts the HTTP server on the specified port
- **Error Handling**: If the server fails to start, we use `log.Fatal()` to exit the program

## Step 4: Complete Server Code

Here's the complete `main.go` file with all components:
```go
package main

import (
	"fmt"
	"log"
	"net/http"
)

// helloHandler handles requests to the /hello endpoint
func helloHandler(w http.ResponseWriter, r *http.Request) {
	// Validate the URL path
	if r.URL.Path != "/hello" {
		http.Error(w, "404 Not Found", http.StatusNotFound)
		return
	}

	// Validate the HTTP method
	if r.Method != "GET" {
		http.Error(w, "Method is not supported", http.StatusNotFound)
		return
	}

	// Send response
	fmt.Fprint(w, "Hello World!")
}

// formHandler processes form submissions
func formHandler(w http.ResponseWriter, r *http.Request) {
	// Parse the form data from the request
	if err := r.ParseForm(); err != nil {
		fmt.Fprintf(w, "ParseForm error: %v", err)
		return
	}

	// Send success message
	fmt.Fprintf(w, "POST request successful!\n")

	// Extract form values
	name := r.FormValue("name")
	email := r.FormValue("email")

	// Display the submitted data
	fmt.Fprintf(w, "Name = %s\n", name)
	fmt.Fprintf(w, "Email = %s\n", email)
}

func main() {
	// Create a file server for static files
	fileServer := http.FileServer(http.Dir("./static/"))
	
	// Register route handlers
	http.Handle("/", fileServer)                    // Serve static files from root
	http.HandleFunc("/submit", formHandler)         // Handle form submissions
	http.HandleFunc("/hello", helloHandler)         // Handle hello endpoint

	// Start the server
	fmt.Println("Starting server at port 8080")
	if err := http.ListenAndServe(":8080", nil); err != nil {
		log.Fatal(err)
	}
}
```

## Step 5: Running Your Web Server

### 5.1 Navigate to Your Project Directory

```cmd
cd simple-web-server
```

### 5.2 Run the Server

```cmd
go run main.go
```

You should see the output:
```
Starting server at port 8080
```

### 5.3 Test Your Server

Open your web browser and visit the following URLs:

1. **Home Page**: `http://localhost:8080`
   - Should display your index.html page
   
2. **Hello Endpoint**: `http://localhost:8080/hello`
   - Should display "Hello World!"
   
3. **Form Page**: `http://localhost:8080/form.html`
   - Should display the contact form
   
4. **Submit Form**: Fill out the form and click submit
   - Should process the form and display the submitted data

## Step 6: Understanding the Key Concepts

### 6.1 HTTP Handler Functions

All HTTP handlers in Go follow this pattern:

```go
func handlerName(w http.ResponseWriter, r *http.Request) {
    // Handler logic here
}
```

- **ResponseWriter (w)**: Interface for writing the HTTP response
- **Request (r)**: Contains all information about the incoming request

### 6.2 Routing in Go

Go provides two main ways to register routes:

```go
// For handler functions
http.HandleFunc("/path", handlerFunction)

// For handler objects (like file servers)
http.Handle("/path", handlerObject)
```

### 6.3 Static File Serving

```go
fileServer := http.FileServer(http.Dir("./static/"))
http.Handle("/", fileServer)
```

This automatically serves files from the `./static/` directory.

### 6.4 Form Processing

```go
// Parse form data
err := r.ParseForm()

// Get form values
value := r.FormValue("fieldName")
```

### 6.5 Error Handling

```go
// Send HTTP error response
http.Error(w, "Error message", http.StatusCode)

// Handle server errors
if err := http.ListenAndServe(":8080", nil); err != nil {
    log.Fatal(err)
}
```


## Troubleshooting Common Issues

### Issue 1: Port Already in Use
```
Error: listen tcp :8080: bind: address already in use
```
**Solution**: Change the port number in `http.ListenAndServe(":8081", nil)`

### Issue 2: Static Files Not Loading
**Problem**: Getting 404 errors for static files
**Solution**: 
- Ensure the `static/` directory exists
- Check file paths are correct
- Verify HTML files are in the static directory

### Issue 3: Form Not Submitting
**Problem**: Form submission returns 404 or method not allowed
**Solution**:
- Ensure form method is POST: `<form method="post">`
- Check form action points to correct endpoint: `action="/submit"`
- Verify the form handler is registered properly

---

### Congratulations! You've built a complete web server in Go.

The Go standard library provides powerful tools for web development, and this foundation will help you build more complex web applications. The concepts you've learned here—handlers, routing, and request processing—are fundamental to all Go web development.