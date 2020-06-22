# Linux

` Linux is a open-source free Operating System.`

Some utility command:

| s.no. | utility-name | work                                     |
|-------|--------------|------------------------------------------|
| 1.    | xprop        | gives class name(which I use             |
|       |              | mostly) and some other info              |
|       |              | about program                            |
| 2.    | xev -event   | gives input data for different           |
|       |              | input devices.                           |
|       |              | e.g., xev -event keyboard                |
| 3.    | xbacklight   | It is a Xorg tool used to control        |
|       |              | brightness(I think by editing            |
|       |              | /sys/class/backlight/.../brightness file |

* to know the groups in your linux system do: `cat /etc/group`
* setup ftp:
	* install vsftpd
	* edit /etc/vsftpd.conf file, uncomment `write_enable=YES` and `local_enable=YES` and then start vsftpd service. Run ftp <ip-address> on client.
	* commands are:
		- dir	=>		display files in current directory
		- cd "dir"	=>	you know it
		- put file	=>	upload file from local to remote computer
		- get file	=>	Download file from remote to local
		- quit		=>	logout
* `expr` command used to print and perform operations on expressions.
* `finger` command to store information/view information in the comment field.
* `locate` find files by name, like:
	```sh
		locate brave-browser.desktop
	```
* `readlink` prints resolved symbolic links or cannonical file names
* `compton-tryone-git` added blur to compton(old package)
* `sysstat` is a package which provides different system monitoring tools. It contains of followning tools:
	* `mpstat` reports processors related statistics.
	* `sar` collect report and store system relative information

* `printf` command is used to display the given string, number or any format specifier on the terminal window. It works same way as printf works in programming languages like `C`.
	- Commonly used format specifiers are `%s, %b, %d, %x and %f`.
* **Capitalized letters** are treated as less than lowercase letters in test comparisions(uses standard ASCII ordering). However, sort command is just its reverse(uses __locale__ settings).

## Cronjab:

```
* * * * * *
  | | | | |_ Day of Week [0-6] where 0 represents Sunday
  | | | |___ Month [1-12]
  | | |_____ Day of Month
  | |_______ Hour
  | ________ Minute
```


* @reboot[command]
* @monthly[command]
* @yearly[command]
* @weekly[command]
* @daily[command]

# awk (utitlity/command):

## Syntaxes to use:

* To read `awk` command from a file(script) use `-f` flag. Like this:
```sh
$ cat '{print}' > command.awk
# a file with something written in it, file.txt(containg Hey and Hii)
$ awk -f command.awk file.txt
Hey
Hii
```

* To assign a value to variable, also before execution, use `-v` flag, like:
```sh
$ awk -v name=abhay 'BEGIN{printf "Name = %s\n", name}'
Name = abhay
```

## vmstat:

`vmstat` reports information about process, memory, paging, block IO, traps, disk, cpu activity etc.

## Some notes for shell scripting:

We know that `$1` is the first argument we enter in command line, e.g., *man lsd*, here $1=lsd. In the same way, `$2` is for second argument, eg., *volume up 10*. Now, here _volume_ is treated as command, _up_ is $1 and _10_ is $2.

Now, let's say there's a script in which you wan't to put something, like this `volume down 15` or `volume up 10`, but if not given any numeric value it should automatically get `5` as value, then you can do like this:
```sh
num=$(2:-5)
```

## Get dominant color's with imagemagick

```sh
convert ~/Path_to_image.ext +dither -colors 10 -define histogram:unique-colors=true \
-format "%c" histogram:info: > file_name_to_store
```

## rsync:

```sh
rsync -avrh -e 'ssh -p 2222' --ignore-existing ~/Pictures/bgwallpapers/luke_wall \
raytracer@192.168.43.247:/home/raytracer/Pictures/bgwallpapers/luke_wall
```
