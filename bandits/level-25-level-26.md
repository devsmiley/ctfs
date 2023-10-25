# Level 25 → Level 26

### Level Goal

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

### Commands you may need to solve this level

ssh, cat, more, vi, ls, id, pwd

### Solution:

[https://david-varghese.medium.com/overthewire-bandit-level-25-level-26-35d375ef61e](https://david-varghese.medium.com/overthewire-bandit-level-25-level-26-35d375ef61e)

```bash
$ /etc/passwd
shows the details of users
```

* Contents of /etc/passwd file for bandit26 user

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

* ssh key is found in home dir for bandit26 user

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

* But on ssh, we exit the connection. This is because our default shell is not /bin/bash but the one mentioned in /etc/passwd file.
* Here the content of file text.txt is small which is not fitting with more command, and exit 0 after exits us from the ssh connection

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

* To resolve, we try to shrink the size of our terminal and try ssh command again
* Now we can see more 66%. **More command** goes in interactive mode is amount of content to be displayed is more than size of terminal

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

* If we click “v” while in interactive mode, current line will be opened in vim editor

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

```bash
$ set shell=/bin/bash
used to change to the desired shell

$ shell
used to set and invoke into that shell
```

<figure><img src="../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

* As we can see, we are logged in as bandit26 user. Extract password from /etc/bandit\_pass folder for bandit26 user

```bash
bandit26@bandit:~$ cat /etc/bandit_pass/bandit26
*******pass*******
bandit26@bandit:~$
```
