# Terminal Usages & Basic Commands

Most of these commands with run on any Unix like operating system.
To use the commands in windows you have to install Linux sub-system or use third-party softwares like [Cygwin](https://www.cygwin.com/)

## Basic Commands

##### Returns the user currently logged in the terminal session.
```bash
whoami
```
---
##### Which
```bash
which <command>
```
---
##### Get linux version
```bash
cat /etc/os-release
lsb_release -a
```
---
##### Get suggession
```bash
who *Press Tab*
$ who whoami whois
```
---

##### Manual pages of any command
```bash
man <command>
```
up arrow and down arrow keys to navigate. 
q to quit.

---
##### Clear the terminal screen
```bash
clear # clears the terminal

clear -x # clears the terminal but keep it in scroll buffer
```
shortcut: ctrl + l

---
##### Get working directory
```bash
pwd # print working directory
```
---
##### Current date and time
```bash
date
```

---
##### Send content of command to a file
```bash
date > date.txt
```
---
##### Append content of command to a file
```bash
date >> date.txt
```
---


##### List files & folders of current directory
```bash
ls # Show files & folders of current directory

ls -a # Show files & folders including hidden files

ls -l # Show files & folders in a long listing format

ls /Users/coderdipto # Show files & folders of a specific location
```

---
##### Change Directory
```bash
cd /Users/coderdipto # Change shell WD

cd ../../ # Change WD to predecessors

cd *Enter* or cd ~ # Goes to home folder
```
---
##### Make Directory
```bash
mkdir <folder>
mkdir -p <folder>/<child> # Creates necessary sub folders

```
---
##### Change timestamp of a file
```bash
touch <file> <file2>

```
---
##### Remove file
```bash
rm <file> <file2>

rm -v <file> # Verbose

```
---
##### Remove folder
```bash
rmdir <folder>

rm -r <folder> # Recursively deletes all children

rm -rv <folder> # Verbose

rm -ri <folder> # Interactive

```
---
##### Open file or folder with default application
```bash
[MAC ONLY] open <file>

[LINUX ONLY] xdg-open <file>

```
---
##### Move files or folder
```bash
mv [-v] <source> <destination>

```
---
##### Copy files or folder
```bash
cp [-v] <source> <destination> # Verbose

cp -r <source> <destination> # Recursive

```
---
##### See content of file from start
```bash
head <file> # Show first 10 lines

head -n 100 <file> # Show first 100 lines

```
---
##### See content of file from end
```bash
tail <file> # Show last 10 lines

tail -n 100 <file> # Show last 100 lines

tail -f <file>

```
---
##### Concatenate two files and print the output in the terminal
```bash
cat [-n] <file>

cat <file1> <file2>
```
---
##### Read files in a more user friendly way
```bash
less <file>
```
Quit - q
Search - /
G - Go the end of the file
g - Go to the start of the file

---
##### Print text in terminal
```bash
echo 'HI'

echo 'DATABASE=postgres' > .env
```
---
##### Get line words and bytes count of a file
```bash
wc <file>
$ <lines> <words> <bytes>
```
---
##### Piping
```bash
ls -al | wc
```
---
##### Sort  
```bash
sort <file> # By default alphanumeric sort

sort -n <file>

uniq -d <file> # Show only duplicate entries

uniq -u <file> # Show only non duplicate entries


uniq -dc <file> # Show non duplicate entries count
```
---
##### Expressions
```bash
~ # Home directory

$PATH # Environment variable file location related

$USER # Current user

ls -l *.txt # Wildcard match

ls -l *.?? # Exact character match

touch {a,b,c}.py # Expanding

echo {1..99} # Range expanding
```
---
##### Difference between two files
```bash
diff <file1> <file2>

diff -y <file1> <file2> # See files side by side

diff -u <file> <file2> # See contextual changes
```
---
##### Find files or folders recursively
```bash
find . -name '*.py' # Search via name

find . -type [d|f] -name '*src*' # Search via name and type

find . -iname '*src*' # Search case insensitive

find . -iname '*src*' or -iname '*dist*' # Using or

find . -iname '*src*' -size +100k -size -1M # Search using file size

find . -mtime +3 # Modified more than 3 days ago
```
---
Reference: https://nicolasbouliane.com/blog/knowing-difference-mtime-ctime-atime
##### GREP (Global Regular Expression Print)
Search text inside file
```bash
grep <word> <file>

grep -n <word> <file> # With line number

grep -C <word> <file> # With context

grep -r <word> # Recursively finds the whole directory

grep -i <word> # Case insensetive
```
---
##### du (Disk Usage)
```bash
du -h # Disk usage in human readable form

du -h | sort -h # Sorting folder based on disk usage
```
---
##### df (Disk Usage of mounted file systems)
```bash
df -h # Disk usage of file systems

du -h | sort -h # Sorting folder based on disk usage
```
---
##### History
```
history

history -c # Clean history

!<history>
```
---
##### PS (Process status)
```
ps

ps axww | grep bash

```
---
##### TOP
```
top

top -o %MEM # Sort via field

htop
```
---
##### Kill process
```
kill -l # List of different signals kill can send

kill -15/9 <pid>
```
---
##### Kill all
```
killall -9/15 <name>
```
---
##### Jobs (Run jobs in background and foreground)
```
 sleep 120 # Type Ctrl + Z to pause a job

 jobs # See list of jobs

 bg <job> # Run job in background

 fg <job> # Run job in foreground

 sleep 120 & # Another way of running bg job
```
---
##### GZIP
```
gzip <filename>

gzip -c <filename> > <name>  # Keep the original file

gzip -k[v] <filename>  # Keep the original file

zcat <compressed> # show compressed file

gzip -d <filename> # Unzip

gunzip <filename> # Unzip
```
---
##### TAR
```
tar -c[z]f <archivename> <file1> <file2> # c for create, f for name, z for compressing

tar -tf <archive> # See files inside

tar -xf <archive> -C <directory> # Extract to a specific folder
```
---
##### Nano
```
nano <filename>
```
Ctrl + W : Search file
Ctrl + X : Quit file
Ctrl + S : Save file
Ctrl + K : Cut
Ctrl + U : Paste
Ctrl + O : Write to a new file
Ctrl + ~ : Jump to next word
Ctrl + / : Jump to line
Ctrl + \ : Find and replace

---
##### Alias
```bash
alias ll='ls -l'

unalias <alias>

```
Write in .bashrc or .zshrc
---
##### Xargs
```bash
cat players.txt | xargs rm
find . -size +1M | xargs ls -lh

```

-> Which commands takes xargs

---
##### Link
```bash
link <file1> <file2>
link -s <file1> <file2>

```
---
##### Swith User (SU)
```bash
su <username>

```
---
##### SUDO
```bash
sudo <command>

```
---
##### Change password
```bash
passwd

```
---
##### Change ownership
```bash
sudo chown <user> <file>

chown -r <user> <folder> # Recursively

chown <user>:<group> <file>
```
---
##### Groups
```bash
groups
```
---
##### Understanding permissions

10 characters

1st character

\- file
d folder
l symlink

3 groups of nine characters

Owner | Group | World
r read
w write
x   execute

---
##### Chmod

u = owner
g = group
a = all
o = others

![Imgur](https://i.imgur.com/kvP0FiO.png)

![Imgur](https://i.imgur.com/6oYTP9T.png)

![Imgur](https://i.imgur.com/t01C2Zy.png)


```bash
chmod <mode> <file>

chmod ug+w <file>

chmod a=r <file>

chmod 755 <file>

```

---
##### Make Executable 
```bash
./<file>

chmod +x <file> # to make executable
```
##### Wget
```bash
wget <url>
```
##### Tree
```bash
tree

tree -f # Full path
```
##### Time to run a command
```bash
time <command>
```
##### Host
```bash
host <domain>
```
##### Add user
```bash
sudo useradd [-m] <username>
sudo passwd <username>

```
##### Add groups
```bash
sudo groupadd <group>

```
##### Modify user groups
```bash
sudo usermod -a -G <group> <user> # add user in group
sudo gpasswd -d <user> <group> # remove user from group

```



Download the linux manual from [here](https://itbook.store/books/1001614175565)
