---
title: chdir()
layout: function
categories:
- functions
divlikes:
- bennugd
module: mod_dir
---

## Definition

    INT chdir ( <STRING directoryname> )

Sets the current path of execution.

## Parameters

- STRING directoryname  - The name of the directory to be entered from the current path of execution or a new path of execution.

## Returns

INT : Success

- `0` - Setting of current path of execution succeeded.
- `!0` - Setting of current path of execution failed.

## Example

```
import "mod_dir"
import "mod_say"
import "mod_key"

Process Main()
Begin

    say(CD());
    ChDir("..");
    say(CD());

    Repeat
        frame;
    Until(key(_ESC))

End
```

Used in example: [`cd()`]({{< ref "/docs/functions/cd" >}}), [`chdir()`]({{< ref "/docs/functions/chdir" >}}), [`say()`]({{< ref "/docs/functions/say" >}}), [`key()`]({{< ref "/docs/functions/key" >}})
