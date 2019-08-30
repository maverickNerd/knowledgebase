# Recon Session 1 on Yahoo

### Check for In-Scope and Out-of -Scope items on Hackerone.com

#### Search on *crt.sh*    ---> %.yahoo.com  
  --> you can put % wildcard anywhere in search like %api.yahoo.com  
  --> %internal%.yahoo.com  
 
#### Search on *certspotter*   ---> yahoo.com  

- Check the github code in *recon_profile* repo of nahamsec for cerspotter bash 1 line command, you can set it in your .bash_profile and then run it just by  calling function name    

\# certspotter yahoo.com                --> output of this will not give all the subdomains of yahoo  

#### Check for first level subdomain example:  

ops.yahoo.com  --> juicy + potentiall internal
ne1.yahoo.com  --> corporate/internal domain
xobni.yahoo.com --> next potential internal

**Do These First**

corp.yahoo.com  
bf1.yahoo.com  
urs.yahoo.com  
adx.yahoo.com  

**Do later**

gq1.yahoo.com  
ir2/yahoo.com  
sg3.yahoo.com  
tp2.yahoo.com  
udb.yahoo.com  --> api enpoints  
payment.yahoo.com ---> associated with internalapi
* these are all interesting as these belong to corporate domains.  

#### Check for how many subdomains are alive/online ?

``` certspotter corp.yahoo.com | httprobe ```  

* httprobe os from tomnonnon github


#### Make directory for target and all subdomains and all alive domains:  
\# mkdir yahoo.com  
\# cd yahoo.com  
\# touch all.txt  
\# touch alive.txt  

* We are picking up api endpoints because these give really cool interesting stuff, internals and corporate because it is internal to yahoo and we want to know if we have access to it from outside.



\# certspotter yahoo.com | grep dev | httprobe  

\# certspotter assistant.yahoo.com | grep dev | httprobe  

open a page from here on browser to check the response   

Note: Error 404 does not mean that we don't have anything there  

##### You can have a simple for loop to run other commands

example:  
for i in `certspotter assistant.yahoo.com  
| httprobe`; do curl $i/phpinfo.php; done

* Template  

for i in `certspotter assistant.yahoo.com
| httprobe`; do <command> ; done

\# crtsh ops.yahoo.com >> all.txt  

\# crtsh corp.yahoo.com >> all.txt

* Process is to able to find interesting things and how infrastructure of a website is built.

* Check for xobni in cr.sh like %xobni%.yahoo.com

\# crtsh xobni.yahoo.com >> all.txt


\# nano ~/.bash_profile

```
getcount(){  
cat all.txt | wc -l  
}  
```

\# source ~/.bash_profile

\# cat all.txt | httprobe



* Put some more wildcard in crt.sh website   ----> %25.%25.%25.%25.%25.yahoo.com

Got some interesting subdomains:    
splunk.yahoo.com  
test-paranoids.yahoo.com  
manhattan.tp2.yahoo.com  

\# crtsh test-paranoids.yahoo.com | httprobe          ----> gave no result, so offline for us and of no use  

\# crtsh bf1.yahoo.com | wc -l   --> 509  

\# crtsh bf1.yahoo.com 

#### Check on crt.sh website for %.bf1.yahoo.com  
     corp.bf1.yahoo.com   
     mail.bf1.yahoo.com  
     infra.bf1.yahoo.com  
     vip.bf1.yahoo.com  
     openstack.bf1.yahoo.com  
     cs.bf1.yahoo.com  
     flurry.bf1.yahoo.com  
     prod.bf1.yahoo.com
     azurite.bf1.yahoo.com  
     omega.bf1.yahoo.com  
**ideas**

%uat%  
run a curl on *adx.bf1.yahoo.com/pguix*

Google Dorks
-----------
site:bf1.yahoo.com -flickr -omega -adx  
"bf1.yahoo.com" github.com  


\# vi bf1          --> dump all bf1 subdomains here  

```
for i in `cmd`; do  
   crtsh $i  
; done  
```  
 
* Run crtsh on all the above bf1 domain

Get some more interesting domains.

 iextract.bf1.yahoo.com    
 diy.bf1.yahoo.com   
 manhatan.bf1.yahoo.com  
 netops.ne1.yahoo.com  
 hk.%.yahoo.com  
 advertising.yahoo.com  
 creative.yahoo.com  


##### Check for Some interesting subdomains containing these keywords

admin    
jenkins  
stage  
test  
dev  
devops  
staff  
db  
qa  
internal  

###### Now find all the alive domains  

\# cat all.txt | httprobe >> alive.txt  


###### Check http probe on all ports except port 80 and 443  

\# cat all.txt | httprove -s -p https:8443  

### Take Screenshots now    
#### Install phantomJS
\# python webscreenshot.py \<input\_dir\> -o \<out\_dir\> -w 20 -m -a  "X-FORWARDED-FOR:127.0.0.1"


```bash
for I in $(ls); do  
    echo "$I" >>index.html  
    echo "<img src=$I><br>" >> index.html;  
done  
```

```
for I in $(cat alive.txt); do  
    python3 dirsearch ... -u https://$I  
done  
```

### Learning:

##### Learn the process of recon, every one has or can use their own tool, don't adopt tools, think about the process that you can take during your recon.


