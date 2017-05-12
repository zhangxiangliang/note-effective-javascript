# Beware of Implicit Coercions

## Contents

### Common
* JavaScript can be surprisingly forgiving when it comes to type errors.
* Calling a nonfunction or attempting to select a property of null, will throw error.
* Sometime, JavaScript coerces a value to the expected type by following various automatic conversion protocols. eg: `-, *, /, %`. But `+` is subtler, because it is overloaded to perform either numeric addtion or string concatenation, depending on the types of its arguments, it is favor of string, converting the number to a string.
* The bitwise operations not only convert to numbers but to the subset of numbers that can be represented as 32-bit integers (bitwise arithmetic operators `~, ^, &, |, <<, >>, >>>`).

### Coercions can also hide errors
* A variable thar turns out to be null will not fail in an arithmetic calculation, but silently convert to 0.
* An undefinded variable will convert to the special floating-point value NaN.
* The NaN is blame `the IEEE floating-point standard`, it is not equals self.

### About NaN
* `isNaN(NaN)` is only useful for number (including '123' will converting to number), other value will return true. so `isNaN` is no safe.
* According to `if a value is NaN by checking it for equality to itself`, we can also abstrat this pattern into a clearly named utility funciton : `isReallyNaN = (x) => x !== x`.

### About Object
* Objects can also be coerced to primitives. Because Objects has `toString` method.
* Objects are converted to strings by implicitly calling their `toString` method.
* Objects can be converted to numbers via their `valueOf` method.
* So you can in Objects rewrite `toString` and `valueOf`, control type conversion.
* If a Objects has both `toString` and `valueOf`, it will make the mistake always call `valueOf`.
* It’s best to avoid valueOf unless your object really is a numeric abstraction and obj.toString() produces a string representation of obj.valueOf(), if not your best make the `valueOf` equal `toString`.

### About truthiness
* The `falsy values` : false, 0, -0, "", NaN, null and undefined.
* The `truthy values`: all other value (not equal fasly) is truthy.
* Because numbers and stirngs can be falsy, it's not always safe to use truthiness to check whether a function argument or object property is defined.

## Things to Remember
* Type errors can be silently hidden by implicit coercions.
* The + operator is overloaded to do addition or string concatenation depending on its argument types.
* Objects are coerced to numbers via `valueOf` and to stirng via `toString`.
* Objects with `valueOf` methods should implement a `toString` method that provides a string representation of the number produced by `valueOf`.
* Use typeof or comparison to undefined rather than truthiness to test for undefined values.

