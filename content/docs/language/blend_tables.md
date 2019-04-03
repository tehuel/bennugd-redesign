+++
categories = ["general", "language"]
title = "Blend Tables"

+++

A blend table contains the blend data needed to perform the blend between the object (source) and where the object is drawn (destination).

The table contains those two sections: source and destination; these section are added together when blending (the adding function cannot be altered) and the sections can be influenced by the blend operations available.

One can even make homemade blending operations, if one has enough knowledge of the subject, as blendop_new() returns a pointer to the created blend table. This table is constructed like this:

| bytes-start | bytes-end | total | purpose |
|---|---|---|---|
| 0 | 65535 | 65536 | Source section |
| 65536 | 131071 | 65536 | Destination section |

Each pixel of a section represents a colour. When a blend table is initialized, it's done like this:

```
for (i = 0 ; i < 65536 ; i++) source[i] = i ;
for (i = 0 ; i < 65536 ; i++) destination[i] = 0 ;
```

So:

- For the source section the following applies: The nth index has value n.
- For the destination section the following applies: The nth index has value 0.

Blendops are not supported in 32bit mode.
