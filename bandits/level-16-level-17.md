# Level 16 → Level 17

### Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

### Commands you may need to solve this level

ssh, telnet, nc, openssl, s\_client, nmap

### Helpful Reading Material

* [Port scanner on Wikipedia](https://en.wikipedia.org/wiki/Port\_scanner)

### Solution:

*   Use nmap to find open ports by scanning the ports specified

    ### **OR**
* Use netstat for finding open tcp ports

<figure><img src="../.gitbook/assets/image (17) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### &#x20;                                         OR

```bash
$ nmap -sV -T4
-sV = specifies the services running on port
-T4 = to increase the speed
```

<figure><img src="../.gitbook/assets/image (18) (1) (1).png" alt=""><figcaption></figcaption></figure>

* **31518 and 31790** ports are open from the range with SSL
* Use openssl s\_client for connecting to ports using SSL encryption. 31518 return the password back as service mentioned is ssl/echo. 31790 returns private key

<figure><img src="../.gitbook/assets/image (19) (1) (1).png" alt=""><figcaption></figcaption></figure>

```
- - -
read R BLOCK
***************
Correct!
-----BEGIN RSA PRIVATE KEY-~---
*****rsa private key***********
----END RSA PRIVATE KEY-~---
closed 
bandit16@bandit:~$
```

* Create a file for private key

<figure><img src="../.gitbook/assets/image (20) (1) (1).png" alt=""><figcaption></figcaption></figure>

* After changing the permission to 400 (owner = read, g, a = no perm), login using ssh to next level

<figure><img src="../.gitbook/assets/image (21) (1) (1).png" alt=""><figcaption></figcaption></figure>

