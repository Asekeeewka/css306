# B part questions(10 points)
Another parts [part A](part2.md) [part C](part4.md)
 ## TOR browser: show your ip before and after using it
 ### Solution 1
 ```
 kali@kali:~$ curl 2ip.ru
 ```
 - Step2
 ```
 kali@kali:~$ proxychains curl 2ip.ru
 ```
 ### Solution 2
 1. Go to [2ip.ru](https://2ip.ru) from default browser
 2. Open **Tor Browser**
 3. Go to [2ip.ru](https://2ip.ru) from Tor Browser
 
 
 ## GoPhish: run and send something (Windows guide)
 1. Run Gophish
 2. Go to [https://127.0.0.1:3333](https://127.0.01.1:3333)
 3. Login (admin/gophish)
 4. Go to [sengrid](https://sendgrid.com)
 5. Register/Login
 6. Go to Email API -> SMTP relay
 7. Create API key
 8. Go to [Sending profiles in gophish](https://127.0.0.1:3333/sending_profiles)
 9. Press new profile
 10. Fill `Host = smtp.sendgrid.net` and `username = "your api key name"` and `password = "your api key"`
 11. Fill other parts and press `Send test email`
 
 
 ## Apache + modsecurity(bWAPP)
 1. Open sites-available folder(might be different for you)
 ```
 kali@kali:-$ cd /etc/apache2/sites-available
 ```
 2. Open `000-default.conf` file
 ```
 kali@kali:/etc/apache2/sites-available$ nano 000-default.conf
 ```
 3. Add `SecRuleEngine On` and (Optional step)
 ```
 SecRule ARGS:movie "@contains union" "id:1234,deny,status:403,msg:'Our test rule has triggered'"
 ```
 4. Run bWAPP 
 ```
 sudo service mysql start
 ``` 
 ```
 sudo service apache2 start
 ```
 5. Try using exploit 
 ```
 localhost/bWAPP/sqli_2.php?movie=-1+union+select+1,login,password,secret,email,6,7+from+bWAPP.users+order%20by%204+desc+&action=go
 ```
 
 ## Honeypot (ssh + wordpress)
 ### Honeypot ssh
 1. Start Honeypot
 ```
 python honeypot.py
 ```
 2. connect via ssh (default port 2222)
 ```
 ssh [your ip] -p 2222
 ```
 ### Honeypot wordpress
 1. start honeypot
 ```
 python wordpot.py
 ```
 2. connect via browser(default port 80)
 ```
 127.0.0.1:80
 ```
