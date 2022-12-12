# Stack Manipulation

## The Stack

Stacko maintains a list of values throughout its lifetime in a list known as the stack. Values can be appended
(*pushed*) and removed (*popped*) from the stack at any time, but can only be done so in a last-in first-out (*LIFO*)
order.

Values on the stack may be used by certain instructions to perform calculations. These calculations may in turn push
more values onto the stack.

To understand this a bit better, lets look at the following example program.

```py
10 5 + dup * printLine
```

When Stacko begins to execute a new program it begins with an empty stack.

```
Stack: [ ]
```

Stack will then proceed to execute the first instruction in our program `#!py 10`. This instruction pushes the
integer value 10 onto the stack.

```
Stack: [ 10 ]
```

The next instruction `#!py 5` likewise pushes the integer value 5 onto the stack.

```
Stack: [ 10 5 ]
```

Both the instructions we've seen so far have simply pushed new values onto the stack. The next instruction we'll look
is the `#!py +` instruction.

The `#!py +` instruction (otherwise known as the add instruction) pops two values off of the stack and then pushes
their sum onto the stack.

### Stack Underflow

Instructions such as the add instruction may assume a certain number of values currently exist on the stack and can
safely be popped off it. This, however, may not always be the case.

Because the add instruction must pop two values off of the stack in order to perform its operation successfully, it
must assume that at least 2 values exist on the stack when it is called.

If these assumptions fail and an instruction attempts to pop a value off of an empty stack an error will occur. This
error is what's known as a stack underflow error. Stack will alert you when these errors occur and halt execution of
the faulty program.

### Stack Signatures

Because understanding how a given instruction will affect the stack is important to preventing errors in programs such
as stack underflows many programming resources (including this one) will annotate instructions with stack signatures.

Here is the stack signature for the add instruction.

```
a b -- c
```

Symbols to the left of the double-dash represent values that the instruction will pop off the stack, while symbols to
the right of the double-dash represent values that the instruction will push onto the stack.

This stack signature tells as the the add instruction expects two values `a` and `b` to be on the stack, and also that
it will push a new value `c` onto the stack before the next instruction in executed.

If two symbols in a stack signature are the same it means that their values will also be the same when executed.

Consider the following stack signature.

```
a -- a a
```

This stack signature tells us that the instruction it is associated with will pop a single value off of the stack then
push it back onto the stack twice.

Symbols may be omitted from either side of the double-dash if no values are pushed or popped respectively.

- `-- a` This instruction pushes a value onto the stack but doesn't pop any values off it.
- `a --` This instruction pops a value off of the stack but doesn't push any values onto it.
- `--` This instruction doesn't push or pop any values onto the stack.

### The Stack (Continued)

Since we currently have the values 10 and 5 on our stack the add instruction will push the integer value 15 onto the
stack as 15 is the sum of 10 and 5.

```
Stack: [ 15 ]
```

The following instruction `#!py dup` pops a value off of the stack and pushed the value back onto the stack twice. This
essentially has the effect of duplicating the top-most value on the stack.

```
Stack: [ 15 15 ]
```

The next instruction `#!py *` (otherwise known as the multiply instruction) functions similarly to the add instruction,
only that it pushes the product of the two top-most values on the stack rather than their sum.

Since we currently have the values 15 and 15 on our stack the multiply instruction will push the integer value 225 onto
the stack as 225 is the product of 15 and 15.

```
Stack: [ 225 ]
```

Finally Stack will execute the final instruction `#!py printLine`.

The `#!py printLine` instruction pops a value off of the stack and writes it to stdout, effectively displaying the
value in your terminal instance.
