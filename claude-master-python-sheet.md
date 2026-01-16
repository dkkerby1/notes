Python Master Reference
BASICS
print() - output to console
input() - get user input as string
type() - check data type
len() - length of string/list/dict
range(start, stop, step) - generate number sequence
int(), str(), float(), bool() - type conversion
help() - get documentation
dir() - list object attributes/methods
VARIABLES & OPERATORS
pythonx = 5                    # assignment
x += 1                   # increment
x -= 1                   # decrement
Comparison: == != < > <= >=
Logical: and or not
Identity: is is not - checks if same object
Membership: in not in - checks if in sequence
STRINGS
pythons = "hello"
s.upper()                # HELLO
s.lower()                # hello
s.capitalize()           # Hello
s.strip()                # remove whitespace
s.replace("h", "j")      # jello
s.split(",")             # split into list
",".join(list)           # join list into string
s.startswith("h")        # True/False
s.endswith("o")          # True/False
s.find("e")              # index or -1
s[0]                     # indexing
s[1:4]                   # slicing
s[::-1]                  # reverse
f"hello {name}"          # f-string formatting
LISTS
pythonlst = [1, 2, 3]
lst.append(4)            # add to end
lst.insert(0, 0)         # insert at index
lst.remove(2)            # remove first occurrence
lst.pop()                # remove and return last
lst.pop(0)               # remove and return at index
lst.extend([5,6])        # add multiple items
lst.sort()               # sort in place
sorted(lst)              # return sorted copy
lst.reverse()            # reverse in place
lst.index(3)             # find index of value
lst.count(2)             # count occurrences
len(lst)                 # length
lst[0]                   # access by index
lst[-1]                  # last item
lst[1:3]                 # slicing
List comprehension:
[x*2 for x in range(5)] - [0, 2, 4, 6, 8]
[x for x in range(10) if x % 2 == 0] - even numbers
DICTIONARIES
pythond = {"key": "value", "age": 25}
d["key"]                 # access value
d.get("key", default)    # safe access with default
d["new"] = "val"         # add/update
del d["key"]             # delete
d.keys()                 # all keys
d.values()               # all values
d.items()                # key-value pairs
d.pop("key")             # remove and return
d.update({"k": "v"})     # merge dictionaries
"key" in d               # check if key exists
Dict comprehension:
{x: x*2 for x in range(5)} - {0:0, 1:2, 2:4, 3:6, 4:8}
TUPLES & SETS
Tuples (immutable):
pythont = (1, 2, 3)
t[0]                     # access
a, b, c = t              # unpacking
Sets (unique, unordered):
pythons = {1, 2, 3}
s.add(4)                 # add item
s.remove(2)              # remove (error if missing)
s.discard(2)             # remove (no error)
s1.union(s2)             # combine sets
s1.intersection(s2)      # common elements
s1.difference(s2)        # in s1 but not s2
CONTROL FLOW
If/elif/else:
pythonif condition:
    # code
elif other_condition:
    # code
else:
    # code
For loops:
pythonfor item in list:        # iterate list
for i in range(5):       # 0 to 4
for i, val in enumerate(list):  # index and value
for k, v in dict.items():       # dict iteration
While loops:
pythonwhile condition:
    # code
    break                # exit loop
    continue             # skip to next iteration
FUNCTIONS
pythondef function_name(param1, param2="default"):
    """docstring"""
    return value

# lambda (anonymous function)
lambda x: x * 2

# *args - variable positional arguments
def func(*args):
    # args is tuple

# **kwargs - variable keyword arguments
def func(**kwargs):
    # kwargs is dict
FILE HANDLING
python# Read
with open("file.txt", "r") as f:
    content = f.read()           # entire file
    lines = f.readlines()        # list of lines
    for line in f:               # iterate lines

# Write
with open("file.txt", "w") as f:
    f.write("text")              # overwrite
    
# Append
with open("file.txt", "a") as f:
    f.write("text")              # add to end

# Modes: "r" read, "w" write, "a" append, "r+" read/write
ERROR HANDLING
pythontry:
    # code that might fail
except ValueError:
    # handle specific error
except Exception as e:
    # handle any error
    print(e)
else:
    # runs if no error
finally:
    # always runs
    
# Raise errors
raise ValueError("error message")
Common exceptions:
ValueError - invalid value
TypeError - wrong type
KeyError - dict key not found
IndexError - list index out of range
FileNotFoundError - file doesn't exist
ZeroDivisionError - divide by zero
CLASSES & OBJECTS
pythonclass ClassName:
    def __init__(self, param):
        self.attribute = param
    
    def method(self):
        return self.attribute

obj = ClassName("value")
obj.method()
Special methods:
__init__ - constructor
__str__ - string representation
__len__ - length
__repr__ - official representation
MODULES & IMPORTS
pythonimport module
import module as m
from module import function
from module import *

# Common modules
import os                # operating system
import sys               # system-specific
import random            # random numbers
import math              # math functions
import datetime          # dates/times
import json              # JSON handling
import csv               # CSV files
import re                # regular expressions
USEFUL BUILT-INS
abs() - absolute value
sum() - sum of iterable
min(), max() - minimum/maximum
round(n, digits) - round number
sorted() - return sorted list
reversed() - return reversed iterator
enumerate() - index and value pairs
zip() - combine iterables
map(func, iterable) - apply function to each item
filter(func, iterable) - filter by condition
any() - True if any element is True
all() - True if all elements are True
LIST/DICT/SET OPERATIONS
python# Copying
list_copy = lst.copy()
dict_copy = d.copy()

# Clear
lst.clear()
d.clear()

# Check empty
if not lst:              # empty list
if lst:                  # has items
STRING FORMATTING
python# f-strings (Python 3.6+)
f"Hello {name}, you are {age} years old"

# format method
"Hello {}, you are {}".format(name, age)
"Hello {n}, you are {a}".format(n=name, a=age)

# % formatting (old)
"Hello %s, you are %d" % (name, age)
COMMON PATTERNS
Read CSV:
pythonimport csv
with open("file.csv") as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(row["column"])
Read JSON:
pythonimport json
with open("file.json") as f:
    data = json.load(f)
    
# Write JSON
with open("file.json", "w") as f:
    json.dump(data, f, indent=2)
List files in directory:
pythonimport os
files = os.listdir("path")
for file in os.listdir("path"):
    if file.endswith(".txt"):
        print(file)
Check if file exists:
pythonimport os
os.path.exists("file.txt")
os.path.isfile("file.txt")
os.path.isdir("folder")