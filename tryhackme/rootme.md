# RootMe

### Reconnaissance:

#### 1. Scan the machine, how many ports are open?

**Solution =>** 2

```bash
$ nmap -T4 -p- ipadd
-T = to specify speed range (1 = low, 5 = highest)
-p- = scan all the ports
```

<figure><img src="../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

#### What version of Apache is running?

**Solution =>** Server: Apache/2.4.29 (Ubuntu)

```bash
$ nikto -h http://ipadd
used for scanning web vulnerability
```

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

#### What service is running on port 22?

**Solution =>** ssh

```bash
$ nmap -T4 -sV -p 22 ipadd
-sV = used to specify the service running on portsh
```

<figure><img src="../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

#### Find directories on the web server using the GoBuster tool.

**Solution =>**

```bash
$ gobuster dir -w wordlist_path -u http://ipadd
-w = specify word list path
-u = specify url

used to search for directories/path on server from common words
```

<figure><img src="../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

#### What is the hidden directory?

Ans = /panel
