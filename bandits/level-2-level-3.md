# Level 2 → Level 3

### Level Goal

The password for the next level is stored in a file called **spaces in this filename** located in the home directory

### Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html)

### Helpful Reading Material

* [Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)

### Solution:

* To read a file with spaces in file name

```bash
$ cat "file name with spaces"

OR

$ cat file\ name\ with\ spaces
```

{% code overflow="wrap" %}
```bash
bandit2@bandit:~$ ls spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename" aBZOW5EmUfAf7kHTQe0wd8bauFJ2lAiG
bandit2@bandit:~$ cat spaces\ in\ this\ filename aBZOW5EmUfAf7kHTQe0wd8bauFJ2lAiG
bandit2@bandit:~$
logout
Connection to bandit. labs.overthewire.org closed.
```
{% endcode %}
