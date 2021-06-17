# If Statements and Operators

Ok, I'll admit it. So far, everything has a been a little boring. Time to add some conditions
to our code!

The `if` statement is crucial to being able to program, and it exists in nearly every programming
language. It allows you to make comparisons in the nature of: _if this, then that_.

Here's an example:
``` python
if 1 == 1:
  print("one equals one");
```
Output:
```
one equals one
```

As you can see, in the example above, a comparison is being made between the value of `1` and `1`. 
Since they were equal to each other, the if statement continued to the next line, which is 
in its __scope__. We'll get to scope a little later. 

### Operators

If you're wondering why the if statement requires double equal signs (`==`), its because it is an
__operator__. __Operators__ are special symbols that perform an arithmetic, comprison, or logical operation
(in this case, comparison).

Some of these you already know! 

#### Arithmetic Operators
``` 
2 + 2 = 4   (+, addition operator)
3 - 2 = 1   (-, subtraction operator)
2 * 1 = 2   (*, multiplication operator)
2 / 1 = 2   (/, the division operator)
2 ** 3 = 8  (**, the exponent operator)
5 % 2 = 1   (%, the modulus operator)
13 // 5 = 3 (//, the floor division operator)
```

#### Comparison Operators
```
3 > 2   (>, the greater than operator)
4 < 5   (<, the less than operator)
4 == 4  (==, the equal to operator)
5 != 6  (!=, the not equal operator)  
5 >=5   (>=, the greater than or equal to operator)
6 <= 7  (<=, the less than or equal to operator)
```

#### Logical Operators
=== "and"

    - returns True when something and something else are true

    ``` python
    x = True
    y = True
    print(x and y)
    ```
    Output:
    ``` python
    True
    ```

=== "or"

    - returns True when something or something else is true

    ``` python
    x = True
    y = False
    print(x or y)
    ```
    Output:
    ``` python
    True
    ```

=== "not"

    - returns the complement (opposite value of) of a variable

    ``` python
    x = True
    print(not x)
    ```
    Output:
    ``` python
    False
    ```

Now let's look at some more examples of if statements.

``` python 
your_age = 40
if your_Age >= 21:
  print("You can drink alcohol");
```
Output:
```
You can drink alcohol
```

``` python 
your_name = "Lars"
if your_name != "Zephyr":
  print("You aren't my cat!");
```
Output:
```
You aren't my cat!
```

### Else

There is another cool thing we can do with if statements, however. What if we want to do something if an if statement isn't triggered?
Well, for that we can use the ```else``` statement:
```python 
your_name = "Zephyr"
if your_name != "Zephyr":
  print("You aren't my cat!");
else:
  print("You are my cat!")
```
Output:
``` 
You are my cat!
```

### Elif

Additionally, you may want to go into another if statement if an else is triggered. For that, we have teh ```elif`` statement, which stands
for "else if".  

```python
name = "Sean"
if name == "Jonathan":
  print("You are my friend")
elif name == "Andrew":
  print("You are my best friend")
elif name == "Sean":
  print("You are me!")
else:
  print("Who are you??")
```
Output:
```
You are me!
```

Notice that the else and the elif statements must come after an if statement. 

### Scope

But how do we organize what is in the if statement and what isn't? Well, we do that with __scope__. 
By indenting with a tab, python will be able to determine what code is a part of other code:

```python
x = True
if x:   # this will always happen because the condition is true!
  print("This is in the if statement")
  print("This is also in the if statement")
  print("This too!")
print("This is not in the if statement")
```
Output:
```
This is in the if statement
This is also in the if statement
This too!
This is not in the if statement
```

The same thing goes for `else` and `elif` statements. 