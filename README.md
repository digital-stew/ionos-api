# ionos-api
update your ionos dns using API


ionos api: replace {your info}
https://developer.hosting.ionos.co.uk/docs/dns

get required software:
sudo apt install python3-miniupnpc


get your domain id: 
curl -X GET "https://api.hosting.ionos.com/dns/v1/zones" -H "X-API-Key: {API KEY}"

get your zone id's you want to update: ["PTR","SRV","CAA","AAAA","SOA","MX","A","TXT","NS","CNAME","TLSA","SPFM","ALIAS","NAPTR"]

curl -X GET "https://api.hosting.ionos.com/dns/v1/zones/{DOMAIN ID}?suffix={DOMAIN eg. mysite.com}&recordType={WHAT ZONE? eg MX or A etc}" -H  "accept: application/json" -H "X-API-Key: {API KEY}"

update the script with your info and run as superuser. I use cron to run the script every 5 mins
