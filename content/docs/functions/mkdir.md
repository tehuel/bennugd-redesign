+++
categories = ["functions"]
layout = "function"
modules = ["mod_dir"]
title = "mkdir()"

+++

## Definition

    INT mkdir ( <STRING directoryname> )

Creates a new directory in the current path of execution with a certain name.

## Parameters

- STRING directoryname - The name of the directory to be created.

## Returns

INT : Success

- `0` (false) - Creating a new directory with the specified name failed.
- `!0` (true)  - Creating a new directory with the specified name succeeded.
