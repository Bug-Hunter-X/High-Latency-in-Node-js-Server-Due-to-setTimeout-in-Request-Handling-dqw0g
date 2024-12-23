# Node.js Server Latency Bug

This repository demonstrates a common performance issue in Node.js servers:  unnecessary delays in the main request handling path. The server uses `setTimeout` to simulate a 5-second delay before responding.  This is bad practice, as it blocks the event loop and leads to poor performance.

## Bug Description

The `server.js` file contains a simple Express.js server with a `setTimeout` function in its request handler.  This causes each request to take 5 seconds to process.  For production systems, this is unacceptable.

## Solution

The `serverSolution.js` file demonstrates the solution.  Instead of blocking the event loop with `setTimeout` in the request handler, it uses asynchronous operations to handle the delay without impacting responsiveness.

## How to Run

1. Clone this repository.
2. Navigate to the repository's directory in your terminal.
3. Run `npm install express` to install the Express.js dependency.
4. Run `node server.js` to start the buggy server.
5. Run `node serverSolution.js` to start the fixed server.

Test the servers by sending requests to `http://localhost:3000`.