# Question:

18. Create a simple HTTP server using Node.js, including routing and handling requests.

# Answer:

## Simple HTTP Server with Node.js: Routing and Request Handling

This example demonstrates a basic HTTP server using Node.js with routing for different paths and handling GET and POST requests.

```javascript
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  const { url, method } = req;

  // Routing
  if (url === '/') {
    if (method === 'GET') {
      res.statusCode = 200;
      res.setHeader('Content-Type', 'text/plain');
      res.end('Welcome to the homepage!');
    } else {
      res.statusCode = 405;
      res.end('Method Not Allowed');
    }
  } else if (url === '/about') {
    if (method === 'GET') {
      res.statusCode = 200;
      res.setHeader('Content-Type', 'text/plain');
      res.end('About page content');
    } else {
      res.statusCode = 405;
      res.end('Method Not Allowed');
    }
  } else if (url === '/data' && method === 'POST') {
    let body = '';
    req.on('data', chunk => {
      body += chunk.toString();
    });
    req.on('end', () => {
      res.statusCode = 200;
      res.setHeader('Content-Type', 'text/plain');
      res.end(`Received data: ${body}`);
    });
  } else {
    res.statusCode = 404;
    res.end('Page not found');
  }
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

**Explanation:**

1. **Import http module:** We import the built-in `http` module to work with HTTP functionalities.
2. **Define hostname and port:** We set the hostname and port for the server to listen on.
3. **Create server:** We create an HTTP server using `http.createServer()`. This function takes a callback that will be executed for each incoming request.
4. **Access request properties:** Inside the callback, we access the request object's `url` and `method` properties to determine the requested path and HTTP method.
5. **Routing:** We use `if` statements to check the URL and method and handle them accordingly.
6. **Handling GET requests:** For GET requests on `/` and `/about`, we set the appropriate status code, content type, and send a response message.
7. **Handling POST requests:** For POST requests on `/data`, we accumulate the request body data using the `data` and `end` events of the request object. Once the entire body is received, we send a response with the received data.
8. **Handling other cases:** For any other URL or method combination, we send a 404 Not Found response.
9. **Start server:** Finally, we start the server using `server.listen()` and provide the hostname and port. 

**To run this code:**

1. Save it as a `.js` file (e.g., `server.js`).
2. Open a terminal and navigate to the directory where you saved the file.
3. Run the command `node server.js`.
4. Open your browser and visit `http://localhost:3000/` to see the homepage. 

**This is a basic example, and you can extend it further by:**

* Adding more routes and handling different HTTP methods.
* Using a routing library like Express.js for more advanced routing capabilities.
* Implementing error handling and logging.
* Serving static files like HTML, CSS, and JavaScript. 
