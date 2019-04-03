+++
categories = ["functions"]
layout = "function"
modules = ["mod_blendop"]
title = "blendop_identity()"

+++

## Definition

    INT blendop_identity ( <INT blendopTable> )

Reinitializes the [blend table]({{< ref "blend_tables" >}}) to default.

The source section of the [blend table]({{< ref "blend_tables" >}}) will be the normal object and the destination section will be cleared, removing translucency.

## Parameters

- INT blendTable - The [blend table]({{< ref "blend_tables" >}}) to free.

## Returns

INT : true
