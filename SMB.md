Default port 445(TCP)

- **SMB (Server Message Block):**
  1. **Network Protocol:** SMB is a network protocol used for file and printer sharing between devices on a local network or the internet.
  2. **Windows File Sharing:** Widely associated with Microsoft Windows, SMB enables seamless sharing of files, directories, and resources among computers in a network.
  3. **Versions:** Various versions of SMB exist, with SMB1, SMB2, and SMB3 being the most notable, each introducing improvements in security, performance, and features.
  4. **Cross-Platform Usage:** While initially designed for Windows, SMB is now supported by other operating systems, facilitating cross-platform file sharing and collaboration.

---
#### Techniques
- Scan the target for open port
- Use enum4linux to see info about SMB
```bash 
enum4linux -a [ip_address] 
```
- See if some shares allows anonymous user using smbclient
```bash
smbclient //[IP]/[SHARE]

Followed by the tags:
-U [name] : to specify the user

-p [port] : to specify the port
```
Ex : ``` smbclient //10.10.67.25/profiles -u Anonymous```
If it works **GREAT** if not 