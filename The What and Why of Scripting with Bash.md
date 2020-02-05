# Types of Linux Shells
___

Every shell has its own features, and some of them are very popular among developers today. These are some popular ones:
* **Sh Shell**: This is called the Bourne Shell`, this was developed in AT&T labs in the 70s by a guy named `Stephen Bourne`. This shell offers many features.
* **Bash Shell**: Also called the `Bourne again shell`, this is very popular and compatible with sh shell scripts, so you can run sh scripts without changing them.
* **Ksh Shell**: Also called `Korn Shell`, this is compatible with sh and bash. Ksh offers some enhancements over the Bourne shell.
* **Csh and tcsh**: Linux was built using the **C** language and that drove developers at _Berkeley University_ to develop a C-style shell in which the syntax is similar to the C language. Tcsh add some minor enhancements in Csh.

# What is Bash Scripting?
___

The basic idea of scipting is to execute multiple commands to automate some specific job.

You can run multiple commands from the shell by separating them with semi-colons(;):
```sh
	ls ; pwd
```

This previous line is a mini bash script.

Every keyword you type in bash is actually `Linux binary(program)`, even the `if` statement or `else` or `while` loops. All are Linux executables.

# The bash command hierarchy
___

When working on the bash shell, you will most likely feel that is a simple matter of typing and hitting the _Enter_ key. You should know, things are never quite as simple as we imagine.

## Command type

Bash's built-in `type` command will display the type of commadn for a given word entered at the command line, which will come in aid to differentiate like between alias or actual command:
	* Alias
	* Function
	* Shell built-in
	* Keyword
	* File(command)
This list is also representative of the order in which they are searched.

The following command demonstrates the simple use of `type`:

```sh
	$ type ls
	ls is an alias for ls -FhN -a --color=auto --group-directories-first
```

We can extend this further to display all the matches for the given command:

```sh
	$ type -a ls
	ls is an alias for ls -FhN -a --color=auto --group-directories-first
	ls is /usr/bin/ls
	ls is /bin/ls
```

If we need to just type in the output, we can use the `-t` option. This is useful when we need to test the command type from within a script and only need the type to be returned. This excludes any superfluous information, and thus makes it easier for us human to read.

```sh
	$ type -t ls
	alias
	$
	$ type -at ls
	alias
	file
	file
```
<!--- type -t doesn't works on zsh as I tested -->

The output is clear and simple and just what a computer or script requires.

The built-in `type` can also be used to identify shell keywords such as `if`, and `cases`. Use of `type` being used against multiple arguments and types:

```sh
	$ type ls quote pwd do id
	ls is /usr/bin/ls
	quote not found
	pwd is a shell builtin
	do is a reserved word
	id is /usr/bin/id
```

Here quote isn't defined but if it is defined you can also the function defination with type(assuming quote is function here).

## Command Path

Linux will check for executables in the `PATH` environment only when the full or relative path to the program is supplied. In general, the current directory is not searched unless it is in the `PATH`. To add the our current directory within the `PATH` by adding the directory to the `PATH` variable. Here,

```sh
	$ export PATH=$PATH:.
```

In general, organizing scripts into a structured directory hierarchy is probably a great idea. Add a dirctory like `$HOME/bin` to your `PATH` variable will enable you to find the scripts by name and without the file path.

The following command creates the directory if it doesn't exists and add it to your `PATH`:

```sh
	$ test -d $HOME/bin || mkdir $HOME/bin
```

Although the preceding command-line list is not strictly necessary, it does show that scripting in bash is not limited to the actual script, and we can use conditional statements and other syntax directly at command line. From our viewpoint, we know that that preceding command will work whether you have the `bin` or not. The use of `$HOME` variable ensures that the command will work without considering your current filesystem context.

# Preparing text editors for scripting
___

It's upto your choice which editor you use. Make configuration according to your need. I'm using `vim` as my text editor.

# Creating and Executing Script

With our editors ready, lets move to creating and executing scripts

## Hello World!

We are begining with simple **Hello World** script. The contents of the file should read as in the following manner:

```sh
	#!/bin/bash
	echo "hello world"
	exit 0
```

Here's the description:-

	* `#!/bin/bash`: Normally this is always the first line of the script which is known as ***shebang***. The shebang starts with the comment, but the system still uses this line. A comment in a shell script has the `#` symbol. The shebang instructs the interpreter of the system to execute the script. We use bash shell scripts, and we may use PHP or Perl for other scripts, as required. If we don't add the shebang then the commands will be run within the current shell; it may cause issues if we run another shell.
