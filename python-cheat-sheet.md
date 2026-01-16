# Python Cheat Sheet

## Running Python

# Python Cheat Sheet

## Running Python
python file.py
python3 file.py

## Python REPL
python
exit()

## Variables
x = 5
name = "Alice"
is_valid = True

## Data Types
int
float
str
bool
list
dict
tuple
set

## Lists
nums = [1, 2, 3]
nums.append(4)
nums[0]
len(nums)

## Dictionaries
user = {"name": "Alice", "age": 30}
user["name"]
user.get("age")

## Conditionals
if x > 5:
    print("Greater")
elif x == 5:
    print("Equal")
else:
    print("Less")

## Loops
for i in range(5):
    print(i)

while x > 0:
    x -= 1

## Functions
def greet(name):
    return f"Hello {name}"

## Files
with open("file.txt", "r") as f:
    data = f.read()

with open("file.txt", "w") as f:
    f.write("Hello")

## Virtual Environments
python -m venv venv