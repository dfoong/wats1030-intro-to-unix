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
/home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*

```
LICENSE challenge_files
nix_scavenger_hunt_stretch.md
README.md  nix_scavenger_hunt.md  super_scavengers.md

```
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*

```
total 40K
drwxrwxr-x  4 cabox cabox 4.0K Jan 21 03:09 .
drwxr-xr-x 11 cabox cabox 4.0K Jan 21 03:09 ..
drwxrwxr-x  8 cabox cabox 4.0K Jan 21 03:09 .git
-rw-rw-r--  1 cabox cabox 1.1K Jan 21 03:09 LICENSE
-rw-rw-r--  1 cabox cabox 2.7K Jan 21 03:09 README.md
drwxrwxr-x  7 cabox cabox 4.0K Jan 21 03:09 challenge_files
-rw-rw-r--  1 cabox cabox 5.6K Jan 21 06:48 nix_scavenger_hunt.md
-rw-rw-r--  1 cabox cabox  317 Jan 21 03:09 nix_scavenger_hunt_stretch.md
-rw-rw-r--  1 cabox cabox  191 Jan 21 03:09 super_scavengers.md
```

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

"ls --help" results for 'a', 'l', 'h'
a: all
l: use a long listing format
h: human-readable

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*

bin   dev  fastboot  lib    media  opt   root  sbin  sys  usr
boot  etc  home      lib64  mnt    proc  run   srv   tmp  var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*

/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

/home/cabox

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*

3 files

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*

/

* Press the up arrow on your keyboard. *What just happened?*

pwd

* Press the up arrow a few more times. *What do you see?*

cd, ls, cd challenge_files

* Run the `history` command. *What do you see?*

    1  cd challenge_fi;es
    2  cd challenge_files
    3  ls
    4  cd /
    5  pwd
    6  history

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

cabox    pts/0        Jan 21 19:48 (52.161.27.120)

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

19:53:27 up 53 min,  1 user,  load average: 0.00, 0.00, 0.00

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*

```
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIMECOMMAND
root         1  0.0  0.9  33204  2600 ?        Ss   21:37   0:00init
root         2  0.0  0.0      0     0 ?        S    21:37   0:00[kthreadd/150367]
root         3  0.0  0.0      0     0 ?        S    21:37   0:00[khelper/1503670]
root       149  0.0  0.3  19428   820 ?        S    21:37   0:00upstart-udev-bridge --daemon
root       164  0.0  0.5  49216  1408 ?        Ss   21:37   0:00/lib/systemd/systemd-udevd --daemon
syslog     344  0.0  0.5 184188  1440 ?        Ssl  21:37   0:00rsyslogd
root       438  0.0  1.1  61316  3080 ?        Ss   21:37   0:00/usr/sbin/sshd -D
root       471  0.0  0.3  15492   844 ?        S    21:37   0:00upstart-file-bridge --daemon
root       473  0.0  0.4  15608  1052 ?        S    21:37   0:00upstart-socket-bridge --daemon
root       485  0.0  1.0  71260  2656 ?        Ss   21:37   0:00/usr/sbin/apache2 -k start
www-data   488  0.0  0.9 415720  2428 ?        Sl   21:37   0:00/usr/sbin/apache2 -k start
www-data   489  0.0  0.9 415720  2428 ?        Sl   21:37   0:00/usr/sbin/apache2 -k start
root       552  0.0  0.3  12740   848 tty1     Ss+  21:37   0:00/sbin/getty 38400 console
root       554  0.0  0.3  12740   852 tty2     Ss+  21:37   0:00/sbin/getty 38400 tty2
root       578  0.0  1.2  63876  3328 ?        Ss   21:37   0:00sshd: cabox [priv]
cabox      580  0.0  0.5  63876  1448 ?        S    21:37   0:00sshd: cabox@notty
cabox      581  0.0  0.3  12784   832 ?        Ss   21:37   0:00/usr/lib/openssh/sftp-server
root       582  0.0  1.2  63876  3336 ?        Ss   21:37   0:00sshd: cabox [priv]
cabox      584  0.0  0.5  64140  1536 ?        S    21:37   0:00sshd: cabox@notty
cabox      585  0.0  0.3  12776   980 ?        Ss   21:37   0:00/usr/lib/openssh/sftp-server
root       586  0.0  1.3  63876  3480 ?        Ss   21:37   0:00sshd: cabox [priv]
cabox      588  0.0  0.5  64008  1492 ?        S    21:37   0:00sshd: cabox@pts/0
cabox      589  0.0  1.7  20564  4468 pts/0    Ss   21:37   0:00-bash
cabox      788  0.0  0.4  15520  1140 pts/0    R+   21:52   0:00ps aux
```

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*

```

USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.9  33188  2516 ?        Ss   19:00   0:00 init
root         2  0.0  0.0      0     0 ?        S    19:00   0:00 [kthreadd/1498
root         3  0.0  0.0      0     0 ?        S    19:00   0:00 [khelper/14989
root       143  0.0  0.3  19428   808 ?        S    19:00   0:00 upstart-udev-b
root       185  0.0  0.5  49216  1396 ?        Ss   19:00   0:00 /lib/systemd/s
syslog     314  0.0  0.5 184188  1452 ?        Ssl  19:00   0:00 rsyslogd
root       356  0.0  0.3  15608   976 ?        S    19:00   0:00 upstart-socket
root       357  0.0  0.3  15488   816 ?        S    19:00   0:00 upstart-file-b
root       383  0.0  1.1  61316  3080 ?        Ss   19:00   0:00 /usr/sbin/sshd
root       439  0.0  1.0  71260  2656 ?        Ss   19:00   0:00 /usr/sbin/apac
www-data   442  0.0  0.9 415720  2428 ?        Sl   19:00   0:00 /usr/sbin/apac
www-data   443  0.0  0.9 415720  2432 ?        Sl   19:00   0:00 /usr/sbin/apac
root       510  0.0  0.3  12740   856 tty1     Ss+  19:00   0:00 /sbin/getty 38
root       512  0.0  0.3  12740   848 tty2     Ss+  19:00   0:00 /sbin/getty 38
root       519  0.0  1.2  63876  3332 ?        Ss   19:04   0:00 sshd: cabox [p
cabox      521  0.0  0.5  64168  1520 ?        S    19:04   0:00 sshd: cabox@no
cabox      522  0.0  0.3  12780   888 ?        Ss   19:04   0:00 /usr/lib/opens
root       723  0.0  1.3  63876  3476 ?        Ss   19:48   0:00 sshd: cabox [p
cabox      725  0.0  0.5  63876  1464 ?        S    19:48   0:00 sshd: cabox@pt
cabox      726  0.0  1.7  20564  4480 pts/0    Ss   19:48   0:00 -bash
cabox      928  0.0  0.4  15520  1144 pts/0    R+   19:54   0:00 ps aux
```

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
`
2 files:
credit_cards.txt
credit_cards2.txt
`

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*

find . -name modi_laboriosam.txt
./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
*Debbie: grep ir "wa"*

`
2 files:
Lissie-Strosin.user
Britt-Erdman.user
`

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
`
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur suntincidunt. Explicabo vel esse blanditiis dolorem culpa non quia.
`

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*

`
01
2015_special_stuff.demo
Afton-Jast.user
Aimee-Maggio.user
Alfonso-Gottlieb.user
Allen-Kemmer.user
Almina-Cormier.user
Alta-Lemke.user
Amina-McGlynn.user
Anabel-Hammes.user
Ancel-Conn.user
Anjali-Halvorson.user
Ardath-Kuvalis.user
Avah-Dickinson.user
Ayaan-Stiedemann.user
Aylin-Grant.user
Bedford-Sipes.user
Benita-King.user
Benito-Stoltenberg.user
Beverlee-Moen.user
Brad-Thiel.user
Brayan-Douglas.user
Bria-Satterfield.user
Bridgette-Reichel.user
Britt-Erdman.user
Britta-Hammes.user
Bryant-Kuhic.user
Bryton-Aufderhar.user
Caitlin-Grady.user
Carroll-Hartmann.user
Claudie-McClure.user
Clemente-Haley.user
Cleo-VonRueden.user
Codie-Romaguera.user
Cooper-Reynolds.user
Corrie-Bogisich.user
Dannielle-Green.user
Deedee-Jacobson.user
Desiree-Marks.user
Deven-Rutherford.user
Doyle-Jones.user
Dustyn-O'Connell.user
Elza-Mraz.user
Emory-Crona.user
Erin-Walker.user
Estela-Schultz.user
Fernanda-Tromp.user
`

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

`
The same files are listed, but is halved. To view the full list, you have to press Enter for 'more', it's not fully displayed, which makes it easier to read (initially).
`

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

`
ps aux | grep <dfoong>
-bash: syntax error near unexpected token `newline'
`


