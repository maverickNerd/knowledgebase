- vi tom\_tools  
- put some tools inside the above file
- cat tom\_tools| xargs -n1 -I{} go get github.com/tomnomnom/{}

- echo$?         -- for checking the last command return value

### Using Assetfinder
\# assetfinder --subs-only sports.yahoo.com | tee -a domain

###HttProbe
\#cat domain | httprobe -c 50 | tee -a hosts


### meg

\# meg -v /                       /*in same direcotory as hosts file*/

cd out/

grep -Hnri aws_

grep -Hnri secret

find . type f | html-tool tags title

find . type f | html-tool attribs src

### vimprev script

#!/bin/bash
VIMENV=prev vim $@

### vimrc

\#vi ~/.vimrc

if $VIMENV == 'talk'
  set background=light
  let g:solarized_termcolors=256
  colo solarized
  noremap \<Space\> :n\<CR\>
  noremap \<Backspace\> :N\<CR\>
else
   " Trans background
   hi Normal ctermbg=none
   hi NonText ctermg=none
endif


if $VIMENV == 'prev'
  noremap \<Space\> :n\<CR\>
  noremap \<Backspace\> :N\<CR\>
  set noswapfile
endif 

### Using above vimprev script

vimprev $(find . -type f) 

Now I can use "space" to move to next file and backspace to move to prev one.

- We often see many pages return "200 OK" but really they are not.

\# grep -Hnri '200 Ok' | grep -v ^index

\# grep -lru '200 OK' | grep -v ^index | xargs -n1 ls -la


\# grep -lru '200 OK' | grep -v ^index | xargs -n1 ls -la | sort -k5,5

Now above output will sort according to length so you can check for interesting length which 

\# find . -type f -exec cat {} \; | sort --version-sort -u | wc

\# find . -type f -exec cat {} \; | sort --version-sort -u | vim -

### Using tok

Break stream of inputs into words.

\# find . -type f -exec cat {} \; | tok | vim -

:%!sort -u --version-sort

to sort them unique

-> then you can grep any interesting word in the host folder to check easily where it belongs and check further from here.

### Deal with a very large file

- Sort the file first in vim
%!sort -u --version-sort


cat urls | urlinteresting | vim -


### To check for subdomain takeover

\# cat domains | while read domain; do host -t CNAME $domain; done | grep -i azure
