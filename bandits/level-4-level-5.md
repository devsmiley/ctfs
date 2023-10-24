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

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

* Another solution is to use **xargs** command (does it old school way)
* The xargs command reads lines of text from the standard input or from the output of another command and turns them into commands and execute them.

<pre class="language-bash"><code class="lang-bash"><strong>$ find . -type f | xargs file
</strong></code></pre>

* **find** command lists file names and **xargs** command provides them one by one (as if it was an input to another command)

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
