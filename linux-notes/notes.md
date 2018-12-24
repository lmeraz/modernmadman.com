# Part 1: Learning the Shell

## 1: What Is the Shell?
the shell is a program that takes keyboard commands and passes them to the operating system to carry out.
mac comes with bash which stands for bourne again shell.

### Terminal Emulators
a terminal is used to interact with the shell. On mac, the program is called terminal.

### Your First Keystrokes
you will see something like
`Luiss-MBP:~ lmeraz$ `
this is called the shell prompt

#### Command History
use the up arrow key to go back in your history after you yped a command. press down arrow key and your previous command disappears.

#### Cursor Movement
use left and right arrow keys to position the cursor.

### Try Some Simple Commands
type `date` - current date time
type `cal` - display calendar of current month
type `df` - current amount of free space in drive

### Ending a Terminal Session
type `exit` - to end a session

## 2: Navigation
`pwd` - print name of current working directory
`cd` - change directory
`ls` - list directory contents

### Understanding the Filesystem Tree
Linux organizes files ina  tree like pattern of directories called hierarchical directory structure. the first directory of a filesystem is called a root directory. It contains files and subdirectories that containe more files and subdirectories.

### The Current Working Directory
since the command line has n pcitures we have to navigate the file system with a few commands. to know where we are we use
`pwd` 

### Listing the Contents of a Directory
type `ls` to list the files and direcories of a current working directory

### Changing the Current Working Directory
type `cd` followed by the path name of the directory you wish to switch to. pathname is a route along the branches of the tree directory. you can use absolute or relative paths

#### Absolute Pathnames
absolute path begins with the root for example /usr/bin
type `cd /usr/bin`
type `pwd`
type `ls`

#### Relative Pathnames
starts from the working directory. two symbols are used
`.` refers to the working directory
`..` refers to the parent directory
in general, if you do not speicy a pathname the working directory will be assumed

#### Some  Helpful Shortcuts
cd changes woriking directory to your home directory
cd - changes the working directory tot he previous working directory
cd ~username changes tot he home directory of username
fun filename facts:
filenames starting with . are hidden. you can view using ll or ls -a
filenames and commds are case sensitive
linux has no contenxt of file extensions
limit punctuation and try not to embed spaces in file names commands are more difficult to use otherwise. use undesrcorse.

## 3: Exploring the System
- ls - list diretory contents
- file - determine the file type
- less - view the file contents

### More Fun with ls
ls is used to see a list of files and subdirectories contained int he current working directory
we can also specify other directories ls /usr or mutiple directories ls ~ /usr
can change format to reveal more detail ls -l

#### Options and Arguments
commands are followed by one or more options that modify behavior and further by one or more arguments the itmes up which the command acts
command -options arguments
cooomands use options consisting of a single character preceded by a dash or a word preceded by 2 dashes or multiple short options strung together
ls -lt
ls -lt --reverse

|option|long option| description|
|-a|--all|lis all files even those with names that begin with a period|
|-d|-directory| see details about the directory rather than it's contents|
|-F|--classfy|appends indicator character file or folder|
|-h|--human-readable|display file sizes in human readable format|
|-l||display results in long format|
|-r|--reverse|display results in reverse order|
|-s||sort by file size|
|-t||sort by modification time|

#### A Longer Look at Long Format
rw-r--r-- 1 root root 3576296 2012-04-03 11:05 Experience ubuntu.ogg
|field|meaning|
|rw-r--r--| access rights to the file. first character indicates type of file. - regular file d indicates a directory. next 3 are access rights for file owner, next 3 are for group, final 3 are for everyone else.
|1|file's number of hard links|
|root|user name of the file's owner|
|root|name of the group that owns the file|
|3576296| size of file in bytes|
|2012-04-03 11:05| date and time of last modification|
|Experience ubuntu.ogg| name of the file|

### Determining a File’s Type with file
`file filename` when invoke prints a brief desctiption

### Viewing File Contents with less
less command is used to view text files. less allows you to scoll forward and back
to exit less press q
`less /etc/passwd`
less commands
|command|action|
|PAGE UP or b| Scroll back one page.|
|PAGE DOWN or Spacebar| Scroll forward one page.|
|Up Arrow| Scroll up one line.|
|Down Arrow| Scroll down one line.|
|G|Move to the end of the text file.|
|1G or g|Move to the beginning of the text file.|
|/characters| Search forward to the next occurrence of characters.|
|n|Search for the next occurrence of the previous search.|
|h|Display help screen.|
|q|Quit less.|

### A Guided Tour
For the following, try to
1. cs into a given directory
2. List the directory contents with file.
3. If you see an interesting file, determine it's wontents with file.
4. if it looks like it might be text, try viewing it with less.

Directories found on Linux file system.
|Directory|Comments|
|/| the root directory, where everything begins.|
|/bin|Contains binaries (programs) that must be present for the
system to boot and run.|
|/boot/Contains the Linux kernel, initial RAM disk image (for drivers needed at boot time), and the boot loader. Interesting files: /boot/grub/grub.conf or menu.lst, which are used to configure boot loader./boot/vmlinuz the linux kernel.|
|/dev|A spcial directory that contains device nodes.|
|/etc| contains all the systemwide configuration files.Also contains collection of shell scrits that start each of the system services at boot time. Interesting files: /etc/crontab, a file that defines when automated jobs
will run, /etc/fstab, a table of storage devices and their
associated mount points, /etc/passwd, a list of the user accounts|
|/home|a user's directory. each user is given a home directory.ordinary users can only write files in their home directory|
|/lib|contains shared library files used by the core system programs.|
|/lost+found|Each formatted partition or device using a Linux file- system, such as ext3, will have this directory. It is used
in the case of a partial recovery from a filesystem cor- ruption event. Unless something really bad has hap- pened to your system, this directory will remain empty.|
|/media|On modern Linux systems the /media directory will contain the mount points for removable media such
as USB drives, CD-ROMs, etc. that are mounted automatically at insertion|
|/mnt|On older Linux systems, the /mnt directory contains mount points for removable devices that have been
mounted manually.|
|/opt|The /opt directory is used to install “optional” software. This is mainly used to hold commercial software products
that may be installed on your system.|
|/proc| it is a virtual filesystem maintained by the Linux kernel. The “files” it contains are peepholes into the kernel itself. The files are readable and will give you a picture of how the kernel sees your computer.|
|/root|This is the home directory for the root account.|
|/sbin|This directory contains “system” binaries. These are programs that perform vital system tasks that are generally reserved for the superuser.|
|/tmp|The /tmp directory is intended for storage of temporary, transient files created by various programs. Some con- figurations cause this directory to be emptied each time the system is rebooted.|
|/usr|The /usr directory tree is likely the largest one on a Linux system. It contains all the programs and support files used by regular users.|
|/usr/bin|/usr/bin contains the executable programs installed by your Linux distribution. It is not uncommon for this directory to hold thousands of programs.|
|/usr/lib|The shared libraries for the programs in /usr/bin.|
|/usr/local|The /usr/local tree is where programs that are not included with your distribution but are intended for system-wide use are installed. Programs compiled from source code are normally installed in /usr/local/bin. On a newly installed Linux system, this tree exists, but it will be empty until the system administrator puts some- thing in it.|
|/usr/sbin|Contains more system administration programs.|
|/usr/share|/usr/share contains all the shared data used by programs in /usr/bin. This includes things like default configuration files, icons, screen backgrounds, sound files, etc.|
|/usr/share/doc|Most packages installed on the system will include some kind of documentation. In /usr/share/doc, we will find documentation files organized by package.|
|/var|With the exception of /tmp and /home, the directories we have looked at so far remain relatively static; that is, their contents don’t change. The /var directory tree is where data that is likely to change is stored. Various databases, spool files, user mail, etc. are located here.|
|/var/log|/var/log contains log files, records of various system activity. These are very important and should be mon- itored from time to time. The most useful one is /var/ log/messages. Note that for security reasons on some systems, you must be the superuser to view log files.|


### Symbolic Links
`lrwxrwxrwx 1 root root 11 2012-08-11 07:34 libc.so.6 -> libc-2.6.so`
soft lin or sym links are file references

## 4: Manipulating Files and Directories
cp—Copy files and directories.
mv—Move/rename files and directories.
mkdir—Create directories.
rm—Remove files and directories.
ln—Create hard and symbolic links.

### Wildcards
wildcards allow you to select file names based on patterns of characters.
(wildcards)['table-4-1-wildcardspng']
(wildcards)['table-4-2-commonly-used-character-classes.png']
(wildcards)['table-4-3-wildcard-examples.png']

### mkdir—Create Directories
`mkdir directory1 directory2` - command used to create directories

### cp—Copy Files and Directories
`cp item1 item2` - copy files or directories
`cp item... directory` - copy multiple items to directory
(cp options)['table-4-4-cp-options']

### mv—Move and Rename Files
`mv item1 item2` - to rename
`mv item... directory` - mov items to a directory
(table-4-6)
(table-4-7)

### rm—Remove Files and Directories
`rm item...`
use ls to test the search pattern prior to using rm
(table-4-8)
(table-4-7)

### ln—Create Links
`ln file link` - create a hadr link
`ln -s item link` create a symbolic link

#### Hard Links
A hard link cannot reference a file outside its own filesystem. This means a link cannot reference a file that is not on the same disk parti- tion as the link itself.
A hard link cannot reference a directory.

#### Symbolic Links
Symbolic links work by creating a special type of file that contains a text pointer
to the referenced file or directory. 

### Let’s Build a Playground
#### Creating Directories
`cd`
`mkdir playground`
`cd playground`
`mkdir dir1 dir2`

#### Copying Files
`cp /etc/passwd .`
`ls -l`
`cp -v /etc/passwd .`
`cp -i /etc/passwd`

#### Moving and Renaming Files
`mv passwd fun`
`mv fun dir1`
`mv dir1/fun dir2`
`mv dir2/fun`
`mv fun dir1`
`mv dir1 dir2`
`ls -l dir2`
`ls -l firt2dir1`
`mv dir2/dir1 .`
`mv dir1/fun .`

#### Creating Hard Links
`ln fun-hard`
`ln fun dir1/fun-hard`
`ln fun dir2/fun-hard`
`ls -l`
`ls -li`

#### Creating Symbolic Links
`ln -s fun fun-sym`
`ln -s ../fun dir1/fun-sym`
`ln -s ../fun dir2/fun-sym`
`ls -l dir1`
`ln -s /home/me/playground/fun dir1/fun-sym`
`ln -s dir1 dir1-sym`
`ls -l`

#### Removing Files and Directories
`rm fun-hard`
`ls -l`
`rm -i fun`
`ls -l`
`less fun-sym`
`rm fun-sym dir1-sym`
`ls -l`
`cd`
`rm -r playground`

### Final Note
Feel free to expand.

## 5: Working with Commands
type—Indicate how a command name is interpreted.
which—Display which executable program will be executed.
man—Display a command’s manual page.
apropos—Display a list of appropriate commands.
info—Display a command’s info entry.
whatis—Display a very brief description of a command.
alias—Create an alias for a command.

### What Exactly Are Commands?
A command is one of four things.
1. an executable program. can be compiled binaries wirtten in c or C++ or scripting languages like Perl or Python.
2. A command built into the shell itself. bash suports commands internally called shell builtins. `cd` is a shell built in.
3. A shell function shell functions are miniature shell scripts incorporated into the environment.
4. An alias is a commnad we can define ourselves.

### Identifying Commands
#### type—Display a Command’s Type
`type` command is a shell built in that displays the kind of command that the shell will execute.
`type command`
`type type`
`type ls`
`type cp`

#### which—Display an Executable’s Location
`which ls` - location of a given executable.

### Getting a Command’s Documentation
#### help—Get Help for Shell Builtins
`help` built in help facility for shell builtins
`help cd`

When square brackets appear in the description of a command’s syntax, they indicate optional items. A vertical bar character indicates mutually exclusive items. An example is the cd command above: `cd [-L|-P] [dir]`.
This notation says that the command cd may be followed optionally by either a -L or a -P and further, optionally followed by the argument dir.

#### --help—Display Usage Information
`--help` - option that displays description of the command's supported syntax and options.

#### man—Display a Program’s Manual Page
`man program` - special paging program to view documentation
`man ls`
generally contain a title, a syn-
opsis of the command’s syntax, a description of the command’s purpose, and a listing and description of each of the command’s options.
(table-5-1)
`man 5 passwd`

#### apropos—Display Appropriate Commands
search list of man pages for possible matches on a serach term
`apropos floppy`

#### whatis—Display a Very Brief Description of a Command
Displays the name and one-line description of a man page matching a spciefied keyword
`whatis ls`

#### info—Display a Program’s Info Entry
info pages are an alternative to man pages. info pages are hyperlinked
`info coreutils`

#### README and Other Program Documentation Files
many other packages have documentation files in /usr/share/doc directory.
you can use gless to read gzip files.

### Creating Your Own Commands with alias
Aliasing allows you to create custom commands.
you can have multiple commands by separating with semicolon
`command1; command2; command3;`
`cd /usr; ls; cd -`
`alias foo='cd /usr; ls; cd -'`
the structure is `alias name='string'`
`foo`
`type foo`
`unalias foo`
`type foo`
avoided a program that already exists, but may be desired if you want common options
`type ls`
`alias` - see all the aliases
`alias l.='ls -d .* --color=tty' alias ll='ls -l --color=tty' alias ls='ls --color=tty'
`
aliases defined in command line disappear. need environments to keep them.
### Revisiting Old Friends
Visit documentation to other commands.

## 6: Redirection
The I/O stands for input/output, and with this
facility you can redirect the input and output of commands to and from files, as well as connect multiple commands to make powerful command pipelines.
`cat` - concatenate files
`sort` - sort lines of text
`uniq` - report or omit repeated lines
`wc` - print newline, word, and byte counts for each file.
`grep` - print lines matching a pattern
`head` - output the first part of a file
`tail` - output the last part of a file
`tee` - read from standard input and write to standard output and files

### Standard Input, Output, and Error
programs send their results to a special file called standard output (stdout) and their status messages to another file called standard error (stderr).
Programs take input from standard input (stdin) often the keyboard.
I/O redirection allows us to change where output goes and where input comes from.

#### Redirecting Standard Output
use the `>` redirection operator followed by the name of the file.
`ls -l /usr/bin > ls-output.txt`
`ls -l ls-output.txt`
`less ls-output.txt`

try with a directory that doesn't exist
`ls -l /bin/usr > ls-output.txt` receive an error
`ls -l ls-output.txt` the file was overwritten
`> ls-output.txt` willt runcate a file or reate a new empty file

use `>>` to apend to a file
`ls -l /usr/bin >> ls-output.txt`

#### Redirecting Standard Error
To redirect standard error we must refer to its file descriptor.
first three of these file streams as standard input, output, and error, the shell references them internally as file descriptors 0, 1, and 2, respectively.

`ls -l /bin/usr 2> ls-error.txt`

#### Redirecting Standard Output and Standard Error to One File
`ls -l /bin/usr > ls-output.txt 2>&1`
First we redirect standard output to the file ls-output.txt, and then we redirect file descriptor 2 (standard error) to file descriptor 1 (standard output) using the nota- tion 2>&1.
new bash
Notice that the order of the redirections is significant. The redirection of standard error must always occur after redirecting standard output or it doesn’t work. 

`ls -l /bin/usr &> ls-output.txt`

#### Disposing of Unwanted Output
The system provides a way to do this by redirecting output to a special file called /dev/null. This file is a system device called a bit bucket, which accepts input and does nothing with it.
`ls -l /bin/usr 2> /dev/null`

#### Redirecting Standard Input
cat—Concatenate Files
The cat command reads one or more files and copies them to standard out- put like so:
`cat ls-output.txt`

can rejoin files
`cat movie.mpeg.0* > movie.mpeg`

cat waits for input try:
`cat`
`The quick brown fox jumped over the lazy dog.`
use ctrl+D to EOF

n the absence of filename arguments, cat copies standard input to standard output, so we see our line of text repeated. 
`cat > lazy_dog.txt`
`The quick brown fox jumped over the lazy dog.`

`cat < lazy_dog.txt`
`The quick brown fox jumped over the lazy dog.`
### Pipelines
The ability of commands to read data from standard input and send to standard output is utilized by a shell feature called pipelines. Using the pipe operator | (vertical bar), the standard output of one command can be piped into the standard input of another.
`command1 | command2`

to see output in a neat way:
`ls -l /usr/bin | less`

#### Filters
pipelines are often used to perform complex operations. you can put several commands together into a pipeline and produce a filtter. filters take input, change it, and output it.

`ls /bin /usr/bin | sort | less`
#### uniq—Report or Omit Repeated 
the uniq command is often used in conjunction with sort. uniq accepts a sorted list of data from either standard input or a single filename argument (see the uniq man page for details) and, by default, removes any duplicates from the list.
remove uniques:
`ls /bin /usr/bin | sort | uniq | less`
see duplcates:
`ls /bin /usr/bin | sort | uniq -d | less`

#### wc—Print Line, Word, and Byte Counts

The wc (word count) command is used to display the number of lines, words, and bytes contained in files. For example:
`wc ls-output.txt`
`ls /bin /usr/bin | sort | uniq | wc -l`

#### grep—Print Lines Matching a Pattern
grep is a powerful program used to find text patterns within files, like this:
`grep patterns [file...]`

#### head/tail—Print First/Last Part of Files
The head command prints the first 10 lines of a file, and the tail command prints the last 10 lines. The head command prints the first 10 lines of a file, and the tail command prints the last 10 lines.

`head -n 5 ls-output.txt`
`tail -n 5 ls-output.txt`

Can be used with pipes as well.
`ls /usr/bin | tail -n 5`

tail has an option that allows you to view files in real time.
`tail -f /var/log/messages`

#### tee—Read from Stdin and Output to Stdout and Files
The tee program reads standard input and copies it to both standard output (allowing the data to continue down the pipeline) and to one or more files.

`ls /usr/bin | tee ls.txt | grep zip`

### Final Note
Many commands make use of standard input and output, and almost all command-line programs use standard error to display their informative messages.

## 7: Seeing the World as the Shell Sees It
### Expansion
With expansion, you enter something, and it is expanded into something else before the shell acts upon it.

When the ENTER key is pressed, the shell automatically expands any qualifying characters on the command line before the command is carried out, so the echo command never saw the \*, only its expanded result

#### Pathname Expansion
The mechanism by which wildcards work is called pathname expansion
`echo D*`

for hidden files `ls -d .[!.]?*`

#### Tilde Expansion
When used at the beginning of a word, it expands into the name of the home directory of the named user or, if no user is named, the home directory of the current user:

`echo ~`

#### Arithmetic Expansion
Arithmetic expansion uses the following form:
`$((expression))`

`echo $(($((5**2)) * 3))`

`echo $(((5**2) * 3))`

#### Brace Expansion
With it, you can create multiple text strings from a pattern containing braces.
`echo Front-{A,B,C}-Back`
Patterns to be brace expanded may contain a leading portion called a preamble and a trailing portion called a postscript.
`echo Number_{1..5}`
`echo {Z..A}`
`echo a{A{1,2},B{3,4}}b`
`mkdir {2009..2011}-0{1..9} {2009..2011}-{10..12}`

#### Parameter Expansion
It’s a feature that is more useful in shell scripts than directly on the command line. Many of its capabilities have to do with the system’s ability to store small chunks of data and to give each chunk a name.

`echo $USER`

#### Command Substitution
Command substitution allows us to use the output of a command as an expansion:
`echo $(ls)`

`ls -l $(which cp)`

`file $(ls /usr/bin/* | grep zip)`

### Quoting
The shell provides a mechanism called quoting to selectively suppress unwanted expansions.

`echo this is a  test`
`echo The total is $100.00`

#### Double Quotes

#### Single Quotes
#### Escaping Characters
### Final Note
## 8: Advanced Keyboard Tricks
### Command Line Editing
#### Cursor Movement
#### Modifying Text
#### Cutting and Pasting (Killing and Yanking) Text
### Completion
### Using History
#### Searching History
#### History Expansion
### Final Note
## 9: Permissions
### Owners, Group Members, and Everybody Else
### Reading, Writing, and Executing
#### chmod—Change File Mode
#### Octal Representation
#### Symbolic Representation
#### Setting File Mode with the GUI
#### umask—Set Default Permissions
### Changing Identities
#### su—Run a Shell with Substitute User and Group IDs
#### sudo—Execute a Command as Another User
#### chown—Change File Owner and Group
#### chgrp—Change Group Ownership
### Exercising Your Privileges
### Changing Your Password
## 10: Processes
### How a Process Works
#### Viewing Processes with ps
#### Viewing Processes Dynamically with top
### Controlling Processes
#### Interrupting a Process
#### Putting a Process in the Background
#### Returning a Process to the Foreground
#### Stopping (Pausing) a Process
### Signals
#### Sending Signals to Processes with kill
#### Sending Signals to Multiple Processes with killall
### More Process-Related Commands
# Part 2: Configuration and the Environment
## 11: The Environment
### What Is Stored in the Environment?
#### Examining the Environment
#### Some Interesting Variables
### How Is the Environment Established?
#### Login and Non-login Shells
#### What’s in a Startup File?
### Modifying the Environment
#### Which Files Should We Modify?
#### Text Editors
#### Using a Text Editor
#### Activating Our Changes
### Final Note
## 12: A Gentle Introduction to vi
### Why We Should Learn vi
### A Little Background
### Starting and Stopping vi
### Editing Modes
#### Entering Insert Mode
#### Saving Our Work
### Moving the Cursor Around
### Basic Editing
#### Appending Text
#### Opening a Line
#### Deleting Text
#### Cutting, Copying, and Pasting Text
#### Joining Lines
### Search and Replace
#### Searching Within a Line
#### Searching the Entire File
#### Global Search and Replace
### Editing Multiple Files
#### Switching Between Files
#### Opening Additional Files for Editing
#### Copying Content from One File into Another
#### Inserting an Entire File into Another
### Saving Our Work
## 13: Customizing the Prompt
### Anatomy of a Prompt
### Trying Some Alternative Prompt Designs
### Adding Color
### Moving the Cursor
### Saving the Prompt
### Final Note
# Part 3: 
Common Tasks and Essential Tools
## 14: Package Management
### Packaging Systems
### How a Package System Works
#### Package Files
#### Repositories
#### Dependencies
#### High- and Low-Level Package Tools
### Common Package Management Tasks
#### Finding a Package in a Repository
#### Installing a Package from a Repository
#### Installing a Package from a Package File
#### Removing a Package
#### Updating Packages from a Repository
#### Upgrading a Package from a Package File
#### Listing Installed Packages
#### Determining Whether a Package Is Installed
#### Displaying Information About an Installed Package
#### Finding Which Package Installed a File
### Final Note
## 15: Storage Media
### Mounting and Unmounting Storage Devices
#### Viewing a List of Mounted Filesystems
#### Determining Device Names
### Creating New Filesystems
#### Manipulating Partitions with fdisk
#### Creating a New Filesystem with mkfs
### Testing and Repairing Filesystems
### Formatting Floppy Disks
### Moving Data Directly to and from Devices
### Creating CD-ROM Images
#### Creating an Image Copy of a CD-ROM
#### Creating an Image from a Collection of Files
### Writing CD-ROM Images
#### Mounting an ISO Image Directly
#### Blanking a Rewritable CD-ROM
#### Writing an Image
### Extra Credit
## 16: Networking
### Examining and Monitoring a Network
#### ping—Send a Special Packet to a Network Host
#### traceroute—Trace the Path of a Network Packet
#### netstat—Examine Network Settings and Statistics
### Transporting Files over a Network
#### ftp—Transfer Files with the File Transfer Protocol
#### lftp—A Better ftp
#### wget—Non-interactive Network Downloader
### Secure Communication with Remote Hosts
#### ssh—Securely Log in to Remote Computers
#### scp and sftp—Securely Transfer Files
## 17: Searching for Files
### locate—Find Files the Easy Way
### find—Find Files the Hard Way
#### Tests
#### Actions
#### A Return to the Playground
#### Options
## 18: Archiving and Backup
### Compressing Files
#### gzip—Compress or Expand Files
#### bzip2—Higher Compression at the Cost of Speed
### Archiving Files
#### tar—Tape Archiving Utility
#### zip—Package and Compress Files
### Synchronizing Files and Directories
#### rsync—Remote File and Directory Synchronization
#### Using rsync over a Network
## 19: Regular Expressions
### What Are Regular Expressions?
### grep—Search Through Text
### Metacharacters and Literals
### The Any Character
### Anchors
### Bracket Expressions and Character Classes
#### Negation
#### Traditional Character Ranges
#### POSIX Character Classes
### POSIX Basic vs. Extended Regular Expressions
### Alternation
### Quantifiers
#### ?—Match an Element Zero Times or One Time
#### *—Match an Element Zero or More Times
#### +—Match an Element One or More Times
#### { }—Match an Element a Specific Number of Times
### Putting Regular Expressions to Work
#### Validating a Phone List with grep
#### Finding Ugly Filenames with find
#### Searching for Files with locate
#### Searching for Text with less and vim
### Final Note
## 20: Text Processing
### Applications of Text
#### Documents
#### Web Pages
#### Email
#### Printer Output
#### Program Source Code
### Revisiting Some Old Friends
#### cat—Concatenate Files and Print on Standard Output
#### sort—Sort Lines of Text Files
#### uniq—Report or Omit Repeated Lines
### Slicing and Dicing
#### cut—Remove Sections from Each Line of Files
#### paste—Merge Lines of Files
#### join—Join Lines of Two Files on a Common Field
### Comparing Text
#### comm—Compare Two Sorted Files Line by Line
#### diff—Compare Files Line by Line
#### patch—Apply a diff to an Original
### Editing on the Fly
#### tr—Transliterate or Delete Characters
#### sed—Stream Editor for Filtering and Transforming Text
#### aspell—Interactive Spell Checker
### Final Note
### Extra Credit
## 21: Formatting Output
### Simple Formatting Tools
#### nl—Number Lines
#### fold—Wrap Each Line to a Specified Length
#### fmt—A Simple Text Formatter
#### pr—Format Text for Printing
#### printf—Format and Print Data
### Document Formatting Systems
#### The roff Family and TEX
#### groff—A Document Formatting System
### Final Note
## 22: Printing
### A Brief History of Printing
#### Printing in the Dim Times
#### Character-Based Printers
#### Graphical Printers
### Printing with Linux
### Preparing Files for Printing
#### pr—Convert Text Files for Printing
### Sending a Print Job to a Printer
#### lpr—Print Files (Berkeley Style)
#### lp—Print Files (System V Style)
#### Another Option: a2ps
### Monitoring and Controlling Print Jobs
#### lpstat—Display Print System Status
#### lpq—Display Printer Queue Status
#### lprm and cancel—Cancel Print Jobs
## 23: Compiling Programs
### What Is Compiling?
#### Are All Programs Compiled?
### Compiling a C Program
#### Obtaining the Source Code
#### Examining the Source Tree
#### Building the Program
#### Installing the Program
### Final Note
# Part 4: 
Writing Shell Scripts
## 24: Writing Your First Script
### What Are Shell Scripts?
### How to Write a Shell Script
#### Script File Format
#### Executable Permissions
#### Script File Location
#### Good Locations for Scripts
### More Formatting Tricks
#### Long Option Names
#### Indentation and Line Continuation
### Final Note
## 25: Starting a Project
### First Stage: Minimal Document
### Second Stage: Adding a Little Data
### Variables and Constants
#### Creating Variables and Constants
#### Assigning Values to Variables and Constants
### Here Documents
### Final Note
## 26: Top-Down Design
### Shell Functions
### Local Variables
### Keep Scripts Running
### Final Note
## 27: Flow Control: Branching with if
### Using if
### Exit Status
### Using test
#### File Expressions
#### String Expressions
#### Integer Expressions
### A More Modern Version of test
### (( ))—Designed for Integers
### Combining Expressions
### Control Operators: Another Way to Branch
### Final Note
## 28: Reading Keyboard Input
### read—Read Values from Standard Input
#### Options
#### Separating Input Fields with IFS
### Validating Input
### Menus
### Final Note
### Extra Credit
## 29: Flow Control: Looping with while and until
### Looping
### while
### Breaking out of a Loop
### until
### Reading Files with Loops
### Final Note
## 30: Troubleshooting
### Syntactic Errors
#### Missing Quotes
#### Missing or Unexpected Tokens
#### Unanticipated Expansions
### Logical Errors
#### Defensive Programming
#### Verifying Input
### Testing
#### Stubs
#### Test Cases
### Debugging
#### Finding the Problem Area
#### Tracing
#### Examining Values During Execution
### Final Note
## 31: Flow Control: Branching with case
### case
#### Patterns
#### Combining Multiple Patterns
### Final Note
## 32: Positional Parameters
### Accessing the Command Line
#### Determining the Number of Arguments
#### shift—Getting Access to Many Arguments
#### Simple Applications
#### Using Positional Parameters with Shell Functions
### Handling Positional Parameters En Masse
### A More Complete Application
### Final Note
## 33: Flow Control: Looping with for
### for: Traditional Shell Form
### for: C Language Form
### Final Note
## 34: Strings and Numbers
### Parameter Expansion
#### Basic Parameters
#### Expansions to Manage Empty Variables
#### Expansions That Return Variable Names
#### String Operations
### Arithmetic Evaluation and Expansion
#### Number Bases
#### Unary Operators
#### Simple Arithmetic
#### Assignment
#### Bit Operations
#### Logic
### bc—An Arbitrary-Precision Calculator Language
#### Using bc
#### An Example Script
### Final Note
### Extra Credit
## 35: Arrays
### What Are Arrays?
### Creating an Array
### Assigning Values to an Array
### Accessing Array Elements
### Array Operations
#### Outputting the Entire Contents of an Array
#### Determining the Number of Array Elements
#### Finding the Subscripts Used by an Array
#### Adding Elements to the End of an Array
#### Sorting an Array
#### Deleting an Array
### Final Note
## 36: Exotica
### Group Commands and Subshells
#### Performing Redirections
#### Process Substitution
### Traps
### Asynchronous Execution
#### wait
### Named Pipes
#### Setting Up a Named Pipe
#### Using Named Pipes
### Final Note
# Index
# Support the Electronic Frontier Foundation
# Updates
