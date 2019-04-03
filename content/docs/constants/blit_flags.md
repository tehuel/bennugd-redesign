+++
categories = ["constants"]
layout = "constant"
title = "Blit Flags"

+++

Blit flags are [bit flags]({{< ref "/docs/language/bit_flags" >}}) which can be passed to some map functions, to specify a certain effect when blitting a graphic. These functions are:

- [`xput()`]({{< ref "/docs/functions/xput" >}})
- [`map_xput()`]({{< ref "/docs/functions/map_xput" >}})
- [`map_xputnp()`]({{< ref "/docs/functions/map_xputnp" >}})

They can also be used to specify a certain effect for the blitting of the graphic of a process, by assigning blit flags to its local variable flags.

## List

| Constant | Value | Description |
|---|---|---|
| `B_HMIRROR` | 1 | Blit the graph horizontally mirrored. |
| `B_VMIRROR` | 2 | Blit the graph vertically mirrored. |
| `B_TRANSLUCENT` | 4 | Blit the graph with half transparency. |
| `B_ALPHA` | 8 | Blit the graph in some way. *(What does this do exactly?)* |
| `B_ABLEND` | 16 | Blit the graph using additive blending. Nice effect for fire. |
| `B_SBLEND` | 32 | Blit the graph using subtractive blending. Nice effect for ghosting. |
| `B_NOCOLORKEY` | 128 | Blit the transparent parts of the graph as black (color 0). |
