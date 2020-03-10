# input and output:

* To take a single character _ch_ as input, you can use `scanf("%c",&ch);` and `printf("%c",ch);` writes a character specified by the argument char to stdout.
* You can take a string as input using `scanf("%s",s)`, but works till it finds first space.
* To take a line as input, use `scanf("%[^\n]%*c",s);`, where _s_ is defined as `char s[MAX_LEN]` where MAX_LEN is the maximum size of _s_. Here, [] is the scanset character. ^\n stands for taking input until a newline isn't encountered. Then, with this %*c, it reads the newline character and here, the used * indicates that this newline character is discarded.

# C programming strings:

* In C programming, a string is a sequence of characters terminated with a null characeter `\0`. For example:
	```c
		char c[] = "c string";
	```
* When the compiler encounters a sequence of characters enclosed in the double quotation marks, it appends a null character `\0` at the end by default.
* Declaration of strings:
	```c
		char s[5];
	```

### How to initialize strings?

Here are the following ways
```c
	char c[] = "abcd";
	//or
	char c[50] = "abcd";
	//or
	char c[] = {'a', 'b', 'c', 'd', '\0'};
	//or
	char c[5] = {'a', 'b', 'c', 'd', '\0'};
```

Let's look into this example:
```c
	char c[5] = "abcde";
```
Here, we trying to assign 6 characters (last char is `\0`) to a `char` array having 5 characters. This is bad.

### Read string from users:

We can use `scanf()` to read a string. The `scanf()` reads the sequence of characters until it encounters `whitespace(space, newline, tab etc.)`.
```c
	char name[20];
	scanf("%s", name); // this will take only one word
	printf("%s", name);
```

We can use `fgets()` function to read a line of string. And, you can use `puts()` to display the string.
```c
	char name[30];
	fgets(name, sizeof(name), stdin); // read string
	printf("Name: ");
	puts(name);	// display string
```
The `sizeof(name)` results to 30. Hence, we can take a maximum of 30 characters as input which is the size of the `name` string.

**Note:**: The `gets()` function can also be to take input from the user. However, it is removed from the C standard.

It's because `gets()` allows you to input any length of characters. Hence, there might be a buffer overflow.

### Passing Strings to Functions

Strings can be passed to a function in a similar ways as arrays.
```c
	int main() {
		char str[50];
		fgets(str, sizeof(str), stdin);
		displayString(str); // Passing string to a function
		return 0;
	}
	void displayString(char str[]) {
		printf("String Output: ");
		puts(str);
	}
```

## Dynamic memory allocations:

### malloc():
The `malloc()` function reserves a block of memory of the specified number of bytes. And, it returns a `pointer` of `void` which can be casted into pointers of any form.

> Syntax:
```c
ptr = (castType*)malloc(size);
// Example:
ptr = (float*)malloc(100 * sizeof(float));
```
The above statement allocates 400 bytes of memory. It's because the size of `float` is 4 bytes. And, the pointer `ptr` holds the address of the first byte in the allocated memory.

The expression results in a `NULL` pointer if the memory can't be allocated.

### calloc():

The name `calloc()` stands for contiguous allocation.

The `malloc()` function allocates memory and leaves the memory uninitialized. Whereas, the `calloc()` function allocates memory and initializes all bits to zero.

> Syntax:
```c
ptr = (castType*)calloc(n, size);
//Example
ptr = (float *)calloc(25, sizeof(float));
```
The above statement allocates contiguous space memory for 25 elements of type `float`.

### free():

This statement frees the space allocated in the memory pointed by `ptr`.

> Syntax:
```c
free(ptr);
```

### realloc():

If the dynamically allocated memory is insufficient or more than required, you can change the size of previously allocated memory using the `realloc()` function.

> Syntax:
```c
ptr = realloc(ptr, x);
```
Here, `ptr` is reallocated with a new size `x`.
