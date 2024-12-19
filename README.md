# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the provided code lacks proper handling for cases where a user ID is not a valid integer, potentially causing application crashes or unexpected behavior.

## Bug Description

The `/users/:id` route attempts to retrieve a user based on the provided ID. It converts the ID to an integer using `parseInt()`.  However, it fails to handle the scenario where the ID is not a valid integer (e.g., a string, null, undefined), leading to a potential `NaN` comparison and an inability to find the user. This results in either an error or unexpected behavior depending on how the rest of the code interacts with the `user` variable. 

## Solution

The solution adds robust error handling to check if `parseInt(userId)` results in a valid number before attempting to use it in a database query or other operations.