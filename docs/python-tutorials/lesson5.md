# For and While loops

Created By: [Sean Boerhout](https://seanboe.github.io)

Suppose we have a list of strings and want to perform an operation involving every element of that string; maybe, printing out the names of 
everyone in a school classroom:
``` python
students = ["Suzie", "Ayush", "David", "Sid", "Brian"]
```
We could do it by explicitly printing out every element of the list:
``` python
print(students[0])
print(students[1])
print(students[2])
print(students[3])
print(students[4])
```
Output:
```
Suzie
Ayush
David
Sid
Brian
```
But this can become much more complicated as the operations being performed on/with the elements in the list become more complex. 
A good example is something with a 2d array (an array that holds other arrays):
``` python
math_students = ["Sean", "Brian"]
literature_students = ["Justin", "Ava"]
all_students = [math_students, literature_students]

print(all_students[0][0])     # The first index is for the host array (all_students),
print(all_students[0][1])     # the second index is for the array inside the host
print(all_students[1][0])     # (math_students or literature_students)
print(all_students[1][1])
``` 
Output:
```
Sean
Brian
Justin
Ava
```

What we'd really like to do is perform the same explicit operation but to different indexes of the array. 
You could imagine a solution to this quite easily; simply have the same code involving the index of an array, 
but increase the index automatically. That's what a loop can do!

## For Loops

__For Loops__ allow you to repeat something __for__ a set number of iterations.

Let's take a look at some real examples.
``` python
for x in range(0, 10):
  print(x)
```
Output:
```
0
1
2
3
4
5
6
7
8
9
```
`in` can be a very useful for looping a set number of times. It assigns x to every element in a list, set, dictionary, etc. 
there are no more elements. That means that you can loop the number of times x could be assigned to something! Note that 
the variable doesn't need to be x; it can be anything. Python makes a new local variable (to be used inside the for loop) for
whatever name you choose to assign the variable. 

In the case above, x is assigned to every output of `range()`. `range()` counts up in increments of one starting at the first argument
and ending at the last argument. Note that it includes the first argument but not the last. 

Let's apply this new knowledge to the issues illustrated above.
``` python
students = ["Suzie", "Ayush", "David", "Sid", "Brian"]

for student in students:
  print(student)
```
Output:
```
Suzie
Ayush
David
Sid
Brian
```

Simple, right? Using the `range()` function, we could've done the same thing this way:
``` python
students = ["Suzie", "Ayush", "David", "Sid", "Brian"]
for x in range(0, len(students)):    # len() returns the number of indexes in the list
  print(students[x])
```
Output:
```
Suzie
Ayush
David
Sid
Brian
```

Both cases are 3 lines of code, while the solution at the top using many `print()` statements involves 6!

#### Nested Loops

Let's go back to the 2d array problem. Notice that what we want to do is iterate through every index of a nested list,
which is an index of another list itself. Basically, we want to loop through the indexes of the host array, but while 
were in each index of that array, loop again. 

This can be solved with two loops inside each other:
``` python
math_students = ["Sean", "Brian"]
literature_students = ["Justin", "Ava"]
all_students = [math_students, literature_students]

for student_subject in all_students:
  for student in student_subject:
    print(student)
```
Output:
```
Sean
Brian
Justin
Ava
``` 

#### Scope

Scope in python is always the same; whatever is indented falls under the domain of the line above it with one
less indentation. Thus, scope for loops is exactly the same as it is for if statements, which was explained in the 
[previous lesson](https://wvarduinoclub.github.io/tutorials/python-tutorials/lesson4/#scope). 

That's why the 2d array example above works: since the nested loop (second one) falls under the scope of the first,
`student_subject` can be accessed and iterated over by the second loop. 


#### Useful stuff

Don't forget the stuff from other lessons! That can be applied here too:

``` python
students = ["Jose", "Abigail", "George"]

for good_student in students[:2]:
  print(f"{ good_student } is a good student!")
```
Output:
```
Jose is a good student!
Abigail is a good student!
```

## While loops

__While loops__ are just like for loops in the sense that they also loop, however they loop until a condition is met. 

``` python
x = 0
while x < 10:
  x += 1
  print(x)
```
Output:
```
1
2
3
4
5
6
7
8
9
10
```

Like an if statement, you can also add an __else__ statement to run when the condition in the while loop is false.

``` python
x = 0
while x < 10:
  x += 1
  print(x)
else: 
  print("x is no longer less than 10")
```
Output:
```
1
2
3
4
5
6
7
8
9
10
```

The great thing about while loops that you can make your program essentially stop at one issue and wait/repeatedly attempt 
to resolve the issue. For Arduinos, for example, you can wait to print something to the Serial console until a serial connection
has been established:

``` cpp
// In void setup()
Serial.begin(9600);   // This is c++, not python,
while (!Serial)       // but the concept of the while
  delay(10);          // still applies.
Serial.println("Serial port open");
```
But this can also be a huge problem; you need to make sure that there is always a way to exit the while loop so that your 
program doesn't accidentally get stuck in it! It's possible that your program gets stuck in the while and never finishes...
leaving you with a program that you can't stop!

There are two solutions to this:
1. Create a way to change the _while_ condition externally (outside the while)
2. Create the possibility for the _while_ condition to change internally (inside the while)

In python, the second will apply more often. It's as simple as this:

``` python
number = 10
while number > 5:   # eventually, number will not be less than 5
  number -= 1
``` 

## Flow control

What if something weird happens that forces us to stop a loop or reset an iteration of a loop? Well, we have the __break__ and __continue__ 
statements for that.

### Break

Break statements terminate the loop that they are in. When your program hits a break statement, it immediately exits the loop it is in as 
if the loop finished its last iteration (in the case of for loops) or the loop condition became `False` (in the case of while loops). When you 
have nested loops, the break statement only terminates the loop it is directly in, not loops enclosing a loop the break is in. 

Breaks are most commonly used to signify an error, or respond to a change that requires the end of a repetitive function. 

``` python
for x in range(0, 9):
  print(x)
  if x == 5:
    break
print("The for loop looped 6 times")
```
Output:
``` 
0
1
2
3
4
5
The for loop looped 6 times
```
 
### Continue

Continue statements end the current iteration of a loop without terminating it completely. If you raise a flag somewhere in your loop and don't want 
the rest of the loop to act on the flag, you may want to use a continue. 

``` python
x_greater_than_five = False
for x in range(0,9):
  if x == 5:
    x_greater_than_five = True  # This is only used on the NEXT loop
    continue
  print(f"x is {x}. Is x greater than five? {x_greater_than_five}")
```