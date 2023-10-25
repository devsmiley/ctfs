# Level 22 → Level 23

### Level Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

### Commands you may need to solve this level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

### Solution:

* **whoami** command prints the username which will be bandit23
* In next echo, we replace $myname with bandit23 which returns the desired key

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>
