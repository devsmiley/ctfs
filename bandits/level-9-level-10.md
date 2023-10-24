# Level 9 → Level 10

### Level Goal

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Ref:

[Finding Strings From Binary Files in Linux | Baeldung on Linux](https://www.baeldung.com/linux/find-string-binary-file)

### Solution:

* File Type is **data** which is binary

```bash
bandit9@bandit:~$ ls
data.txt
banditabandit:~$ file data.txt
data.txt: data
```

* To determine human readable string in this file, use strings command

```bash
bandit9@bandit:~$ ls data. txt
banditabandit:~$ strings data.txt | grep "="
4====================the#
5P=GnFE
=================password
'DN9=5
=================is 
$Z=_ 
=TU% 
=^,T,?
W=y
q=W
X=К,

============G7w8LIi6J3kTb8A7j9\grywtEUlyyp6s
&S=(
nd?= 
bandit9@bandit:~$
logout
Connection to bandit.labs.overthewire.org closed.
```
