# Level 10 → Level 11

### Level Goal

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Helpful Reading Material

* [Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)

### Solution:

{% code overflow="wrap" %}
```bash
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ file data.txt
data.txt: ASCII text
bandit10@bandit:~$ cat data. txt
 ****encoded pass******
bandit10@bandit:~$ base64 -decode data.txt
The password is ****pass******
bandit10@bandit:~$
logout
Connection to bandit.labs.overthewire.org closed.
```
{% endcode %}
