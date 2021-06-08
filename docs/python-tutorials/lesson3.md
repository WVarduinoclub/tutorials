# A Quick Recap
Created by: Sean Boerhout


Here I'll give you a quick recap of what you've learned in the form of an example.

Suppose I wanted user input at a vending machine, where customers need to type in the drink that they want. 
Using a dictionary, I can easily relate the name of that drink to a price:
``` python
drink_prices = {
  "sprite" : 2.50,
  "coke" : 2.00,
  "fanta" : 3.00
}
```
In order to get the user's input, I'll use a cool function called ```input()```. It prompts python to 
ask for your input and assigns the input to a string:
``` python
customer_drink = input()
```
Now we can ask someone for their desired drink and tell them the price! 
``` python
customer_drink = input()
print(drink_prices[customer_drink])
```
But we can do better than that... let's make the process more friendly with some ```print()```s.
``` python
print("Welcome! What drink would you like? Please choose from one of the choices below:") 
print(drink_prices.keys())

# ask them for their drink and say the price
customer_drink = input()
print(f"{ customer_drink.title() }s costs { drink_prices[customer_drink] } dollars!")
```

But, wait. What if the user makes a typo by using the wrong capitalization? We can ensure that the input
is always read correctly:
``` python
customer_drink = input().lower()
```
Since all the keys in our dictionary are lowercase, this will fix that problem.

#### Finished Code
Here's all that code put together:
``` python
drink_prices = {
  "sprite" : 2.50,
  "coke" : 2.00,
  "fanta" : 3.00
}

print("Welcome! What drink would you like? Please choose from one of the choices below:") 
print(drink_prices.keys())

customer_drink = input().lower()

print(f"{ customer_drink.title() }s costs { drink_prices[customer_drink] } dollars!")
```

#### Try it yourself

<iframe src="https://trinket.io/embed/python3/1a196fccc9" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### Challenge

Create a fictional character that a user can learn about! You should use at least one dictionary, one input, and one list.

Here is an example:
<iframe src="https://trinket.io/embed/python3/7a39be2117?outputOnly=true" width="100%" height="150" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>