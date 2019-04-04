+++
categories = ["functions", "songs"]
layout = "function"
modules = ["mod_sound"]
title = "fade_music_off()"

+++

## Definition

    INT fade_music_off ( <INT ms> )

Fades off the song, played by [`play_song()`]({{< ref "play_song" >}}).

## Parameters

- INT ms - Microseconds of fading (the duration).

## Returns

INT : Error.

- `-1` - Error: sound inactive.

## See also

- [`fade_music_in()`]({{< ref "fade_music_in" >}})
