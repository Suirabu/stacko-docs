# File

## Description

Include the contents of an external Stacko script in another Stack script.

Recursive includes are automatically resolved by the Stacko interpreter.

## Example

UserInfo.stacko
```py
"John Doe" const userName
```

Greeter.stacko
```py
fnn greet {
    "Hello " print
    print
    "!" printLine
}
```

Main.stacko
```py
file UserInfo.stacko
file Greeter.stacko

userName greet
```

Result (Main.stacko)
```
Hello John Doe!
```
