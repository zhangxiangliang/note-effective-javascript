# Prefer Primitives to Object Wrappers
## Primitive values

### Types of Primitive Values
* In JavaScript has five types of primitive values: `object`, `boolean`, `number`, `string`, `undefined`， `null`, `function`, `symbol` (`function` is subset of `object`, `symbol` new in ECMAScript 2015).

* You can create a String object that wraps a string value.
* In some ways, a String object behaves similarly to the string value it wraps.
* But unlike primitive strings, a String object is a true object.
* This is an important difference, because it means that you can’t compare the contents of two distinct String objects using built-in operators.
* You can use this method on a primitive string value, the implicit wrapping produces a new String object each time it occurs.

## Things to Remember
* Object wrappers for primitive types do not have the same behavior as their primitive values when compared for equality.
* Getting and setting properties on primitives implicitly creates object wrappers.
