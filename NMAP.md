### Nmap Tool 
- Port scanning is a crucial initial step
- Nmap is the industry standard for port scanning
- Unmatched functionality and powerful scripting engine
- Used for vulnerability scanning and exploitation

### Command Nmap
- **Syn Scan First Switch:**
  - `nmap -sS`

- **UDP Scan Switch:**
  - `nmap -sU`

- **Detect Operating System Switch:**
  - `nmap -O`

- **Service Version Detection Switch:**
  - `nmap -sV`

- **Increase Verbosity Switch:**
  - `nmap -v`

- **Verbosity Level Two Switch:**
  - `nmap -vv`

- **Save Results in Three Major Formats Switch:**
  - `nmap -oA`

- **Save Results in "Normal" Format Switch:**
  - `nmap -oN`

- **Save Results in "Grepable" Format Switch:**
  - `nmap -oG`

- **Enable "Aggressive" Mode Switch:**
  - `nmap -A`
- **Timing Template Level 5 Switch:**
  - `nmap -T5`

- **Scan Specific Port (e.g., Port 80) Switch:**
  - `nmap -p 80`

- **Scan Port Range (e.g., Ports 1000-1500) Switch:**
  - `nmap -p 1000-1500`

- **Scan All Ports Switch:**
  - `nmap -p-`
  
- **Activate Nmap Scripting Library Switch:**
  - `nmap --script` 
  
  - **Activate All Scripts in "vuln" Category Switch:**
  - `nmap --script=vuln` 

- **Basic Scan Types:**
  - `nmap -sT`: TCP Connect Scans
  - `nmap -sS`: SYN "Half-open" Scans
  - `nmap -sU`: UDP Scans

- **Less Common Scan Types:**
  - `nmap -sN`: TCP Null Scans
  - `nmap -sF`: TCP FIN Scans
  - `nmap -sX`: TCP Xmas Scans


- Quick nmap scan
  - ```nmap -p0- -v -A -T5 10.10.3.72```


