# Learn command line

Please follow and complete the free online [Command Line Crash Course
tutorial](https://web.archive.org/web/20160708171659/http://cli.learncodethehardway.org/book/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. Each "chapter" focuses on a command. Type the commands you see in the _Do This_ section, and read the _You Learned This_ section. Move on to the next chapter. You should be able to go through these in a couple of hours.

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> >#Cheat Sheet:#
> > * show current working directory path: pwd
> > * move up one directory level: cd ../
> > * switch to directory at same level: cd../directory
> > * create a directory: mkdir directoryname
> > * delete a directory: rm -r directory
> > * create a file: touch filename.ext
> > * delete a file: rm filename.ext
> > * rename a file: mv filenameOLD.ext filenameNEW.ext
> > * move a file: mv filename.ext directory
> > * list hidden files: ls -a
> > * list files by date created: ls -t
> > * copy file to another directory: cp directory1/file1.ext directory2
> > * append data to a file: cat file1.txt >> file2.txt
> > * copy-overwrite data in a file: cat file1.txt > file2.txt

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  
 
> >#Answers:#
> > * 'ls' lists files and directories in current directory
> > * 'ls - a' does the same as 'ls', including hidden files
> > * 'ls -l' does the same as 'ls' with long format filenames and permissions
> > * 'ls -lh' as above, with readable file size formats
> > * 'ls -lah' as above, including hidden files
> > * 'ls -t' sorts results by time & date
> > * 'ls - Glp' shows long format files in color, with '/' denoting directories

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> >#Favorites:#
> > 1. '1' - displays each file on a separate line
> > 1. 'u' - lists files by date accessed
> > 1. 'd' - displays only directories
> > 1. 'm' - displays files as comma-separated list
> > 1. 'R' - displays subdirectories as well

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > 'xargs' allows terminal commands to accept standard input in cases
> > where they would normally only accept arguments after the command itself. It
> > does so by passing lists of arguments/parameters, e.g. filenames, to
> > to the command line in batches.
> >
> > Example: 'echo 1 2 3 4' prints '1 2 3 4' on one line  
> >          'echo 1 2 3 4 | xargs -n 2' would execute the command in batches  
> >           of two, so that '1 2' and '3 4' appear on different lines.
 

