# Uncommon HTML Bug: Method Called on Null Value

This repository demonstrates a subtle bug that can occur in HTML/JavaScript when attempting to use a method on a value that might be null.  This is especially relevant when using getAttribute or other methods that could return null if the target element or attribute doesn't exist.

The `bug.html` file shows the buggy code, and `bugSolution.html` demonstrates a corrected approach.

## Bug Description

The primary issue lies in accessing the 'length' property of a variable ('text') that might be null. The `getAttribute` method returns null if the attribute does not exist on the specified element. Subsequently, calling `text.length` throws a TypeError. This can be hard to debug unless proper null checks are employed.

## Solution

The solution in `bugSolution.html` uses an if statement to first check if the `text` variable is null before attempting to access its length property. This prevents the TypeError and handles the case where the attribute doesn't exist gracefully.