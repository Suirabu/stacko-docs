# Keyword Reference

Text between curly braces (`{}`) represent blocks. A block is a sequence of instructions encased in curly braces in
source code.

```py
{
    "This is a block!" printLine
}
```

Text between less than and greater than symbols (`<>`) represent identifiers in source code.

```py
# These are all valid identifiers
foo
_bar
baz13
```

Text between square brackets (`[]`) is optional.

## Stack Operations

| Name | Signature | Description |
|------|-----------|-------------|
| `dup` | `a -- a a` | Duplicates `a`. |
| `pop` | `a --` | Pops `a` off of the stack. |

## Arithmetic Operations

| Name | Signature | Description |
|------|-----------|-------------|
| `+` | `a b -- c` | Returns the sum of `a` and `b`. |
| `-` | `a b -- c` | Returns `a` minus `b`. |
| `*` | `a b -- c` | Returns the product of `a` and `b`. |
| `/` | `a b -- c` | Returns `a` divided by `b`. |
| `%` | `a b -- c` | Returns `a` modulo `b`. See [modular arithmetic](https://en.wikipedia.org/wiki/Modular_arithmetic). |

## Logical Operations

| Name | Signature | Description |
|------|-----------|-------------|
| `=` | `a b -- c` | Returns true if `a` and `b` are equal. Returns false otherwise. |
| `<` | `a b -- c` | Returns true if `a` is less than `b`. Returns false otherwise. |
| `<=` | `a b -- c` | Returns true if `a` is less than or equal to `b`. Returns false otherwise. |
| `>` | `a b -- c` | Returns true if `a` is greater than `b`. Returns false otherwise. |
| `>=` | `a b -- c` | Returns true if `a` is greater than or equal to `b`. Returns false otherwise. |
| `not` | `a -- b` | Returns the opposite of `a`. `a` must be a boolean. |

## Type Operations

| Name | Signature | Description |
|------|-----------|-------------|
| `toBool` | `a -- b` | Converts `a` into a boolean value. |
| `toNum` | `a -- b` | Converts `a` into a numeric value. |
| `toString` | `a -- b` | Converts `a` into a string. |

## Assertions

| Name | Signature | Description |
|------|-----------|-------------|
| `assert` | `a --` | Halts execution of the program if `a` is false. |
| `assertEqual` | `a b --` | Halts execution of the program if `a` and `b` are not equal. |
| `assertNotEqual` | `a b --` | Halts execution of the program if `a` and `b` are equal. |

## List Operations

| Name | Signature | Description |
|------|-----------|-------------|
| [`getElement`](./keyword-examples/get-element.md) | `list index -- elem` | Returns the element from a list `list` at index `index`. |

## System Operations

| Name | Signature | Description |
|------|-----------|-------------|
| `print` | `a --` | Writes contents of `a` to stdout. |
| `printLine` | `a --` | Writes contents of `a` to stdout with a trailing newline character. |
| `readLine` | `-- input` | Returns a single line of input from stdin. |
| `waitMore` | `a --` | Halts execution of the program for `a` seconds. `a` must be a float. |

## Identifier Operations

| Name | Signature | Description |
|------|-----------|-------------|
| `const <name>` | `a --` | Creates a constant with the name `<name>` and a value of `a`. |
| `var <name>` | `--` | Creates a variable with the name `<name>`. |
| `set <name>` | `a --` | Assigns the value of `a` to a variable with the name `<name>`. |
| `<name>` | `-- a` | Pushes the value of a variable or constant with the name `<name>` onto the stack. |

## Control Flow

| Name | Signature | Description |
|------|-----------|-------------|
| `while {body}` | `a --` | Continually executes the instructions in `{body}` so long as `a` is true. |
| [`fnn <name> {body}`](./keyword-examples/function.md) | `--` | Creates a new function with the name `<name>`. |
| `if {body} [else {else-body}]` | `a --` | Conditionally executes the instructions in `{body}` if `a` is true, otherwise the instructions in `{else-body}` are executed. |
| [`<name>`](./keyword-examples/function.md) | Unknown | Executes instructions in the body (`{body}`) of a function with the name `<name>`. |

## Meta Operations

| Name | Signature | Description |
|------|-----------|-------------|
| [`file <file-path>`](./keyword-examples/file.md) | `--` | Includes the contents of another Stacko file at `<file-path>`. |
