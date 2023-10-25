# Level 12 → Level 13

### Level Goal

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

### Helpful Reading Material

* [Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex\_dump)

### Solution:

* Copy the data.txt file in the /tmp/myname directory

```bash
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ file data.txt
data.txt: ASCIIs text
bandit12@bandit: ~$ cp data.txt /tmp/myname/test.txt
bandit12@bandit: ~$ cd /tmp/myname
bandit12@bandit:/tmp/myname$ ls
data.txt test.txt testing
bandit12@bandit:/tmp/myname$ rm testing
bandit12@bandit:/tmp/myname$ ls
data.txt test.txt
bandit12@bandit:/tmp/myname$
```

* The file is hexdump with multiple compressions performed on it
* To revert hexdump of file

```bash
$ xxd -r file_name output_file
```

```bash
bandit12@bandit:/tmp/myname$ ls
test. txt
b1CNQOXTcYZWU6\gzi
bandit12@bandit:/tmp/myname$ xxd -r test.txt compressed
bandit12@bandit:/tmp/myname$ ls
compressed test.txt
bandit12@bandit:/tmp/myname$ file compressed
compressed: gzip compressed data, was "data2.bin", last modified: Sun Apr 23 18:04:23 2
023, max compression, from Unix, original size modulo 2^32 581
```

* gzip compression is used on the file. To decompress, rename the file using .gz extension

```bash
$ gunzip file_name

gunzip = short for gzip -d
```

```bash
bandit12@bandit:/tmp/myname$ mv compressed compressed_file.gz
bandit12@bandit:/tmp/myname$ ls
compressed_file.gz   test.txt
bandit12@bandit:/tmp/myname$ gunzip compressed_file.gz
bandit12@bandit:/tmp/myname$ ls
compressed_file test.txt
bandit12@bandit:/tmp/myname$ file compressed_file
compressed_file: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/myname$
```

* bzip2 compression is used on the file.

```bash
$ bunzip2 file_name

bunzip = short for bzip2 -d
```

{% code overflow="wrap" %}
```bash
bandit12@bandit:/tmp/myname$ bunzip2 compressed_file
bunzip2: Can't guess original name for compressed_file - using compressed_file.out 
bandit12@bandit:/tmp/myname$ ls 
compressed_file.out test.txt
bandit12@bandit:/tmp/myname$ file compressed_file.out
compressed__file.out: gzip compressed data, was "data4.bin", last modified: Sun Apr 23 1 8:04:23 2023, max compression, from Unix, original size modulo 2^32 20480 bandit12@bandit:/tmp/myname$ mv compressed_file.out compressed_file.gz bandit12@bandit:/tmp/myname$ ls compressed_file.gz test. txt
bandit12@bandit:/tmp/myname$ gunzip compressed_file.gz
bandit12@bandit:/tmp/myname$ ls compressed_file test.txt
bandit12@bandit:/tmp/myname$ file compressed_file compressed_file: POSIX tar archive (GNU)
bandit12@bandit:/tmp/myname$
```
{% endcode %}

* File is now a tar archive.

```bash
$ tar -xf file_name

x = used to indicate extraction of data
f = for filename
```

* After multiple decompressions, we finally get the plain text file with password for next level

{% code overflow="wrap" %}
```bash
bandit12@bandit:/tmp/myname$ tar -xf compressed_file bandit12@bandit:/tmp/myname$ ls 
compressed_file data5.bin  test.txt
bandit12@bandit:/tmp/myname$ file data5.bin 
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/myname$ tar -xf data5.bin bandit12@bandit:/tmp/myname$ ls
compressed_file data5.bin datab.bin test.txt bandit12@bandit:/tmp/myname$ file data6.bin
datab.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/myname$ bunzip2 data6.bin
bunzip2: Can't guess original name for datab.bin - using datab.bin.out 
bandit12@bandit:/tmp/myname$ ls
compressed_file data5.bin datab.bin.out test.txt bandit12@bandit:/tmp/myname$ file data6.bin.out data6.bin.out: POSIX tar archive (GNU)
bandit12@bandit:/tmp/myname$ tar -xf datab.bin.out bandit12@bandit:/tmp/myname$ ls
compressed_file data5.bin data.bin.out data8.bin test.txt bandit12@bandit:/tmp/myname$ file data8.bin
data8.bin: gzip compressed data, was "data.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 49 bandit12@bandit:/tmp/myname$ mv data8.bin data8.gz
bandit12@bandit:/tmp/myname$ gunzip data8.gz bandit12@bandit:/tmp/myname$ ls
compressed_file data5.bin datab.bin.out data8
test.txt
bandit12@bandit:/tmp/myname$ file data8 data8: ASCII text
bandit12@bandit:/tmp/myname$ cat data8
The password is ****pass******
bandit12@bandit:/tmp/myname$
```
{% endcode %}



















