`
	# !/bin/sh
`

`
	export str=$(cat ./file)
	echo "$str"
`

`
	cat ./file | wc -m
	cat ./file | wc -l
	cat ./file | wc -w
	cat ./file | wc -c
	cat ./file | wc -L
`

-m (number of chars)
-l (number of lines)
-w (number of words)
-c (number of bytes)
-L (length of longest line)