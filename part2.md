# A part questions(7 points)
Another parts [part B](part3.md) [part C](part4.md)
 ## Find email addresses which belong to some organization
 ### Solution 1
 ```
 kali@kali:~$ theHarvester -d [domain name] -b [sources] -l [number of results]
 ```
 - Example
 ```
 kali@kali:~$ theHarvester -d sdu.edu.kz -b all -l 200
 ```
 ### Solution 2
 Go to [hunter.io](https://hunter.io) and search
 
 
## Show how to find google dork for "pages containing login"
1. Go to [Exploit database](https://exploit-db.com/google-hacking-database?)
2. Press Filters button (it's orange)
3. Select `Pages Containing Login Portals` in `Category` drop down menu
4. Run any exploit (no matter if it works) 
 
 
## Perform DOS attack on sdu.edu.kz
```
kali@kali:~$ python hulk.py https://sdu.edu.kz
```
## Wireshark: show any packet and analyze it
