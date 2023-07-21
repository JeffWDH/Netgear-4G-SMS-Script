# Netgear-4G-SMS-Script
A Bash script used to send SMS messages via Netgear 4G / LTE modems. 

Tested on a Netgear LB1120.  
Firmware Version: M18Q2_v12.09.163431  
App Version: NTG9X07C_12.09.05.30  
Web App Version: LBHDATA_03.03.103.176  

Requires bash and curl.

Tested with curl 7.68.0 and bash 5.0.17.

Usage:
````
netgearsms <hostname> <password> <phonenumber> <message>
````

The maximum message length for these modems is 70 characters. If the message provided is more than 70 characters (and less then 335), it will be split and sent in a maximum of 5 separate SMS messages. 
