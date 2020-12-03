# Python Lists DevRef

## Declaring list objects

```python
alphabets = ["a", "b", "c", "d"]
numbers = [1, 2, 3, 4, 5]
matrix = [[1, 2], [5, 7], [3, 9]]

# populating lists
five_zeros = [0] * 5
# o/p : [0, 0, 0, 0, 0]

# lists can be concatenated
one_to_five = [1, 2, 3, 4, 5]
six_to_zero = [6, 7, 8, 9, 0]

digits = one_to_five + six_to_zero
# o/p : [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
```

## Generating Lists

The function `list()` can be used to generate lists. It accepts any iterable object and generates a list out of its componenets.

```python
one_to_five = list(range(1, 6))
# o/p : [1, 2, 3, 4, 5]

message = "Hello"
alphabets = list(message)
# o/p : ['H', 'e', 'l', 'l', 'o']
```

## Accessing Lists

Lists can be accessed via their `index` position similar to how characters on a string are accessed.

```python
string = "Hello"
string[0]     # o/p : "H"
string[-1]    # o/p : "o"
string[0:2]   # o/p : "Hel"

# we can get a copy of the list with
string2 = string[:]
```

## Steps in Lists

The syntax to apply steps while accessing lists is `list[start : end : step]`.

The default values are `list[0 : n : None or 1]`.

```python
digits = list(range(1, 11))

# step examples
digits[::None]
digits[::1]
digits[::2]
digits[::3]

# reversing a list
digits[::-1]
```

## Unpacking Lists

The elements of a list can be unpacked and saved to individual elements. Say for example we have a list `items_list` which has a few items that we want to save to individual elements.

We can manually save the elements like so:

```python
items_list = [1, 2, 3, 4, 5]

item0 = items_list[0]
item1 = items_list[1]
item2 = items_list[2]
item3 = items_list[3]
item4 = items_list[4]

print(f"{item0}, {item1}, {item2}, {item3} and {item4}")
# o/p : 1, 2, 3, 4 and 5
```

OR, we can unpack them directly into the variables.

Syntax: `ele1, ele2,el... = list`

We can rewrite the above code-snippet as follows:

```python
items_list = [1, 2, 3, 4, 5]

item0, item1, item2, item3, item4 = items_list

print(f"{item0}, {item1}, {item2}, {item3} and {item4}")
# o/p : 1, 2, 3, 4 and 5
```

**Note**: The number of elements that you are unpacking ***should be equal*** to the number of elements on the list.

If you try to copy more items into fewer elements you will run into `ValueError: too many values to unpack`.

In order to overcome this, you can unpack the rest of the elements into a single list using a `*args`.

```python
items_list = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

item0, item1, item2, *other_items = items_list

print(f"{item0}, {item1}, {item2}")
# o/p : 0, 1, 2

print(f"{other_items}")
# o/p : [3, 4, 5, 6, 7, 8, 9]
```

Just as we can unpack the initial elements *before* `*args`, we can also unpack a fixed number of elements *after* `*args`. In the code snippet below you will see the element `last_item` after `*other_items`. We are *unpacking the last element* of `items_list` into `last_item`.

```python
items_list = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

item0, item1, *other_items, last_item = items_list

print(f"{item0}, {item1}")
# o/p : 0, 1, 2

print(f"{other_items}")
# o/p : [3, 4, 5, 6, 7, 8]

print(f"{last_item}")
# o/p : 9
```

Let us illustrate the concept of unpacking lists with a real-life(ish) example.

Do you like John Wick? Well, I do. So, let's view a snippet of code that will unpack a few facts about John Wick into their respective variables.

```python
john_wick = ["John Wick", "The Bogeyman",
             "Killing enemies with a pencil", "Avenging killed beagle puppy named Andy", "If you are gonna kill people, do it in style..."]

name, aka, *hobbies, motto = john_wick

print(f"Name : {name}")
print(f"Alias : {aka}")
print(f"Hobbies : {hobbies}")
print(f"Motto : {motto}")

# o/p :
# Name : John Wick
# Alias : The Bogeyman
# Hobbies : ['Killing enemies with a pencil', 'Avenging killed beagle puppy named Andy']
# Motto : If you are gonna kill people, do it in style...
```
