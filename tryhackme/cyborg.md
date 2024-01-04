# Cyborg

## Scan the machine, how many ports are open?

### **Solution =>** 2

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## What service is running on port 22?

### Solution => ssh

## What service is running on port 80?

### Solution => http

## What is the user.txt flag?

### Solution => flag{1\_hop3\_y0u\_ke3p\_th3\_arch1v3s\_saf3}

#### Gobuster Scan:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* Let us navigate to /admin route

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

* Under Archive Menu, on clicking Download option, an archive file is downloaded
* For decompressing, use **tar** command

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

* A home folder is created with multiple files in it

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

* On reading the contents of **README** file

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

* Ok, so the backup is prepared using Borg Backup
* With a quick research on Google, Borg Backup is a type of backup software for compression.
* On visiting official website ([https://borgbackup.readthedocs.io/en/stable/index.html](https://borgbackup.readthedocs.io/en/stable/index.html)), an example was provided for extracting the backup

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

* Download `borg-linux64` and run `./borg-linux64`
* Let us go back to /admin route to see if we can find information on the archive. Here under Admins menu, we find a note

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

* Interesting, so the archive name is **music\_archive.** From the examples provided for extracting, we will use below command

`borg extract /path/to/repo::my-files`

* Instead of `my-files` we use `music_archive`
* On entering the command, it asks for a passphrase which is not with us at the moment.
* Lets try /etc path found in gobuster scan
* It has squid folder with below contents

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### passwd file:

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

* Value seems to be a hash. We can use **`hash-identifier`** for determining its type

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

* Let us save above hash in a file `hash.txt`
* For cracking above hash, we will be using `hashcat`

#### Syntax:

`hashcat -m hash_type -a attack_mode hash_to_crack wordlist`

* Let us figure out the `hash_type` for MD5(APR) using `grep` command

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

* So in our case, `hash_type` = 1600 and `attack_mode` = 0 (dictionary attack)

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

* We have obtained the hash value = `squidward`
* Let us open the another file found in /etc/squid path

### squid.conf

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

* Now that we have a passphrase, let us extract the files from archive
* Post extraction, folder named `home` is added

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

* On navigating the folder, we find Documents sub folder with note and credentials for user `alex`

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* As ssh port is enabled (from nmap scan), we can use above credentials to login

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

* We are logged in as alex. On listing the folder contents, file user.txt is present with flag

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

## What is the root.txt flag?

### Solution => flag{Than5s\_f0r\_play1ng\_H0p£\_y0u\_enJ053d}

* Let us check our permissions with `sudo -l` command

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* As seen, we can run backup.sh file with sudo privileges
* Let us read the file

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

* It takes certain backup files, moves to destination folder further archiving it and finally prints the command entered while executing the `backup.sh` file&#x20;
* Let us execute the script with CLI of `echo hello.` We can see that `Hello` is printed at the bottom

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

* Now let us pass the `cat /root/root.txt` for its contents thus obtaining the root flag![](<../.gitbook/assets/image (21).png>)
