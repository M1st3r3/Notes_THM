---

---
---
## 1.Broken Access Control
**Defintion**: 
Broken access control allows attackers to bypass **authorisation**, allowing them to view sensitive data or perform tasks they aren't supposed to.

Insecure Direct Object Reference -> **IDOR** or **Insecure Direct Object Reference** refers to an access control vulnerability where you can access resources you wouldn't ordinarily be able to see. This occurs when the programmer exposes a Direct Object Reference, which is just an identifier that refers to specific objects within the server. By object, we could mean a file, a user, a bank account in a banking application, or anything really.

---
## 2.Cryptographic Failure
**Definition**:
A **cryptographic failure** refers to any vulnerability arising from the misuse (or lack of use) of cryptographic algorithms for protecting sensitive information. Web applications require cryptography to provide confidentiality for their users at many levels.

When we encrypt the network traffic between the client and server, we usually refer to this as **encrypting data in transit**.

When the server encrypt the data when storing it this is referred to as **encrypting data at rest**.

Common Example is when a database file is get accessed by an attacker & they can crack the password

---
## 3.Injection
**Definition**:
These flaws occur because the application interprets user-controlled input as commands or parameters. Injection attacks depend on what technologies are used and how these technologies interpret the input. Some common examples include: SQL Injection, Command Injection

Main Defense :
- **Using an allow list**
- **Stripping input**

----

## 4.Insecure Design
**Definition:**
Vulnerabilities which are inherent to the application's architecture. They are not vulnerabilities regarding bad implementations or configurations, but the idea behind the whole application (or a part of it) is flawed from the start. Most of the time, these vulnerabilities occur when an improper threat modelling is made during the planning phases of the application and propagate all the way up to your final app.

---

## 5.Security Misconfiguration
**Definition:**
Security Misconfigurations are distinct from the other Top 10 vulnerabilities because they occur when security could have been appropriately configured but was not. Even if you download the latest up-to-date software, poor configurations could make your installation vulnerable.

Security misconfigurations include:
- Poorly configured permissions on cloud services, like S3 buckets.
- Having unnecessary features enabled, like services, pages, accounts or privileges.
- Default accounts with unchanged passwords.
- Error messages that are overly detailed and allow attackers to find out more about the system.
- Not using [HTTP security headers](https://owasp.org/www-project-secure-headers/).

---

## 6.Vulnerable and Outdated Components
**Definition:**
Occasionally, you may find that the company/entity you're pen-testing is using a program with a well-known vulnerability.For example, let's say that a company hasn't updated their version of WordPress for a few years, and using a tool such as [WPScan](https://wpscan.com/wordpress-security-scanner), you find that it's version 4.6. Some quick research will reveal that WordPress 4.6 is vulnerable to an unauthenticated remote code execution(RCE) exploit, and even better, you can find an exploit already made on [Exploit-DB](https://www.exploit-db.com/exploits/41962).

---

## 7. Identification and Authentication Failures
**Definition:**
Authentication and session management constitute core components of modern web applications. Authentication allows users to gain access to web applications by verifying their identities. The most common form of authentication is using a username and password mechanism. A user would enter these credentials, and the server would verify them. The server would then provide the users' browser with a session cookie if they are correct. A session cookie is needed because web servers use HTTP(S) to communicate, which is stateless. Attaching session cookies means the server will know who is sending what data. The server can then keep track of users' actions.

---

## 8. Software and Data Integrity Failures
**Definition:**
This vulnerability arises from code or infrastructure that uses software or data without using any kind of integrity checks. Since no integrity verification is being done, an attacker might modify the software or data passed to the application, resulting in unexpected consequences. There are mainly two types of vulnerabilities in this category:
- Software Integrity Failures
- Data Integrity Failures

---

## 9. Security Logging and Monitoring Failures
**Definition:**
When web applications are set up, every action performed by the user should be logged. Logging is important because, in the event of an incident, the attackers' activities can be traced. Once their actions are traced, their risk and impact can be determined. Without logging, there would be no way to tell what actions were performed by an attacker if they gain access to particular web applications. The more significant impacts of these include:
- **Regulatory damage:** if an attacker has gained access to personally identifiable user information and there is no record of this, final users are affected, and the application owners may be subject to fines or more severe actions depending on regulations.
- **Risk of further attacks:** an attacker's presence may be undetected without logging. This could allow an attacker to launch further attacks against web application owners by stealing credentials, attacking infrastructure and more.
The information stored in logs should include the following:
- HTTP status codes
- Time Stamps
- Usernames
- API endpoints/page locations
- IP addresses

---

## 10.Server-Side Request Forgery
**Definition:**
This type of vulnerability occurs when an attacker can coerce a web application into sending requests on their behalf to arbitrary destinations while having control of the contents of the request itself. SSRF vulnerabilities often arise from implementations where our web application needs to use third-party services.

