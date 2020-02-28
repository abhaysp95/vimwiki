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
* `readlink` prints resolved symbolic links or cannonical file names
* `compton-tryone-git` added blur to compton(old package)
* `sysstat` is a package which provides different system monitoring tools. It contains of followning tools:
	* `mpstat` reports processors related statistics.
	* `sar` collect report and store system relative information

* `printf` command is used to display the given string, number or any format specifier on the terminal window. It works same way as printf works in programming languages like `C`.
	- Commonly used format specifiers are `%s, %b, %d, %x and %f`.
* **Capitalized letters** are treated as less than lowercase letters in test comparisions(uses standard ASCII ordering). However, sort command is just its reverse(uses __locale__ settings).

## Cronjab:

* * * * * *
  | | | | |_ Day of Week [0-6] where 0 represents Sunday
  | | | |___ Month [1-12]
  | | |_____ Day of Month
  | |_______


* @reboot[command]
* @monthly[command]
* @yearly[command]
* @weekly[command]
* @daily[command]
