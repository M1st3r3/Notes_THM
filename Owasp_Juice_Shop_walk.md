## All Flags i did

1 - Log into admin Account with SQLinjection  -> ['or 1=1 --] \n
2 - Same thing to connect into Bender Account
3 - Used Burpsuite with Intruder and best1050.txt wordlist to find admin password -> admin123
4 - Reset Jim password with OSINT question -> Samuel (Star Trek)
5 - Found that i can access ftp server when reading "boring terms of use"
6 - Found mc.safesearch account with his rap video
7 - Download package.json.bak from the ftp server with Poison Null Byte -> [ip_serv]/ftp/package.json.back%2500.md (%2500 is a null terminator) 
8 - Inspectt page -> Debugger -> Search for admin & found administration page -> [ip_serv]/#/administration
9 - When viewing my Basket if i change in Burpsuite GET /rest/basket/1 HTTP/1.1 to GET /rest/basket/2 HTTP/1.1 -> Access
10 - I can remove 5 star reviews from /administration
11 - DOM XSS in search bar -> <iframe src="javascript:alert(`xss`)"> 
12 - Persistent XSS if when loggout of admin account intercet the request and add <iframe src="javascript:alert(`xss`)"> in a new header called True-Client-Ip
13 - Reflected XSS when you track an order if you change the id field to <iframe src="javascript:alert(`xss`)">  it will works

 /#/score-board/  -> to see whats left
---
24 novembre 2024 

