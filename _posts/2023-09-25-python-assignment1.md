---
layout: post
title: Python | Assignment 1
date: 2023-09-25 21:05:55 +0800
mermaid: true
categories: [UAS, Python]
tags: [coding]
comments: true
---

# What I have learnt on Day 1

- `print()`function
- `input()` function
- string manipulation
  - f string: `print(f"Hello, {user_name}!\n")`
- Python Variables
  - Naming Variables: make your code readable

<br>

```python
#soulution to question 1
#User input
user_name = input("What is your name?\n")
print(f"Hello, {user_name}!\n")

# soulution to question 2
import math

# User Input
radius_of_circle = float(input("Please ether the radius of a circle: "))
area_of_circle = math.pi * radius_of_circle**2

print(f"The area is {area_of_circle:.2f}\n")


# soulution to question 3
# User Input
length_of_rectangle = float(input("Please ether the length of a rectangle: "))
width_of_rectangle = float(input("Please ether the width of a rectangle: "))

# Formulas
perimeter_of_rectangle = (length_of_rectangle + width_of_rectangle) * 2
area_of_rectangle = length_of_rectangle * width_of_rectangle

print(
    f"The perimeter of rectangle is {perimeter_of_rectangle:.2f}, and the area of rectangle is {area_of_rectangle:.2f}.\n"
)


# soulution to question 4
# User Input
user_int_string = input("Pleaese enter three integer numbers, separated by a comma: ")
user_int_list = user_int_string.split(", ")

# Convert strings to integers
user_integers = [int(num) for num in user_int_list]

# Calculate the sum
total_sum = sum(user_integers)
print(f"The sum is: {total_sum}")
https://github.com/iVanology/python_exercise

# Calculate the product
product = 1
for num in user_integers:
    product *= num
print(f"The product is: {product}")

# Calculate the average
average = total_sum / len(user_integers)
print(f"The average is: {average:.2f}\n")


# soulution to question 5
# Unit conversion
lots_to_grams = 13.3
pounds_to_lots = 32
talent_to_pounds = 20

# User Input
user_talents = float(input("Enter talents: \n"))
user_pounds = float(input("Enter pounds: \n"))
user_lots = float(input("Enter lots: \n"))

# Calculate the total grams
user_total_grams = (
    (user_talents * talent_to_pounds * pounds_to_lots * lots_to_grams)
    + (user_pounds * pounds_to_lots * lots_to_grams)
    + (user_lots * lots_to_grams)
)

# Convert grams to kilograms
kilograms = int(user_total_grams // 1000)
grams = user_total_grams % 1000

print(f"The weight in modern units: \n{kilograms} kilograms and {grams:.2f} grams.")
```
