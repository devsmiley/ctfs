# Level 26 → Level 27

### Level Goal

Good job getting a shell! Now hurry and grab the password for bandit27!

### Commands you may need to solve this level

ls

### Solution:

* The file has setuid bit set for owner
* When we execute the file, it allows us to execute it as another user using **id** command
* The result shows we can execute the command as bandit27 user
* Thus the executable is used to get the password for next level

<figure><img src="../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

```bash
bandit26@bandit:~$ •/bandit27-do id
uid=11026 (bandit26) gid=11026 (bandit26) euid=11027 (bandit27) groups=11026 (bandit26)
bandit26@bandit:~$./bandit27-do cat /etc/bandit_pass/bandit27
******pass********
bandit26@bandit:~$
```

