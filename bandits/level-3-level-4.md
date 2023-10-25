# Level 3 → Level 4

### Level Goal

The password for the next level is stored in a hidden file in the **inhere** directory.

### Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html)

### Solution:

* To list hidden file

```bash
$ ls -a
```

{% code overflow="wrap" %}
```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/ 
bandit3@bandit:~/inhere$ ls 
bandit3@bandit:~/inhere$ ls -a
. .. .hidden
bandit3abandit:~/inhere$ cat hidden
****pass******
bandit3@bandit:~/inhere$
logout
Connection to bandit.labs.overthewire.org closed.
```
{% endcode %}
