# Custom Functions

Created By: Sean Boerhout

Suppose that you wanted to do something complicated over and over again... not in the sense of looping through something often,
but rather you want a snippet of code to run at many places around your program. 

I'll give you an example: I have two lists of numbers, and I want to added up all the numbers in them. 
``` python
numbers = [1, 5, 3, 8, 9, 3, 7, 4, 8]
more_numbers = [6, 2, 6, 9, 3, 6, 8, 4, 6, 8, 9, 3, 6, 4, 0, 2]
``` 
Instead of using a bunch of explicit arithmetic, we can apply what we learned from the previous lesson to solve this problem:
``` python
numbers_sum = 0
for x in numbers:
  numbers_sum += x
print(numbers_sum)

numbers_sum = 0
for x in more_numbers:
  numbers_sum += x
print(numbers_sum)
```
Output:
``` 
48
82
```

While this did solve the problem for both lists, notice that the only difference between the two for loops is the list we are iterating
through. Since we had to explicitly define which list each for loop would sum, we needed two for loops.

So how can we optimize this? Well, by making our code general and able to be applied to many different applications. This can be done with 
_functions_.

## Functions

A function is a block of code that runs only when it is called and generally contains lengthy code. 

``` python
def my_function():
  # Function code goes here
  print("my_function was run!")

my_function() # function called here
```
Output:
``` 
my_function was run!
```

Now, the code from above (with the lists) can be simplified a little bit, but not really. We can put the for loops in a function to 
minimize the length of computing the sum of a certain list, but since the list being summed must still be explicitly defined in our function,
we'll need to use two functions.

``` python
def sum_numbers():
  numbers_sum = 0
  for x in numbers:
    numbers_sum += x
  print(numbers_sum)

def sum_more_numbers():
  numbers_sum = 0
  for x in more_numbers:
    numbers_sum += x
  print(numbers_sum)

sum_numbers()
sum_more_numbers()
```
Output:
``` 
48
82
```

Notice that `numbers_sum` is the same in both functions. The variable name isn't deemed as repeating because variables initialized (declared and defined)
in functions lie under the function's own scope (local).

### Arguments

Anyway, how can we optimize this? Well, we can pass an _argument_, sometimes known as a _parameter_ to the function. This allows the function to act on 
something that we know will change in multiple contexts. 

``` python
def my_function(argument):
  print(argument)

my_function("Hello")
```
Output:
```
Hello
```
When the function is run, whatever arguments you put in the paratheses get copied to new variables to be used in your function locally. This means that you are never
directly modifying the variable you pass to the function, which means that you can pass different variables depending on what you want to do!

Let's use this new knowledge to create a clean solution to the list summing problem.
``` python
numbers = [1, 5, 3, 8, 9, 3, 7, 4, 8]
more_numbers = [6, 2, 6, 9, 3, 6, 8, 4, 6, 8, 9, 3, 6, 4, 0, 2]

def sum_list(list):
  list_sum = 0
  for number in list:
    list_sum += number
  print(list_sum)

sum_list(numbers)
sum_list(more_numbers)
```
Output:
```
48
82
```

Perfect!

### Returns

In the functions above, we printed out the output of the function, but what if wanted to hold the output of the function as a variable instead?

We could use a _global_ variable (accessible over the entire program) that is modified inside the function like this:
``` python
list_sum = 0
def sum_list(list):
  for number in list:
    list_sum += number
```
But then if we wanted to use the function multiple times, it would become confusing keep track of when list_sum is holding data from a certain function call.

This is where _return_ comes in. Instead of printing the output of the function, we can _return_ it, essentially making the function data available to be stored by a variable.

``` python
def sum_list(list):
  list_sum = 0
  for number in list:
    list_sum += number
  return list_sum

numbers_sum = sum_list(numbers) # store the return as a variable, or
print(numbers_sum)
print(sum_list(more_numbers))   # pass it to a function right away!
```

The advantage of this becomes apparent when we want to perform an operation on the return of a function. Say we wanted to compute the sum of lists (like before), but also the sum
of those sums.

``` python
numbers = [1, 5, 3, 8, 9, 3, 7, 4, 8]
more_numbers = [6, 2, 6, 9, 3, 6, 8, 4, 6, 8, 9, 3, 6, 4, 0, 2]

def sum_list(list):       # same as before
  list_sum = 0
  for number in list:
    list_sum += number
  return list_sum

def sum_list_sums(list1, list2):
  return sum_list(list1) + sum_list(list2)

print(sum_list_sums(numbers, more_numbers))

```
Output:
```
130
```

With functions, we can create highly optimized and clean code. Since they can be applied to any arguments we specify (just of the correct type), it is much easier to write code 
using functions since there is less typing (thus less room for mistakes), but modifications to a function can be applied throughout your code, whereever you have called it. 

__Fun fact:__
The function `sum_list(list)` created above is a built in function called `sum()`. If you ever want to sum a list, just use that. 
