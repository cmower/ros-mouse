# ros-mouse

This package allows you to recieve mouse events, similar to how the joy node and keyboard packages work (and has been partially modelled on the [ros-keyboard](http://wiki.ros.org/keyboard) package).

Since it uses [Pygame](https://www.pygame.org/) to capture mouse events, a separate window will be opened when the node starts, and this is where all mouse input will be recieved. In other words, the node will recieve mouse events only when this window is focused.

# Node

## `mouse`

### Parameters

* `~screen_width` (int, default: 500)

    The width of the screen, note the screen height is set equal to the width.

* `~hz` (int, default: 50)

    The node sampling frequency.

### Published topics

* `mouse/focused` ([std_msgs/Bool](http://docs.ros.org/en/lunar/api/std_msgs/html/msg/Bool.html))

	True if the display is receiving mouse input, False otherwise.

* `mouse/joy`	([sensor_msgs/Joy](https://docs.ros.org/en/api/sensor_msgs/html/msg/Joy.html))

    The state of the mouse as a `sensor_msgs/Joy` message. Eight elements make up the axes: `pos[x,y], rel[x,y], npos[x,y], nrel[x,y]` where `pos` and `rel` are the cursor position and amount of mouse movement respectively, and `npos`/`nrel` are the normalized versions, i.e. `npos = pos/screen_width` and similarly for `nrel`.

* `mouse/buttondown` (mouse/MouseButton)

    Mouse button-down events.

* `mouse/buttonup` (mouse/MouseButton)

    Mouse button-up events.

* `mouse/wheel` (mouse/MouseWheel)

    Mouse wheel events.

* `mouse/motion` (mouse/MouseMotion)

    Mouse motion events.
