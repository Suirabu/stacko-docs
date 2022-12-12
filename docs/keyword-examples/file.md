# File

## Description

Include the contents of an external Stacko script in another Stack script.

Recursive includes are automatically resolved by the Stacko interpreter.

## Example

UserInfo.stko
```py
"John Doe" const userName
```

Greeter.stko
```py
fnn greet {
    "Hello " print
    print
    "!" printLine
}
```

Main.stko
```py
file UserInfo.stko
file Greeter.stko

userName greet
```

Result (Main.stko)
```
Hello John Doe!
```
