# Unresponsive Node.js Server

This repository demonstrates a common Node.js issue: an unresponsive server caused by a long-running synchronous operation that blocks the event loop.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem

The original code performs a 5-second CPU-bound operation within the request handler.  This blocks the event loop, meaning no other requests can be processed during that time.  The server effectively becomes unresponsive for those 5 seconds, leading to poor performance and a bad user experience.

## Solution

The solution employs asynchronous programming techniques, allowing other requests to be handled concurrently while the long-running task completes. This preserves the responsiveness of the server.