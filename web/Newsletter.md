## Challenge Description:
- the administrator put the backup file in the same root folder as the application, help us download this backup by retrieving the backup file name

## Methodology:
 - The website is an email field with send button and after submitting the email is show up a message says that your email has been saved successfully.
 - After I read the challenge description I started with fuzzing the root directory to find the backup file, So I created a backup files wordlist and I fuzzed the website but got no positive results.
 - I tried to submit a random string, tested for SQLi and also XSS in email field but their was a filter .
 - So I looked at the page source code and the found that the application send the user email as `POST` request with a post parameter `email`.
 - In terminal I send a the `POST` request to the server with random string as a parameter value, The respone said the email shoud contain only [& @ .] characters.
 - The second time I sent a request with `email=sasa&hello@world.com` and found the first word was printed back in the response.
 - And after playing with the email parameter some time I verified that Its vulnerable to RCE with the command ```email=`whoami`&hello@world.com``` with backticks and the respons was www-data.
 - So to solve the challenge I listed the rood directory with `ls` command found the backup file and submited its name and BOOM the challenge was sovled :) .