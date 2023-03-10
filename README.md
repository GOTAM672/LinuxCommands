# LinuxTextManipulationTools
My learning of Linux Text Manipulation Tools in journey of DevOps learning.

## Table of Content

- [cat command](#cat-command)
- [nl command](#nl-command)
- [wc command](#wc-command)
- [grep command](#grep-command)

- [My learning Resources](#My-learning-Resources)



## cat command

cat command is used to create, concatenate, append and display files.
we can create a file with cat using '>' to give standard input to a file. The '>' operator truncates the contents of the output file specified, but '>>' operator append standard input into an existing file. Text entered after that is redirected to the file specified to the right of the ‘>’ operator. The control-d signals an end-of-file, returning control to the shell.

```bash
#Example of cat to create a file:

cat > grocery.list
apples
bananas
plums
<ctrl‑d>
```

```bash
# Example of cat to append a file:

cat >> grocery.list
carrots
<ctrl‑d>
```

```bash
# Example of cat to display content of a file:

cat grocery.list
```

```bash
# Example of cat to count lines:

cat ‑n grocery.list
```

## nl command

The nl command reads lines from stdin or from specific files.

```bash
# default usage of nl:

nl grocery.list 
```

Use the -b flag to specify lines to be numbered. This flag takes as its argument a “type”. The type tells nl which lines need to be numbered – use ‘a’ to number all lines, ‘t’ tells nl to not number empty lines or lines that are only whitespace, ‘n’ specifies no lines be numbered. In the example a type of ‘p’ for pattern is shown. nl numbers the lines specified by a regular expression pattern, in this case, lines starting with the letters ‘a’ or ‘b’.

```bash
# nl to number lines conforming to a regex:

nl ‑b p^[ba] grocery.list
```

By default, nl separates the line number from the text using a tab. Use -s to specify a different delimiter, such as the ‘=’ sign.

```bash
# nl to specify a delimiter:

nl –s= grocery.list
```


## wc command 

The wc (wordcount) command counts the number of lines, words (separated by whitespace), and characters in specified files, or from stdin. we can use flag -l, -w, -c to count only number of lines, number of words, and number of characters respectively.

```bash

wc grocery.list
wc ‑l grocery.list
wc ‑w grocery.list
wc ‑c grocery.list
```


## grep command

The grep command searches specified files or stdin for patterns matching a given expression(s).

```bash
# To search apple in grocery.list and grocery.list2 files
grep apple grocery.list grocery.list2

```

To display the filename with number of lines on which the pattern was found – in this case, count the number of lines the word ‘apple’ occurs in each file. we can use -c flag for this.

```bash
# grep - counting number of matches in files:
grep ‑c apple grocery.list grocery.list2

```
using the -h flag option, we can suppresses printing the filename as part of the output.

```bash

# grep - suppress filename in output:
grep ‑h apple grocery.list grocery.list2

```

If you want to ignore case-sensitive search, then grep command has the -i option to ignore case-sensitivity when doing searches.

```bash

# grep – case insensitive:
grep ‑i apple grocery.list grocery.list2

```

Sometimes, only the filename needs to be printed, not the pattern-matching line. grep provides the -l option to only print filenames containing lines with a matching pattern.

```bash

# grep – filenames only:
grep ‑l apple grocery.list grocery.list2

```

Line numbers can be provided as part of the output by using the -n flag option.

```bash

# grep – include line numbers:
grep ‑n carrot grocery.list grocery.list2

```

Sometimes the pattern desired forms a “word” surrounded by whitespace or other characters like a dash or parentheses. Most versions of grep provide a -w option to ease writing searches for these patterns.

```bash

# grep – word matching:
grep ‑w apples grocery.list grocery.list2

```

There are times when lines not matching the pattern are the desired output. In such situations use the -v option.


```bash

# grep – inverted matching:
grep ‑v beans grocery.list2

```


## My learning Resources

- [Introduction to text manipulation on UNIX-based systems](https://developer.ibm.com/articles/au-unixtext/)
- [Linux Filters](https://www.javatpoint.com/linux-filters)
