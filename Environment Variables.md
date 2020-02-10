# Exploring Environment Variables
___

`Environment variables is used to store information about shell session and the working environment. Data stored in it is easily accessible by any program and script from the shell.`

	There are two types environment variables:
	- Gloabal Variables
	- Local Variables

## Looking at global environment variables
___

`Global environment variables are visible from the shell session and from the spawned child subshells.`
Local Variables are only visible in the shell in which they are created. <u>To view global env. variables use **env** or **printenv** command.</u>

```sh
	$ printenv
	# variable names
```
To display an individual env. variables, use _printenv_ but not _env_

```sh
	$ printenv HOME
	/home/raytracer
	$
	$ env HOME
	env: HOME: No such file or directory
	# where HOME is a variable
```
Use **$** sign to display variable's value with <u>echo</u>. Also, the $ sign as variable name also allows the variable to be passed as a command parameter:

```sh
	$ ls $HOME
	Desktop		Download	Music	Pictures	Documents
	.vimrc		.zshrc		.tmux.conf
	$ ls /home/raytracer
	Desktop		Download	Music	Pictures	Documents
	.vimrc		.zshrc		.tmux.conf
```
Global variables are available to any process in subshell, check it out:

```sh
	$ bash
	$
	$ ps -f
	# informations about process
	$ echo $HOME
	/home/raytracer
	$
	$ exit
	exit
	$
```
## Looking at local environment variables

`Local variables can only be seen in the local process in which they are defined.`

You can define local variables of your own, that's why they are known as user-defined local variables(as linux system also sets some of the local variables).

There isn't a command which would tell you the local variables in CLI. Although, you can use **set** command to display all variables(global and local).

```sh
	$ set
	BASH=/bin/bash
	ZSH=/bin/zsh
	[...]
	dox=/home/raytracer/Documents
	[...]
	$
```
Here, are some points to remember -
* Variables from __env__ and __printenv__ are also displayed under the __set__ command.
* __set__ command displays variables in sorted order.
* __env__ command has some additional functionalities which __printenv__ doesn't have.
* As global variables are all in upper-case, you should try to define local(user-defined) variables in lower-case to not make system confuse.

# Setting User-defined Variables
___

## Setting local user-defined variables

In a new shell, you are allowed to create a local user-defined variable which will be visible in your current shell process.

```sh
	$ echo $my_variable
	# nothing comes up
	$ my_variable=Hello		# don't use space before and after =
	$ echo $my_variable
	Hello
```

Now, you can just use $my_variable to reference to __Hello__.

To assign a string value which contains space, you need to single or double quote to delineate the begining and the end of the string(as shell understoods words after space as another command):

```sh
	$ my_variable=Hello World
	-bash: World: command not found
	$
	$ my_variable="Hello World"
	$
	$ echo $my_variable
	Hello World
	$
```

Also, as mentioned above don't put space in asignments. If you put spaces in the assignments, the shell interprets the value as separate command:

```sh
	$ my_variable = "Hello World"
	-bash: my_variable: command not found
	$
```

After you set local variable it's available for your any shell process. However, if you spawn other shell or spawn a child shell it will not be available for them:

```sh
	$ my_variable="Hello World"
	$
	$ bash
	$
	$ echo $my_variable

	$ exit
	exit
	$ echo $my_variable
	Hello World
	$
```

> In the same way, if you created a local variable in a child shell it will not exist in it's parent shell.

```sh
	$ echo $my_variable

	$ bash
	$
	$ my_child_variable="Hello little world"
	$
	$ echo $my_child_variable
	Hello little world
	$
	$ exit
	exit
	$ echo $my_child_variable

	$
```

## Setting global environment variables

Global environment variables are visible from any child process. Method is to set first the local variable and then make it global. This is done by **export** command and variable name minus **$** sign.

```sh
	$ my_variable="It's global"
	$
	$ export my_variable
	$
	$ echo $my_variable
	It\'s global
	$
	$ bash
	$
	$ echo $my_variable
	It\`s global
	$ exit
	$
	$ echo $my_variable
	It\`s global
	$
```

> Changing a global environment variable in child shell doesn't affect the variable's value in parent shell.

```sh
	$ my_variable="Hii"
	$ export $my_variable
	$
	$ echo $my_variable
	$
	$ bash
	$ echo $my_variable
	Hii
	$ my_variable="NULL"
	$
	$ echo $my_variable
	NULL
	$ exit
	$ echo $my_variable
	Hii
	$
```

It is worth noting that a child shell can't use _export_ command to change the parent's shell global environment variable's value:

```sh
	$ my_variable="Excuse me!"
	$ echo $my_variable
	Excuse me!
	$
	$ bash
	$ export my_variable="Yes?"
	$ echo $my_variable
	Yes?
	$
	$ exit
	exit
	$ echo $my_variable
	Excuse me!
```
# Removing Environment Variables
___

If you can create an environment variable then you can also remove an existing environment variable. It can be done by ***unset*** command.
You have not to use **$** sign while referencing to a variable in _unset_ command:

```sh
	$ echo $my_variable
	It\`s global
	$
	$ unset my_variable
	$
	$ echo $my_variable

	$
```
> #### Tip:
>
> It can be confusing to remember when to use **$** and when not to use. Remember, if you are doing anything with variable use $ and if you're doing anyting to variable don't use $ sign. The exception in this rule is _printenv_ to display variable.

# Uncovering Default Shell Environment Variables:
___

Bash shell has some specific environment variables by default to define the system environment.
Below table shows some of them that are compatible with unix sh:

**Table 6.1: The bash Shell Bourne Variables**

| Variable | Description                                              |
|----------|----------------------------------------------------------|
| CDPATH   | A colon seperated list of directories used as            |
|          | a search path for the cd command                         |
| HOME     | The current user's home directory                        |
| IFS      | A list of characters that separate fields used by        |
|          | shell to split text strings                              |
| MAIL     | The filename for the current user's mailbox(The          |
|          | bash shell checks this file for new mail.)               |
| MAILPATH | A colon-seperated list of multiple filenames for         |
|          | the curent user's mailbox(The bash shell check           |
|          | each file in this list for new mail)                     |
| OPTARG   | The value of the last option argument processed          |
|          | by the getopt command                                    |
| OPTIND   | The index value of the last option argument processed    |
|          | by the `get opt` command                                 |
| PATH     | A colon-seperated list of directories where the shell    |
|          | looks for commands                                       |
| PS1      | The primary shell command line interface prompt string   |
| PS2      | The secondary shell command line interface prompt string |
|          |                                                          |

Besiders, some of the default of Bourne Shell, bash provides some other global variables of itself also

| Variable     | Description                                                          |
|--------------|----------------------------------------------------------------------|
| BASH         | The full pathname to execute the current instance of bash            |
|              | shell                                                                |
| BASH_ALIASES | An associative array of currently set aliases                        |
| BASH_ARGC    | A variable array that contains the number of parameters              |
|              | being passed to a subroutine or shell script                         |
| BASH_ARCV    | A variable array that contains the parameters being                  |
|              | passed to a subroutine or shell script                               |
| BASH_CMDS    | An associative array of locations of commands the shell has executed |

There are many others which I can't write now here.

# Setting the PATH Environment Variable
___

When you enter the command in the shell CLI, the shell must search the system to find the program. The PATH environment variables defines the directories it searches looking for the command or programs. PATH variable can look like this:

```sh
	$ echo $PATH
	/home/raytracer/.local/bin/.scripts:/home/raytracer/.local/bin:/usr/local/bin:/usr/bin:/bin:/usr/local/sbin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl:/var/lib/snapd/snap/bin:/home/raytracer/.fzf/bin
	$
```

This show that there are eight directories where the shell looks for the command or program. The directories in the path are seperated by colons.

If a command or program's location is not included in the PATH variable, the shell cannot find it without an absolute directory reference.

```sh
	$ myprog
	-bash: myprog: command not found
```

To add a program, command or executable script, you can add new search directories to existing PATH environment variable without building it from scratch. This looks something like this:

```sh
	$ echo $PATH
	/usr/loca/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
	$
	$ PATH=$PATH:/home/raytracer/Scripts
	$
	$ echo $PATH
	/usr/loca/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/home/raytracer/Scripts
	$
	$ myprog	# it's an example script here
	The factorial of 5 is 120
```

By adding the directory to the PATH environment variable, you can now execute your program from anywhere in the virtual directory structure:

```sh
	$ cd /temp
	$
	$ myprog
	The factorial of 5 is 120
	$
```

> **TIP**->
> If you want your programs locatation to available on every subshell make sure to export your modified _PATH_ environment variable.

Changes to PATH variable last only until you exit the system or reboot. In next section, see how to make these changes persistent.

# Locating System Environment Variables
___

When you start a shell(bash,zsh etc.) by logging in to the linux system, by default it checks several files for commands. These files are called _Startup files_ or _environment files_. The startup files that shell process depend on the method you use to start the shell, which is in the following three ways:
* As a default login shell at login time
* As an interactive shell that is started by spawning a subshell
* As a non-interactive shell to run a script.
The following section will describe startup files executed by shell in each of these startup methods.

## Understanding the login shell process

When log in to the linux system, the bash(shell) starts a login shell. It looks up for typically five different startup files to process commands from:
- /etc/profile
- $HOME/.bash_profile
- $HOME/.bashrc
- $HOME/.bash_login
- $HOME/.profile
The /etc/profile file is the main default startup file for the bash shell on the system. All users on the system execute this startup file when they log in.

> **NOTE**
> Be aware that some linux distributions use Pluggable Authentication Modules(PAM). In this case, before the bash shell is started, PAM files are processed, including ones that may contain environment variables. PAM file examples include the `/etc/environment` file and `$HOME/.pam_environment` file. Find more information about PAM at `http://linux-pam.org`.

The other four startup files are specific for each user and can be customized for an individual user's requirements. Let's look closer at these files.

# Learning about Variable Arrays

* From pg no. 194 to 195
