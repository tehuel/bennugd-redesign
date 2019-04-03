+++
categories = ["functions"]
layout = "function"
modules = ["mod_effects"]
title = "blur()"

+++

## Definition

    INT blur ( <INT fileID> , <INT graphID> , <BYTE mode> )

This will make the specified graphic blurry by using a specified mode. It manipulates the graphic directly.

Only 16bit graphics are supported on 16bit video mode.

## Parameters

- INT fileID - The fileID of the file that holds the graphics.
- INT graphID - The graphID of the graphic to convert.
- BYTE mode - The [blur mode]({{< ref "blur_modes" >}}) that is applied to the graphic.

## Returns

INT

- `0` - Invalid graphic or non 16bit graphic used.
- `1` - Success.

## See also

- [Blur Modes]({{< ref "blur_modes" >}})
