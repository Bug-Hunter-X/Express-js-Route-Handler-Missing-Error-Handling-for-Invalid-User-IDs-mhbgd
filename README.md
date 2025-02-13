# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the provided code fails to handle cases where the user ID is not a valid number.

## Bug

The `bug.js` file contains an Express.js route handler that retrieves a user by ID.  It attempts to parse the ID as an integer using `parseInt()`, but doesn't check if the result is actually a number. If a non-numeric ID is provided, `parseInt()` will return `NaN`, causing the `find()` method to fail silently or throw an error depending on the environment. This can lead to unexpected behavior or crashes.

## Solution

The `bugSolution.js` file demonstrates the corrected code. It includes explicit checks to ensure that the user ID is a valid number before attempting to access the user object.  If the ID is invalid, an appropriate error response is sent.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install express` to install the necessary dependencies.
3. Run `node bug.js`.
4. Send a request to `/users/abc` (or any other non-numeric ID) and observe the error or unexpected response.
