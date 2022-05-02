# Day 2 - Beginner - Understanding Data Types and How to Manipulate Strings
---
___

## round function:

- The `round()` function returns a floating point number that is a rounded version of the specified number, with the specified number of decimals.

- The default number of decimals is 0, meaning that the function will return the nearest integer.

### Syntax

`round(number, digits)`

#### Parameter Values

| Parameter | Description                        |
| --------- | ---------------------------------- |
| _number_  | Required. The number to be rounded |
| _digits_  | Optional. The number of decimals to use when rounding the number. Default is 0 |


___
___

## float type format:

- Bacially `print(f"{someFloatingNumber:.30f}")` will give us a float with upto 30 decimal point precision.
- To know more read these:
	- https://stackoverflow.com/questions/455612/limiting-floats-to-two-decimal-points
	- https://docs.python.org/3.9/library/string.html#formatspec


___
___
___

# Day 19 - Intermediate - Instances, State and Higher Order Functions

___
___

## Function inside function

- Use func1(func2), not func1(func2()) since the latter one will call the function when passed as an argument.
- So basically no parenthesis.

___
___
___

# Day 21 - Intermediate - Build the Snake Game Part 2_ Inheritance & List Slicing

## Class Inheritance

- Inherit everything from a super class.
- So the sytntx is:

```python
class SubsetClassName(SuperClassName):
	def __init__(self):
		super().__init__()
```


- Example:
```python
class Animal:
	def __init__(self):
		self.cells = True
		self.breathe = True

	def how_breathe(self):
		print('inhale exhale')

class Fish(Animal):
	def __init__(self):
		super().__init__()
		self.lives_on_land = False

	def breathe(self):
		self.how_breathe() # is same as super().how_breathe() as Animal class is just a subset now
		print('but underwater')

```


___
___
___

# Day 24 - Intermediate - Files, Directories and Paths
___
___
## Realative path:
- Use `../` to go up one folder.
- Example:
	If current dir is `C:/Users/lucky/Documents/python`and I want to access a file in Desktop named main.py:
	The relative path will be:
	`../../Desktop/main.py`
- Very usefel with file context management.
- Read all string and file methods. They are all very fascinating. 
	- https://www.w3schools.com/python/python_ref_string.asp
	- https://www.w3schools.com/python/python_ref_file.asp


___
___
___
# Day 25 - Intermediate - Working with CSV Data and the Pandas Library
___
___
## Pandas Library (import pandas as pd)
- `data = pd.read_csv(pathtocsv)` will return a pandas dataframe object.
- After that the the columns will be saved under name of topmost row, and they then are saved as attributes.
- Filter dataframe like this:
	- `data[data.name_of_column == certain_condition]` 
	- Above will return a pandas series.
	- We can then use `int()` or `str()` functions on the series to change the type.

- From series to dataframe with index https://stackoverflow.com/questions/26097916/convert-pandas-series-to-dataframe





tkinter
list and dictiopnary comprehension
error handling
json in pythonm
smtplib
twilio

# Day 45 - Intermediate+ Web Scraping with Beautiful Soup

___
___
```python
from bs4 import BeautifulSoup

soup = BeautifulSoup('some.html', 'lxml or html.parser')
```

```python
soup.find_all('html_tag') 
```
will return a list full of said tags 

To use css class (remember its class_ not  class):
```python
soup.find_all('tag_name', class_='the_class_name_without_.')
```


To get text, use 

```python
for tag in the_list:
	print(tag.get_text())
```

To get href or something similiar:
```python
for tag in the_list:
	print(tag.get('href'))	
```

___
___
___
# Day 48 - Intermediate+ Selenium Webdriver Browser and Game Playing Bot
___
___

```python
from selenium import webdriver

from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys

```

`<input type="text" name="passwd" id="passwd-id" />`
if html, then:

```python
element = driver.find_element_by_id("passwd-id")
element = driver.find_element_by_name("passwd")
element = driver.find_element_by_xpath("//input[@id='passwd-id']")
element = driver.find_element_by_css_selector("input#passwd-id")
```

to send keys, and imput:

```python
element.send_keys("some text")
element.send_keys(" and some", Keys.ARROW_DOWN)
```

to clear a field:
```python
element.clear()
```

# 54 Day 54 - Intermediate+ Introduction to Web Development with Flask

SOOOOOOOOOOO I am gonna write all flask here.

## Decorators
```python
def decorator_function(func):
	def wrapper(*args, **kwargs):
		...
		func()
		...
	return wrapper

@decorator_function
def some_function():
	do_something

some_function()

```


An example (my own)(Copyright TM):
```python
def logging_decorator(func):
	def wrapper(*args):
		print(f'You called {func.__name__}{args}')
		print(f'It returned: {func(*args)}')
	return wrapper

@logging_decorator
def add(*args):
	return sum(args)

add(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
```

`function.__name__` returns the function name.
`args` is just a tuple

