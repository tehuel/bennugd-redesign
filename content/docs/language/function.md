+++
categories = ["general", "language", "keywords", "basic statements"]
title = "Function"
syntax_legend = "true"

+++

## Syntax

```
Function <returntype> <name> ( [ <parameters> ] )
[ Public

    [ <public variables> ]

End ]
[ Private

    [ <private variables> ]

End ]
Begin

    [ <function code> ]

[ OnExit

    [ <exit code> ]

]
End
```

| Notation | Description |
|---|---|
| `< ... >` | item |
| `[ ... ]` | optional |
| `( ... )*` | 0 or more times |
| `( ... )+` | 1 or more times |

## Description

`function` is a reserved word used to start the code of a function.

A function is a subroutine to which one or more of the following apply:

- it receives parameters
- it acts on the parameters
- it processes data located elsewhere
- it returns a value

The difference between a function and a [process]({{< ref "process" >}}) is that the calling process or function waits until the function is completed. When a process or function calls a process, it doesn't wait. This means that, even when the called function contains `frame;` statements, the calling function or process still waits for the function to finish. This is shown in this tutorial.

For a list of functions, see this list of functions.

## Example

```
function int addInts( int a , int b )
private
    // declare private variables here
end
begin
    // start the function code
    return a+b;
end
```

`addInts(3,6);` will return `9`. One can see that the function does indeed:

- receive parameters.
- act on the parameters.
- returns a [value]({{< ref "value" >}}).
