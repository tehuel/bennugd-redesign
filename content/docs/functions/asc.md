+++
categories = ["functions", "strings"]
layout = "function"
modules = ["mod_string"]
title = "asc()"

+++

## Definition

    BYTE asc ( <STRING character> )

Returns the ASCII value of the first character of the string character.

## Parameters

- STRING character - The string of which the ASCII value of the first character will be returned.

## Returns

BYTE : The ASCII value of the first character of the string character.

## Example

```
Program asciis;
Begin

    write(0,0, 0,0,asc("A"));
    write(0,0,10,0,asc("CAT"));

    Repeat
        frame;
    Until(key(_esc))

End
```

Used in example: [`write()`]({{< ref "write" >}}), [`key()`]({{< ref "key" >}})
