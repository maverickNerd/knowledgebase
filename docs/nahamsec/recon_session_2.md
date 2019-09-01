#### This Week's Topics:
- crt.sh  
- certspotter.com  
- Shodan  
- Censys.io  

All Subdomains and Data:  
https://github.com/nahamsec/SundayStr...  

Github:  
https://github.com/nahamsec  

Tools:  
JSParser: https://github.com/nahamsec/JSParser  
LazyRecon: https://github.com/nahamsec/LazyRecon  
Bash Aliases: https://github.com/nahamsec/recon\_pro...  
Webscreenshot: https://github.com/maaaaz/webscreenshot  
httprobe: https://github.com/tomnomnom/httprobe  
aquatone: https://github.com/michenriksen/aquatone 


---> anew from tomnomnom, append lines from stdin to a file, but only if they don't already appear in the file

\# cat things.txt
\# cat newthings.txt

\# cat newthings.txt | anew things.txt

##### Check meg tool also from tomnomnom

##### Get jq from here - https://stedolan.github.io/jq/      --> jq is like sed for JSON data - you can use it to slice and filter and map and transform structured data

```
for i in `cat target.txt`  
do  
    curl -s 'https://crt.sh/\?q\=\%25.$i\&output\=json' | jq -r '.[].name_value' | sed 's/\*\.//g' | sort -u |tee -a all.txt
done  

#### Censys 

Search for 443.https.tls.chain.parsed.names:yahoo.com

### ToDo:

ysm.yahoo.com  
bfv.yahoo.com  
cp.yahoo.com  
adspecs.yahoo.com  
yahoo-inc.com  
admanageplus.com  
tw.yahoo.com  
vpg.yahoo.com  
uad2.yahoo.com  
ah.yahoo.com  
abuse.yahoo.com  
sk1.yahoo.com  
sync.yahoo.com  
hk.%25.yahoo.com  
sports.yahoo.com  
sg3.yahoo.com  
sg3.yahoo.com  
yql.yahoo.com  

esports.yahoo.com  
api.fantasysports.yahoo.com  
mobile.yahoo.com  
data.yahoo.com  
sandbox.yahoo.com  
%answers%.yahoo.com  

geo.yahoo.com  
groups.yahoo.com  
gemini.yahoo.com
admanager.yahoo.com  


#### Country based Searches

%25.ect.yahoo.com  
%25.eds.yahoo.com  
%25.tw1.yahoo.com  
%25.bid.yahoo.com  
hk.%25.biling.yahoo.com  
hk.%25admin.yahoo.com  
hk.%25.deals.yahoo.com  
hk.%25.token.yahoo.com  
\%25.hk.\%25.yahoo.com  
hk.%25api.token.yahoo.com  
hk.%25.auctions.yahoo.com  
yw.%25.yahoo.com  
tw.%25.mall.yahoo.com  
hk.%25.store.auctions.yahoo.com  
tw.back  


#### ideas / future domains  
diy.bf1.yahoo.com  
yahooapis.com  
verizonmedia/oauth.com ?????  

txmblr.com  
t.umblr.com  
srvcs.tumblr.com  
makers.com  
builtbygirls.com  


--> Check in Certificated of Censys for yahoo.com

#### Gogle Search

site:yahoo.com ext:php -hk -tw -maktoob  


### Aquatone and gowitness for screenshot of websites

\# cat alive.txt | aquatone -chromepath \<chromium\_path\> -out \<out\_dir\> -threads 50

#### Search on shodan for ipv4 addresses of yahoo



### Aproach

Find Subdomains -> port scan -> screenshot -> ditbrute force -> Hack all the things
