+++
categories = ["general", "language"]
title = "Blend Operations"

+++

A blend operation is the act of executing the blending of a graphic (source) with the pixels the graphic is drawn on (target) using a [blend table]({{< ref "blend_tables" >}}).

This is done in two ways:

- The blendop is performed explicitly using blendop_apply(), modifying the graphic.
- The blendop is assigned to a graphic and performed implicitly when that graphic is drawn. This method is not available for modes lower than 16bit.

Blendops are not supported in 32bit mode.