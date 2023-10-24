# Level 8 → Level 9

### Level Goal

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Helpful Reading Material

* [Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)

### Solution:

{% code overflow="wrap" %}
```bash
$ sort file_name
used to sort the file in ascending order

$ uniq -c
counts the unique occurence of each line. Sorting is required prior else it wont work
```
{% endcode %}

{% code overflow="wrap" %}
```bash
bandit8@bandit:~$ sort data.txt | uniq -c 
10 08Jd2vmb6FjR4ZXPteGHhpJm8A000A5B
10 OdEKX1sDwYtc4vyjrKpGu30ecWBsDDa9
10 OYDTDPCLc585IaFu911ukE9QfD6Ykrlz
10 0zP9wfUcMKjZM2hiQUYR1nTfmaRdYSQE
10 11FFcDRW5ZXXmX7geZORYRwiJf j8B3Gh
10 1jZv2X102JypCBIgDNRwWQzS1CyhvByt
10 1MUdfR7bGGCpNfGEOXaIEdrA8hT2L8Tk
10 2fepTygKSkWHQJS2GrmGwjy136eXSWJe
10 3cTCUFe6MT11FDALOZ49cRByfq1MRIxJ
10 3PBOnB0h1WKb1K6MImHdvwQjItFcxfdF
10 30XFsSepZUIOznxndwnQNnxvbpcXG05c
10 47eFxPAuZ4t\WbT4P5ADs1tCOtwlr51V
10 4a0tDpqjXGIMOcyqirndla7J8S3jZZAy
10 4Fi1Ig3h4mDd\64v3gRPre3qNx26k0U
10 4u67BT7FonRZeibEb910|6pHcMtzq03H
10 6R258gRryXf9CBoGberTEgGJb8ykWYrV
10 7J5LX5IxjJ75DSStY7k9QXgY8Hcygxu
10 7rUrQcuUE8W3u7sHw6GqIw5KIm1vnvT0
10 8faonpI57h2Bc2yVSHJTKYwkGF1f25nm
10 8mUGsbsFDyMVhqsbCIu5VQdKyNS6B4yK
10 9b0fkcvfVG8CImKfqmzFFSxszfYoGje3
10 9rdQWtaWPaCwsiYUmcR7DZsTjIDzCIDk
10 9uChpaBSAkMtOSNBVJ1HAzRR5SQePFZe
10 a6SMGsFpTKq8UGdndarh86000hHccjbo
10 AWuhqidoTFNEaYmsX7njF8elfk6UTt8V
10 Bap5iwr9yiz7NNLdn2pRIBDuz jS4apt6
10 bbFQ44ZGHTUPiPEBvfADGWpwXzdhco23
10 cBuyMeLeT15bFQMj|zWIGHpbVwqQZkWQ
10 cmtlazWcnfmS07dz52EdwhfVXD5hm80x
10 DCEBVSEhDdFKdhuYgoK5615GOhkxkRbS
10 dMNfFWOt7tDLsN6 jM4t15q7sGdXIJLDO
1 EN632PLfYiZbn3PhVK3X0GSLNInNE00t
10 EoxGdakqWSJE03uzpJBLKabYEb5J458U
```
{% endcode %}

```bash
$ sort -n
sorts the data based on numeric interpretation of uniq -c
```

```bash
bandit8@bandit:~$ sort data.txt | uniq -c 1 sort -n
1 EN632PlfYiZbn3PhVK3X0GSINInNE00t
10 08Jd2vmb6F jR4ZXPteGHhpJm8A000A5B
10 OdEKX1sDwYtc4vyjrKpGu30ecWBsDDa9
10 OYDTDPCLc585IaFu911ukE9QfD6Ykrlz
10 0zP9wfUcMKjZM2hiQUYR1nTfmaRdYSQE
10 11FFCDRW5ZXXmX7geZORYRwiJfj8B3Gh
10 1jZv2X102JypCBIgDNRwWQzS1CyhvByt
10 1MUdfR7bGGCpNfGEOXaIEdrA8hT2L8Tk
10 2fepTygKSkWHQJS2GrmGwjy136eXSWJe
10 3cTCUFe6MT11FDALOZ49cRByfq1MR\xJ
10 3PB0nB0h1WKb1K6MImHdvwQjItFcxfdF
10 3QXFsSepZUIOznxndwnQNnxvbpcXG05c
10 47eFxPAuZ4tlWbT4P5ADs1tC0twlr51V
10 4a0tDpqjXGIMOcyqirndla7J8S3jZZAy
10 4Fi1Ig3hG4mDdl64v3gRPre3qNx26k0U
10 4u67BT7FonRZeibEb9i016pHcMtzq03H
```

```bash
$ head -n 1 
print 1st line from top
```

```bash
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq-c lsort -n | head -n 1
Level 1 EN632PlfYiZbn3PhVK3X0GSINInNE00t KqJU
bandit8@bandit:~$
Logout
Connection to bandit.labs.overthewire.org closed.
```
