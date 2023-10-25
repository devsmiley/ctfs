# Level 28 → Level 29

### Level Goal

There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

### Commands you may need to solve this level

git

### Solution:

* The password is not displayed

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

* From git command, we can see git log provides the history of commits
* We can check if previous commits had the password in plain text

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

* 1st commit did not have pass

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

{% code overflow="wrap" %}
```bash
bandit28@bandit:/tmp/new_tempo/repo$ git checkout abcff758fa6343a0d002a1c0add1ad8c71b88534
Previous HEAD position was c0a8c3c initial commit of README.md
HEAD is now at abcff75 add missing data bandit28@bandit:/tmp/new_tempo/repo$ 1s
README.md
bandit28@bandit:/tmp/new_tempo/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.
## credentials
- username: bandit29
- password: ******pass*****
```
{% endcode %}





