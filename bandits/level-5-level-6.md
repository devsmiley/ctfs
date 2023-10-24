# Level 5 → Level 6

### Level Goal

The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

* human-readable
* 1033 bytes in size
* not executable

### Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html)

### Solution:

* To find the file with specific size in current directory

```bash
$ find . -size <S>1000<X>
    
S = + (greater than) 
    - (smaller than)

X = c - byte
		k - kilo
    M - mega
    G - giga

```

<pre class="language-bash" data-overflow="wrap"><code class="lang-bash">bandit5@bandit: ~$ ls inhere
bandit5@bandit:~$ cd inhere/ 
bandit5abandit:~/inhere$ ls 
maybehere00 maybehere04
maybehere08
maybehere12
maybehere16
maybehere01 
maybehere05
maybehere09
maybehere13
maybehere17
maybehere02 
maybehere06
maybehere10
maybehere14
maybehere18
maybehere03 
maybehere07 
maybehere11
maybehere15
maybehere19
bandit5@bandit:~/inhere$ find -size 1033c -type f -exec file {} \;
<strong>./maybehere07/.file2: ASCII text, with very long lines (1000) 
</strong><strong>bandit5abandit:~/inhere$ cat maybehere07/.file2
</strong>P4L4vucdmLnm8I7V17jG1ApGSfjYKqJU
bandit5@bandit:~/inhere$
logout
Connection to bandit.labs.overthewire.org closed.
</code></pre>
