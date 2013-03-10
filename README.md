# Squad vs Squad

Is a successor of [Agent vs Agent](https://github.com/Velrok/Agent-vs-Agent)(AvA).

Like AvA Squad vs Squad is a programming game. The rules a very similar:

## Rules of the Game

### The Goal

The goal is to write a squad of processes that collect all the point randomly distributes on a 2D field faster than the other squad.


### The Field

It is a configurable `<width> x <height>` donat, which means stepping out on one side will port you back to the other side (top-> bottom, left -> right, and so forth).

For programmers:

```
get_position(x, y):
  return [x % width , y % height]
```

### The Setup

On the field a configurable amount of *points* is *randomly distributed*.
Each squad has a *home base*. The squad size is configurable.

A *game master process* sets up *one port for each squad member process*. When all members are connected the game starts.


### Playing the Game

The game master will always announce the current surrounding and then ask for an action. The squad member process can then decide to do one of the following:

- move (top, down, left, right)
- communicate
	- a broadcast to all fellow squad members
- collect
	- attempt to collect a point from the current position
	- one squad member can only carry one point at a time
	- entering the home base with a point will score the point
	
Each action takes time (in milliseconds) how much exactly is jet to define.


### Winning the Game

The squad with the most points wins.
The games ends when all points are scored.


## Getting Technical

All communication is done via *sockets* using the *JSON format*.
A message has to end with a newline and may not contain any newlines inside a message.

### Protocol Definition

Jet to come.


## Running an Example

Jet to come.



## License

Copyright © 2013 FIXME

Distributed under the Eclipse Public License, the same as Clojure.
