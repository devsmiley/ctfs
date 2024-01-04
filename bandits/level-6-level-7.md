# Level 6 → Level 7

### Level Goal

The password for the next level is stored **somewhere on the server** and has all of the following properties:

* owned by user bandit7
* owned by group bandit6
* 33 bytes in size

### Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html) , [grep](https://man7.org/linux/man-pages/man1/grep.1.html)

### Solution:

<figure><img src="../.gitbook/assets/image (8) (1) (1).png" alt=""><figcaption></figcaption></figure>

* To avoid error message printed on terminal, use error file descriptors

```bash
$ 2 > /dev/null

0 = stdin
1 = stdout
2 = error
```

* The /dev/null is a null device that discards any data that is written to it. However, it reports back that the write operation is successful

{% code overflow="wrap" %}
```bash
bandit6@bandit:~$ find / -size 33c-user bandit7 -group bandit6 -type f 2 > /dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
****pass******
bandit6@bandit:~$
logout
Connection to bandit.labs.overthewire.org closed.
```
{% endcode %}
