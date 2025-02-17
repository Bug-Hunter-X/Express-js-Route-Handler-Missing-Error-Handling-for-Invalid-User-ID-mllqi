# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling when parsing user input. The provided code attempts to fetch a user based on their ID, but lacks checks for non-numeric IDs.  This can lead to runtime errors or unexpected behavior.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version with proper error handling.

## Bug
The primary issue is the lack of error handling when converting `req.params.id` to an integer using `parseInt()`. If the ID is not a number (e.g., a string), `parseInt()` returns `NaN`, causing the `find()` method to fail to locate the user.  This can result in an unhandled exception or unexpected 404 errors.

## Solution
The solution in `bugSolution.js` explicitly checks if `parseInt(userId)` returns `NaN`. If it does, a more appropriate error response is sent, making the code more robust and less prone to unexpected issues.