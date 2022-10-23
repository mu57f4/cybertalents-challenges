### Challenge Description:
- Do not Start a fight you can not stop it

### Methodology
 - The page was a normal login page the first thing I did I took a look at the source code and I found username and password for Guest account and after loged in using this credentials the page said access denied so you should be loged in with admin account to access the flag.
 - Using FireFox add-on Cookie-Editor I checked the cookies and found a cookie named authentication with base64 encoded value, Decode it and I says `login=Guest` so I change it to `login=administrator`, Submited the new cookie and got the flag :)