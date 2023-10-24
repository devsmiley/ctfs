# Level 7 → Level 8

### Level Goal

The password for the next level is stored in the file **data.txt** next to the word **millionth**

### Commands you may need to solve this level

[man](https://man7.org/linux/man-pages/man1/man.1.html), grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Solution:

```bash
bandit7@bandit:~$ ls
data.txt
banditz@bandit:~$ grep -i "millionth" data.txt
millionth.      TESKZCOXvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$
logout
Connection to bandit.labs.overthewire.org closed.
```
