# Level 14→ Level 15

### Level Goal

The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

### Commands you may need to solve this level

ssh, telnet, nc, openssl, s\_client, nmap

### Helpful Reading Material

* [How the Internet works in 5 minutes (YouTube)](https://www.youtube.com/watch?v=7\_LPdttKXPc) (Not completely accurate, but good enough for beginners)
* [IP Addresses](http://computer.howstuffworks.com/web-server5.htm)
* [IP Address on Wikipedia](https://en.wikipedia.org/wiki/IP\_address)
* [Localhost on Wikipedia](https://en.wikipedia.org/wiki/Localhost)
* [Ports](http://computer.howstuffworks.com/web-server8.htm)
* [Port (computer networking) on Wikipedia](https://en.wikipedia.org/wiki/Port\_\(computer\_networking\))

### Solution:

* To connect to port, use netcat (nc) command with host name **localhost**

```bash
bandit14@bandit:~$ nc localhost 30000
****previous pass******
Correct!
****pass******
bandit14@bandit:~$ exit
logout
Tast, versatile, remote (and Local) Tile-copying to
Connection to bandit.labs.overthewire.org closed.
```











