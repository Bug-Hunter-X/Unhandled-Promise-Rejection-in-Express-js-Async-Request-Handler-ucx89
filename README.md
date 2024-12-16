# Unhandled Promise Rejection in Express.js Async Request Handler

This repository demonstrates a common yet subtle error in Express.js applications: unhandled promise rejections within asynchronous request handlers.  Improper error handling can lead to server crashes without clear error messages in the logs.

## The Problem

The `bug.js` file shows an Express.js server with an asynchronous request handler (`/`).  If the asynchronous operation (`someAsyncOperation`) fails (simulated by a random chance), the promise rejection is not handled.  This results in a server crash without clear indication to the developer.

## The Solution

The `bugSolution.js` file demonstrates the proper way to handle promise rejections. It uses a `.catch()` block to handle errors gracefully, logging the error details and sending an appropriate response to the client.

## How to Reproduce

1. Clone the repository.
2. Navigate to the directory containing `bug.js`.
3. Run `node bug.js`.
4. Refresh the page repeatedly until the server crashes (due to the simulated error). 
5. Then repeat for `bugSolution.js`, and observe the error handling.