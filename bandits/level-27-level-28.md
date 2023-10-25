# Level 27 → Level 28

### Level Goal

There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

### Commands you may need to solve this level

git

### Solution:

* Move to /tmp folder

<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

{% code overflow="wrap" %}
```bash
bandit27@bandit:/ tmp/tempo$ ls
repo
bandit27@bandit:/tmp/tempo$ 1s -1
total 4
drwxrwxr-x 3 bandit27 bandit27 4096 Sep 9 09:21 repo bandit27@bandit:/tmp/tempo$ cd repo/ bandit27@bandit:/tmp/tempo/repo$ 1s -1
total 4
9 09:21
-rw-rw-r-- 1 bandit27 bandit27 68 Sep 9 09:21 README
bandit27@bandit:/tmp/tempo/repo$ cat README
The password to the next level is: ****pass****
bandit27@bandit:/ tmp/tempo/repo$
```
{% endcode %}













