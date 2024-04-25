# Question:

6. Lifecycle of Servlet with block diagram.

# Answer:

## Servlet Lifecycle with Block Diagram

A servlet's life cycle consists of the following stages, which are managed by the servlet container:

1. **Loading:** The servlet class is loaded into the container when it's first requested or during server startup, depending on the configuration.
2. **Initialization:** The `init()` method is called once after loading, allowing the servlet to perform one-time setup tasks like loading configuration or establishing connections.
3. **Request Handling:** For each client request, the container creates a new thread and calls the `service()` method. The `service()` method determines the type of request (GET, POST, etc.) and calls the appropriate method (`doGet()`, `doPost()`, etc.) to handle it.
4. **Service:** The specific `doXXX()` method executes the request-specific logic, generating the response content.
5. **Destruction:** When the container decides to unload the servlet, it calls the `destroy()` method, allowing the servlet to clean up resources and save state.

### Block Diagram

```
                   +----------------+
                   | Servlet Class  |
                   +--------+-------+
                            |
                            | Loaded
                            v
                   +--------+-------+
                   |   Loading    |
                   +--------+-------+
                            |
            +----------------+----------------+
            |                |                |
            | Initialized?   |   Destroyed?   |
            |                |                |
            +--------+-------+--------+-------+
                     |                |
                     |  Yes           | No
                     v                v
            +--------+-------+--------+-------+
            | Initialization |   Servicing   |
            | (init())      | (service())   |
            +--------+-------+--------+-------+
                     |                |
                     | Request        |
                     v                v
            +--------+-------+--------+-------+
            |   doGet()     |   doPost()   |
            |  ... etc.   |  ... etc.   |
            +--------+-------+--------+-------+
                     |
                     | Response
                     v
                   +--------+-------+
                   |    Client     |
                   +----------------+
``` 
