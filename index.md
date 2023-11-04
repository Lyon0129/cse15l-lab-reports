# Part 1
<img width="652" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/01410f06-8626-443b-af85-b4909c452221">



<img width="446" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/8d551aee-aec4-4158-aa25-c0386dd023e7">
<img width="581" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/4ae426cd-71c3-4b46-a562-560985e5b566">

## Screenshot 1
1. Which methods in your code are called?
   The .start(port, handler) method of Server.java
   
   The .create method of HttpServer
   The .createContext method of HttpServer
   The .start method of HttpServer
   
   The .handleRequest method of URLHandler
   The .getRequestURI method of HttpExchange
   The .sendResponseHeaders method of HttpExchange
   The .getResponseBody of HttpExchange

   The .getQuery method of URI
   The .getPath method of URI

   The .write of OutputStream
   The .close of OutputStream
   
   
  The server is started with the main method.
  The server waits for incoming HTTP requests.
  On receiving a request for /add-message?s=Hello, it triggers the handle method of MessageHandler.
  This method processes the message "Hello", adds it to the list of messages, and sends the response back to the client (browser).
3. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  int port: The port number on which the server will run.
  URLHandler handler: The user-defined handler that processes requests.
  HttpServer server: The HTTP server instance.
  HttpExchange exchange: Contains details of the HTTP request/response.
  URI url: The request URI passed to the handleRequest method.
4. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  When the request /add-message?s=Hello is processed:

  The value of count 

  
## Screenshot 2
1. Which methods in your code are called?
  HttpServer.create(new InetSocketAddress(port), 0)
    This method is called once when the server is being set up before it starts. It binds the server to a specific port number.
  server.createContext("/", new ServerHttpHandler(handler))
    This method is called during the setup process as well, and it establishes a context for the root path /. It associates an instance of     ServerHttpHandler with the root context.
  server.start()
    This method starts the server. It's called once after the server has been set up with the necessary context and before it begins listening for incoming HTTP requests.
    Once the server is running, for each incoming request:
    
    ServerHttpHandler.handle(final HttpExchange exchange)
    
    This is the method in ServerHttpHandler that is called every time there is an HTTP request to the server's context path. It manages the request-response lifecycle.
    handler.handleRequest(exchange.getRequestURI())
    
    Within the handle method, this line is invoked to process the request URI, which will include the query part with the new message ("How are you"). It calls the handleRequest method of the URLHandler interface that ServerHttpHandler has been initialized with. The actual handling logic (parsing the request and formulating a response) would be within this method.
    exchange.sendResponseHeaders(200, ret.getBytes().length) 
    This method is called to set the HTTP status code (200 OK) and the length of the response body.
    OutputStream os = exchange.getResponseBody()
    This line gets the OutputStream that will be used to send the response body.
    os.write(ret.getBytes())
    The response body (which now includes "1. Hello\n2. How are you") is written to the output stream.
    os.close()
    The output stream is closed, finalizing the response.
    The handleRequest method must have logic that appends the new message to the existing messages. The actual code that handles the message addition and storage isn't provided here. It would typically be a part of the implementation of the URLHandler interface, where messages are likely being stored in a list or other data structure and then formatted into the string response that includes all messages received so far.
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  HttpServer.create
Argument 1: new InetSocketAddress(port) where port is an int that specifies the port number the server will listen on.
Argument 2: 0 which is the backlog, the maximum number of queued incoming connections to allow. A value of 0 means use the system default value.
server.createContext
Argument 1: "/" which is a String representing the root context path that this handler will be associated with.
Argument 2: new ServerHttpHandler(handler) where handler is an instance of a class that implements the URLHandler interface, responsible for handling the logic of the incoming requests.
server.start
No arguments; this simply starts the server.
ServerHttpHandler.handle
Argument: final HttpExchange exchange which is an instance of HttpExchange containing the details of the HTTP request.
HttpExchange.sendResponseHeaders
Argument 1: 200 which is an int representing the HTTP status code for OK.
Argument 2: ret.getBytes().length where ret is a String that contains the response to the client. getBytes().length provides the length of the response body in bytes.
OutputStream.write
Argument: ret.getBytes() which writes the byte representation of the String response to the OutputStream.
Relevant Fields in ServerHttpHandler
URLHandler handler: This field in ServerHttpHandler stores the reference to the URLHandler instance which will process the request.
The URLHandler interface would have a method handleRequest(URI url) that takes a URI object as an argument. The actual value of this URI would change with each request, as it encapsulates the details of the request URI.

For instance, when processing the request /add-message?s=Hello, the URI object would have the path /add-message and the query string s=Hello. If the URLHandler implementation appends messages to a list or concatenates them into a String, these would not be part of the ServerHttpHandler class but instead part of the state within the URLHandler implementation.
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  How it changes from this specific request:
  Before the request: Due to the prior request of /add-message?s=Hello, the messages list already contains: ["1. Hello"].
  During the request: The code extracts the message How are you from the request? It then appends the next sequence number (in this case, 2) and the extracted message to the messages list.
  After the request: The messages list now contains two entries: ["1. Hello", "2. How are you"].

# Part2
![image](https://github.com/Lyon0129/Lab-report2/assets/130290363/0eb765a0-dc65-4f4c-8fa1-ecd79ae801da)
![image](https://github.com/Lyon0129/Lab-report2/assets/130290363/95be1e6c-7e4c-4944-8f9c-2b882619fd8c)
![image](https://github.com/Lyon0129/Lab-report2/assets/130290363/4a8d28c1-dc0f-4e19-91fc-25046af757b5)
<img width="567" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/aed17195-c19f-4136-86a7-aa37807b5d9b">
<img width="710" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/ede0ba3c-9afc-4d35-bcf3-5784ee5dc067">
On my local machine, the path to my public key is ~/.ssh/id_rsa.pub and the path to my private key is ~/.ssh/id_rsa
On the ieng6 server, the path to my public key is ~/.ssh/authorized_keys

# Part3
I have learned how to how to building and run a server.
I also know about how to set my SSH keys for easy access.







