---
title: say()
categories:
- functions
- debug
divlikes:
- bennugd
module: mod_say
---

## Definition

	INT say ( <STRING message> )

Prints message to stdout (console).

 - Similar to `System.out.println(message)` in Java.
 - Similar to `printf("%s\n",message)` in C

## Parameters

- STRING message - The message to print to stdout

## Returns

- (INT) `true`
	- 0 There was an error.
	- >0 The handle of the opened directory.

## Example

```
import "mod_say"

Process Main()
Begin
    Say("Hello World!");
End
```

This will result in the output on console:

>Hello World!
