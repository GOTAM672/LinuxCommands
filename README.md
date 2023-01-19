# LinuxTextManipulationTools
My learning of Linux Text Manipulation Tools in journey of DevOps learning.

## Table of Content
<br>

- [cat command](#cat-command)


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
#Example of cat to append a file:

cat >> grocery.list
carrots
<ctrl‑d>
```

```bash
#Example of cat to display content of a file:

cat grocery.list
```

```bash
#Example of cat to count lines:

cat ‑n grocery.list
```




