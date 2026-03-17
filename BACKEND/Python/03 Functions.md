## Define Function

```python
def hello(name="world"): # world is the default value
	print(f"Hello, ${name}")

name = input("What's your name? ")
hello(name)
```

- `def` is to define a function
- Python has indentations and not braces for scoping
- Function has to be defined at top before using them

## Ordering Functions

```python
def main():
	name = input("What's your name? ")
	hello(name)

def hello(name="world"):
	print(f"Hello, ${name}")

main() # Calling the main function at last
```

- Functions need to be defined before use means we have to define all our functions above in file and the main code at last, but this wont be good
- We can work out a way by defining a main function that runs our code and define all other functions below it as above
- It's just a way of ordering function that allows functions to be defined later

## Return from Function

```python
def main():
	num = int(input("What's the number to square? "))
	print(f"Squared value of {num} is {square(num)})

def square(num):
	return num * num # you can also use pow(num, 2)

main() # Calling the main function at last
```

- **`return`** statement returns a value from function