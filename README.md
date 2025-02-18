# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js applications:  unresponsiveness caused by long-running operations that block the event loop.  The `bug.js` file shows a server that hangs for 5 seconds due to a simulated long task.  `bugSolution.js` provides a solution using asynchronous operations to avoid blocking.

## Problem

Node.js is single-threaded.  Long-running synchronous operations within request handlers will block the event loop, preventing it from processing other requests or events.  This leads to unresponsiveness and potentially poor performance.

## Solution

The solution involves using asynchronous operations (e.g., `setTimeout` with a callback, promises, async/await) to avoid blocking the event loop.  Asynchronous operations allow the event loop to continue processing other tasks while the long-running operation is being performed.