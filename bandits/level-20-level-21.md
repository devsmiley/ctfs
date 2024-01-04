# Level 20 → Level 21

### Level Goal

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

### Commands you may need to solve this level

ssh, nc, cat, bash, screen, tmux, Unix ‘job control’ (bg, fg, jobs, &, CTRL-Z, …)

### Solution:

* Setup a listener to one of the ports, as no ip is mentioned, it will consider **localhost**

```bash
$ nc -nlvp port_number
n = numeric only
l = listen
v = verbose
p = port no
```

<figure><img src="../.gitbook/assets/image (22) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Connect to the same port using executable file
* Enter the password for this level on listener side

{% code overflow="wrap" %}
```bash
bandit20@bandit：~$ 1s-1
total 16
-rwsr-x--- 1 bandit21 bandit20 15600 Apr 23 18:04 suconnect
bandit20@bandit:~$ file suconnect
suconnect: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, int erpreter /lib/ld-linux.so.2, BuildID|shal]=67d1a01f06a6ae6a42184cc8cf912967cecf72da, for GNU/Linux 3.2.0, not stripped 
bandit20@bandit:~$ •/suconnect 4343
Read: *****pass******
Password matches, sending next password 
bandit20@bandit:~$
```
{% endcode %}

