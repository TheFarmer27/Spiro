# Spiro creator #

*This project is taken from the book "Python Playground" by Mahesh Venkitachalam.*

Spiro.py creates spiro images using the turtle module.

## Imports ##

Reading the code from top to bottom, we begin with importing "sys", "random", and "argparse" modules. We then import the turtle module to draw the spiro images. We are importing the math module to help set the parameters of each spiro. We are importing the "Image" module from the PIL module so we can save the images that we create. We import the "datetime" module to we can put dates in our filename.

## Classes ##

After importing all modules, we begin creating our program by defining two global classes named "Spiro" and "SpiroAnimator". Both of which have a constructor that gives the general framework for the fucntions in their respective classes.

### Spiro ###

In this class's constructor, we create the turtle object and set the flag "drawingComplete" to False. The parameters of the class are "self", "xc", "yc", "col", "R", "r", and "l".

In the "setParams" function, we set up the parameters for the spiros. For the spiros, the parameters "R" and "r" are representing the radii of the large circle and small circle respectively. For the sake of simplicity, we are setting them to be integers.

The parameter "col" defines the color the spiro is. The parameters "xc" and "yc" define the constants as to where the turtle is placed at the start of drawing of each spiro. The variable "a", which is referenced from the "restart" function, represents the angle the turtle will take when drawing the spiros.

In the "restart" function, the flag "drawingComplete" is set to False. We then show the turtle object, and put it on the canvas. In the function, the variables "x" and "y" are calculated using cos and sin respectively, which both come from the math module. The statement "t.down" puts the turtle in position so that the drawing can begin.

In the "draw" function, a range is used where the angle is converted in radians. The variables "x" and "y" are calculated by using cos and sin function respectively. The psition of the turtle is then set by using the sums of the constants and the variables of each value on the cordinae system.

In the "update" function, we check if any spiros have been drawn. If a spiro has been completed, the function returns the current state. If no spiros have been completed, one step is added to the parameter "a". This is then converted in radians. The variables "x" and "y" are calculated using cos and sin respectively. The turtle's position is then set. One final if statement is used to check if a drawing has been complete after the function has been run.

### SpiroAnimator ###

In this calss's constructor, the parameter "deltaT" is measured in milliseconds. We get both the height and width of the window the animator has to work with using "window_height" and "window_width" from the turtle module. Then we store the spiros as an array.

A range is then used for the number of times the functions are to be looped, as represented by the parameter "N". In the range, the variable "rparams" is set to the function "genRandomParams". The variable spiro list is assigned as Sprio with the all random parameters.

In the "restart" function, we clear all items out of the list "spiros", and set the variable "rparams" as the result of the function "genRandomParams". We then create the function setparams using all random parameters.

In the "genRandomParams" function, we set the width and height. We then set "R" and "r" as random integers. The parameter "l" is a random fraction. The parameters "xc" and "yc" set where the center of the spiro will be. The "col" parameter is stored as a tuple using rgb notation. The function then returns the result.

In the "update" function, the variable nComplete show howmany spiros have been drawn. A range is used to determine how many spiros have been completed. Then we check if the number of spiro completed is the length of the list of needed spiros, the function "restart" is then called.

## Global Functions ##

After the classes we have two global functions, "saveDrawing" and "main".

### saveDrawing ###

In this function, we first hide the turtle object, then generate a unique filename. The picture is being saved as a postscipt file (.eps), which will be converted to a png file.

### main ###

Here is where we take in arguments from the command line. The arguments excpected arguments are "r", "R", and "l". The turtle is then setup with its shape. The title of the window is then set to "Spiros!" the "onkey" function says that if the user presses "s", call the function "saveDrawing". The turtle is told to listen of the key is hit or not.

An if-else statement is then used to determine if any arguments are used before drawing the spiros. If there are no arguments specified, the variable spiroAnim is assigned with the SpiroAnimator with "4" as the given number of spiros. Then two onkey functions are set for calling the "toggleTurtles" and "restart" functions.

Finally, we check if the function is called from the command line.