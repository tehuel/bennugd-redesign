---
title: dirclose()
layout: function
categories:
- functions
divlikes:
- bennugd
module: mod_dir
---

## Definition

    INT dirclose ( <INT handleId> )

Close a directory using a given handle id obtained with [`diropen()`]({{< ref "/docs/functions/diropen" >}}).

## Parameters

INT handleId  - The handle id of a directory.

## Returns

INT : The handle of the opened directory.

- `0` - There was an error.
- `1` - The directory was closed successfully.
