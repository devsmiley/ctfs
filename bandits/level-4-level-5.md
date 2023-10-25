# Level 4 → Level 5

### Level Goal

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

### Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html)

#### Ref:

[15 Super Useful Examples of Find Command in Linux (linuxhandbook.com)](https://linuxhandbook.com/find-command-examples/)

### Solution:

* To find the file type of a file

```bash
$ file
```

* To get the file type of all files in current directory, use find and file combined
* But **find** command cannot directly combine the output of one command with the input of another command
* To resolve this, use **exec** command

{% code overflow="wrap" %}
```bash
$ find . -type f -exec file {} \\;

{} = references the result of find command (imagine it to be like {file 1, file 2, file 3})
\\ = used to escape special characters

OR

$ find . -type f -exec file {} +
+ = used to terminate the exec command
```
{% endcode %}

{% code overflow="wrap" %}
```bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/ bandit4@bandit:~/inhere$ ls
-file00
-file02 -file04 -file06 -file08
-file01-file03 -file05 -file07 -file09
bandit4@bandit:~/inhere$ find . -type f -exec file {} \;
•/-file03: data
•/-file06: data
•/-file08: data
•/-file07: ASCII text
•/-file04: data
•/-file00: data
•/-file01: data
•/-file02: data
•/-file09: Non-ISO extended-ASCII text, with no line terminators
•/-file05: data
bandit4@bandit:~/inhere$ cat ./-file07
****pass******
bandit4@bandit:~/inhere$
logout
Connection to bandit.labs.overthewire.org closed.
```
{% endcode %}

* Another solution is to use **xargs** command (does it old school way)
* The xargs command reads lines of text from the standard input or from the output of another command and turns them into commands and execute them.

<pre class="language-bash"><code class="lang-bash"><strong>$ find . -type f | xargs file
</strong></code></pre>

* **find** command lists file names and **xargs** command provides them one by one (as if it was an input to another command)

```bash
bandit4@bandit:~$ ls
inhere
OwcBapmTEZ13bVBHMM9H66VVX]L
bandit4@bandit:~$ cd inhere/ bandit4@bandit:~/inhere$ ls
SaX8MKIRTbICNQoXTcYZWU61gz1
-file00
-file04 a-file06
-file02ev-file04 a-file06 U-file08 0eOwd8bauFJ21AiG
-file01 -file03 -file05 -file07 -file09
EgX26XNe
bandit4@bandit:~/inhere$ find . -type fI xargs file
•/-file03: data
•/-file06: data
eveL t
•/-file08: data
•/-file07: ASCII text
•/-file04: data
•/-file00: data
•/-file01: data ./-file02: data
•/-file09: Non-ISO extended-ASCII text, with no line terminators ./-file05: data bandit4@bandit:~/inhere$ cat ./-file07
****pass******
bandit4@bandit:~/inhere$
logout
Connection to bandit.labs.overthewire.org closed.
```
