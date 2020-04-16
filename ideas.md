* make a dmenu/rofi type wifi network connect selector
* shortcut for nwidw

# Some tools:

* `exa` instead of `ls`:
	Like `ls`, but
	+- Pretty
	+- git support
* `fd` instead of `find`:
	Like `find`, but
	+- Fast
	+- User friendly
	+- Good default ignores
* `ripgrep` instead of `grep`:
	Like `grep`, but
	+- **Insanely** fast
	+- User friendly
	+- Good default ignores
* `tokei` instead of `cloc`(to count lines of code):
	Like `cloc`, but
	+- Fast
	+- User friendly
	+- Good default ignores
* `httpie` instead of `curl`:
	Like `curl`, but
	+- **Very** user friendly
	+- Pretty output
	+- Automatically formats responses
* `bat` instead of `cat` or `less`:
	Like `cat` or `less`, but has
	+- Syntax highlighting support
	+- Automatic pager for long pages
	+- git support
* `sd`:
	Like `sed`, but
	+- User friendly
* `hyperfine`(benchmarking):
	Like `time`, but has
	+- Initial warm-up phase
	+- Multiple runs for better overall measurements
	+- Also pretty
* `Bonus:mdp - Presentation tool`:
	Like `Powerpoint`, but
	+- with 1% of the feature
	+- on the command line
* `Bonus:genact - Pretending to do work`:
	+- Pretends to be a legitimate tool
	+- Actually doesn't really do anything
	
# some memory and cpu commands

* `show memory`
	* free -h | awk '/^Mem:/ {print $3 " / " $2}'
* `cpu temperature`
	* sensors | head -n 5 | awk '/^temp1/ {print $2}'
* `memory intensive process`
	* ps axch -o cmd:15,%mem --sort=-%mem | head
* `cpu intensive process`
	* ps axch -o cmd:15,%cpu --sort=-%cpu | head

-> About me
------------
