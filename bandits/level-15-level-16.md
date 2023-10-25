# Level 15 → Level 16

### Level Goal

The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign\_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

### Commands you may need to solve this level

ssh, telnet, nc, openssl, s\_client, nmap

### Helpful Reading Material

* [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Secure\_Socket\_Layer)
* [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)

### Solution:

* Using ncat command which is advanced version of nc

```bash
bandit15@bandit:~$ ncat localhost 30001 --ssl
****previous pass******
Correct!
****pass******
```
