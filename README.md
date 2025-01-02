# Express.js Hanging Request Bug

This repository demonstrates a common Express.js error: a hanging GET request due to a missing response in a route handler. The server receives the request but doesn't send back a response, leaving the client waiting indefinitely.

## Bug Description
The `bug.js` file contains an Express.js server with a GET route that logs a message to the console but omits the crucial `res.send()` (or similar) to send a response back to the client. This results in hanging requests and potentially timeouts for the client.

## Solution
The `bugSolution.js` file provides a corrected version. It includes `res.send()` in the route handler to return a response to the client, resolving the issue. 

## How to Reproduce
1. Clone this repository.
2. Run `node bug.js`
3. Make a GET request to `http://localhost:3000/` using a tool like `curl` or a browser. Observe the hanging request.
4. Run `node bugSolution.js`
5. Make the same GET request. This time, you'll receive a response.