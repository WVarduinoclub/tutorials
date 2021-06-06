# The Basics
Created by: Sean Boerhout

### Variables and Data Types

So where do we start? Well, nearly all programming involves __variables__, or snippets of 
memory in your computer that holds some data. Say I wanted to take user input, or record the 
number of times someone pressed a button. You'd need variables to do this!

Let's start with a simple example: the number of minecraft worlds I have on my computer to date, which is 27.
```
minecraft_world_count = 27
```
Here, ```minecraft_world_count``` is my variable, and it holds a number (an integer to be exact). Different types of 
data need to be held with different types of variables; for example, 1.1 isn't an integer anymore, it's a rational 
number (in coding terms, a floating-point number). 

Another cool thing in python is that you can easily represent large numbers. Whenever you assign a number to a variable,
you can't use commas to make it easily readable. For example, 

```
myNumber = 100,000
```

Will actually cause python to think that your number is of type __tuple__, which is a data type that doesn't allow
you to change its value. To tell python that the number is still an integer you can do this:

```
my_number = 100_00
```

### Printing

Now, suppose I wanted to print the value of a variable as an output. Python has a useful __function__ called ```print()``` for
this, so 

```print(myNumber)```

will output ```100000```.

Say I wanted to give my favorite world a name, and hold that name in a variable. I could do it like this:
```
minecraft_world_name = "Zombie manhunt"
```
And in this case, the variable would be of type ```string```. 

In python, strings are neat because you can add characters to them like this:

```
my_name = "Bill"
my_full_name = my_name + " Mitchell"
print(my_full_name)
```
Output:
```
Sean Boerhout
```

One more example: suppose I wanted to say whether python is cool. I could use a ```boolean``` type variable:
```python_is_awesome = True```

### Basic Arithmetic

So... pure variables are boring - you've probably figured that out by now. Can we modify them?

In fact, yes! And it's super easy. Whenever you modify a variable, python essentially overrides one of the variables. 
Say I just made a new minecraft world. To add another world, I'd just do:

```minecraft_world_count = minecraft_world_count + 1```

Super easy! Since programmers use this kind of arithmetic very often, however, there is shorthand notation for this:

```minecraft_world_count += 1```

```
+= # variable = variable + increment
-= # variable = variable - increment
*= # variable = variable * increment
/= # variable = variable / increment
```

### Commenting

What if you have code and you want to write a description about it? Just writing next to it won't work because python
will think that you're still trying to code. In this case, you can use __comments__. Simply prefix any words/sentences/phrases
with a hashtag: ```#```. For bulk commenting, you can use three quotes.

Example:
``` 
# My name is Zephyr:
print("My name is Zephyr!")

"""
Do you like striders in minecraft?
I do... they are fun, but could use
more health. On a scale of 1-10, 
this is how much I like striders:
"""
print(7)
```