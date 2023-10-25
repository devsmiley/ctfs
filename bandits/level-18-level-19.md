# Level 18 → Level 19

### Level Goal

The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

### Commands you may need to solve this level

ssh, ls, cat

### Solution:

* Due to changes in startup file, we use the default path for shell to login for next level

```bash
$ ssh -t /bin/sh
used for forced pseudo terminal execution
```

{% code overflow="wrap" %}
```bash
$ ssh p 2220 -t bandit18@bandit.labs.overthewire.org /bin/sh

This is an OverTheWire game server.
More information on http://www.overthewire.org/wargames
bandit18@bandit.labs.overthewire.org's password:
$ pwd
/home/bandit18
$ 1s -la 
total 24
drwxr-xr-x 2  root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r--r-- 1  root     root     220  Jan 6 2022 .bash_logout
-rw-r----- 1  bandit19 bandit18 2794 Apr 23 18:04 .bashrc
-rw-r--r-- 1  root     root     807  Jan 6 2022  .profile
-rw-r----- 1  bandit19 bandit18 33   Apr 23 18:04 readme
$ cat readme
*****pass*******
```
{% endcode %}

