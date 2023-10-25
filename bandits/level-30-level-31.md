# Level 30 → Level 31

### Level Goal

There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

### Commands you may need to solve this level

git

### Solution:

<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

* We try to list the tags associated and find one with “secret”

```bash
$ git show-ref --tags
used to show reference of tag with commits

$ git show tag_name
used to view the tag message
```

```bash
bandit30@bandit:/tmp/bandit30/repo$ git tag
secret
bandit30@bandit:/tmp/bandit30/repo$ git show-ref -- tags 831aac22341f0094046392a4f5d318483019 refs/tags/secret
bandit30@bandit:/tmp/bandit30/repo$
git show secret
****pass******
bandit30@bandit:/tmp/bandit30/repo$
```





