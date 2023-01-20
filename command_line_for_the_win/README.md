# Command line for the win

## 0. First 九 tasks
* Complete the first 9 tasks.

## 1. Reach חי completed tasks
* Complete the 9 next tasks, getting to 18 total.

## 2. Reach the perfect cube, 27

[![](https://cmdchallenge.com/img/emojis/1F421.png)]()
#### level 11:
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
#### level 12: 
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
#### level 13: 
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
#### level 14:
* <b>There is a file named access.log in the current working directory. 
Print all lines in this file that contains the string "GET".</b>

```
grep "GET" access.log
```

[![](https://cmdchallenge.com/img/emojis/1F997.png)]()
#### level 15:
<b>Print all files in the current directory, one per line (not the path
just the filename) that contain the string "500".</b>

```
grep -l '500' *
```

[![](https://cmdchallenge.com/img/emojis/1F577.png)]()
#### level 16:
<b>Print the relative file paths, one path per line for all filenames 
that start with "access.log" in the current directory.</b>

* This command uses 'find' to search for all files in current dir(.) whose
name starts with "access.log"('-name "access.log"') then uses 
'-printf "%P\n' to print the relative path of each file found.
```
find . -name "access.log" -printf "%P\n"
```

[![](https://cmdchallenge.com/img/emojis/1F577.png)]()

#### level 17:
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

#### level 18:
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

#### level 19:
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
