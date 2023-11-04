# Level 21 → Level 22

### Level Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

### Commands you may need to solve this level

cron, crontab, crontab(5) (use “man 5 crontab” to access this)

### Solution:

* For next level, we read the cronjob\_bandit22 file and find the user bandit22 is reboot and the data from /usr/…. file is redirected to /dev/null
* /usr/… file is a shell script where permission for another file is set to 644 which means all the users can read the file

<figure><img src="../.gitbook/assets/image (23) (1).png" alt=""><figcaption></figcaption></figure>
