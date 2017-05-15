# Minimize Use of the Global Object
## Content

* Defining global variables pollutes the common namespace shared by everyone, introducing the possibility of accidental name collisions.

* Some uses of the global namespace are unavoidable, a component or library has to define a global name so that other parts of the program can use it.

* You have two mechanaisms to choose from for creating a global variable: you can declare it with `var` in the global scope, or you can add it to the global object.

* Can use an alternate implementation of feature detection is especially important in web browsers, where the same code may be excuted by a wide variety.
```
if (!this.JSON) {
    this.JSON = {
        parse: ...,
        stringify: ...
    };
}
```

## Things to Remember
* Avoid declaring global variables.
* Declare variables as locally as possible.
* Avoid adding properties to the global object.
* Use the global object for platform feature detection.
