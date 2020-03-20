# Lecture 1,2,3 (Video 1):

## Naming and Using Variables:

* Variables names can contain only letters, numbers and underscores
* Spaces are not allowed in variable names, but underscores can be used to separate words in variable names
* Avoid using Python keywords and function names as variable names
* Variable names should be short but discriptive.

> A traceback is the record of where the interprator ran into trouble while executing the code.

This is just a preview for git hunk

## Strings

* You can use double as well as single quotes like,
	- 'This is a "new line"'
	- "This is a 'new line'"
* Here are some methods provided by python to remove whitespace from variable or message
	- lstrip() - removes whitespace from left
	- rstrip() - removes whitespace from right
	- strip() - removes whitespace from both sides
* To assign a variable's value into new variable or print() use `f` at the
  starting and {variable's name} in parenthesis
* When you're writing long numbers, you can group digits using underscores to
  make a large numbers more readable:
  ```python
	>>> age = 14_000_000_000
	>>> print(age)
	14000000000
  ```
* You can assign values to more than one variable using just a single line:
	```python
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
* ![boolean operation
  results](/home/raytracer/dox/npython/ictiitk_python/python_ss/mpv-shot0003.jpg)
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

# Lecture 6:

## Tuples:

A tuple consists of a number of values separated by commas

```python
>>> t = 'abhay', 'shanker', 'pathak', 101
>>> t[2]
'pathak'
>>> type(t)
<class, 'tuple'>
>>> empty = ()
>>> type(empty)
<class, 'tuple'>
>>> single = 1,
>>> type(single)
<class, 'tuple'>
>>> single
1,
>>> single = 1
>>> type(single)
<class, 'int'>
```

As, you can see above to get a single tuple `comma` after that single element
is necessary

### Nesting tuples:

Tuples can be nested in following way:

```python
>>> course = 'python', 'lecturer', 101
>>> student = 'you', 20, course
# I nested `course` tuple inside `student` tuple
>>> course
('python', 'lecturer', 101)
>>> student
('you', 20, ('python', 'lecturer', 101))
```

Important thing is that `course` tuple is copied to `student` tuple, not like
embedde. So, If we do something like this

```python
>>> course = 'python', 'lecturer', 102
>>> course
('python', 'lecturer', 102)
>>> student
('you', 20, ('python', 'lecturer', 101))
```

As you can see, we previously made `course` a tuple element of `student`, then
after changing `course` it's still the same. So, it copies. Changing `course`
doesn't affects `student`.

### length of tuple:

Using tuples from previous headings
```python
>>> len(singleton)
1
>>> len(empty)
0
>>> len(student)
3
# it'll not show 5, cause it's treating course as a element
>>> len(student + course)
6
```

### more operation on tuples:

Tuples can be **concatenated, repeated, indexed and sliced**. Here's some
examples:

* **Concatenation**:
```python
>>> student + course
('abhay shanker', 45, ('c', 'shivam', 102), 'c', 'shivam', 103)
>>> (course + student)[3]
'abhay shanker'
>>> (student + course)[2:]
(('c', 'shivam', 102), 'c', 'shivam', 103)
>>> (course + student)[1:6]
>>> (course + student)[1:6]
('shivam', 103, 'abhay shanker', 45, ('c', 'shivam', 102))
>>> (course + student)[1:5]
('shivam', 103, 'abhay shanker', 45)
```

* **repeatition**:
```python
>>> 2*student
('abhay shanker', 45, ('c', 'shivam', 102), 'abhay shanker', 45, ('c',
'shivam', 102))
```

## Unpacking Sequences:

* Strings and tuples are examples of sequences:
	* indexing, slicing, concatenation, repeatition operations applicable on
	  seqsequences.
* Sequence unpacking operation can be applied to sequences to get the
  components:
	- _Mulitple assignment statement_
	- LHS and RHS must have equal length
Let's take examples:

```python
>>> student	# from previous tuple
('abhay shanker', 45, ('c', 'shivam', 102))
>>> name, roll, course = student
>>> name
'abhay shanker'
>>> roll
45
>>> course
('c', 'shivam', 102)
# let's take string as example as it is also sequence
>>> a,b,c='dhanu'
Traceback (most recent call last):
  File "<input>", line 1, in <module>
	a,b,c='dhanu'
ValueError: too many values to unpack (expected 3)
>>> a,b,c = 'luv'
>>> a
'l'
>>> b
'u'
>>> c
'v'
>>> print(a,b,c)
l u v
```

As you have noticed from above that, LHS should equal to RHS

## Lists

* Ordered sequence of values
* Written as sequence of comma-separated values between square brackets
* Values can be of different types:
	- usually the items all have the same types

```python
>>> lst = [1, 2, 3]
>>> type(lst)
<class 'list'>
>>> lst1 = [2, 3, 'name']
>>> lst1
[2, 3, 'name']
```

* List is also a sequence type:
	* All the operations of sequence are also applicable here

```python
>>> len(lst)
3
>>> lst1[1:]	# slicing
[3, 'name']
>>> [0] + lst1 + [10]		# concatenation
[0, 2, 3, 'name', 10]
>>> 3 * lst		# repeatition
[1, 2, 3, 1, 2, 3, 1, 2, 3]
>>> x, y, z = lst1	# unpacking
>>> x
2
>>> y
3
>>> z
'name'
```

### More operations on list

* lst.append(x)		     # append the value x at last pos
* lst.extend(seq)	     # add a sequence to list(from end)
* lst.insert(index, x)	 # insert with index and value x
* lst.remove(x)		     # remove by value
* lst.pop(i)		     # providing index
* lst.pop()			     # remove from last
* lst.index(x) `*`		     # get the value of index x
* lst.count(x) `*`          # no. of repeatition of value x in a list
* lst.sort()             # sort the list, elements should be of same data type
* lst.sort(reverse=True) # sorts from descending-ascending
* sorted(lst)  `*`          # sorts lst, but doesn't saves it(temporary)
* lst.reverse()          # reverses the list

> *Note*: every operation which isn't containing `*` is modifying the list
permanantly.

# Lecture 7:

## Mutabale and Immutable types:

* tuples and list types look very similar
* however, there is one major difference: Lists are *mutable*
	- Contents of list can be modified
* tuples and strings are *immutable*
	- Contents can't be modified

```python
>>> indoor = ['badminton', 'table-tennis', 'chess']

>>> outdoor = ['football', 'cricket']
>>> games = (indoor, outdoor)
>>> type(games)
<class, 'tuple'>
>>> games
(['badminton', 'table-tennis', 'chess'], ['football', 'cricket'])
# let's take another example
>>> lower = 'pants', 'shorts'
>>> upper = 'shirt', 't-shirt'
>>> type(lower)
<class, 'tuple'>
>>> dress = [lower, upper]
# we don't need to cover lower/upper in `''` as they are already defined
>>> type(dress)
<class, 'list'>
>>> dress
[('pants', 'shorts'), ('shirt', 't-shirt')]

# now, lets try some for mutable and immutable
>>> games[0]
['badminton', 'table-tennis', 'chess']
>>> games[0] = card	# or 'card'
Traceback (most recent call last):
  File "<input>", line 1, in <module>
    games[0] = 'card'
TypeError: 'tuple' object does not support item assignmen
# so, can't change tuple, it's immutable

# let's make another tuple, but listing explicitly all elements
>>> games1 = (['badminton', 'table-tennis', 'chess'], ['football', 'cricket'], ['solitaire', 'hearts', 'freecell'])
>>> games1[:1]
(['badminton', 'table-tennis', 'chess'],)
>>> games1[:2] == games
True
>>> indoor[2] = 'carrom'
>>> games1[:2] == games
False
```

Now, let's resolve some questions raised above:
* Why did tuple `games` changed when we changed `indoor` list's element?
	- tuple `games` contains reference of lists `indoor` and `outdoor`.
	- Thus, changing *outdoor* updated *games* as well.
* But why `games1` didn't changed?
	- Because it contains a different list(even though elements are same, we
	  gave it explicitly)
	- Two lists can have the same content
	- Modifying one will not change the other.
	- So, `games` and `games1` tuple elements had co-incidently same elements
	  even though address of those elements were different

So, we can also change element of `games1` tuple or should I say, elements
inside the list of tuple `games1`

```python
>>> games1[0][2] = 'carrom'
>>> games1[:2] == games
True
```

## Summary of Sequences

| *Operation*    | *Meanining*                                       |
|----------------|---------------------------------------------------|
| seq[i]         | i-th element of the sequence                      |
| len(seq)       | length of the sequence                            |
| seq1 + seq2    | concatenate the two sequence                      |
| num*seq        | repeat seq num items                              |
| seq[start:end] | slice starting from *start* and ending at *end-1* |
| e in seq       | True if e is present in seq, False otherwise      |
| e not in seq   | True if e is not present in seq, False otherwise  |
| for e in seq   | Iterate over all elements in seq                  |
|                | (e is bound to one element per iteration)         |


## list comprehension

* A concise way to build list
* Similar to Math's set builder notation
* Example: let's represent square of natural numbers until 10 in set builder notation:
	* {x*x | x _belongs to_ {1,2,3,....,10}}
* In Python, we can say:

```python
>>> lst = [x*x for x in range(1, 11)]
>>> lst
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

* Consists of a bracket containing an expression followed by a `for` clause,
then zero or more `for` or `if` clauses.

```python
>>> nums = [-1, 25, 9, -30, 5]
>>> pos = [x for x in nums if x > 0]
>>> pos
[25, 9, 5]

>>> sqneg = [x*x for x in nums if x < 0]
>>> sqneg
[1, 900]

# let's get tuple with list commprehension
>>> abspair = [(x, abs(x)) for x in nums]
>>> abspair
[(-1, 1), (25, 25), (9, 9), (-30, 30), (5, 5)]
# although it's still a list type
>>> type(abspair)
<class 'list'>
```

### Evaluation of list commprehension

Let's understand with an example:

```python
>>> eqlst = [(x, y) for x in [1, 2, 3] for y in [12, 9, 27, 4, 50] if x
*x == y]
>>> eqlst
[(2, 4), (3, 9)]
```

Now, in general the above list comprehension syntax could be given in following
nested loop/case

```python
>>> for x in range [1, 2, 3]:
...     for y in range [12, 9, 27, 4, 50]:
...         if x*x == y:
...				(x,y)
```

# sets:
* Another kind of sequence
* An unordered collection with no duplicate elements
* Supports:
	 - membership testing
	 - eliminating duplicate entries
	 - set operations: union, intersection, difference, and symmetric difference

```python
>>> basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
>>> type(basket)
<class 'list'>
# using set constructor to convert list 'basket' to set sequence
>>> fruits = set(basket)
>>> fruits
{'pear', 'orange', 'apple', 'banana'}
# Note: order in above given set is different to what was in the list, order isn't considered
>>> type(fruit)
Traceback (most recent call last):
  File "<input>", line 1, in <module>
    type(fruit)
NameError: name 'fruit' is not defined
>>> type(fruits)
<class 'set'>
>>> 'apple' in fruits
True
>>> 'mango' in fruits
False
```

As, we know now, operations of sets are possible(order can be changed):
```python
>>> A = set('acads')
>>> B = set('institute')
>>> A + B
Traceback (most recent call last):
  File "<input>", line 1, in <module>
    A + B
TypeError: unsupported operand type(s) for +: 'set' and 'set'
>>> A
{'d', 's', 'a', 'c'}
>>> B
{'t', 's', 'u', 'i', 'e', 'n'}
>>> A - B	# set difference
{'d', 'a', 'c'}
>>> B - A	# set difference
{'t', 'u', 'i', 'e', 'n'}
>>> A | B	# set union
{'d', 't', 's', 'u', 'c', 'i', 'a', 'e', 'n'}
>>> A & B	# set intersection
{'s'}
>>> A ^ B	# symmetric difference
{'t', 'c', 'i', 'e', 'd', 'u', 'a', 'n'}
>>> (A - B) | (B - A)	# symmetric difference
{'d', 't', 'u', 'c', 'i', 'a', 'e', 'n'}
```

## Conditional tests:

Python uses the values True and False to decide whether the code in an if statement should be executed.
Testing for equality is case sensitive in Python.

### Checking whether a Value is in a list

* Key-word `in` is used to find out whether a particular value is already in a list
* This technique is quite powerful because you can create a list of essential values, and then easily check whether the value you're testing matches on of the values in the list.

```python
>>> wm = ['bspwm', 'awesome', 'qtile', 'dwm']
>>> 'i3wm' in wm
False
>>> 'dwm' in wm
True
```

### Checking whether value is not in a list:

* Use keyword `not in` for this situation

```python
fruits = ['mango', 'apple', 'guava', 'grapes']
fruit = 'pear'

if fruit not in fruits:
	print(f"{fruit.title()}, it has to be bought yet")
	# or use
	print (fruit.title(), "it has to be bought yet")
```

## Boolean Expressions

* A boolean expression is just another name for a conditional test.
* A boolean value is either **True** or **False**.
* Boolean values are often used to keep track of certain conditions.
* Boolean values provide an efficient way to track the state of a program or a particular condition that is important in your program.
