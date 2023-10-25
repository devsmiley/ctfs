# Level 13 → Level 14

### Level Goal

The password for the next level is stored in **/etc/bandit\_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on

### Commands you may need to solve this level

ssh, telnet, nc, openssl, s\_client, nmap

### Helpful Reading Material

* [SSH/OpenSSH/Keys](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)

### Solution:

* ssh private key is provided in home directory of bandit13 user
* Connect using private key to bandit14 user as password file can be read by this user

{% code overflow="wrap" %}
```bash
bandit13@bandit:~$ 1s 
sshkey.private
bandit13@bandit:-$ ssh bandit14@localhost -i sshkey.private -p 2220
The authenticity of host ' [localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wURb4RrEcL£XC5CX1hmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes Could not create directory '/home/bandit13/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit13/.ssh/known_hosts).
This is an OverTheWire game server.
More information on http://www.overthewire.org/wargames
!!! You are trying to log into this SSH server with a password on port 2220 from localhost.
!!! Connecting from localhost is blocked to conserve resources.
!!! Please log out and log in again.
```
{% endcode %}

* cat the file for password and exit

{% code overflow="wrap" %}
```bash
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
****pass******
bandit14@bandit：~$ exit
logout
Connection to localhost closed.
bandit13@bandit:~$ exit
logout 
Connection to bandit.labs.overthewire.org closed.
```
{% endcode %}

Enter this password for next level
