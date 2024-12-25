# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where long-running operations can cause the server to hang or become unresponsive.  The example uses a `setTimeout` to simulate a delay, but it represents scenarios like database queries, complex calculations, or file I/O that take considerable time.

## Bug
The `serverBug.js` file shows a simple HTTP server that introduces a 5-second delay before sending a response.  During this delay, the server is unable to handle new requests, leading to unresponsiveness.

## Solution
The `serverSolution.js` demonstrates how to solve this using asynchronous operations (Promises) and `async/await` to prevent blocking the event loop, allowing the server to remain responsive.

## How to reproduce the bug
1. Run `node serverBug.js`
2. Make a request to `http://localhost:3000`.  You will receive the response after 5 seconds.
3. Try making another request during those 5 seconds.  You will notice the second request might time out or experience delays.

## How to run the solution
1. Run `node serverSolution.js`
2. Make multiple requests to `http://localhost:3000`.  The requests should be processed concurrently without significant delays.