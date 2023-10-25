# Level 32 → Level 33

After all this `git` stuff its time for another escape. Good luck!

### Commands you may need to solve this level

sh, man

### Solution:

```bash
$ $0
- holds the name of file or script that is being executed
- if executed as it is in terminal, it will spwan an new shell

$ echo $0
in terminal, if executed, it echos the name of currently used shell
```



{% code overflow="wrap" %}
```bash
WELCOME TO THE UPPERCASE SHELL
27 80
$ whoami bandit33
$ cat /etc/bandit_pass/bandit33 
***pass***
$
```
{% endcode %}
