+++
categories = ["functions"]
layout = "function"
modules = ["mod_grproc"]
title = "collision_box()"

+++

## Definition

    INT collision_box ( <INT processID|processTypeID> )

Checks if a [`process`]({{< ref "process" >}}) collided with the [`process`]({{< ref "process" >}}) calling `collision_box()`.

When a `processTypeID` is specified, there could be multiple fitting collisions. In this case, `collision_box()` returns a `processID` on each subsequent call, until it returns `0`. This can be reset by use of the `frame;` statement, and in such case, `frame(0);` can be handy.

The diference between `collision_box()` and [`collision()`]({{< ref "collision" >}}) is that `collision_box()` only checks the distance with the edges of the processes, on the other side `collision()` check pixel by pixel between these processes. Consequently, `collision_box()` is faster, but less accurate than `collision()`.

## Parameters

- INT processID|processTypeID - The ProcessID of the [`process`]({{< ref "process" >}}) or the ProcessTypeID of the type of processes to be checked.

## Returns

INT : The ID of the collided [`process`]({{< ref "process" >}}).

- `0` - No collision
- `>0` - The processID of the [`process`]({{< ref "process" >}}) colliding with the current [`process`]({{< ref "process" >}})

## See Also

See also [`collision()`]({{< ref "collision" >}}) and [`collision_circle()`]({{< ref "collision_circle" >}}).

## Example

```
Process SpaceShip( int file , int graph , int x , int y , int angle , int maxspeed , int maxturnspeed )
Private
    int speed;
    int collisionID;
    string text;
Begin
    write_string(0,0,0,0,&text);
    Loop
        // Handle movement
        speed+=key(_up)*(speed<maxspeed)-key(_down)*(speed>-maxspeed);
        angle+=(key(_left)-key(_right))*maxturnspeed;
        advance(speed);
        // Handle collision_box
        if( (collisionID = collision_box(type main)))
            text = "collision with: " + collisionID;
        else
            text = "no collision";
        end
        frame;
    End
End

Process Main()
Private
    int map;
Begin

    // Create the graph for the ship
    map = map_new(20,20,8);
    map_clear(0,map,rgb(0,255,255));

    // Create the graph for the Main process
    graph = map_new(50,50,8);
    map_clear(0,graph,rgb(255,255,0));

    // Position the main process and create the ship
    x = y = z = 100;
    SpaceShip(0,map,100,100,0,20,5000);

    Repeat
        frame;
    Until(key(_ESC))

    let_me_alone();

End
```

Used in example: [`write_string()`]({{< ref "write_string" >}}), [`key()`]({{< ref "key" >}}), [`collision_box()`]({{< ref "collision_box" >}}), [`map_new()`]({{< ref "map_new" >}}), [`map_clear()`]({{< ref "map_clear" >}}), [`advance()`]({{< ref "advance" >}}), [`let_me_alone()`]({{< ref "let_me_alone" >}}), graph, type.
