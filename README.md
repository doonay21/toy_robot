# Toy Robot Simulator

Please provide your source code, and any test code/data
you using in developing your solution.

Do not create a pull request against this repository.

Please engineer your solution to a standard you consider
suitable for production.

## Description

* The application is a simulation of a toy robot moving
on a square tabletop, of dimensions set up with first command, eg. 5 units by 5 units.
* There are no other obstructions on the table surface.
* The robot is free to roam around the surface of the table,
but must be prevented from falling to destruction.
Any movement that would result in the robot falling
from the table must be prevented, however further
valid movement commands must still be allowed.

## Task

Create an application that can read in commands of the following form:

```
SIZE W,H
PLACE X,Y,F
MOVE
LEFT
RIGHT
REPORT
```

* `SIZE` will set the board dimensions W (width) and H (height)
* W and H arguments for `SIZE` command have to be in 2..9 range
* The first valid command to the robot is a `SIZE` command.
The application should discard all commands in the sequence
until a valid `SIZE `command has been executed.
* `SIZE` can be executed only once, any other `SIZE` commands shoul be discarded.
* `PLACE` will put the toy robot on the table in position X,Y
and facing `NORTH`, `SOUTH`, `EAST` or `WEST`.
* The origin (0,0) can be considered to be the `SOUTH WEST` most corner.
* The second valid command to the robot is a `PLACE` command,
after that, any sequence of commands may be issued, in any order,
including another `PLACE` command.
The application should discard all commands in the sequence
until a valid `PLACE `command has been executed.
* `MOVE` will move the toy robot one unit forward
in the direction it is currently facing.
* `LEFT` and `RIGHT` will rotate the robot 90 degrees
in the specified direction
without changing the position of the robot.
* `REPORT` will announce the X,Y and F of the robot.
This can be in any form, but standard output is sufficient.

* A robot that is not on the table can choose
to ignore the `MOVE`, `LEFT`, `RIGHT` and `REPORT` commands.
* Input can be from a file. In this case filename has to be taken from command line arguments.
* If filename is not given input has to be taken from "Standard Input".
* Provide test data to exercise the application.
* It is not required to provide any graphical output
showing the movement of the toy robot.

## Constraints

The toy robot must not fall off the table during movement.
This also includes the initial placement of the toy robot.
Any move that would cause the robot to fall must be ignored.

Example Input and Output:

```
# Example a
PLACE 0,0,NORTH
MOVE
REPORT
# Output: 0,1,NORTH
```


```
# Example b
PLACE 0,0,NORTH
LEFT
REPORT
# Output: 0,0,WEST
```


```
# Example c
PLACE 1,2,EAST
MOVE
MOVE
LEFT
MOVE
REPORT
# Output: 3,3,NORTH
```

## Acknowledgement

The Toy Robot Challenge was originally formulated by [Jon Eaves](https://twitter.com/joneaves)
