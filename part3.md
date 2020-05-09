# B part questions(10 points)
Another parts [part A](part2.md) [part C](part4.md)
 ## TOR browser: show you ip before and after using it
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
 
 
 ## Apache + modsecurity
 
 
