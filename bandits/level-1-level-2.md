# Level 1 → Level 2

### Level Goal

The password for the next level is stored in a file called **-** located in the home directory

### Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html)

### Helpful Reading Material

* [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
* [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)

### Solution:

* To read a **dash (-) file**

```bash
$ cat ./-
```

```bash
banditl@bandit:~$ ls
banditl@bandit:~$ cat ./-
****pass******
bandit1@bandit:~$
logout
Connection to bandit.labs.overthewire.org closed.
```
