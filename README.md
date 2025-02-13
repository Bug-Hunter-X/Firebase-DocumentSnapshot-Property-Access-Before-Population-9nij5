# Firebase DocumentSnapshot Property Access Before Population

This repository demonstrates a common error in Firebase applications where you try to access a property of a `DocumentSnapshot` before the data has been fully loaded. This often happens when dealing with asynchronous operations.

## Bug

The bug occurs because asynchronous operations in Firebase (such as `getDoc()`) don't return data immediately.  If you try to access the snapshot's properties before the asynchronous operation is complete, you will get an undefined result or an error.

## Solution

The solution involves using promises or async/await to ensure that the data is fully loaded before accessing its properties.  This makes your code wait for the operation to complete before proceeding.

## How to reproduce the bug

1. Clone the repository.
2. Install the required dependencies: `npm install`
3. Run the `bug.js` script.  You'll see an error or undefined values.
4. Then run the `bugSolution.js` script which fixes the error using async/await.
