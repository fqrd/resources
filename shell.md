.sh file shebang

	# !/bin/sh

### Variables

Assign content of `cat` to a variable

	export str=$(cat ./file)
	echo "$str"

### Counters

	cat ./file | wc -(m|l|w|c|L)

- `-m` (number of chars)
- `-l` (number of lines)
- `-w` (number of words)
- `-c` (number of bytes)
- `-L` (length of longest line)
