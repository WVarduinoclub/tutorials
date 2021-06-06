# The Basics
Created by: Sean Boerhout

### Variables and Data Types

So where do we start? Well, nearly all programming involves __variables__, or snippets of 
memory in your computer that holds some data. Say I wanted to take user input, or record the 
number of times someone pressed a button. You'd need variables to do this!

Let's start with a simple example: the number of minecraft worlds I have on my computer to date, which is 27.
``` python
minecraft_world_count = 27
```
Here, ```minecraft_world_count``` is my variable, and it holds a number (an integer to be exact). Different types of 
data need to be held with different types of variables; for example, 1.1 isn't an integer anymore, it's a rational 
number (in coding terms, a floating-point number). 

Another cool thing in python is that you can easily represent large numbers. Whenever you assign a number to a variable,
you can't use commas to make it easily readable. For example, 

``` python
myNumber = 100,000
```

Will actually cause python to think that your number is of type __tuple__, which is a data type that doesn't allow
you to change its value. To tell python that the number is still an integer you can do this:

``` python
my_number = 100_00
```

### Printing

Now, suppose I wanted to print the value of a variable as an output. Python has a useful __function__ called ```print()``` for
this, so 

``` python
print(myNumber)
```

will output ```100000```.

If I wanted to combine a string with the number, all you need to do is pass another __argument__ (what ```print()``` will print)
to ```print()```.

``` python
print("My number is ", myNumber)
```
Output:
```
My number is 100000
```

One more thing: what if we wanted to format a string into different parts i.e. number here, string there without using commas? 
Python allows us to do this super easily too:

``` python
print(f"My number is { myNumber }")
```
Output:
```
My number is 100000
```
Python recognizes that you wanted a formatted string by prefixing the string with an _f_. Then you can use curly braces to say where
you want the number! (You'll see how awesome this is in future lessons).

### Strings

Say I wanted to give my favorite world a name, and hold that name in a variable. I could do it like this:
```
minecraft_world_name = "Zombie manhunt"
```
And in this case, the variable would be of type ```string```. 

In python, strings are neat because you can add characters to them like this:

``` python
my_name = "Bill"
my_full_name = my_name + " Mitchell"
print(my_full_name)
```
Output:
```
Bill Mitchell
```

There are also some cool __methods__ to modify strings:

=== "upper()"
    
    - Makes a string uppercase

    ``` python
    rock = "let's rock"
    print(rock.upper())
    ```
    Output:
    ```
    LET'S ROCK 
    ```

=== "lower()"

    - Makes a string lowercase

    ``` python
    fruit = "APPLES"
    print(fruit.lower())
    ```
    Output:
    ```
    apples
    ```

=== "title()"

    - Capitalizes a string

    ``` python
    my_name = "bill mitchell"
    print(my_name.title())
    ```
    Output:
    ```
    Bill Mitchell
    ```

### Booleans

One more example: suppose I wanted to say whether python is cool. I could use a ```boolean``` type variable:
```python_is_awesome = True```

### Type Function

If you ever want to know what the type of something is, then you can use a function called ```type()```. This
outputs the type of the variable:

``` python
print(type(1))
print(type(1.1))
print(type(1000000000))
print(type("one"))
print(type([1,2,3,4]))  # Coming next lesson!
```
Output:
``` python
<type 'int'>
<type 'float'>
<type 'int'>
<type 'str'>
<type 'list'>
```




### Basic Arithmetic

So... pure variables are boring - you've probably figured that out by now. Can we modify them?

In fact, yes! And it's super easy. Whenever you modify a variable, python essentially overrides one of the variables. 
Say I just made a new minecraft world. To add another world, I'd just do:

``` python
minecraft_world_count = minecraft_world_count + 1
```

Super easy! Since programmers use this kind of arithmetic very often, however, there is shorthand notation for this:

``` python
minecraft_world_count += 1
```

``` python
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
```  python
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