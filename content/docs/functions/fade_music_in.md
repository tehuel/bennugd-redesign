+++
categories = ["functions", "songs"]
layout = "function"
modules = ["mod_sound"]
title = "fade_music_in()"

+++

## Definition

    INT fade_music_in ( <INT songID> , <INT num_loops> , <INT ms> )

Fades the music in, stepping up the volume from silence to the main song volume, i.e. set by the [`set_song_volume()`]({{< ref "set_song_volume" >}}) function.

## Parameters

- INT songID - The identification code of the song, returned by [`load_song()`]({{< ref "load_song" >}}).
- INT num_loops - The number of loops, a value of `-1` will be an infinite loop.
- INT ms - Microseconds of fading (the duration).

## Returns

INT : Error.

- `-1` - Error: sound inactive.

## See also

- [`fade_music_off()`]({{< ref "fade_music_off" >}})
