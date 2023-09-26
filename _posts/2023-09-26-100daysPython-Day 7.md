```
layout: post
title: Python | Assignment X
date: 26-09-2023  16:33:20  +0800
mermaid: true
categories: [100 Days of Python, Day7]
tags: [python]
```


# Day 7  Functions with input | Arguments vs. Parameters

> [!Ci] Today's Goal: Cipher Program (Caeser Cipher)
>**Learn:** 
> - Functions with Input
> - Arguments vs Parameters
> 

```python
# Simple Function 
def greet(): 
	print("How are you?") 
greet() 

# Function with inputs 
def greet(name): 
	print(f"How are you {name}") 
greet("iVan") 
-> How are you iVan? 

#NB. `name` is a parameter (the name of the data) in this function; while `ivan` is a argument that is passed over to this function

# Positional vs. Keyword Arguments 
# Function with more than 1 input 
def greet_with(name, location): 
	print(f"Hello, {name}. Do you from {location}?") greet_with("ivan", "Guangzhou")
# example out 
-> Hello, ivan. Do you from Guangzhou?


# Code Challenge 1 - Paint Area Calculator 

# Write your code below this line 👇 
import math 
def paint_calc(height, width, cover): 
	area = height * width numbers_of_cans = math.ceil(area / cover) # round UP to the next whole number 
	print(f"You will need {numbers_of_cans}.") 
# Write your code above this line 👆 

# Define a function called paint_calc() so that the code below works.
# 🚨 Don't change the code below 👇 
test_h = int(input("Height of wall: ")) 
test_w = int(input("Width of wall: ")) 
coverage = 5 
paint_calc(height=test_h, width=test_w, cover=coverage)


# Code Challenge 2 - Prime Number Check 
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


