# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 
/c/Users/Tim_T/projects/wats1030-intro-to-unix
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
challenge_files  LICENSE  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  README.md  super_scavengers.md
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
total 78K
drwxr-xr-x 1 Tim_T 197609    0 Jan 13 19:51 .
drwxr-xr-x 1 Tim_T 197609    0 Jan 13 19:51 ..
drwxr-xr-x 1 Tim_T 197609    0 Jan 13 19:51 .git
drwxr-xr-x 1 Tim_T 197609    0 Jan 13 19:51 challenge_files
-rw-r--r-- 1 Tim_T 197609 1.1K Jan 13 19:51 LICENSE        
-rw-r--r-- 1 Tim_T 197609 5.7K Jan 13 20:00 nix_scavenger_hunt.md
-rw-r--r-- 1 Tim_T 197609  325 Jan 13 19:51 nix_scavenger_hunt_stretch.md
-rw-r--r-- 1 Tim_T 197609 2.8K Jan 13 19:51 README.md
-rw-r--r-- 1 Tim_T 197609  268 Jan 13 19:51 super_scavengers.md
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
-a --all, do not ignore entries starting with .
-l   use a long listing format
-h --human-readable, with -l and/or -s, print human readable sizes (e.g., 1K 234M 2G)
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
bin  cmd  dev  etc  git-bash.exe  git-cmd.exe  LICENSE.txt  mingw64  proc  ReleaseNotes.html  tmp  unins000.dat  unins000.exe  unins000.msg  usr
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
/
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
/c/Users/Tim_T
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
2015_special_stuff.demo cloaked-wookie.demo scooter-double-mamba.demo 
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
/c/Users/Tim_T/projects/wats1030-intro-to-unix
* Press the up arrow on your keyboard. *What just happened?*
$ pwd
* Press the up arrow a few more times. *What do you see?*
$ cd ..
* Run the `history` command. *What do you see?*
History of commands used all the way back to when I first linked my local device to github.
### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
Tim_T
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
None
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
bash: uptime: command not found
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
From the text in the manual, ps aux is showing active processes. It shows each process with a process ID (PID), terminal associated with the process (TTY), the cumulated CPU time, and the executable name (COMMAND).
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
bash: top: command not found
According to the manual, top is used for repetitive updates of 'ps'.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
$ ls credit*
credit_cards.txt  credit_cards2.txt
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
$ more -d credit_cards.txt
bash: more: command not found
01-15-2015
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
./tmp/modi_laboriosam.txt
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
$ more -d files.txt
bash: more: command not found
Found all the files from the challenge_files inside the files.txt.
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
$ ls -alh | more
bash: more: command not found
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
Was not able to perform this task in bash terminal.