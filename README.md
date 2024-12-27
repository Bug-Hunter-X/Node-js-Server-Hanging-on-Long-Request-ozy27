# Node.js Server Hanging on Long Request

This repository demonstrates a common issue in Node.js: a server hanging when handling a long-running request that blocks the event loop. The `bug.js` file contains code that reproduces this problem. The solution (`bugSolution.js`) demonstrates how to use asynchronous operations or worker threads to prevent blocking the event loop.

## Problem

Node.js is single-threaded, meaning it uses only one thread to handle all requests. If a request handler performs a long-running synchronous operation (like a computationally intensive task or waiting for I/O), it blocks the event loop. This prevents the server from processing other requests, effectively causing it to hang.

## Solution

The solution involves avoiding synchronous operations that might block the event loop. Techniques to accomplish this include:

* **Asynchronous Operations:** Utilize asynchronous APIs (like promises or async/await) for I/O or long-running tasks. This allows the event loop to remain responsive while these operations are in progress.
* **Worker Threads:** Offload computationally intensive tasks to worker threads. This uses multiple threads to improve performance without blocking the main thread.

This repository provides clear examples to understand and resolve this common Node.js issue.