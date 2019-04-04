+++
categories = ["variables", "local"]
layout = "variable"
title = "resolution"

+++

## Definition

    INT resolution = 0

Resolution is used to alter the precision of the position of [`process`]({{< ref "process" >}}) on screen; the level of precision is defined by the value of resolution.

This simulating of fractions in positions is useful for calculations or animations in need of a high precision in order to work properly. It causes the coordinates of all processes to be interpreted as being multiplied by the value of the local variable resolution, associated with that [`process`]({{< ref "process" >}}). So when a process' [`graphic`]({{< ref "graph" >}}) is displayed, it will appear as if the process' x and y values were divided by the value of resolution.

A resolution of `0` is interpreted as if it were `1`.

The default value of resolution is `0`, so set it to `1` if the correct value is needed.

### Screen Resolution

The resolution of a screen is the dimensions of the screen in pixels.

Bennu's default screen resolution is `320×200` pixels. This can be altered by use of [`set_mode()`]({{< ref "set_mode" >}}).

## Example

```
import "mod_grproc"
import "mod_time"
import "mod_key"
import "mod_video"
import "mod_map"
import "mod_draw"
import "mod_proc"
import "mod_wm"

Process Main()
Begin

    // Set screen resolution to 320x200 with a color depth of 8bit
    set_mode(320,200,8);

    // Set the FPS to 60
    set_fps(60,0);

    // Set resolution for this process (try changing it to see the effect)
    resolution = 100;

    // Create a 200x200 cyan circle and assign its graphID to the local variable graph
    graph = map_new(200,200,8);
    drawing_map(0,graph);
    drawing_color(rgb(0,255,255));
    draw_fcircle(100,100,99);

    // Set size
    size = 10;

    // Set the coordinates at screen position (160,180).
    x = 160 * resolution;
    y = 180 * resolution;

    // Move around in circles while leaving a trail behind
    Repeat
        trail(x,y,graph,(int)(0.2*size),get_timer()+1000); // create a mini reflection of this process,
                                                // lasting one second
        advance(3*resolution); // advance (3 * resolution) units (= 3 pixels)
        angle+=2000; // turn 2 degrees left
        frame;
    Until(key(_ESC)||exit_status)

OnExit

    let_me_alone();
    map_unload(0,graph);

End

Process trail(x,y,graph,size,endtime)
Begin

    // Get the resolution of the process calling this one
    resolution = father.resolution;

    // Remain existent until the specified endtime was reached
    Repeat
        frame;
    Until(get_timer()>=endtime)

End

```

Used in example: [`set_mode()`]({{< ref "set_mode" >}}), set_fps(), map_new(), drawing_map(), drawing_color(), draw_fcircle(), get_timer(), key(), let_me_alone(), map_unload(), advance(), resolution, graph, size, x, y, angle, exit_status