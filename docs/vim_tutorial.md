#### USing Assetfinder to get subdomains

\# assetfinder --subs-only uber.com > domains

#### Know which are running webservers, it checks which are having http and https server listening
 
\# cat domains | httpprobe | tee hosts                      /\* Use "tee -a" to append \*/

#### Using meg

\# meg -d 1000 -c 10 /

Above command will make an output direcotry called "out" and inside it, it will make individual directory for each subdomain.
Each subdomain directory will contain a file for both http and https request.

You also get a index.html file which will show the path with response code, so you can easily grep for 200 status code and get accepted urls.

\# grep -Hnri uber internal * | vim -

you can save this result in a file ":w results" 

### Running commands in the vim

- :%!sort -u                     (% means current file, ! to run shell command)

- :%grep -v Content-Secu

### awk - text processing command

:%!awk -F';' ;{print $3}'                       /\* -F = Field Separator, '{print $X}' = print X field \*/

Ctrl+v/right click       to put vim in visual mode and then you can use arrow keys to do vertical/horizontal selection and then hit 'X' to delete them

Shift+a  to go to the end of the line
and delete a single item and then press dot(.) and vim will repeat the last thing(instruction)

:/\.$                        (\ -> don't treat as an expression, $= End of the line)

### Search and replace

:%s/\<search\_item\>/\<replace\>

:%s///                         (// -> it search for whatever you last searched for)

### xargs

xargs takes multiple lines of input and runs a command on every line of it.

:%!xargs -n1 -I{} sh -c 'echo {} | base64 -d'                           (n1 -> give 1 input at a time, -I{} is a placeholder of input, sh -c -> to pass the command to shell )

### html-tool from tomnomnom

\# find . -type f | html-tool attribs src                   (this will give all of the src attributes from all of the files)

\# find . -type f | html-tool tags title | vim -          ( give the title tag from all of the files)

:tabnew | read !grep -HNR 'self'                      (grep for whatever under the cursor and then open the result in a new buffer in a new tab so it shows up at a few places then ctrl+w+g+shift+f and this will take me straight to the line where that title exists.

### gf

gf urls | grep yahoo.com | vi -                   (finds every url)

### unfurl from tomnomnom                     (its a great tool to make wordlist using keys and values for fuzzing)

:%!unfurl -u paths                         (gives the uniques paths from all the urls)

:%!unfurl -u keys                          (to get query strings)

param miner extension - finds hidden parameters, above will be a good wordlist




