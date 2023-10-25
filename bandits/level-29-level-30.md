# Level 29 → Level 30

### Level Goal

There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

### Commands you may need to solve this level

git

### Solution:

* It says no passwords in production

<figure><img src="../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

* We list all the branches available and find dev branch

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

```bash
bandit29@bandit:/tmp/bandit29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.
## credentials
- username: bandit30
- password: ****pass********
```
