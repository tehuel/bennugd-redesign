+++
categories = ["functions"]
layout = "function"
modules = ["mod_mem"]
title = "memseti()"

+++

## Definition

    INT memseti ( <VOID POINTER data> , <INT value> , <INT ints> )

Sets all ints in the specified memory block to the specified value.

Also called `mem_seti()`.

## Parameters

- VOID POINTER data   - Pointer to the block of ints in memory.
- INT value   - Value to set all ints to.
- INT ints    - Number of ints to change the value of.

## Returns

INT : true

## See Also

- [`memset()`]({{< ref "memset" >}}).
- [`memsetw()`]({{< ref "memsetw" >}}).
- [`alloc()`]({{< ref "alloc" >}}).
- Also useful in conjunction with [`map_buffer()`]({{< ref "map_buffer" >}}) with 32bit maps. (Example needed.)
