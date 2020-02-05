# Requisites

	Following are the requisites before installing manjaro. I will try to make it step by step.

- [.] Download iso of *windows*
- [ ] Test iso in Virtualbox in *hp* laptop
- [ ] Report successful
- [X] Download iso for *manjaro*
- [X] Check for mbr or gpt in acer laptop

	Got uefi(gpt) partition

- [ ] Make live bootable in rufus(etcher) in gpt partition
- [ ] Test live media with non-free driver
- [ ] Check manjaro settings manager for nvdia graphic card
- [ ] Run following command in terminal

```bash
	$ primusrun glxinfo | grep "renderer string"
```
- [ ] Report which type of driver you found and driver version
- [ ] Install windows in virtualbox in acer after successful installation

## Things to check for installation

- [X] brightness working
	```sh
		$ ls -l /sys/class/backlight
		[....] intel backlight -> .....
		# using xrandr
		$ xrandr -q | grep 'connected' | head -n 1 | cut -d ' ' -f1
		eDP1	#monitor name
		$ xrandr --output eDP1 --brightness 0.7	# sets to 70%
	```
	Another command for backlight is to change file in following directory

```sh
	$ sudo vim /sys/class/backlight/.../brightness
	# or
	$ echo 200 | sudo tee /sys/class/backlight/radeon_bl0/brightness
```

Find your brightness file there and change the value accordingly. In my case (my hp) max. value is 255.

- [X] Audio is working
```sh
	$ sudo pacman -S pulseaudio
	$ sudo pacman -S pulsemixer		# default is alsa-mixer
```

## Keyboard backlight

- [ ] work from termianl
- [ ] run this command for keyboard events
```sh
	$ xmodmap -pke		# list all keymapping
	$ ls -l /sys/class/leds/*/brightness
	$ light		# command for lightning
```

<++>

