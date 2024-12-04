# Unhandled Promise Rejection in Asynchronous Express.js Route Handler

This repository demonstrates a common error in Node.js applications using Express.js: unhandled promise rejections in asynchronous route handlers.  The bug arises when an error is thrown within an asynchronous operation (in this case, a `setTimeout` callback) without proper error handling. This can lead to application crashes or unexpected behavior.

## The Problem

The `bug.js` file contains an Express.js route handler that simulates an asynchronous operation.  Sometimes this operation throws an error. However, because the error occurs within a `setTimeout` callback, it's not caught by the Express.js middleware and is not gracefully handled resulting in a process crash.

## The Solution

The `bugSolution.js` file demonstrates the correct way to handle errors within asynchronous route handlers using try...catch blocks or promises. By wrapping the asynchronous operation in a `try...catch` block, any errors that occur are caught and can be handled appropriately (e.g., logging the error, sending an error response to the client).