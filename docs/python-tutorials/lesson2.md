# Lists, Sets, Dictionaries, and Tuples

Created By: [Sean Boerhout](https://seanboe.github.io)

### Lists
We've already learned about variables, which allow us to store data in different chunks of memory. But what if 
there are a whole bunch of varaibles that are actually related to each other? Suppose I wanted to list my favorite animals.
I could do it like this:

``` python
my_favorite_animal1 = "Tiger"
my_favorite_animal2 = "Turtle"
my_favorite_animal3 = "Elephant"
my_favorite_animal4 = "Dolphin"
```

But this isn't very nice; the variables are essentially all the same, except holding my next favorite animal. To 
make this more readable, we can use a __list__.

``` python
my_favorite_animals = ["Tiger", "Turtle", "Elephant", "Dolphin"]
#                     ^         You must use brackets          ^
```

The cool thing about this is that there is no need to have a bunch of variables, because all the data is essentially
held in one. 

#### Indexing

But how do I get each variable out? For that, we need to talk about __index__. The index of one of each item in a list
is where it lies in the list. It's super simple; the first item in the list has an index of 0, and the rest have an index
of 1 + (previous index). For the example above, ```"Tiger"``` has an index of 0, ```"Turtle"``` has an index of 1, etc.

``` python
my_most_favorite_animal = my_favorite_animals[0]  # Tigers
print(my_most_favorite_animal)
```
Output:

```
Tiger
```

You can also use a negative number as an index... what do you think this means?

``` python
my_least_favorite_animal = my_favorite_animals[-1]
print(my_least_favorite_animal)
```
Output:
``` python
Dolphin
```
That's right! Negative numbers start form the back of the list.

We can also use colons, to specify a range:
``` python
print(my_favorite_animals[:])
print(my_favorite_animals[0:3])
print(my_favorite_animals[1:])
print(my_favorite_animals[:3])
print(my_favorite_animals[:-1])
```
Output:
``` python
['Tiger', 'Turtle', 'Elephant', 'Dolphin']
['Tiger', 'Turtle', 'Elephant']
['Turtle', 'Elephant', 'Dolphin']
['Tiger', 'Turtle', 'Elephant']
['Tiger', 'Turtle', 'Elephant']
```
Each number on the sides of the colon specify the start/endpoints of the range of numbers. The number 
in front of the colon will always be included, the number behind the colon won't be included (but the 
number before it will).

#### Modifying Elements

Like normal variables, you can also override certain elements in a list:

``` python
my_favorite_animals = ["Tiger", "Turtle", "Elephant", "Dolphin"] # original
my_favorite_animals[0] = "blue whale"
print(my_favorite_animals)
```
Output:
``` python
['blue whale', 'Turtle', 'Elephant', 'Dolphin']
```

And you can do basic arithmetic with them too!

=== "Strings"

    ``` python
    print("My favorite animal is " + my_favorite_animals[0])
    ```
    Output:
    ``` python
    My favorite animal is blue whale
    ```

=== "Numbers"

    ``` python
    bananas_every_day = [2, 1, 1, 3, 2, 5, 6]
    print("I ate ", bananas_every_day[1] + bananas_every_day[2], " bananas on Monday and Tuesday")
    ```
    Output:
    ``` python
    I ate  2  bananas on Monday and Tuesday
    ```

#### Useful Methods

There are also some cool __methods__ that can be used to modify lists:

=== "append()"

    - Adds an element to the end of a list

    ``` python
    my_favorite_animals.append("Hyena")
    print(my_favorite_animals)
    ```
    Output:
    ``` python
    ['Tiger', 'Turtle', 'Elephant', 'Dolphin', 'Hyena']
    ```

=== "pop()"

    - removes an element from a list and returns its output

    ``` python
    print(my_favorite_animals.pop(0)) # remove Tiger
    print(my_favorite_animals)
    ```
    Output:
    ``` python
    Tiger
    ['Turtle', 'Elephant', 'Dolphin', 'hyena']
    ```

=== "insert()"

    - Allows you to insert a value at a specified index

    ``` python
    fruits = ["apples", "oranges", "lemons"]
    fruits.insert(0, "grapes")
    print(fruits)
    ```
    Output:
    ``` python
    ['grapes', 'apples', 'oranges', 'lemons']
    ```

#### Multi-dimensional lists

You can also put lists in other lists:

``` python
my_favorite_ocean_animals = ["Tiger Shark", "Sea Turtle", "Dolphin"]
my_favorite_animals = [my_favorite_ocean_animals, "Tortoise", "Elephant"]
print(my_favorite_animals)
```
Output:
``` python
[['Tiger Shark', 'Sea Turtle', 'Dolphin'], 'Tortoise', 'Elephant']
```

And access elements inside the list inside the list
``` python
print("My favorite sea creature is ", my_favorite_animals[0][0])
```
Output:
```
Tiger Shark
```

### Sets

Sets are just like lists, but have three main exceptions:

  - Every element must be unique
  - They don't preserve their order
  - No indexing (since they have no order!)

Let's compare them with some examples.

``` python
making_cereal_list = ["Put cereal in bowl", "Put milk in bowl", "Eat!"] # This is a list
making_cereal_set = {"Put cereal in bowl", "Put milk in bowl", "Eat!"} # This is a set
#                   ^               Sets use curly braces            ^
print(making_cereal_list)
print(making_cereal_set)
```
Output:
``` python
['Put cereal in bowl', 'Put milk in bowl', 'Eat!']
{'Eat!', 'Put cereal in bowl', 'Put milk in bowl'}
```

What? Eat the cereal before putting it in your bowl? That doesn't makes sense! 

Let's see how sets stay unique:

``` python
making_cereal_list = ["Put cereal in bowl", "Put milk in bowl", "Eat!", "Eat!", "Eat!"] # This is a list
making_cereal_set = {"Put cereal in bowl", "Put milk in bowl", "Eat!", "Eat!", "Eat!"} # This is a list
print(making_cereal_list)
print(making_cereal_set)
```
Output:
``` python
['Put cereal in bowl', 'Put milk in bowl', 'Eat!', 'Eat!', 'Eat!']
{'Eat!', 'Put milk in bowl', 'Put cereal in bowl'}
```

As you can see, there is only one ```"Eat!"``` in the set, but three in the list. 

#### Useful Methods

Here are the counterparts to ```append()``` and ```pop()``` but for sets:

=== "add()"

    - Adds an element to a set (no particular order)

    ``` python
    candy_types = {"Twix", "Airhead", "Kit Kat"}
    candy_types.add("Skittles")
    ```
    Output:
    ``` python
    {'Twix', 'Kit Kat', 'Skittles', 'Airhead'}
    ```

=== "remove()"

    - removes an element from a set

    ``` python
    candy_types = {"Twix", "Airhead", "Kit Kat"}
    candy_types.remove("Twix")
    ```
    Output:
    ``` python
    {'Kit Kat', 'Airhead'}
    ```

### Dictionaries

Dictionaries are like lists with some extra features. They allow you to associate a name to a value in a structured manner:
``` python
about_me = {
  'name' : 'Zephyr',
  'food' : 'fish',
  'siblings' : 5,
  'species' : 'cat'
}
print(about_me)
print(about_me['name'])
print(about_me['siblings'])
```
Output:
```
{'species': 'cat', 'food': 'fish', 'siblings': 5, 'name': 'Zephyr'}
Zephyr
5
```
This can make your code more easy to understand because the index of an element has a custom name. If you wanted to, however,
you could make the __key__ of an element (the name denoted to its index) a number:
``` python
size_chart = {
  1 : 5
  2 : 10
}
print(size_chart[1])
``` 
Output:
``` 
5
```

#### Modifying dictionaries

Here are the counterparts to ```append()``` and ```pop()``` but for dictionaries:

=== "Adding data"

    - In dictionaries, it is super easy to add data! Just make a new key with its own value:

    ``` python
    cookies = {
      "smell" : "delicious",
      "type" : "Chocolate"
    }
    cookies["taste"] = "amazing"
    print(cookies)
    ```
    Output:
    ``` python
    {'type': 'Chocolate', 'smell': 'delicious', 'taste': 'amazing'}
    ```

=== "del"

    - deletes a key and value from a dictionary

    ``` python
    pies = {
      "apple" : "good",
      "pumpkin" : "terrible"
    }
    del pies["pumpkin"]
    print(pies)
    ```
    Output:
    ``` python
    {'apple': 'good'}
    ```

#### Useful methods

=== "keys()"

    - returns all the keys of a dictionary in the form of a list

    ``` python
    course = {
      "language" : "python",
      "students" : 100_000,
      "Instructor" : "WV Arduino Club"
    }
    keys = course.keys()
    print(keys)
    ```
    Output:
    ``` python
    dict_keys(['language', 'Instructor', 'students'])
    ```

=== "values()"

    - returns all the values of a dictionary in the form of a list

    ``` python
    course = {
      "language" : "python",
      "students" : 100_000,
      "Instructor" : "WV Arduino Club"
    }
    values = course.values()
    print(values)
    ```
    Output:
    ``` python
    dict_values(['python', 'WV Arduino Club', 100000])
    ```

=== "items()"

    - returns the items of the dictionary as a list

    You can use a for loop to access the list as such:

    ``` python
    course = {
      "language" : "python",
      "Instructor" : "WV Arduino Club"
    }
    for key, values in course.items():
      print(f"The course {key} is {value}")
    ```
    Output:
    ``` python
    The course Instructor is WV Arduino Club
    The course language is python
    ```

### Tuples

Tuples are nearly axactly like a list, but they can't be modified. Like lists, they also mainting their order (Sets don't!).
Also, indexing works exactly the same way:

```python
chemistry_consts = (6.022, 2.998, 6.626)
#                  ^ Tuples use parens ^
print(chemistry_consts[0])
```
Output:
```python
6.022
```

As mentioned, you can't modify them:
```python
chemistry_consts = (6.022, 2.998, 6.626)
chemistry_consts.append(8.314)
```
Output:
```python
Line 2: AttributeError: 'tuple' object has no attribute 'append'
```
That's an error! The ```append()``` method doesn't exist for tuples!

Instead, we can create new tuples that have the elements we want from old tuples. 

```python
chemistry_consts = (6.022, 2.998, 6.626)
updated_chemistry_consts = chemistry_consts[0:2]
print(updated_chemistry_consts)
```
Output:
```
(6.022, 2.998)
```

#### Useful methods

What can we do to tuples?

=== "count()"

    - returns number of times a value is in a certain tuple

    ``` python
    chemistry_consts = (6.022, 2.998, 6.626, 2.998)
    print(chemistry_consts.count(2.998))
    print(chemistry_consts.count(6.022))
    ```
    Output:
    ``` python
    2
    1
    ```

=== "index()"

    - returns index of a the first instance of a certain item in the tuple

    ``` python
    chemistry_consts = (6.022, 2.998, 6.626, 2.998)
    print(chemistry_consts.index(2.998))
    print(chemistry_consts.index(6.022))
    ```
    Output:
    ``` python
    1
    0
    ```