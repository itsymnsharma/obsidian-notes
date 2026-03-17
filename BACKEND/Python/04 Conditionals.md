
## if elif conditions

```python
if(age>=60):
	print("Senior Citizen")
elif(age>=20):
	print("Adult")
else
	print("Teenager")
```

- if elif else can be used for conditional statements

## Match

```python
file = input("File name:").strip().lower()

# get the extension of the file e.g. my.dp.jpeg -> ["my", "dp", "jpeg"]
type = file.split(".")[-1]

def contentType(type):
    match type:
        case "gif" | "png":
            return f"image/{type}"
        case "jpg" | "jpeg":
            return "image/jpeg"
        case "txt":
            return "text/plain"
        case "pdf" | "zip":
            return f"application/{type}"
        case _:
            return "application/octet-stream"

print(contentType(type))
```

- **`match`** in Python is used for **pattern matching**.
- It's like switch statements in other languages.
- We use `|` in `match` because it tells Python to **match any of the given patterns**, while `or` just **evaluates to one value before matching**.

```python
match ext:  
	case "gif" | "png":  
		print("image")
```

- Here Python matches **"gif" or "png"**.

```python
case ("gif" or "png")
```

- Python first evaluates `"gif" or "png"` → `"gif"`, so it becomes: case ("gif") and hence "png" would never match