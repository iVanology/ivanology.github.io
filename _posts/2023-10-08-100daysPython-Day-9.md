---
layout: post
title: Day 9 Dictionaries & Nesting
date: 2023-10-08 18:43:47  +0800
mermaid: true
categories: [100 Days of Python, Day 9]
tags: [python]
comments: true
---

## Dictionary

```python
{KEY: VALUE}

# Example
{
 "Bug": "An error in a programme that prevents the program from running as expected."
 }
```

### More than 1 entry in dictionary

```python
programming_dictionary = {
    "Bug": "An error in a programme that prevents the program from running as expected.",
    "Function": "A piece of code that you can easily call over and over again",
    "Loop": "The action of doing something over and over again.",
}
# NB. Every subsequent entry of a dictionary is indented by 1 indent (2 spaces).
```

### Retrieving items from dictionary

```python
print(programming_dictionary["Bug"])

```

### Adding new items to dictionary

```python
programming_dictionary["testing"] = "testing message"
print(programming_dictionary)

# Example outoput
# programming_dictionary = {"Bug": "An error in a programme that prevents the program from running as expected.", "Function": "A piece of code that you can easily call over and over again", "Loop": "The action of doing something over and over again.", "testing":"testing message"}
```

### Create an empty dictionary

```python
empty_dictionary = {}
```

### Wipe an existing dictionary

```python
programming_dictionary = {}
print(programming_dictionary)
```

### Edit an item in a dictionary

```python
# redefine the value
programming_dictionary["Bug"] = "A moth in your computer."
print(programming_dictionary)
```

### Loop through a dictionary

```python
### ONLY print out `key`
for thing in programming_dictionary:
  print(thing)


### print out `key` and `value` at the same time
for key in programming_dictionary:
  print(key)
  print(programming_dictionary[key])
```

## Nesting

### Multiple key-value pairs

```python
{
  key: [List],
  key2: {Dict},
}

# Example
capitals = {
  "France": "Paris",
  "Germany" "Berlin",
}

```

### Nesting a List in a Dictionary

```python
travel_log = {
  "France": ["Paris", "Lille", "Dijon"],
  "Germany": ["Berlin", "Hamburg", "Stuttgart"],
}
```

### Nesting a Dict in a Dict

```python
travel_log = {
  "France": {"cities_visited": ["Paris", "Lille", "Dijon"], "total_visits": 12},
  "Germany": {"cities_visited": ["Berlin", "Hamburg", "Stuttgart"], "total_visits": 5},
}
```

### Nesting a Dict in a List

```python
[{
  key:[List],
  key2:{Dict},
},
{
 key:value,
 key2: value,
}]

# Example
travel_log = [
  {
  "country": "France",
  "cities_visited": ["Paris", "Lille", "Dijon"],
  "total_visits": 12
  },
  {
  "country": "Germany",
  "cities_visited": ["Berlin", "Hamburg", "Stuttgart"],
  "total_visits": 5
  },
]
```

### Exercise

```python
country = input() # Add country name
visits = int(input()) # Number of visits
list_of_cities = eval(input()) # create list from formatted string


travel_log = [
  {
    "country": "France",
    "visits": 12,
    "cities": ["Paris", "Lille", "Dijon"]
  },
  {
    "country": "Germany",
    "visits": 5,
    "cities": ["Berlin", "Hamburg", "Stuttgart"]
  },
]
# Do NOT change the code above 👆


# TODO: Write the function that will allow new countries
# to be added to the travel_log.
def add_new_country(country, visits, list_of_cities):
  new_country = {
    "country": country,
    "visits": visits,
    "cities": list_of_cities
    }
travel_log.append(new_country)

# Do not change the code below 👇
add_new_country(country, visits, list_of_cities)
print(f"I've been to {travel_log[2]['country']} {travel_log[2]['visits']} times.")
print(f"My favourite city was {travel_log[2]['cities'][0]}.")
```

## Today's Project

### Solution 1

```python
import os
import art
print(art.logo)

bids={}
bidding_finished = False

def find_highest_bidder(bidding_record):
    highest_bid = 0
    winner = ""
    for bidder in bidding_record:
      bid_amount = bidding_record[bidder]
      if bid_amount > highest_bid:
        highest_bid = bid_amount
        winner = bidder
    print(f"The winner is {winner} with a bid of ${highest_bid}")


while not bidding_finished:
  name = input("What is your name?: ")
  price = int(input("What is your bid?: $"))
  bids[name] = price
  should_continue = input("Are there any other bidder? Type 'yes' or 'no'.\n")
  if should_continue == "no":
    bidding_finished = True
    find_highest_bidder(bids)
  elif should_continue == "yes":
      os.system("clear")
```

### Solution 2

```python
import os
import art
print(art.logo)


silent_bids = []
end_of_bidding = False

def add_bid(name, bid):
  new_bid = {
      "name": name,
      "bid": bid,
    }
    silent_bids.append(new_bid)

while not end_of_bidding:
  name = input("What is your name?: ") # Ask user's name
  bid = int(input("What is your bid?: $")) # Ask user's bid
  add_bid(name, bid)

  should_continue = input("Are there any other bidders? Type 'yes' or 'no': ").lower()

  if should_continue == 'yes':
    os.system('cls' if os.name == 'nt' else 'clear') # Clear the console
else:
  end_of_bidding = True

# Find the highest bid
winner = max(silent_bids, key=lambda x: x['bid'])
print(f"The winner is {winner['name']} with a bid of ${winner['bid']}.")
```

### Solution 3

```python
import os
import art

print(art.logo)

bids = {}
bidding_finished = False


while not bidding_finished:
  name = input("What is your name?: ")
  price = int(input("What is your bid?: $"))
  bids[name] = price
  should_continue = input("Is there other bidder? Type 'yes' or 'no'. \n")
  if should_continue == "no":
    bidding_finished = True
  elif should_continue == "yes":
    os.system("clear")

# Find the highest bid
highest_bidder = max(bids, key=bids.get)
print(f"The winner is {highest_bidder} with a bid of ${bids[highest_bidder]}")
```

## About _max()_ function

1. **For a simple dictionary** where you want to find the key with the maximum value:

   ```python
   bids = {"Alice": 100, "Bob": 150, "Charlie": 90}
   highest_bidder = max(bids, key=bids.get)
   print(highest_bidder)  # Outputs: "Bob"
   ```

   Here, `bids.get` is a method that returns the value for a given key. By passing this method as the `key` parameter to `max()`, you're effectively telling `max()` to compare the values of the dictionary rather than the keys.

2. **For a list of dictionaries** (or any other complex data structure), you can use a `lambda` function to specify which part of each dictionary you want to compare.

   For example, if you have a list of words and you want to find the longest one:

   ```python
   words = ["apple", "banana", "cherry", "date"]
   longest_word = max(words, key=lambda x: len(x))
   print(longest_word)  # Outputs: "banana"
   ```

   And if you have a list of dictionaries and you want to find the dictionary with the highest 'bid' value:

   ```python
   silent_bids = [{"name": "Alice", "bid": 100}, {"name": "Bob", "bid": 150}, {"name": "Charlie", "bid": 90}]
   highest_bid = max(silent_bids, key=lambda x: x['bid'])
   print(highest_bid)  # Outputs: {'name': 'Bob', 'bid': 150}
   ```

In summary, the `key` parameter in functions like `max()` allows you to specify custom comparison logic. For simple dictionaries, you can often use built-in methods like `get`. For more complex data structures, a `lambda` function provides the flexibility to define custom comparison logic inline.
