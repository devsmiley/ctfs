# Level 11 → Level 12

### Level Goal

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Helpful Reading Material

* [Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)

### Solution:

* **tr command** is used to translate, delete and squeeze characters from the standard input and writes the result to the standard output.&#x20;
* It accepts two sets of characters, usually with the same length, and replaces the characters of the first sets with the corresponding characters from the second set.

{% code overflow="wrap" %}
```bash
$ tr SET1 [SET2]
SET = string of characters, including the special backslash-escaped characters.
```
{% endcode %}

* a+13 = n; z+13 = m

```bash
bandit11@bandit:~$ ls
data. txt
bandit11@bandit:~$ cat data.txt | tr '[a-zA-Z]' '[n-za-mN-ZA-M]'
The password is JVNBBFSmZwKKOP0XbFX00W8chDz5yVRv
bandit11@bandit:~$
logout
vel
aLXHBM
Connection to bandit.labs.overthewire.org closed.
```
