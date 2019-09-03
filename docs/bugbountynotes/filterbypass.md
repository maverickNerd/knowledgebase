### XSS Filter

- Are the basic " ' \< \> allowed? what if you try in different combinations ?

- Is "on[]=" filtered or jut the common 'onerror', 'oncommon' filtered? try other such as onload, onhover  
   --> put onxx=
   --- if this passes, that mean they are whitelisting few terms
   ->> remove = and try, sometimes dev people check for any statemement and they stop all statements.

- How do they handle unicode, double encoding, unusual encoding ?


**Note:** *When you find a XSS filter bypass, it's usually common throughout because developers copy the same code through out application.

Example:

1. if -> \<img%20src="x" onerror="alert(0)"\> encoded properly by developer try this:

     \<img%20src='data:'onerror='alert(0)\>

2. try sscriptrscriptiscriptpscripttscript if the developer is blocking script tag

3. the use of \/\/ will bypass the filter check for "//", and the use of \n will bypass their check for .com, .co.uk etc.

