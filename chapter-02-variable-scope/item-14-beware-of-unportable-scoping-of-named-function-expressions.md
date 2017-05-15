# Beware of Unportable Scoping of Named Function Expressions

## Things to Remember
* Use named function expressions to improve stack traces in Error objects and debuggers.
* Beware of pollution of function exxpression scope with Object.prototype in ES3 and buggy JavaScript environments.
* Beware of hoisting and duplicate allocation of named function expressions in buggy JavaScript environments.
* Consider avoiding named function expressions or removing them before shipping.
* If you are shipping in properly implemented ES5 environments, you've got nothing to worry about.
