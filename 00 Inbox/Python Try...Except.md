---
tags:
  - literature
source: 
created: 2025-08-24
Type: "[Lecture | Book | PDF | Video]"
---
```python
try:  
  f = open("demofile.txt")  
  try:  
    f.write("Lorum Ipsum")  
  except:  
    print("Something went wrong when writing to the file")  
  finally:  
    f.close()  
except:  
  print("Something went wrong when opening the file")

```

## Raise an exception

As a Python developer you can choose to throw an exception if a condition occurs.

To throw (or raise) an exception, use the `[raise](https://www.w3schools.com/python/ref_keyword_raise.asp)` keyword.

### Example

Raise an error and stop the program if x is lower than 0:
```python
x = -1  
  
if x < 0:  
  raise Exception("Sorry, no numbers below zero")
```

The [raise](https://www.w3schools.com/python/ref_keyword_raise.asp) keyword is used to raise an exception.

You can define what kind of error to raise, and the text to print to the user.
### Example

Raise a TypeError if x is not an integer:
```python
x = "hello"  
  
if not type(x) is int:  
  raise TypeError("Only integers are allowed")
```
