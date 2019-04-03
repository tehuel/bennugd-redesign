+++
categories = ["functions"]
layout = "function"
modules = ["mod_mem"]
title = "free()"

+++

## Definition

    INT free ( <VOID POINTER data> )

Frees a block of memory.

The [`pointer`]({{< ref "pointer" >}}) used must be a pointer to a previously allocated block of memory, else the behavior of `free()` is undefined.

Also called `mem_free()`.

## Parameters

- VOID POINTER data - [`Pointer`]({{< ref "pointer" >}}) to the block of memory to be freed.

## Returns

INT : true

## Example

```
Program example;
Private
    byte pointer pbyte;
    word pointer pword;
    int  pointer pint;
    int elements = 10;
    int i;
Begin

    // Allocate memory
    pbyte = alloc(elements);
    pword = alloc(elements*sizeof(word));
    pint  = alloc(elements*sizeof(int));

    // Reset memory to 0's
    memset (pbyte,0,elements);
    memsetw(pword,0,elements); // same as  memset(pword,0,elements*sizeof(word));
                               // because value-parameter is 0.
    memset (pint ,0,elements*sizeof(int)); // There isn't a "memseti()", so we need to
                                           // set the individual bytes to 0. To change
                                           // ints to nonzero values, memset() can't be
                                           // used easily

    // Write numbers to bytes and ints
    for(i=0; i<elements; i++)
        pbyte[i]  = 133; // pbyte[i] is the same as *(pbyte+i)
        *(pint+i) = 4555; // pint[i] is the same as *(pint+i)
    end

    // Write numbers to words
    memsetw(pword,345,elements);

    // Show numbers
    for(i=0; i<elements; i++)
        say("byte["+i+"] = " + *(pbyte+i));
        say("word["+i+"] = " + pword[i]);
        say("int ["+i+"] = " + pint[i]);
    end

    Repeat
        frame;
    Until(key(_esc))

    // Free the used memory
    free(pbyte);
    free(pword);
    free(pint);

End
```

Used in example: [`alloc()`]({{< ref "alloc" >}}), memset(), memsetw(), [`sizeof()`]({{< ref "sizeof" >}}), [`say()`]({{< ref "say" >}}), free(), [`pointer`]({{< ref "pointer" >}}).
