+++
categories = ["functions"]
layout = "function"
modules = ["mod_grproc"]
title = "get_dist()"

+++

## Definition

    INT get_dist ( <INT processID> )

Returns the distance between the coordinates of a certain [`process`]({{< ref "process" >}}) and the [`process`]({{< ref "process" >}}) calling `get_dist()`.

The distance returned is converted to the [`resolution`]({{< ref "resolution" >}}) of the [`process`]({{< ref "process" >}}) calling `get_dist()`.

## Parameters

- INT processID - The other [`process`]({{< ref "process" >}}).

## Returns

INT : The wanted distance.

- `-1`  - An error occurred: invalid [`process`]({{< ref "process" >}}).
- `!-1`  - The wanted distance.

## Example

```
Program angling;
Const
    screen_width     = 320;
    screen_height    = 200;
    screen_depth     = 8;
    screen_fps       = 60;
    screen_frameskip = 0;
Global
    int distance;
    int tempID;
Begin

    // Set the screen mode
    set_mode(screen_width,screen_height,screen_depth);
    set_fps(screen_fps,screen_frameskip);

    // Change this to see what happens
    resolution = 100;

    // Create mouse graph and start mousepointer
    x = map_new(20,20,screen_depth);
    map_clear(0,x,rgb(255,0,0));
    mousepointer(0,x);

    // Create arrow, assign to graph
    graph = map_new(30,30,screen_depth);
    drawing_map(0,graph);
    drawing_color(rgb(0,255,0));
    draw_line( 0,29,29,30/2);
    draw_line( 0, 0,30,30/2);

    // Set position
    x = screen_width /2 * resolution;
    y = screen_height/2 * resolution;

    // Display distance
    write(0,0,0,0,"Distance:");
    write_int(0,60,0,0,&distance);

    // Always point to the mouse
    Repeat
        // Get the angle and distance between this process' coordinates and those of mousegraph.
        // We can use TYPE and get_id() here, because usually there would only be one
        // mousepointer and one always.
        tempID = get_id(type mousepointer);
        angle = get_angle(tempID);
        distance = get_dist(tempID);
        frame;
    Until(key(_esc))

End

/**
 * Follows the mouse coordinates. x is always mouse.x and y is always mouse.y
 * for processes with priority <1. The graphic of this process will be a certain graphic.
 * int file     - The fileID of the file where the graphic is located
 * int graph    - The graphID of the graphic to be used for this process
 */
Process mousepointer(int file,int graph)
Begin
    // Set the priority to 1, because we first want to have the correct coordinates of
    // the mouse set in this process. Then after that other process can use those coordinates.
    priority = 1;
    // Obtain father's resolution
    resolution = father.resolution;
    // Loop
    Loop
      // Obtain X and Y coordinates of the mouse and adjust for resolution
        // (mouse.y and mouse.y have an unchangeable resolution of 1)
        x = mouse.x * resolution;
        y = mouse.y * resolution;
        frame;
    End
End
```

Used in example: [`set_mode()`]({{< ref "set_mode" >}}), [`map_new()`]({{< ref "map_new" >}}), [`map_clear()`]({{< ref "map_clear" >}}), [`drawing_map()`]({{< ref "drawing_map" >}}), [`drawing_color()`]({{< ref "drawing_color" >}}), [`draw_line()`]({{< ref "draw_line" >}}), [`write()`]({{< ref "write" >}}), [`write_int()`]({{< ref "write_int" >}}), [`get_id()`]({{< ref "get_id" >}}), [`get_angle()`]({{< ref "get_angle" >}}), [`get_dist()`]({{< ref "get_dist" >}}),resolution, mouse, graph, x, y, angle, priority

This example could also be done with [`fget_dist()`]({{< ref "fget_dist" >}}), which is easier and doesn't require an extra process. It also give a much more accurate distance when the resolution is `>1`.

> Resolution is 100:
> http://wwwhome.cs.utwente.nl/~bergfi/fenix/wiki/get_angle.PNG VS http://wwwhome.cs.utwente.nl/~bergfi/fenix/wiki/fget_angle.PNG
> get_angle() and get_dist() with a process   fget_angle() and fget_dist()
