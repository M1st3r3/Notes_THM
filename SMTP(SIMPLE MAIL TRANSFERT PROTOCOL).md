Default port 25

3 basic functions:
-  It verifies who is sending emails through the SMTP server.
-  It sends the outgoing mail
-  If the outgoing mail can't be delivered it sends the message back to the sender

---
**Steps of Sending**
1. The **Mail User Agent** (your email client or an external program) connects to the SMTP server of your domain (e.g., smtp.google.com) over the SMTP port (usually 25), initiating the SMTP handshake. Once validated, the SMTP session begins.

2. The client submits the sender's and recipient's email addresses, along with the email body and any attachments, to the server.

3. The SMTP server checks if the domain names of the recipient and sender match.

4. The sender's SMTP server establishes a connection with the recipient's SMTP server and relays the email. If the recipient's server is inaccessible, the email goes into an SMTP queue.

5. The recipient's SMTP server verifies the incoming email by checking the domain and user name. It then forwards the email to the POP or IMAP server.

6. The email appears in the recipient's inbox.
---
Exploit
List the Domain with metasploit : module : smtp_version
List the users with metasploit : module : smtp_enum
