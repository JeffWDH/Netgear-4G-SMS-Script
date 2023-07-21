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

Examples:
````
jeff@server:~$ ./netgearsms 192.168.5.1 password 0000000000 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusm
Message sent.

Resulting message:
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusm

jeff@server:~$ ./netgearsms 192.168.5.1 password 0000000000 Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Message sent.

Resulting messages:
[1]Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiu
[2]smod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
[3] minim veniam, quis nostrud exercitation ullamco laboris nisi ut al
[4]iquip ex ea commodo consequat. Duis aute irure dolor in reprehender
[5]it in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
````
