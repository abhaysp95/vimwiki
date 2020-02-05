# Lecture 1,2,3 (Video 1):

## Naming and Using Variables:

* Variables names can contain only letters, numbers and underscores
* Spaces are not allowed in variable names, but underscores can be used to separate words in variable names
* Avoid using Python keywords and function names as variable names
* Variable names should be short but discriptive.

> A traceback is the record of where the interprator ran into trouble while executing the code.

## Strings

* You can use double as well as single quotes like,
	- 'This is a "new line"'
	- "This is a 'new line'"
* Here are some methods provided by python to remove whitespace from variable or message
	- lstrip() - removes whitespace from left
	- rstrip() - removes whitespace from right
	- strip() - removes whitespace from both sides
* To assign a variable's value into new variable or print() use `f` at the starting and {varible's name} in parenthesis
* When you're writing long numbers, you can group digits using underscores to
  make a large numbers more readable:
  ```py
	>>> age = 14_000_000_000
	>>> print(age)
	14000000000
  ```
* You can assign values to more than one variable using just a single line:
	```py
		>>> x, y, z = 0,9,3
	```
* Python doesn't have built-in constant types, but Python programmers use all
  capital letters to indicate a variable should be treated as a constant and
  never be changed.

## Elements of Python:

* A python program is a sequence of `definations` and `commands(statement)`
* Commands manipulate `objects`
* Each object is associated with a `Type`
* Type:
	- A set of values
	- A set of operations on these values
* `Expressions`: An operation (combination of objects and `operators`)

### Types in Python:

* int:
	- Bounded integers, e.g., 732 or -5
* float:
	- Real numbers, e.g., 3.14
* long:
	- long integers with unlimited precision
* str:
	- Strings, e.g., 'hello' or 'c'

* two types in python:
	* Scalar:
		- Individual objects that don't have internal structure
		- `int`(signed integers), `float`(floating point), `bool`(Boolean),
		  `NoneType`
		  - NoneType is special type with single value which is `None`
	* Non-Scalar:
		- Objects have internal structure
		- `str`(strings)
* You can use `type` function to find the type of an expression
* Note that, float to int conversion is truncation not rounding off

## Recap

* Python program is a sequence of commands
* Commands manipulate objects
* Objects have types
* Commmands contain operations:
	- Arithmetic, logical, relational,...
* Multiple operations are possible in a single command
* ![boolean operation results](/home/raytracer/dox/npython/ictiitk_python/mpv-shot0003.jpg)
# Lecture 4:

* Most lists you create will be dynamic
	- Means build a list and then add or remove elements from it as your
	  program runs
* The simplest way to add a new item to a list is to append the item to the
  list.

## Organizing the list:

Often time we don't have control of how the elements are entered in the list.
So, to organize them we have few methods:

### Sorting a List Permanantly with sort() Method:

* Python's sort() method makes it relatively easy to sort a list.
* You can also sort any list in reverse alphabetical order by passing the
  argument `reverse=True` to sort() method.
* syntax of sort is: `list_name.sort(key=NONE(use some), reverse=Boolean_value)`
  > It is not possible to revert back to orignal order now.

### Sorting a List Temporarily with sorted() Function:

* Maintain the original order of a list but present it in a sorted order, use
  `sorted()` function.
* syntax of sorted is: `sorted(list_name, key=NONE(use some), reverse=Boolean_value)`

### Printing a List in Reverse Order:

* To reverse the original order of a list, you can use the `reverse()` method.
* The reverse() method changes the order of a list permanantly, but you can
  revert to the original order anytime by applying `reverse()` to the same list
  second time.

## Finding the Length of a List:

* We can quickly find the length of a list by using the `len()` function
* We'll find `len()` useful when you need to identify the number of aliens that
  still to be shot down in a game.
