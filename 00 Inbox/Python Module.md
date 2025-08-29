---
tags:
  - literature
source: https://www.w3schools.com/python/python_modules.asp
created: 2025-08-24
Type: Website
---
## Naming a Module

You can name the module file whatever you like, but it must have the file extension `.py`

## Re-naming a Module

You can create an alias when you import a module, by using the [as](https://www.w3schools.com/python/ref_keyword_as.asp) keyword:

### Example

Create an alias for `mymodule` called `mx`:
```python
import mymodule as mx  
  
a = mx.person1["age"]  
print(a)
```
```python
from mymodule import person1  
  
print (person1["age"])
```