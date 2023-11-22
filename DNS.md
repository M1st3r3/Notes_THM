Default port 53 (TCP/UDP)
![[Pasted image 20231107001929.png]]

#### Top-Level Domain (TLD)
- The TLD is the rightmost part of a domain name, such as ".com" in "tryhackme.com."
- Two types of TLDs: gTLD (Generic Top-Level Domain) and ccTLD (Country Code Top-Level Domain).
- Historically, gTLDs indicated the domain's purpose (e.g., .com for commercial, .org for organizations, .edu for education, .gov for government).
- ccTLDs were used for geographical purposes (e.g., .ca for Canada, .co.uk for the United Kingdom).
- The demand has led to the creation of numerous new gTLDs like .online, .club, .website, and .biz.

#### Second-Level Domain
- In a domain like "tryhackme.com," the ".com" portion is the TLD, and "tryhackme" is the Second-Level Domain.
- Second-Level Domains are limited to 63 characters, plus the TLD.
- They can only use lowercase letters (a-z), numbers (0-9), and hyphens (cannot start or end with hyphens or have consecutive hyphens).

#### Subdomain
- A subdomain is situated to the left of the Second-Level Domain and is separated by a period.
- For example, in "admin.tryhackme.com," "admin" is the subdomain.
- Subdomain names follow the same creation rules as Second-Level Domains: limited to 63 characters, using a-z, 0-9, and hyphens (with the same hyphen restrictions).
- Multiple subdomains can be used, creating longer names (e.g., "jupiter.servers.tryhackme.com").
- The total length should not exceed 253 characters.
- There is no set limit to the number of subdomains that can be created for a domain name.

## Record Types

DNS (Domain Name System) includes various record types that serve different purposes in mapping domain names to IP addresses and providing other domain-related information. Here are some common DNS record types:

#### A Record
- Resolves to an IPv4 address.
#### AAAA Record
- Resolves to an IPv6 address.
#### CNAME Record
- Resolves to another domain name. 
#### MX Record
- Resolves to the addresses of servers responsible for handling email for the queried domain.
- Includes a priority flag, indicating the order in which email servers should be used.
- Useful for routing email to backup servers if the primary server is unavailable.
- Example: "alt1.aspmx.l.google.com" is an MX record for "tryhackme.com."

#### TXT Record
- TXT records store free-text data and have various use cases:
- Listing authorized email servers for the domain, aiding in spam prevention and preventing email spoofing.
 - Domain ownership verification when signing up for third-party services.
- TXT records are versatile and can contain any text-based information.


## DNS Resolution Process
![[Pasted image 20231107002813.png]]
1. **Local Cache Check**
2. **Recursive DNS Server**
3. **Local Cache Hit**
4. **Root DNS Servers**
5. **TLD Server**
6. **Authoritative DNS Server**
7. **Caching**

## Example of DNS Request

**A Record**  - nslookup --type=A website.thm
**AAAA Record** - nslookup --type=AAAA website.thm
**Cname Record**  - nslookup --type=CNAME website.thm
**MX Record**  - nslookup --type=MX website.thm
**TXT Record**  - nslookup --type=TXT website.thm

