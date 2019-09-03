### Authorize and Autorepeater burp plugins to find IDOR.

### Authorize

For each request you do, it will send a equal request with something changed..  
And this something is usually cookie of the session or any additional header.

Example:
User A will browse the webapp and we will use authorize to use cookies of user B automatically.

- Copy all the cookies if user 1, paste in authorize configuration

In interception filter, add filters:

Ignore spider request
Scope items only
URL Not Contains(regex): \.Js|css|png|jpg|jpeg|gif|woff|BMP|ICO$

Start Authorize

Browse Web using user1 and authorize will capture the request, and send the request again with modified cookies of user 2

Now you can click on each indiviual request to check modified response, if response is 403 forbidden that means user2 is not authorize to browse that webpage.

403 == Enforced == No Go

So go through the webapp, browsing everything, changing profile and saving adn authorize will show if it is enforced or not. if it is not, try reading the response to check if it is vulnerable or not.


### Autorepeater

Autorepeater is the buffed version of authorize.

So suppose you have user1, user2, org1, org2...

you have access to org1, but you want to check if you have access to org2, you can configure autorepeater with options of match and replace

Add a Replacement:

"Replace String" -> provide 1 org ID in Match and other org id in replace

You can set highlight filter also in autorepeater.

You can change content-length from application/json to application/xml in Request Header function of match and repleace.
