# Libraries and Modules

Created By: [Sean Boerhout](https://seanboe.github.io)

Nearly all programming language have libraries, or collections of code that perform a very specific task and 
are available to the public to use. For example, python's [`random`](https://docs.python.org/3/library/random.html)
library allows you to get random numbers, lists of numbers, and more, while [`faker`](https://faker.readthedocs.io/en/master/)
allows you to get fake data about fake people, like a random name, address, email account, or country. 

While those libraries may seem niche and somewhat useless, nearly all projects require a library for something since they 
can be so powerful. [`numpy`](https://numpy.org), for example, is an extremely powerful in math-related functions. 
[`tensorflow`](https://www.tensorflow.org) does machine learning.

If you aren't using an ide that has a library built in, you may need to install it onto your computer with [__pip installer__](https://pip.pypa.io/en/stable/installing/).
Generally, libraries will give you the intructions to install them on their website


## Importing and Basic use

Let's get started!

Libraries are essentially large collections of code, just like anything you'd write. With the `import` function, you can 
essentially copy-paste that code.

``` python
import random
```

Functions associated with a library must be shown to be linked to a library. For example, random has a _method_ (a function 
made accessible by a _class_, which we'll learn more about later) which _returns_ a random number between a given range
called `randint()`. We can call it like this:

``` python
import random

random_number = random.randint(0, 9)
```

Notice that `randint(0, 9)` is prefixed by a `random.`. This denotes the fact that `randint()` is defined by the `random` library
and not by you. 

You might not always want to use the name of the library to prefix the method, however. To optimize this, you can use `as`:

``` python
import random as rdm

random_number = rdm.randint(0, 9)
```

That's about it with libraries!

If you want to konw the syntax of a function or what a function does, a quick google search for the documentation of the library
would probably be the best course of action. 