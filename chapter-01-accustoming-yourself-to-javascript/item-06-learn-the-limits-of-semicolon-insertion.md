# Learn the Limits of Semicolon Insertion

## Contents
1. Semicolons are only ever inserted before a `}` token, after one or more newlines, or at end of the program input.

2. Semicolons are only ever inserted when the next input token cannnot be parsed.
    * You always have to pay attention to the start of the next statement to detect whether you can legally omit a semicolon.

    * Each one of `(, [, +, -, /` can act either as an expression operator or the prefix of a statement, depending on the context. If the next line starts with any of the five problematic characters, no semicolon will be inserted.

    * Omitted semicolons can cause problems is with script concatenation, Each file might consist of a large function call expression, you can protect scripts against careless concatenation by defensively prefixing every file with an extra semicolon.

    * The newline following the `someting` forces an automatic semicolon insertion.
        * A return keyword.
        * A throw keyword.
        * A break or continue statement with an explicit label.
        * A postfix ++ or -- operator.

3. Semicolons are never inserted as separators in the head of a for loop or as empty statements(while).

## Things to Remember
* Semicolons are only ever inferred before a `}`, at the end of a line, or at the end of a program.
* Semicolons are only ever inferred when the next token cannot be parsed.
* Never omit a semicolon before a statement beginning with `[, (, +, - , /`.
* When concatenating scripts, insert semicolons explicitly between scripts.
* Never put a newline before the argument to return, throw.
