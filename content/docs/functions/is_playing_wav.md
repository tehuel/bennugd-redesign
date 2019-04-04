+++
categories = ["functions"]
layout = "function"
modules = ["mod_sound"]
title = "is_playing_wav()"

+++

## Definition

    INT is_playing_wav ( INT <channel > )

Checks to see if Bennu is playing a wave file on the indicated Sound_channel, started with [`play_wav()`]({{< ref "play_wav" >}}).

## Parameters

INT channel: The Sound_channel

## Returns

INT : Whether Bennu is playing a wave file at the moment of calling.

- `true` - Bennu is playing a wave file.
- `false` - Bennu is not playing a wave file.
