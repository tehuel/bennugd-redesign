+++
categories = ["general", "language"]
title = "TextID"

+++

`TextID` is an identifier associated with a certain text. It is returned by various text functions, like [`write()`]({{< ref "/docs/functions/write" >}}), [`write_int()`]({{< ref "/docs/functions/write_int" >}}), [`write_string()`]({{< ref "/docs/functions/write_string" >}}), [`write_float()`]({{< ref "/docs/functions/write_float" >}}) and [`move_text()`]({{< ref "/docs/functions/move_text" >}}).

When a dynamic text is created, it has the color last set by [`set_text_color()`]({{< ref "/docs/functions/set_text_color" >}}). By default this is white ([`rgb(255,255,255)`]({{< ref "/docs/functions/rgb" >}})). Its `Z` value is equal to `text_z` at the moment of creation, which is `-256` by default.

To move the dynamic text associated with a TextID, use [`move_text()`]({{< ref "/docs/functions/move_text" >}}). To delete the text, use [`delete_text()`]({{< ref "/docs/functions/delete_text" >}}).

## Notes

There can be a total of 512 dynamic texts on screen simultaneously.

## See Also

- [Text]({{< ref "/docs/language/text" >}})
