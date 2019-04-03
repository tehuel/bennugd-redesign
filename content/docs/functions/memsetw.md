+++
categories = ["functions"]
layout = "function"
modules = ["mod_mem"]
title = "memsetw()"

+++

## Definition

    INT memsetw ( <VOID POINTER data> , <WORD value> , <INT words> )

Sets all words in the specified memory block to the specified value.

Also called `mem_setw()`.

## Parameters

- VOID POINTER data   - Pointer to the block of words in memory.
- WORD value  - Value to set all words to.
- INT words   - Number of words to change the value of.

## Returns

INT : true

## See Also

- [`memset()`]({{< ref "memset" >}}).
- [`memseti()`]({{< ref "memseti" >}}).
- [`alloc()`]({{< ref "alloc" >}}).
- Also useful in conjunction with [`map_buffer()`]({{< ref "map_buffer" >}}) with 16bit maps. (Example needed.)
