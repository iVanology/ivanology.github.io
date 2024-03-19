---
layout: post
title: Day 7  Functions with input | Arguments vs. Parameters
date: 2023-10-06 18:43:47  +0800
mermaid: true
categories: [100 Days of Python, Day 7]
tags: [python]
comments: true
published: false
---

# Today's Goal: Cipher Program (Caeser Cipher)

# Functions with Input

```python
# Simple Function
def greet():
	print("How are you?")
greet()

# Function with inputs
def greet(name):
	print(f"How are you {name}")
greet("iVan")
# example output
# How are you iVan?

NB. `name` is a parameter (the name of the data) in this function; while `ivan` is a argument that is passed over to this function
```

# Arguments vs. Parameters

```python
# Positional vs. Keyword Arguments
# Function with more than 1 input
def greet_with(name, location):
    print(f"Hello, {name}. Do you from {location}?")
greet_with("ivan", "Roman")
# example output
# Hello, ivan. Do you come from Roman?


#Positional Argument - the default way to call a function
greet_with("ivan", "Roman")
# Hello, ivan. Do you come from Roman?
greet_with("Guangzhou", "ivan")
# Hello, Roman. Do you from ivan?

# if you want to aviod the above problem, `Keyword` argument is in place
def greet_with(name, location):
    print(f"Hello, {name}. Do you from {location}?")
greet_with(location="Guangzhou", name="ivan")
# Hello, ivan. Do you from Guangzhou?

NB. Keyword argument
- pros: less erro prone
- cons: each line of code longer
```

# Code Challenge 1 - Paint Area Calculator

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
paint_calc(height=test_h, width=test_w, cover=coverage)
```

# Code Challenge 2 - Prime Number Check

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
