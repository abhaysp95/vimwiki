# termux(android) ssh host setup:

There are few apps to setup android as ssh host, but didn't worked out for me, so trying in termux(which I use frequently in android). Maybe there is a better way to do so of what I'm doing(I'll try to find out).

## Pre-requisites:

Need to have ssh installed on both laptop(desktop) and termux:
```sh
# for arch based distro
$ sudo pacman -S openssh
# for debian based distro
$ sudo apt install openssh
```

## Copy public key:

```sh
$ ssh-keygen
```
Enter the file you wan't the key to be written on. If you wan't default then simply press `enter`.

For passphrase, if you wan't then type a `password` or simply press `enter` for no password.

By default, ssh key is saved in `$HOME` directory. There are two keys saved:
* One without extension `id_rsa` is private key. You don't want to share it(although I don't know much about it)
* One with extension `id_rsa.pub` is public key.

```sh
$ cat ~/.ssh/id_rsa.pub
# copy the output and get in on your phone
```

## On android:

### start ssh server

```sh
sshd
```
Find out listening port
```sh
$ logcat -s 'syslog'
```
Remember the port number

### setup

Find out your host name on android
```sh
$ whoami
```

Now, do following things:
```sh
$ mkdir ~/.ssh
$ vim authorized_keys	# use your preffered text editor
```
Paste the key copied from computer in this file

Find out your local ip addr:
```sh
$ ifconfig
```

### connect

In computer, enter
```sh
ssh termux_username@ip_addr_from_there -p port_number
```

And now, you should be accessing your termux terminal in your computer.

## Alternate

If above method doesn't works for you, then do this:

### in termux

Do following in termux, first:
```sh
$ sshd
$ ssh-keygen
$ whoami # remember, this is user name in termux
```

Create a password for this user:
```sh
$ passwd
```

This will start and give you prompt to ask the `path` to save your public and private key as host. If you give no passphrase by default it will store in `~/.ssh`. Both public and private keys will be stored. Now, copy the file `id_rsa` from your mobile to desktop.

This is to be done so it'll not prompt for password in time of connection, as you don't have a user passwd in termux.

### in desktop

```sh
$ mkdir -p ~/.ssh/ssh_termux
# copy the id_rsa file from mobile to here
```

Or, you can use `ssh-copy-id` to copy the public id of your mobile to you host node.
```sh
$ ssh-copy-id -p <port_num> <username>@<domain_name/ip_addr>  # of your desktop
```

If ask for password, enter the password you created in termux.

### connection

By default ssh on termux will start in port `8022`, if you don't change it in `sshd_config`.

Files related to ssh are stored in following path:
* **In mobile**:
	* path -> /data/data/com.termux/files/usr/etc/ssh
* **In desktop**:
	* path -> /etc/ssh

There you can change ssh server related settings, but be careful. Now, it's time to connect termux ssh host to desktop,

```sh
$ ssh user_name@192.168.***.*** -p 8022 -i ~/.ssh/ssh_termux/id_rsa
```

On entering the above command, it will connect your mobile as ssh client to desktop which is ssh host. It will prompt you for nothing.
