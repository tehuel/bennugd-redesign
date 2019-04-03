+++
categories = ["functions"]
layout = "function"
modules = ["mod_blendop"]
title = "blendop_free()"

+++

## Definition

    INT blendop_free ( <INT blendTable> )

Frees the given [blend table]({{< ref "blend_tables" >}}). Before doing this, make sure it is not assigned to a graphic.

## Parameters

- INT blendTable - The [blend table]({{< ref "blend_tables" >}}) to free.

## Returns

INT : true
