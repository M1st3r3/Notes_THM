FUNCTIONALITY
- **Proxy:** The most well-known aspect of Burp Suite, the Burp Proxy allows us to intercept and modify requests/responses when interacting with web applications.
- **Repeater:** The second most well-known Burp feature -- [Repeater](https://tryhackme.com/room/burpsuiterepeater) -- allows us to capture, modify, then resend the same request numerous times. This feature can be absolutely invaluable, especially when we need to craft a payload through trial and error (e.g. in an SQLi -- **S**tructured **Q**uery **L**anguage **I**njection) or when testing the functionality of an endpoint for flaws.
- **Intruder:** Although harshly rate-limited in Burp Community, [Intruder](https://tryhackme.com/room/burpsuiteintruder) allows us to spray an endpoint with requests. This is often used for bruteforce attacks or to fuzz endpoints.
- **Decoder:** Though less-used than the previously mentioned features, [Decoder](https://tryhackme.com/room/burpsuiteom) still provides a valuable service when transforming data -- either in terms of decoding captured information, or encoding a payload prior to sending it to the target. Whilst there are other services available to do the same job, doing this directly within Burp Suite can be very efficient.  
- **Comparer:** As the name suggests, [Comparer](https://tryhackme.com/room/burpsuiteom) allows us to compare two pieces of data at either word or byte level. Again, this is not something that is unique to Burp Suite, but being able to send (potentially very large) pieces of data directly into a comparison tool with a single keyboard shortcut can speed things up considerably.  
- **Sequencer:** We usually use [Sequencer](https://tryhackme.com/room/burpsuiteom) when assessing the randomness of tokens such as session cookie values or other supposedly random generated data. If the algorithm is not generating secure random values, then this could open up some devastating avenues for attack

![The four quadrants of the burp dashboard labelled in anti-clockwise order, starting from the top left.](https://tryhackme-images.s3.amazonaws.com/user-uploads/5d9e176315f8850e719252ed/room-content/11202e4c73faa30a757f1439b63b85c6.png)  
1. The Tasks menu allows us to define background tasks that Burp Suite will run whilst we use the application. The Pro version would also allow us to create on-demand scans. The default "Live Passive Crawl" (which automatically logs the pages we visit) will be more than suitable for our uses in this module.
2. The Event log tells us what Burp Suite is doing (e.g. starting the Proxy), as well as information about any connections that we are making through Burp.
3. The Issue Activity section is exclusive to Burp Pro. It won't give us anything using Burp Community, but in Burp Professional it would list all of the vulnerabilities found by the automated scanner. These would be ranked by severity and filterable by how sure Burp is that the component is vulnerable.
4. The Advisory section gives more information about the vulnerabilities found, as well as references and suggested remediations. These could then be exported into a report.

|   |   |
|---|---|
|**Shortcut**|**Does**|
|`Ctrl + Shift + D`|Switch to the Dashboard|
|`Ctrl + Shift + T`|Switch to the Target tab|
|`Ctrl + Shift + P   `|Switch to the Proxy tab|
|`Ctrl + Shift + I   `|Switch to the Intruder tab|
|`Ctrl + Shift + R   `|Switch to the Repeater tab|

---

### Proxy
##### Connect Burpsuite Proxy to FoxyProxy
![[Pasted image 20231114003108.png]]
Click Options
![[Pasted image 20231114003134.png]]
![[Pasted image 20231114003145.png]]

##### For Https get the certificate [[https://portswigger.net/burp/documentation/desktop/external-browser-config/certificate]]
![[Pasted image 20231114005235.png]]
![[Pasted image 20231114005241.png]]
![[fb2a8717ae887eda024a7791d83cefaf.gif]]


---

##### Scoping
Setting a scope for the project allows us to define what gets proxied and logged. We can restrict Burp Suite to _only_ target the web application(s) that we want to test. The easiest way to do this is by switching over to the "Target" tab, right-clicking our target from our list on the left, then choosing "Add To Scope". Burp will then ask us whether we want to stop logging anything which isn't in scope -- most of the time we want to choose "yes" here.
![[7e11c5dec4dba4336927aa7561e5c793.gif]]
![[Pasted image 20231114011757.png]]

---
