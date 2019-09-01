-- Picking a target. It is tough to choose, but choose wisely.

* Poke a little bit on a target, find some low hanging fruit, understand the basic diffense the target is having.  
* Get the feel for things on target.  
* Do recon on the target, got subdomains now what??  

  -- it all depends now on the process that you want to follow or like:  
       * You might only go for interesting names of subdomains and try to get some files.  
       * You can find signup/registration adn login prompt subdomains and poke on these
       * Don't follow the complete process of others(hackers), make your own, take bit and pieces.

**Understand the target**

* Learn how the developers are thinking, learn how the website is working. If the dev is missing something at one place, chances are that there will be some other places where they are missing the same.

* Understand what they are trying to protect, what they are trying to achieve.

--> Never stop doing recon, websites are always bringing new code.


--> XSS, open URL redirect, CSRF, clickjacking are low hanging fruits. 

--> Most apps are vulnerable to IDOR.

* Don't spray wild payloads everywhere, understand whats going on, make POC according to that.

* Try to understand what the website is actually about.

* There are som many bug class, so try to set your focus on what you what you want to find at the endpoint or in a website.

* If you find the key, google the key/token, check if there is some talk around it.


* Come up with your won checklists when testing !  
Example: If you are abel to signup, you can interact, things to test for -stored xss, open redirect, can you upload photo, token leaks. Check what can you do?

* Look on burp, see interesting parameters.

* Example:  This applies to XSS, open redirect -
\<h2\>
\<h2
\<%00h2\>
\<%0dh2\>
\</h2/x\>

* Try to understand the filter, try to understand if their filter is vulnerable.

* Put beeceptor kind of url in referer and check if site reaches to you.

* Use spider to find endpoints and JS links.

* Read, Read and read ! Disclose reports, tutorials, writeups, Test for bypasses !

* Try Changing content-type

* Find the IP to bypass cloudfare.

* Found something in X-Forwarded-For or Cookie header which is exploting XSS, you can use cache poisoning, try it, it might work.

* How do you know if endpoint is vulnerable to SSRF?  
  --> check for parameters,  
if something is URL, or something that is looking as url ,even if the endpoint like "/endpoint", potentially making a request somewhere to something, if you put your URL there, your server ip, or you can even put open url redirect so for example there's a end point where it will take another endpoint and send a request to it internally and give you the contents and if you try to change it to external website it doesn't work and it can only be an endpoint.  
Now if you found a open URL redirect what about if you force the server to visit that does it follow the redirect, which might follow it to somehting internal which might follow you the response.

**Example of Session Managament Issue**

I had a website where I could only insert an image but link to my website, I bypassed their protection to link it to my website and on the login they were pretty secure I can go to my URL and find some endpoints  
and one of the enpoint was where my image was so after logging in I get to that endpoint where my image was and then that image page link to my URL in the images and in the referer was leaked the user's token.

* Use X-Forwarded-For with 127.0.0.1 or local IP when you do signup/login/password reset and see what happens.

* There is no time for recon to stop, you can go as long as you can.


