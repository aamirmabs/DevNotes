# Python Language Basics DevRef

## Python Strings

### Formatted Strings

- Formatted strings are enclosed within `f" ..string here.."`.
- The strings can contain expressions enclosed within `{...}`.
- Any expression within the `{...}` will be evaluated and the resultant value will be replaced in its place.

```python
First = "Coder"
Last = "Apex"

Full = f"{First} {Last}"
# o/p : "Coder Apex"

Anything within the {} will be evaluated
Full = f"{len(First)} {Last}"
# o/p : "5 Apex"
```

Note: Formatted strings will only work on Python 3.7 or higher

### Multi-Line Strings

- Strings in Python can be single-lined or multi-lined.
- Single-lined strings are enclosed within single quotes `'...'` or double quotes `"..."`.

```python
# single lined strings
stringy = "Coder Apex"
channel_name = "CoderApex"
```

- Multi-lined strings are enclosed within triple quotes `"""..."""`.

```python
# multi lined strings
paragraph = """
start of para.

line 1.

line 2.

end…
"""
```

### String Methods

string = "Python"

| Function                                                                   |   Output    | Logic/Notes                                                                       |
| -------------------------------------------------------------------------- | :---------: | --------------------------------------------------------------------------------- |
| len(string)                                                                |      6      | Returns length                                                                    |
| string[0]                                                                  |      P      | Return character at index 0                                                       |
| string[-1]                                                                 |      n      | Return character at -1 position from index 0                                      |
| string[0:3]    string[0:n]                                                 |     Pyt     | Return string from 0 till excluding 3                                             |
| string[0:]                                                                 |   Python    | Return string from 0 till n last characters                                       |
| string[:3]                                                                 |     Pyt     | Return string from start till excluding 3                                         |
| string[:]                                                                  |   Python    | Return string from start till n                                                   |
| string.upper()                                                             |   PYTHON    | Return new string converted to upper case string                                  |
| string.lower()                                                             |   python    | Return new string converted to lower case string                                  |
| string.title()                                                             |   Python    | Return new string converted to title case string                                  |
| string.strip()                                                             |   Python    | Return new string with white space removed                                        |
| string.lstrip()                                                            |   Python    | Return new string with left white space removed                                   |
| string.rstrip()                                                            |   Python    | Return new string with right white space removed                                  |
| string.find("t")                                                           |      2      | Return the first index of the occurrence or -1 if not found                       |
| string.replace("P", "X")  string.replace("Pyt", "a")  string.replace(A, B) | Xython ahon | Replaces all occurrences of A with B                                              |
| "Pyt" in string   "string" in variable                                     |    True     | Returns True of False depending on if the "string" exists in the variable         |
| "pyt" not in string   "string" not in variable                             |    True     | Returns True of False depending on if the "string" does NOT exist in the variable |

## Numbers

```python
# integer values
inter = 10
attendee_count = 97

# floating decimal points
floater = 5.66
rating = 4.9

# imaginary numbers
value = 8 + 4i
```

Numeric operations

```python
# numeric operations
value = 10 + 3
value = 10 - 3
value = 10 * 3

# two types of division
value = 10 / 3
# o/p : 3.33333333…

value = 10 // 3
# o/p : 3

# modulus
10 % 3
# o/p : 1

# exponential
10 ** 3
# o/p : 1000

```

### Built-in Numerical Functions

| Function                           | Output | Notes                                                                                         |
| ---------------------------------- | ------ | --------------------------------------------------------------------------------------------- |
| Round(number, decimals)            |        | Rounds the value with number of decimal points. If decimal is not specified, round to integer |
| Round(2.9)   Same as Round(2.9, 0) | 3      |                                                                                               |
| Round(2.956821, 3)                 | 2.957  |                                                                                               |
| Round(2.956121, 3)                 | 2.956  |                                                                                               |
| Abs(-2.9)                          | 2.92   | Returns the absolute value of a number                                                        |

## Type Conversion

```python
x = input("Enter x: ")

# convert the type of int to str
# as only similar types can be concatenated
y = f"Value is {str(x)}"

print(y)
```

## Conditionals

```python
If Statements
temp = 32

if temp > 30:
    print("It's warm")
elif temp > 20:
    print("It's nice")
else:
    print("It's COLD!")
```

```python
age = 22

if age > 18:
    message = "Eligible"
else:
    message = "Not Eligible"

print(message)
```

### Shorter Version

```python
age = 25

message = "Eligible" if age > 18 else "Not Eligible"

print(message)
```

### Chaining comparison operators

```python
age = 25

if age >= 18 and age < 65:
    print("Eligible")

if 18 <= age < 65:
    print("Eligible")
```

## Looping

### Using range()

Using 'range()' to define start, stop and step

Syntax :  `range(start: int, stop: int, step: int=...)`

- range(stop: int)
- range(stop) -> range object
- range(start, stop[, step]) -> range object

range() returns an object that produces a sequence of integers from start (inclusive) to stop (exclusive) by step. range(i, j) produces i, i+1, i+2, ..., j-1.
`start` defaults to 0, and `stop` is omitted!

range(4) produces 0, 1, 2, 3. These are exactly the valid indices for a list of 4 elements. When step is given, it specifies the increment (or decrement).

```python
For Loop
for number in range(5):
    print(number)

For-Else Loop
for number in range(0, 100):
  if number % 150 == 0
    print("Number equals 150!")
    break
Else:
  print("Number 150 not found!")
# Else is executed if there is
# no break in the for loop
```

## Functions

### Function With Parameter

```python
def greet(name):
    print(f"Hello {name}")

greet("John")
```

### Two Types of Functions

1. Perform a task

```python
def greet(name):
    print(f"Hello, {name}")

def add2(a, b):
    result = a + b
    print(result)
```

2. Return a value

```python
def greet():
    return(f"Hello, {name}")

def add2(a, b):
    result = a + b
    return(result)
```

### Keyword Arguments

```python
def increment(number, by):
    return number + by

print(increment(5, 3))

# using keyword arguments
print(increment(5, by=3))
# improved readability
```

### Default Arguments

```python
def increment(number, by = 1):
    return number + by

print(increment(5))
# used default value for argument
# makes parameters optional
# defaults should be the last parameters

# example : not allowed
def increment(number, by = 1, x, y):
```

### *args

```python
# *args accepts multiple arguments
# example : not using args
def multiply(x, y):
    return(x * y)

multiply(5, 3)

# *args = can pass multiple args
def multiply(*numbers):
    print(numbers)
multiply(2, 4, 6, 8)
# o/p : (2, 4, 6, 8)
# passed object is a tuple
# tuples are iterable
# and can be used in loops

# we can now write multiply as
def multiply(*numbers):
    result = 1
    for number in numbers:
        result = result * number
    print(result)

multiply(2, 4, 6, 8)
# o/p : 384
```

### **args

```python
# **args accepts multiple arguments
# converts them to key-value pairs
# (key-value pairs are called dictionary)
# and passes that object to function
# dictionaries are also iterable

# example
def save_user(**user_data):
    print(user_data)

    # access data of each key-value pair
    print(user_data["name"])
    print(user_data["age"])
    print(user_data["is_member"])

save_user(name="John", age=25, is_member=True)

# o/p :
# {'name': 'John', 'age': 25, 'is_member': True}
# John
# 25
# True
```
