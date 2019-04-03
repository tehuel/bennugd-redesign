+++
categories = ["functions"]
layout = "function"
modules = ["mod_mem"]
title = "memmove()"

+++

## Definition

    INT memmove ( <VOID POINTER destination> , <VOID POINTER origin> , <INT size> )

Copies a certain number of bytes from one point in memory to another.

Difference between `memmove()` and [`memcopy()`]({{< ref "memcopy" >}}) is that the first one can be used if the destination section and origin section overlap. With [`memcopy()`]({{< ref "memcopy" >}}), this can go wrong, though some systems make [`memcopy()`]({{< ref "memcopy" >}}) safe too.

Also called `mem_move()`.

## Parameters

- VOID POINTER destination - Pointer to the first byte of the destination.
- VOID POINTER origin - Pointer to the first byte of the origin.
- INT size - The size of the to be copied memory in bytes.

## Returns

INT : true

## Example

```
import "mod_mem"
import "mod_say"

Const
    elements = 5;
End

Process Main()
Private
    byte bytearray[elements-1];
    byte* pbyte;
    int i;
End
Begin

    // Allocate memory
    pbyte = alloc(elements);

    // Set numbers
    for(i=0; i<elements; i++)
        bytearray[i] = i;
    end

    // Copy bytes to bytearray
    memmove(pbyte,&bytearray[0],elements);

    // Show numbers
    for(i=0; i<elements; i++)
        say("byte["+i+"] = " + pbyte[i]);
    end

OnExit

    // Free the used memory
    free(pbyte);

End
```

Used in example: [`alloc()`]({{< ref "alloc" >}}), `memmove()`, [`say()`]({{< ref "say" >}}), [`free()`]({{< ref "free" >}}), [`pointer`]({{< ref "pointer" >}})
