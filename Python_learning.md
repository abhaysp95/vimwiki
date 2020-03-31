
- python is prerquisite for placement.
	* InfyTQ offers only python for problem solving.
	* Approx. all the placement companies offers Python Programming Language for solving the coding based questions.

# Introduction of Python

* The implementation of Python was started in the December, 1989 by Guido Van Rossum at  CWI in Netherland.
* He name it after the television show `Monty Python's Flying Circus`.
* It is high level programming language.
* Python uses interpreter for converting High Level language into low level language.
* Python is case sensitive.
* Free and open source.

> Range of int(signed) => -32768 to 32767

## Data type in python -

In python data type doesn't matters. You can put any value in a variable in python.

## Identifiers in python

- Any keyword can't be identifier
- Don't give space in variable name(you can use special characters)
- There are almost 33 keywords in python eg,. True, None, for, while,
- Special literal in python None(same as NULL in c)
- Input functions is identified by default as string.
- Two new operator in python
	* % = To return remainder after division modulus
	* // = prints the int part of division
	* ** = this is basically exponent like 2**3=8
- syntax of if
```py
	if condition:
		true
	else:
		false
```
	or to put ladder

```py
	if condition-1:
		statement-1
	elif condition-2:
		statement-2
	...
	elif  condition-n:
		statement-n
	else:
		default statement
```

- Comments in pyhon is given by #
- Can't use `-` in python
- Python returns `true` or `false` in decision making
- There is no increment operator in python(++,--)
- There is new operator <> similar to (!= not equal to) doesn't works in python 3
- Assignment operators
	* =		assignment
	* /=	divide and assign
	* +=	add and assign
	* -=
	* **=
	* %=
	* //=

- Logical Operators are	`and`, `or` & `not` (written in same way)
- `in`		Returns true if a variable is in sequence of another variable, else false.
- `not in`	Returns true if a variable is not in sequence of another variable, else
- `is`		Returns true if identity of two operands are true, else false
- `not is`	Reverse of _is_

Learn for modules or objects by using `dir`, like this

```py
	>>> import random
```

Python interpreter also has help command which displays the section from the python docs related to the name you're interested in.

```py
	>>> help(random.randint)
```

## List

* List is defined in following way:
```py
	>>> lst=['abhay', 'shanker', 'pathak', 9]
	# it can be shown in following ways
	>>> lst
	['abhay', 'shanker', 'pathak', 9]
	>>> lst[2]
	['pathak']
	>>> lst[-3]
	['shanker']
	>>> lst[1:3]
	['shanker', 'pathak', 9]
	>>> lst[:2]
	['abhay', 'shanker', 'pathak']
	>>> lst[2:]
	['pathak', 9]
	>>> lst[0:3:2]
	['abhay', 'pathak']
	>>> lst[::-1]
	[9, 'pathak', 'shanker', 'abhay']
```

* to iterate a list two ways:
	* traditional way:
	  ```py
		>>> for i in range(0, len(lst)):
			print(lst[i])
		abhay
		shanker
		pathk
	  ```
	* python approach:
	  ```py
		>>> for n in lst:
			print(n)
		abhay
		shanker
		pathak
	  ```

* `List` in python are of static type.
```py
	>>> c = [10, 20, 30, 40, 50, 60]
	>>> del c[3:]		# deletes onwards of index 3
	# or
	>>> del c[3:6]		# in range
```

### some functions/methods for list:

| **Methods**              | **Description**                                           |
|--------------------------|-----------------------------------------------------------|
| max(lst)                 | gets max element of list                                  |
| min(lst)                 | gets min element of list                                  |
| len(lst)                 | gets length of list                                       |
| lst = list(num)          | converts string in list,                                  |
|                          | where num='3028490' (in string format)                    |
| sum(lst)                 | gives sum of list elements(if elements are in int format) |
| index(object)            | returns the index value of object                         |
| count(object)            | number for how many times element appeared                |
| pop() or pop(index)      | deletes last element of list or element on index          |
| insert(loc, object)      | insert object on given index(loc)                         |
| list1.extend(list2)      | add list2 contents to list1, or                           |
|                          | list3 = list1 + list2                                     |
| remove(value)            | give the value present in a list(different from pop)      |
| reverse(list)            | reverses the list content                                 |
| sort()                   | sorts the list                                            |
| sort(reverse=True) | reverse sort list                                         |
|                          |                                                           |

> **Note**: sum(lst)	, sum is function
		lst.reverse()	, reverse is method
## Array:

* `Array` in python are of dynamic type:
```py
	>>> size=int(input("Enter number: "))
	>>> lst=[]
	>>> print("Enter ", size, "Elements :")
	>>> for i in range(size):
		n = int(input())
		lst.append()
	>>> print("Given elements are: ")
	>>> for n in range(len(lst)):
			print(n)
```

* remove method doesn't returns value
* We can change list items but not of tuple:
	```py
	>>> tup = (19, 20, 21)
	>>> tup
	(19, 20, 21)
	```

| List        | Tuple       |
|-------------|-------------|
| Mutable     | Immutable   |
| Slow        | Fast        |
| More memory | Less memory |
|             |             |

* Blank tuple => `tup()`
* One element in tuple => `tup(10, )`, without `,` it'll be treated as `int`.
* All the slicing rules of tuple will be same to list.
* printing:
	```py
	>>> print(*tup, sep="\n")
	```
* Functions will be same as list.
* Tuple doesn't have sort `(lst.sort())`, it has `sorted(tup)`
* It doesn't have `lst.reverse()`, it has `reversed(c)`. By default it will return memory address. To see reverse of tuple use:
	```py
	>>> reversed(tup)
	<reversed object at 0x3947....34>
	>>> list (reversed(c))
	[.....]
	```
* Tuple has `c.index(element)` prints index, `c.count(element)` which gives count of that element inside tuple
* To append in tuple you have to insert the element in another tuple and then merge with previous tuple.

## Strings:

* Strings pythons are immutable
* In python, Strings are stored as individual characters in contiguous memory location(same as `C`).
* String can be accessed from both the directions forward and backward.(Indexing is same as in `list` e.g., 1,2,3 and -1,-2,-3).
* E.g.,:
	* python2
		```py
			sname=raw_input('Enter the data: ')
		```
	* python3
		```py
			sname=input('Enter the data: ')
		```
* 3 operators in string:
	* **Basic Operators**{(m `+` n), or n`*`10}
		* eg.,
		```py
			for i in range(6):
				print("*"*i, end=" ")
		```
		> **Note**: 'salman'+420 is invalid, while 'salman'+'420' or 'salman'+str(420) is valid
	* **Membership Operators**
		* two operaors: `in` and `not in`
		* eg.,
		```py
		s=input('enter a string: ')
		ss=input('enter a substring: ')
		if ss in s:
			print('Substring found')
		else:
			print('Substring not found')
		```
		or you can write like this:
		```py
		s=input('enter a string: ')
		ss=input('enter a substring: ')
		print("Substring Found" if ss in s else "Substring not Found")
		```
	* **Relational Operators**
		* eg.,
		```py
		>>> "RAJAT"=="RAJAT"
		True
		>>> "Z"!='z'
		True
		```
* Slicing is same in string as it was in `list`.
* `reverse` a string, n="united", reverse will be n[::-1] or n[-1::-1]
* To convert a list don't do p=str(lst), if will be like `"['d', 't']"`, use `".join(lst)"`
* You can do `sum(tup)` to get the sum of the elements of tuple.
* Use `string.capitalize()` to make the first letter of sentence capitle(`title()` makes every words first letter capital).
* `string.count('element')` gives first position of that element in string.
* To get some specific element out of list:
	```py
	>>> lst=['abhay pathak', 'ayush singh', 'salman khan', 'utkarsh maurya', 'nirbhay pathak']
	>>> for n in lst:
		if n.endswith ("pathak"):
			print(n)

	abhay pathak
	nirbhay pathak
	```py
	>>> n.find('pathak')	# currently n has value nirbhay pathak
	8
	>>> n.find('singh')
	-1
	```
* `string.isalnum()` gives __true__ if string contains __number, alphabets or both__, anything else will give __false__
* `string.isalpha()` only for alphabets
* `string.isdigit()` only for digits
* `string.lower()` gives __true__ if all alpha are in lowercase else __false__
* `string.upper()` inverse of `.lower()`
* `string.isspace()` gives __true__ if strings contains all space and nothing else.
* `string.swapcase()` toggles upper and lowercase
* `string.startwith()` same as __endwith()__ but from start
* `string.strip()` strips space from both left and right. Other are **string.lstrip() string.rstrip()**
* `string.split(element)` splits from the given element(removes the element also). If no argument given then it will consider __space__ as split element by default.


## Sets
-----------

A set is an unordered collection data type with no duplicate elements Sets are iterable and mutable. The elements appear in an arbitrary order when sets are iterated.

Sets are commonly used for membership testing, removing duplicates entries, and also for operations such as intersection, union and set difference.

### How to create Sets

Sets can be created calling the built-in set() function with a sequence or another iterable object.
```python
>>> # creating an empty set
>>> setA = set()
>>> setA
set()

>>> print(setA)
set()
>>> type(setA)
<class 'set'>

>>> # creating a set with a string
>>> setA = set('coolabhays')
>>> print(setA)
{'c', 'y', 'a', 'l', 's', 'o', 'b', 'h'}
>>> setA
{'c', 'y', 'a', 'l', 's', 'o', 'b', 'h'}
>>>
```

As you can see above, set removed all the duplicate elements inside the string. And also, it has no particular or unique order of printing.

So, another example is shown below for the above mentioned characterstics of set:

```python
>>> # let's create a list
>>> lst=[10, 20, 30, 40, 50, 40, 10, 30, 20]
>>> lst
[10, 20, 30, 40, 50, 40, 10, 30, 20]
>>> strB = set(lst)
>>> strB
{40, 10, 50, 20, 30}
>>>
>>> # taking on more example
>>> string='dhananjay'
>>> lst = list(string)
>>> lst
['d', 'h', 'a', 'n', 'a', 'n', 'j', 'a', 'y']
>>> strC = set(lst)
>>> strC
{'y', 'a', 'd', 'h', 'j', 'n'}
>>>
```

### Methods of set:

let's perform some methods of on set in following way:

```python
>>> # methods of set
>>> strC.add('p')
>>> strC
{'y', 'a', 'p', 'd', 'h', 'j', 'n'}
>>> # see that, 'p' is added in random place
>>> strC.add('y')
>>> strC
{'y', 'a', 'p', 'd', 'h', 'j', 'n'}
>>> # since 'y' was already in the set, so it wasn't added again
>>>
```

We can update set with multiple elements as follow:

```python
>>> # add multiple elements
>>> strC.update([8, 9, 10])
>>> strC
{'y', 'a', 'p', 8, 9, 'd', 10, 'h', 'j', 'n'}
>>>
```

Now, we can also remove elements from set by `remove()` and `discard()` function.

```python
>>> # for removing element
>>> strC.remove('d')
>>> strC
{'y', 'a', 'p', 8, 9, 10, 'h', 'j', 'n'}
>>> strC.discard(9)
>>> strC
{'y', 'a', 'p', 8, 10, 'h', 'j', 'n'}
>>>
```

Differenece between `discard` and `remove` is, let if element you are removing is not present in the set, then `remove` will give error while `discard` will not.

We can also use pop to remvoe elements, it removes the first element of set.

```python
>>> # we can also use pop
>>> strC.pop()
'y'
>>> strC
{'a', 'p', 8, 10, 'h', 'j', 'n'}
>>>
```

To remove all elements use `clear()` method
```python
>>> strC.clear()
```

There is also a `isdisjoint()` method, which returns `false` if even a element is common among them, else it'll return `true`.

```python
>>> # disjoint
>>> # if common element in two sets then it'll return false, else true
>>> seta.isdisjoint(setb)
False
>>> setb.isdisjoint(seta)
False
>>> seta.isdisjoint(seta)
False
>>> setA
{'c', 'y', 'a', 'l', 's', 'o', 'b', 'h'}
>>> seta.isdisjoint(setA)
True
>>>
```

### Operations on set

We can perform some operations on set, like union, intersection, difference etc. They are as follow:

```python
>>> # operations on set
>>> seta = {1, 3, 4, 2, 9}
>>> setb = {3, 8, 6, 4, 5, 7, 1}
>>> seta
{1, 2, 3, 4, 9}
>>> setb
{1, 3, 4, 5, 6, 7, 8}
>>>
>>> # intersection operation
>>> seta.intersection(setb)
{1, 3, 4}
>>> seta&setb
{1, 3, 4}
>>> # difference
>>> seta.difference(setb)
{9, 2}
>>> seta - setb
{9, 2}
>>> setb.difference(seta)
{8, 5, 6, 7}
>>> # as you can see, order of variable is important in difference
>>>
>>> # union
>>> seta.union(setb)
{1, 2, 3, 4, 5, 6, 7, 8, 9}
>>> seta|setb
{1, 2, 3, 4, 5, 6, 7, 8, 9}
```
