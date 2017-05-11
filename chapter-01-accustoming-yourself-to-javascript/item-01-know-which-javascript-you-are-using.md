# Know Which JavaScript You Are Using

## If you want to write robust code that can be combined with a wide variety of code:
1. Never concatenate strict files and nonstrict files.
2. Concatenate files by wrapping their boodies in immediately invoked function expressions.

## Things to Remember
* Decide which versions of JavaScript your application supports.
* Be sure that any JavaScript features you use are supported by all environments where your application runs.
* Always test strict code in environments that perform the strict mode checks.
* Beware of concatenating scripts that differ in their expectations about strict mode.
