# Avoid Using == with Mixed Types

* When the two arguments are different type, `==` will implicit coercions, they are both converted to numbers before being compared.
* But it's actually easy to vonvert values to numbers explicitly using the Number function or the unary + operator.
* Most of the time, the conversions attempt to produce numbers.

| Argument Type One | Argument Type Two | Coercions |
| -- | -- | -- |
| null | undefined | always true |
| null or undefined | Any other | always false |
| string, number or boolean | Data object | Primitive => number. Data => toString => valueOf |
| string, number or boolen | Non-Data object | Primitive => number. object => valueOf => toString |
| string, number or boolean | string, number or boolean | Primitive => number |

* A better policy is to make the conversions explicit with custom application logic and use the strict equality operator

## Things to Remember
* The == operator applies a confusing set of implicit coercions when its aruments are of different types.
* Use === to make it clear to your readers that your comparison does not involve any implicit coercions.
* Use your own explicit coercions when comparing value of different types to make your program's behavior clearer.
