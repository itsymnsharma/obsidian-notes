
- Devices connected to each other is called a network
- Min of 2 devices connected
- once connected, they can talk to each other and share thing
- but they need to follow some rules for that, which are called protocols



before a ccompany connected their deviecs using wires to send data ro each other called arpanet (its an intranet)
later another company made something similar lets say abp

what if this two companies need to talk to each other, lets say one knows french other neglish
they should have common language for communication or sending info

that is then tcp/ip came a protocol governing transmission of data/information
like for mails now we have smtp
file transfer we have ftp
web pages http
? internet vs intranet


https://www.submarinecablemap.com/

? what is fiber optic cables

? since sound is waves and turns to elec and send, how voice stays same


DNS
--

just like homes have address to recieve parcels
even computers had thier addresses to unqiuely idenitfy them to get thier data
firstly computer had numbers like our phonenumbers but it got sophisticated later on and became like 192.168.2.1

? do we have any ip address like 0.0.0.0 or phonenumber that are all 0s

like how we have phone numbers and in old times we used to maintain a diary of phone numbers of friends and relatives
? how  a sim stores numbers

similarly computers with numbers have to keep a diary to get to know the numbers of other computers
this file was called hosts.txt file
back then any new ip address who need to be added to the internet, has to have thier number registered in the hosts.txt file

? is this hosts file the same hosts file we have now that saves our loopback address

every computer in a network has to have the hosts file and using that used to dial up using terminal with telnet command

? what is telnet

elizabeth fienler added org connected with internet in hosts files as per the work like .com..gov and etc

but this was inefficent

someone suggested that we should have a computer that keeps this hosts file and we all remember that computer address only, that computer sole responsibility is to give address when asked for, This became as DOMAIN NAME SYSTEM

DNS is domain name system and not domain name server
DNSS is domian name system server

now anyone who wants to get something from ford.com has to go to DNSS, get the ip adress of ford.com and then use telent to access it

but they thought more and came with how if we just do telnet ford.com and behind the scenes the job of DNSS lookup happens


STORY OF WWW

with internet, people used to transfer files 
in a research file, there will be many words or terms and to know more about it, we have to go to that word file
like ->  this is called teleportation(see page no 14 for more info)
This is then used to be called as hypertext ie asking us to go to another file to get more info

there was a problem then that the doc for page no 14 might be in some other computer and we have to go ask and get it

so time berners less thought what if instead of just having see page no 14 for more info, what if there is a link that on click, gets us that file through the internet and we read it

so he developed HTML (hyper text markup langauge) where hypertext will be clickable text so that we can get more information abiut it and to open such documnets we need a software which he called as Browser and gave the browser name as www

https://info.cern.ch/

before hyper text, we need to mention the address of the file but now after clicking on the hypertext. we can reach the file easily

he made a protocol as well called HTTP which knows how using this protocol a file in my system (server) could go to a browser (client)
a browser on click of a hypertext or going to an ip address can ask for a documnet and through http protocol the server responds

at first it was only GET protocol, like can ask docs from server to browser, cant send from browser to server

then www became public

after html, css and js came






















