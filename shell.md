.sh file shebang

	# !/bin/sh

### Variables

Assign content of `cat` to a variable

	export str=$(cat ./file)
	echo "$str"

### Counters

`-m` (number of chars)


	cat ./file | wc -m


`-l`   (number of lines)

	cat ./file | wc -l

`-w`   (number of words)

	cat ./file | wc -w

`-c`   (number of bytes)

	cat ./file | wc -c

`-L`   (length of longest line)

	cat ./file | wc -L

