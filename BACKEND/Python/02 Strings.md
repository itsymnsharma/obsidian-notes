## Printing a string

```python
name = input("What's your name? ") # David
print("Hello,"name)      # Hello, David
print(f"Hello, {name}") # Hello, David
```

- Passed two arguments that prints string and a dynamic value
- Format strings `f"Hello, {name}"` will print the value of name

## Remove Whitespace from string

```python
name = input("What's your name? ") # David        
name = name.strip() # remove whitespaces and update name
print(f"Hello, {name}") # Hello, David
```

- `strip()` is a method on string that removes whitespaces from left and right of a string

## Capitalize a string

```python
name = input("What's your name? ")
name = name.capitalize() # capitalize and update name
print(f"Hello, {name}") # Hello, David Malan
```

- `capitalize` will make the first letter of the word capital

## TitleCase a string

```python
name = input("What's your name? ")
name = name.title() # capitalize and update name
print(f"Hello, {name}") # Hello, David Malan
```

- `title` will make the first letter of all the words capital

## Split a string

```python
name = input("What's your name? ") # david malan
# split on white character, outputs sequence of values
first, last = name.split(" ") 
print(f"Hello, {first}") # Hello, david
```

- `split` splits a string into multiple sub strings
- `split(" ")` - white space indicates we want to split by that character
- outputs sequence of values

## Replace

```python
text = input("How is your day?") # I had a good day :)
text = text.replace(":)", "emoji")
```

- `replace` replaces a substring with another substring
- In our example, we are replacing emoticon with emoji

## Type Conversion (string to int)

```python
firstnum = input("Enter first number") # 3
secondnum = input("Enter second number") # 3

print(firstnum + second num) # 33 as both got concatenated bcoz of strings

print(int(firstnum) + int(secondnum)) # 6 converted strings to number

```

- int() converts something to a number

