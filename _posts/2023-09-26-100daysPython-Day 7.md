---
layout: post
title: Day 7 Functions with input | Arguments vs. Parameters
date: 2023-09-26 16:33:20  +0800
mermaid: true
categories: [100 Days of Python, Day7]
tags: [python]
comments: true
---

## Functions with input

```python
#Simple Function
def greet():
    print("How are you?")
greet()

#Function with inputs
def greet(name):
    print(f"How are you {name}")
greet("iVan")
```

## Arguments vs. Parameters

In the example above, `name` is a parameter (the name of the data) in this function; `ivan` is a argument that is passed over to this function (the acutal value of the data)

### Positional Argument ------ the default way to call a function

```python
# Function with more than 1 input
def greet_with(name, location):
    print(f"Hello, {name}. Do you from {location}?")
greet_with("ivan", "Rome")
```

{: .prompt-info}

> #### ¿ Think about it ?
>
> If you mess up with `name` and `location`, what will happened?
>
> ```python
> # Think about what will be printed?
> greet_with("ivan", "Rome")
> greet_with("Rome", "ivan")
> ```

### Keyword argument

If you want to aviod the problem above, Keyword argument is in place

```python
def greet_with(name, location):
   print(f"Hello, {name}. Do you from {location}?")
greet_with(location="Rome", name="ivan")
```

##### Pro and Con of Keyword argument

- pros: less erro prone
- cons: each line of code longer

## Code Challenge 1 - Paint Area Calculator

```python
# Write your code below this line 👇
import math

def paint_calc(height, width, cover):
    area = height * width
    numbers_of_cans = math.ceil(area / cover) # round UP to the next whole number
    print(f"You will need {numbers_of_cans}.")
# Write your code above this line 👆

# Define a function called paint_calc() so that the code below works.

# 🚨 Don't change the code below 👇
test_h = int(input("Height of wall: "))
test_w = int(input("Width of wall: "))
coverage = 5
numbers_of_cans = paint_calc(height=test_h, width=test_w, cover=coverage)
```

## Code Challenge 2 - Prime Number Check

```python
# Write your code below this line 👇

def prime_checker(number):
    if number <= 1:
        print("NOT Prime")
        return
    for i in range(2, number):
        if number % i == 0:
        print("NOT Prime")
        return
    print("Prime")
# Write your code above this line 👆

# Do NOT change any of the code below👇
n = int(input("Check this number: "))
prime_checker(number=n)
```
