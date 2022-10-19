### Challenge Description:
- simple search website we need to know which cookie to eat ;)

### Methodology:
 - The website is a simple search bar with some photos I put a random string and clicked the search button and the string got reflected back on the string so I decided to test for XSS.
 - When looking at the page source code I found that the some chars not sanitized at a `script` tag.
 - After tring to bypass the single quote found that It got doubled, So the solution to execute XSS alert was to break out of the `script` tag itself.
 - Using the payload `</script><script>alert(document.cookie)//` I could successfully execute the alert with cookie flag and solved the challenge :).