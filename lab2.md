import com.sun.net.httpserver.HttpServer;
import com.sun.net.httpserver.HttpHandler;
import com.sun.net.httpserver.HttpExchange;

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetSocketAddress;
import java.util.ArrayList;
import java.util.List;

public class StringServer {

    private static final List<String> messages = new ArrayList<>();

    public static void main(String[] args) throws Exception {
        HttpServer server = HttpServer.create(new InetSocketAddress(8000), 0);
        server.createContext("/add-message", new MessageHandler());
        server.setExecutor(null);
        server.start();
    }

    static class MessageHandler implements HttpHandler {
        @Override
        public void handle(HttpExchange exchange) throws IOException {
            String query = exchange.getRequestURI().getQuery();
            String response = "Invalid request.";

            if (query != null && query.startsWith("s=")) {
                String message = query.substring(2).replace("%20", " "); // rudimentary URL decoding
                messages.add((messages.size() + 1) + ". " + message);

                response = String.join("\n", messages);
            }

            exchange.sendResponseHeaders(200, response.getBytes().length);
            try (OutputStream os = exchange.getResponseBody()) {
                os.write(response.getBytes());
            }
        }
    }
}
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/81a19d6a-5bd0-49ee-9079-c30d56f2d515)
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

![f455e3fda9b0039a1bfc858ffe5ae91](https://github.com/Awu-Lin/cse15l-lab-reports/assets/94472422/c7cc1ccb-c789-4f2f-a983-319f28bb8318)
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

![91fdb0a3a219b6aefc67cfeff52fc6a](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/2e1e51eb-86a7-4134-beff-1c904ba91863)
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/cdaba673-e56a-49c5-ac74-823669d76ad0)

Part3
I have learned about how to how to building and running a server.
I also know about how to set my SSH keys for easy access.
