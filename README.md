# Unhandled Asynchronous Error in Node.js Server

This repository demonstrates a common error in Node.js: unhandled errors in asynchronous operations. The `bug.js` file contains a simple HTTP server that simulates an asynchronous operation which may randomly fail.  Without proper error handling, this leads to the server silently failing without any logs or reporting.

The `bugSolution.js` shows how to use proper error handling to catch and report these errors, preventing silent failures and providing helpful diagnostics.

## How to Run

1.  Clone this repository.
2.  Navigate to the repository's directory.
3.  Run `node bug.js` to run the buggy server.
4.  Run `node bugSolution.js` to run the corrected version.
5.  Use a tool like `curl` or a web browser to send requests to `http://localhost:3000` to observe the behavior.

## Problem

The original code lacks error handling within the asynchronous `setTimeout` callback. If the simulated operation fails, the error is swallowed and the server continues running, appearing to be functioning normally, but not providing any indication of the failure.

## Solution

The solution uses a `try...catch` block to catch potential errors within the asynchronous callback.  This ensures that any exceptions are handled and logged, giving a more robust server.