
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
