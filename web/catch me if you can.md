### Challenge Description:
- I'm Just wanna Make Sure if you Are Mr.Robot

### Methodology:
 - the page is just a static web page so the first thing I took a look at the `robots.txt` file and found two files got my attention `S3cr3t.php` & `source.php` .
 - After requesting the two pages I found kind of authentication page in `S3cr3t.php` and in `source.php` a  PHP source code for the first one.
 - Started analyising the code in the source file, I found `S3cr3t.php` includes `flag.php` file and It sends a 'pass' post parameter but their was two filters
    - The fist one was the 'pass' value should contain 'R_4r3@' string.
    - The second one was regex for value of 'pass' parameter.
  if you passed the two filters the page will echo a '$cipher' variable and I tought it contain the flag.
 - I submited the 'R_4r3@' string as password, The response was 'ILLEGAL CHARACTERS', The problem was how to bypass the second filter ?!.
 - After googleing for the answer I found that I could bypass the regex a newline char '%0a', And using curl with the payload 'a%0aR_4r3@' as pass value the page printed 'Can You Read This For Me ?' with encoded value as brainfuck, Decoded the cipher and the got the flag.