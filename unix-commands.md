```bash
$ date
Tue, May 16, 2023  1:55:03 PM

$ echo hello
hello

$ tty => display terminal name
/dev/cons0

$ clear

$ pwd (path of present working dir)
/d/Github/big-data

$ mkdir sam

$ cd sam

$ rmdir sam

$ cat > file1.txt (creates a file and ask us to write to it)
$ cat >> f3 (appends to the file)


$ touch file2.txt (creates a file)
$ echo dark > night.txt => (cr8 new one & wri8 to it)
$ echo black >> night.txt => (appends to the file)

$ cat file1.txt (shows file contents)

$ ls
$ ls -a => (Shows list of hidden files)

$ cp [source file] [destination file] | $ cat file1.txt >> file2.txt
$ mv f3 f1 (f3 is renamed to f1 ||| cat f3 does not exist)

$ rm file2.txt => (remove file2.txt) | $ rm -rf file2.txt

$ rm --h (Askig for help)

$ $ cat > f3
peach 
orange
banana
mango
grapes
(pressed ctrl + c to get out)

$ sort f3
banana
grapes
mango
orange
$ sort -r f1 (sort in reverse)


$ wc f3 ||| wc --h
$ wc -c f3 => no. of chars
$ wc -l f3 => no. of lines
$ wc -w f3 => no. of words

$ head f1 => show top 10-lines of f1
$ tail f1 => show btm 10-lines of f1

(Search for reg ex pattern in a file)
$ grep peach f1 
reply: peachify

$ grep -v peach f1 (displays those lines that do not match)

$ grep -n st f1 (add line no. to matching line)
7:student

$ grep -c g f1 (says 4lines matched the letter g)
4

$ grep -i peach f1 (ignores case)
peachify
PEACHIFY

$ tr "[a-z]" "[A-Z]" (converts case)
unix
UNIX
```

linux
```bash
$ who (display who are the users connected to our computer)
$ who am i (Display the details of the current working directory)
$ cal [year]
$ cal [mon] [year]
```
