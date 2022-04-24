# Turtle Graphics

* Goal: to develop a simple simulation with Turtle Graphics
* The use of 
  * functions and methods
  * parameters, abstractions
  * simulation to explore behavior
* Using JES (MediaComputation) version 6.0  https://github.com/gatech-csl/jes/releases


## Example 1: Worlds and Turtles

```html
<!-- return values... -->
<!-- functions return values -->
def newTurtle():
  w = makeWorld(500, 500)
  t = makeTurtle(w)
  return t
```
* now  t = newTurtles()  creates a world, turtle and returns it
* w = makeWorld(500, 500) creates a world with 500x500 space large

### Moving turtles

```html
<!-- Moving turtles -->
>>> t = newTurtle()
>>> t.forward()
>>> t.setBodyColor(red)
>>> t.setColor(red)
>>> t.turnRight()
>>> t.forward()
>>> t.setPenWidth(4)
>>> t.forward()
```
* forward(t,d) - move t forward d units, default is 100
* turnRight(t) - turn t 90 degrees to the right

* functions also available as methods off the turtle itself
* forward(t) - t.forward()

### Information about each turtle

* Each turtle has a series of attributes that are "stored" within the turtle 
  * Location - each turtle has its own location   t.getXPos(),  t.getYPos()
  * Color - each has its own color: t.setBody Color (red)
  * Width of the pen: t.setPenWidth (2)
  * Pen Up/Down: t.penDown() or t.penUp() or t.clearPath()
  * Control visibility t.hide(), t.show(), t.isVisible()


## Example 2: Move turtles
* Create a world and put turtles in it
* Define our own move that will move the turtle and turn randomly
```html
<!-- Define our own move -->
def move(t):
t.turn(random.randint (-45, 45))
t.forward(50)
...
```
![](https://github.com/TianbinLiu/Tianbin-Github/blob/github_pages/images/AAP3Coordinates.png?raw=true)


## Example 3: Simulation
* Create a number of turtles
  * Each moves a different direction (randomly selected)
  * Each a different color

* Let them run around and see what happens
![](https://github.com/TianbinLiu/Tianbin-Github/blob/github_pages/images/AAp3Simulation.png?raw=true)


## Example 4: Simulation
* Same simulation but ... now if two turtles are near each other, then one of them hides
  * hide the turtle
  * hide the path
* Let them run around and see what happens
![](https://github.com/TianbinLiu/Tianbin-Github/blob/github_pages/images/AAP3Simulation2.png?raw=true)


## Example 5: CSPTurtle
* Create an object oriented turtle that can keep some information internally
  * counter that when turtle hides, it stays hidden for number of cycles, then comes back
```html
<!-- new methods -->
# is t afraid of other
t.afraid(other) : true/false

# hide t
t.hideMe()

#run again (if enough time has lapsed)
t.runAgain()
```


# Wrapping up
* Functions can return values that can be used for other purposes
* Functions can be used to build (encapsulate) common behavior to facilitate reuse
* The names of the functions become like a mini language to describe the problem
* Classes can encapsulate data/functions to make your code easier to read