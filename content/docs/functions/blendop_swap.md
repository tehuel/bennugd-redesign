+++
categories = ["functions"]
layout = "function"
modules = ["mod_blendop"]
title = "blendop_swap()"

+++

## Definition

    INT blendop_swap ( <INT blendTable> )

Modify the [blend table]({{< ref "blend_tables" >}}) by swapping the source and destination sections. This means that the graphic the blend operation is assigned to will appear like what is behind the object and the background will look like the object.

This will swap the source and destination section of the [blend table]({{< ref "blend_tables" >}}).

## Parameters

- INT blendTable - The [blend table]({{< ref "blend_tables" >}}) to apply.

## Returns

INT : true

## Notes

To understand what swapping actually does, consider the following:

- When done a `blendop_swap()` on a just initialized blend table, the graphic it is assigned to will 'disappear'.
