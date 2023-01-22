# Command line for the win

## 0. First 九 tasks
* Complete the first 9 tasks.

## 1. Reach חי completed tasks
* Complete the 9 next tasks, getting to 18 total.

## 2. Reach the perfect cube, 27

[![](https://cmdchallenge.com/img/emojis/1F421.png)]()
#### level 10:
* <b>A symbolic link is a type of file that is a reference to another file.
Create a symbolic link named take-the-command-challenge that points to the file 
tmp/files/take-the-command-challenge</b>.

*  <p>You can use the command 'ln -s' to create a symbolic link.This is a special
    type of file that points to another file or dir.
    It allows multiple paths to reference the same file or directory
    To create a symbolic link name "link-to-file" that points to the file
    "original-file"</p>

>`ln -s original-file link-to-file`

>`ln tmp/files/take-the-command-challenge take-the-command-challenge`

[![](https://cmdchallenge.com/img/emojis/1F43A.png)]()
#### level 11: 
<b>Delete all of the files in this challenge directory including all subdirectories 
and their contents.
    Hint: There are files and directories that start with a dot ".", 
    "rm -rf *" won't work here!</b>

* This command will recursively search for files and directories starting
from the current dir and delete them.This command will delete all the files
and dirs including the hidden ones & the curent directory that you are
running the command from.
```
find . -delete
```

[![](https://cmdchallenge.com/img/emojis/1F41D.png)]()
#### level 12: 
* <b>There are files in this challenge with different file extensions.
    Remove all files with the .doc extension recursively in the 
    current working directory.</b>

* This command will find all the files with the extension ".doc" in the
current working dir and all subdir and delete them.The '-name' option is
used to search files with a specific name pattern and '-delete' option is
used to delete the files that are found.
```
find . -name ".doc" -delete
```

[![](https://cmdchallenge.com/img/emojis/1F41E.png)]()
#### level 13:
* <b>There is a file named access.log in the current working directory. 
Print all lines in this file that contains the string "GET".</b>

```
grep "GET" access.log
```

[![](https://cmdchallenge.com/img/emojis/1F997.png)]()
#### level 14:
<b>Print all files in the current directory, one per line (not the path
just the filename) that contain the string "500".</b>

```
grep -l '500' *
```

[![](https://cmdchallenge.com/img/emojis/1F577.png)]()
#### level 15:
<b>Print the relative file paths, one path per line for all filenames 
that start with "access.log" in the current directory.</b>

* This command uses 'find' to search for all files in current dir(.) whose
name starts with "access.log"('-name "access.log"') then uses 
'-printf "%P\n' to print the relative path of each file found.
```
find . -name "access.log" -printf "%P\n"
```

[![](https://cmdchallenge.com/img/emojis/1F577.png)]()

#### level 16:
<b>Print all matching lines (without the filename or the file path) in all 
files under the current directory that start with "access.log" that 
contain the string "500".
Note that there are no files named access.log in the current directory, 
you will need to search recursively.</b>

* this command will list all files and directories in the current dir, and
pipe that output to 'grep'.'grep' will then search for string "500" recursively
in the current dir('-r') and only print the matched file or directory
names('-h')

```
ls | grep -rh 500
```

[![](https://cmdchallenge.com/img/emojis/1F982.png)]()

#### level 17:
<b>Extract all IP addresses from files that start with "access.log" 
printing one IP address per line.</b>

* grep - a command-line tool that searches for patterns in text.
* '-r' - option tells grep to search recursively in subdirectories.
* '-o' option tells grep to only print the matching parts of the line.
* '-E' option tells grep to use extended regular expressions.

The regular expression "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" is used to match
IP address specifically:
    * <b>'\b'</b> is a word boundary that ensures that the pattern is only matched
        if it starts or ends a word.
    * <b>'([0-9]{1,3}\.){3}'</b> matches three groups of 1 to 3 digits
        followed by a dot.This is the format of the three parts of an IP
        address (eg. 192.168.1.)
    * <b>[0-9]{1,3}</b> matches the last part of the IP address, which is
        also 1 to 3 digits.

So, the above command will search recursively in subdirectories and 
prints out only the matching parts of the line which are IP addresses and it 
will only match the IP addresses which are word bounded by whitespace or 
punctuation.

```
grep -rOE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b"
```

[![](https://cmdchallenge.com/img/emojis/1FAB0.png)]()

#### level 18:
<b>Count the number of files in the current working directory. 
Print the number of files as a single integer.</b>

This command uses a combination of 'find' and 'wc' commands to achieve
this:
    * <b>'find . -type f'</b>finds all files (indicated by the 'type f' option)
        in the current working dir and it's subdirectories.The '.' 
        specifies the current working dir as the starting point for search.
    * <b>'wc --lines'</b>  counts the number of lines from the output of 
        'find' command which are files, and it will print the number of files
        as a single integer
```
find . -type f | wc --lines
```

[![](https://cmdchallenge.com/img/emojis/1FAB1.png)]()

#### level 19:
<b>Print the contents of access.log sorted</b>
```
sort access.log
```

[![](https://cmdchallenge.com/img/emojis/1F9A0.png)]()

#### level 20:
<b>Print the number of lines in access.log that contain the string "GET"</b>
```
grep "GET" access.log | wc -l
```

[![](https://cmdchallenge.com/img/emojis/1F435.png)]()

#### level 21:
<b>The file split-me.txt contains a list of numbers separated by a ; character.

Split the numbers on the ; character, one number per line.</b>
```
tr ';' '\n' < split-me.txt
```

* tr is a command in unix-like os systems that stands for "translate".It is
    used to translate or delete specific chars in a given input text stream
    or file.
>`tr [options] set1 set2`

* where 'set1' is the set of chars you want to replace, and 'set2' is the set
    of characters you want to replace them with

[![](https://cmdchallenge.com/img/emojis/1F436.png)]()

#### level 22:
<b>Print the numbers 1 to 100 separated by spaces.</b>
```
echo {1..100}
```
* the command uses a feature of bash called "brace expansion" which allows you
    to generate a string that includes a sequence of numbers, or letters, by
    using curly braces

[![](https://cmdchallenge.com/img/emojis/1F98A.png)]()

#### level 23:
<b>This challenge has text files (with a .txt extension) that contain the phrase 
"challenges are difficult". Delete this phrase from all text files recursively.
Note that some files are in subdirectories so you will need to search for them</b>
```
find . -name "*.txt" -exec sed -i '/challenges are difficult/d' {} +
```
* you can use the command "find" in combination with "sed" to delete a specific
 phrase from text files with a ".txt" extansion recursively

```
sed '/phrase/d' filename
```
* In the context of deleting a specific phrase from a text file, "sed" is used
to search for the phrase in the text file, and then delete the entire line
containing the phrase

* The "/d" flag at the end of the command tells "sed" to delete the entire line
containing the specified phrase

* The "-i" is used with "sed" to edit the file in place, which means it modifies
 the original file, rather than creating a new one.

* The "sed" command is a very powerful tool for text processing, it can also
be used to substitute, insert and extract text from files, it can also be used
to manipulate multiple files in one go, making it a great tool for batch processing

[![](https://cmdchallenge.com/img/emojis/1F431.png)]()
#### level 24:
<b>The file sum-me.txt has a list of numbers, one per line. Print the 
sum of these numbers.</b>
```
cat sum-me.txt | tr '\n' '+' | sed '/s/+$\/n/' | bc
```
* sed is a command line utility that is used to perform basic text transformations
on an input stream(a file or input from a pipeline).

* the command is using the 's' command of 'sed' which is used for substitution
This command searches for a specific pattern and replaces it with another.

* The basic syntax of the 's' command is:
>`'s/pattern/replacement'`

[![](https://cmdchallenge.com/img/emojis/1F981.png)]()

#### level 25:

<b>Print all files in the current directory recursively without the 
leading directory path.</b>

```
find . -type f -exec basename {} \;
```
* -type f option only returns regular files.Then uses command "basename" to
strip off the leading directory path, and the option "-exec" to execute a
command for each file found.

* The command `basename {}` is executed for each file that is found by the
`find` command, and `{}` is replaced by the current file's path.The `basename`
takes the file path as an arg and removes the leading directory path, so it
returns the file name only

```
find . -type f -exec echo {} \; | sed 's|\./||'
```
* Uses the command '-exec' to execute the command "echo {}" to print the full
path of each file found, then it pipes the output to "sed" command which uses
the regular expression 's|\./||' to remove the leading directory path.

* The `s|\./||` is a regular expression that is used with the `sed` command to
remove the leading directory path from the file names.

* The `s` command in `sed` is used for substitution.

* In this case, the pattern is `\./`, it matches the characters `./` which represent
the current working directory, this pattern is present at the beginning of the
file path.

* The replacement is `||`, which is empty, so it removes the matched pattern.

* The `|` character is used as a delimiter between the `s` command and the pattern
, this is done to avoid conflicts with the `./` charcter which is present in
the pattern

* The `-exec` option can also be replaced by `-exec {} +` this will execute the
command using as many files as possible, which can be more efficient, because it
reduces the number of times the command needs to be invoked, but will not give
the expected output.

[![](https://cmdchallenge.com/img/emojis/1F42F.png)]()

#### level 26:
<b>Rename all files removing the extension from them in the current directory</b>
```
find . -type f -exec rename 's/\.[^.]+$//' {} +
```
* `rename` - is a command-line utility
* The basic syntax of the `rename` command:
```
rename [options] expression files
```

* `files` is a list of one or more file names or patterns that specify the
files to be renamed

* if you want to rename all files in a directory that have the extension ".txt"
to ".text", you could use the following command:
```
rename 's/\.txt$/.text/' *.txt
```

* In the code for renaming, the command uses a regular expression to match the
file extension (`.[^.]+$`) and replace it with nothing, effectively removing
the extension.

* `s/\.[^.]+$//`:
* `\.` - is a special character that matches a period or dot.The backslash (`\`)
is used to escape the dot, so it is treated as a literal dot rather than a special
character.

* `[^.]` - is a negated character class that matches any character that is not a
dot.The `+` quantifier specifies that one or more of the negated charcter class
should be matched.

* `\.[^.]+$` - matches any sequence of characters starting with a dot, followed
by one or more characters that are not dots, and ending at the end of the character


