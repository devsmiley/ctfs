# Level 23 → Level 24

### Level Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

### Commands you may need to solve this level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

### Solution:

* The shell script mentions the execution and deletion of all files in the path, if files does not belong to current dir (.) or parent directory (..) and owner is bandit23, file will be deleted after 60 s

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* For this, we know passwords are stored in /etc/bandit\_pass/bandit24 folder for user bandit24, we create a bash script for copying the password to temp file password in /tmp.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

* Copy the file to the desired path and wait for cron to execute.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

* Cat the file and password is copied in password file

```
bandit23@bandit:/tmp$ cat password
*****pass******
bandit23@bandit: / tmp$
```
