<img width="652" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/01410f06-8626-443b-af85-b4909c452221">



<img width="446" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/8d551aee-aec4-4158-aa25-c0386dd023e7">
<img width="581" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/4ae426cd-71c3-4b46-a562-560985e5b566">


1. Which methods in your code are called?
  The server is started with the main method.
  The server waits for incoming HTTP requests.
  On receiving a request for /add-message?s=Hello, it triggers the handle method of MessageHandler.
  This method processes the message "Hello", adds it to the list of messages, and sends the response back to the client (browser).
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  The HttpExchange exchange object will encapsulate the HTTP request made to the server.
  The getRequestURI().getQuery() method extracts the s=Hello part from the URL.
  The extracted Hello message is then added to the messages list as "1. Hello".
  The response is set to the content of the messages list, which is "1. Hello".
  This response is then sent back to the client.
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  When the request /add-message?s=Hello is processed:
  The code extracts the message Hello from the request.
  It then appends the next sequence number (in this case, 1) and the extracted message to the messages list.
  The purpose of the server is to keep track of incoming messages by adding them sequentially to the messages list. 
  Each time a valid request to /add-message?s=<string> is received, the string value is extracted and appended to the list with its     sequence number. 
  This behavior results in a change in the messages field for every valid request.
![image](https://github.com/Lyon0129/Lab-report2/assets/130290363/5e579269-cb34-41db-807d-34135e757dd9)
1. Which methods in your code are called?
  the specific methods that get called when the "How are you" message is added (resulting in the "1. Hello\n2. How are you" response) are the handle method of the MessageHandler class. The internal state of the messages list changes with each new request to keep track of all the messages sent to the server.
2. What are the relevant arguments to those methods, and the values of any relevant fields of the class?
  The handle method gets called with the argument HttpExchange exchange that represents the incoming request. The internal state of the messages list changes with the request, appending the new message with its sequence number. After the second request, the messages list contains two entries: ["1. Hello", "2. How are you"].
3. How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
  The relevant field of the class that changes is:Field: private static final List<String> messages
  How it changes from this specific request:
  Before the request: Due to the prior request of /add-message?s=Hello, the messages list already contains: ["1. Hello"].
  During the request: The code extracts the message How are you from the request? It then appends the next sequence number (in this case, 2) and the extracted message to the messages list.
  After the request: The messages list now contains two entries: ["1. Hello", "2. How are you"].
Part2
![image](https://github.com/Lyon0129/Lab-report2/assets/130290363/0eb765a0-dc65-4f4c-8fa1-ecd79ae801da)
![image](https://github.com/Lyon0129/Lab-report2/assets/130290363/95be1e6c-7e4c-4944-8f9c-2b882619fd8c)
![image](https://github.com/Lyon0129/Lab-report2/assets/130290363/4a8d28c1-dc0f-4e19-91fc-25046af757b5)
<img width="567" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/aed17195-c19f-4136-86a7-aa37807b5d9b">
<img width="710" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/ede0ba3c-9afc-4d35-bcf3-5784ee5dc067">
On my local machine, the path to my public key is ~/.ssh/id_rsa.pub and the path to my private key is ~/.ssh/id_rsa
On the ieng6 server, the path to my public key is ~/.ssh/authorized_keys

Part3
I have learned how to how to building and run a server.
I also know about how to set my SSH keys for easy access.







