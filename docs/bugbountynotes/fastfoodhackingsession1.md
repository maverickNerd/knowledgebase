#### Check for page source
- Check for any variable in script which is blacnk, most probably they are filled with URL parameters, so try those in query parameters.  
- if some parameter is like "trackingid", and if it doesn't work, try other permutations of it like id, tid, tracking\_id  
- Use different user-agents like of iphone/android and see if there is any other parameter appear in the source code, use that in query parameter to check for XSS or injection.  

#### Check robots.txt page

### Got a login Page ??

- Try admin,admin or other default passwords.  
- if it works and you are logged in, try to access other pages like mentioned in robots.txt  

Try html tags in signup form:  
like : \<h2\>test  

If they filter tags(<>), then try \<h2

#### Check pagesource in settings page

if they are hiding some button using comment, uncomment, and capture the request by sending the request.

- Try removing tokens, anc check if they are vaidating tokens on server side.

#### When you login, usually after successfull login website redirected you to some page like home page, check if you can change this redirect.

- Check for page source for any JS, see if there is any redirect url code in it.

Try to capture login request and add redirect\_url parameter.

### Add to the query statement of login.php page, like ?r\_url=1&url=https://

### Check in github for the website for any keys

#### Just Try Things, if something you see in page source, thing about it, question yourself and try it. 
