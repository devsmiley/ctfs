# Level 19 → Level 20

### Level Goal

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit\_pass), after you have used the setuid binary.

### Helpful Reading Material

* [setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)

### Solution:

* The file has setuid bit set for owner
* When we execute the file, it allows us to execute it as another user using **id** command
* The result shows we can execute the command as bandit20 user
* Thus the executable is used to get the password for next level

```bash
bandit19@bandit:~$ 1s -1
total 16
-rwsr-x--- 1 bandit20 bandit19 14876 Apr 23 18:04
bandit20 - do
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
Example: /bandit20-do id bandit19@bandit:~$ •/bandit20-do id
uid=11019 (bandit19) gid=11019 (bandit19) euid=11020 (bandit20) groups=11019 (bandit19)
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
****pass*****
bandit19@bandit：~$
```







