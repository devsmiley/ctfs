# Pickle Rick

### What is the first ingredient that Rick needs?

**Solution =>** mr. meeseek hai

#### Nmap scan: 2 open ports

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

#### Nikto scan: /login.php

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

#### Gobuster scan: /index.html, /robots.txt

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

* Navigating to http://10.10.36.163/robots.txt, we find clear text data![](<../.gitbook/assets/image (11).png>)
* Navigating to http://10.10.36.163/, we find the user name

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

* Finally we go to http://10.10.36.163/login.php from Nikto scan and enter user name from source code and password from robots.txt file

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

* On trying to cat a file, error is displayed which says command disabled

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

* Tried less command and it worked. Also we got our 1st ingredient

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

### What is the second ingredient in Rick’s potion?

**Solution =>** 1 jerry tear

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

* Listing contents of current users home directory, displays two folders

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

* On listing rick directory contents, we find second ingredient

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

### What is the last and final ingredient?

**Solution =>** fleeb juice

* After users home directory, we check if we are root or have superuser privileges.

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

* Display contents of home directory for root user i.e. /root

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

* Here we go, 3rd ingredient

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
