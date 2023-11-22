
### Operator
|   |   |
|---|---|
|Symbol / Operator|Description|
|&|This operator allows you to run commands in the background of your terminal.|
|&&|This operator allows you to combine multiple commands together in one line of your terminal.|
|>|This operator is a redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere.|
|>>|This operator does the same function of the `>` operator but appends the output rather than replacing (meaning nothing is overwritten).|


### Root Directories on Linux System

#### /etc

- The `/etc` directory is one of the most important root directories on your system.
- It is a commonplace location to store system files used by your operating system.
- Notable contents:
  - `sudoers`: Contains a list of users and groups with permission to run `sudo` commands as the root user.
  - `passwd` and `shadow`: These files store user passwords in encrypted SHA-512 format.

#### /var

- The `/var` directory, short for "variable data," is a main root folder on a Linux install.
- It stores data frequently accessed or written by services and applications.
- Notable contents:
  - `/var/log`: Log files from running services and applications.
  - Other data not associated with a specific user, such as databases.

#### /root

- The `/root` folder is the home directory for the "root" system user.
- Unlike the `/home` directory, this is the default home for the root user.
- Notable contents may vary based on system configuration.

#### /tmp

- The `/tmp` directory is a unique root directory in Linux, short for "temporary."
- It is volatile and used to store data needed temporarily.
- Contents are cleared out upon system restart.
- Any user can write to this folder by default, making it useful for storing temporary files in pentesting.
- Notable contents:
  - Various temporary files and data.






### Serving Files From Your Host - WEB

- Ubuntu machines come pre-packaged with Python3, which includes a lightweight and easy-to-use module called "HTTPServer."

- Python's "HTTPServer" module allows you to turn your computer into a quick and easy web server, enabling you to serve your own files. These files can then be downloaded by other computers using commands such as `curl` and `wget`.

- By default, Python3's "HTTPServer" serves files in the directory where you run the command. However, you can change this behavior by providing options that can be found in the manual pages.

#### Using Python to Start a Web Server

```bash
tryhackme@linux3:/tmp# python3 -m http.server
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
```

#### Updog

***Updog is a replacement for Python's `SimpleHTTPServer`***

`updog [-d DIRECTORY] [-p PORT] [--password PASSWORD] [--ssl]`

|Argument|Description|
|---|---|
|-d DIRECTORY, --directory DIRECTORY|Root directory [Default=.]|
|-p PORT, --port PORT|Port to serve [Default=9090]|
|--password PASSWORD|Use a password to access the page. (No username)|
|--ssl|Enable transport encryption via SSL|
|--version|Show version|
|-h, --help|Show help|

**Installation:**
```shell
pip3 install updog
```

**Usage:**
- Serve files from the current directory: `updog`
- Serve files from another directory: `updog -d /another/directory`
- Specify a custom port (e.g., 1234):   `updog -p 1234`
- Password protect the page (HTTP basic auth, username is blank): 
`updog --password examplePassword123!`
- Use an SSL connection:`updog --ssl`

***When using password protection, leave the username blank and enter the password in the password field.***
### Understanding Processes in Linux

#### Viewing Processes

- Use the `ps` command to list running processes, displaying details like PID, status code, session, CPU usage, and the program name.
- To view processes of all users and system processes, use `ps aux`.

- Another useful command is `top` or `htop`providing real-time statistics about running processes.

#### Managing Processes

- You can send signals to terminate processes. The `kill` command, followed by the PID, kills a process.
- Common signals include SIGTERM (clean termination), SIGKILL (forceful termination), and SIGSTOP (process suspension).

#### Starting Processes

- Namespaces divide system resources among processes.
- The process with PID 0 (init) starts when the system boots.
- systemd, on Ubuntu, manages user processes and sits between the OS and users.
- To start software on boot, use `systemctl` to interact with systemd, with options like start, stop, enable, and disable.
```bash
systemctl start [process name]
systemctl stop [process name]
systemctl enable [process name]
systemctl disable [process name]
systemctl status [process name]
```

#### Backgrounding and Foregrounding

- Processes can run in the background or foreground.
- Commands run in the foreground by default.
- Use the `&` operator to run a command in the background.
- Ctrl + Z can suspend a foreground process.
- To resume a background process, use the `fg` command.


### Scheduling Tasks with Cron and Crontabs

Users often want to schedule actions, such as running commands, backing up files, or launching programs, to occur after the system has booted.

#### Cron and Crontabs

- Cron is a process responsible for scheduling tasks.
- Crontabs are files used to interact with the cron process.
- A crontab is a special file with formatting recognized by cron for executing tasks.
- Crontabs have six specific values:

|   |   |
|---|---|
|Value|Description|
|MIN|What minute to execute at|
|HOUR|What hour to execute at|
|DOM|What day of the month to execute at|
|MON|What month of the year to execute at|
|DOW|What day of the week to execute at|
|CMD|The actual command that will be executed.|


#### Crontab Example

- For example, to back up "cmnatic"'s "Documents" every 12 hours:
```bash
0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/
```


- Crontabs support wildcard or asterisk (*), allowing flexibility in specific time fields.
- Use an asterisk when you don't need to specify a value for a particular time field.

#### Editing Crontabs

- Edit crontabs using the `crontab -e` command, selecting an editor (e.g., Nano) to modify your crontab.

- Online resources like [CronTab Generator](https://crontab-generator.org/) and [Cron Guru](https://crontab.guru/) can help generate crontab formatting.

### Introducing Packages & Software Repositories in Linux

#### Adding and Managing Repositories

- Operating system vendors maintain their own repositories.
- You can add community repositories to extend your OS capabilities.
- Add repositories using the "add-apt-repository" command or manually.
- Good Practice is to create 1 File.list for each source & comment it
- To manually add a repository (e.g., Sublime Text), follow these steps:

1. Download the GPG key: `wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -`

2. Create a file for the repository in `/etc/apt/sources.list.d` (e.g., "sublime-text.list").
![[Pasted image 20231107221102.png]]

4. Edit the newly created file to include the repository information.
![[Pasted image 20231107221123.png]]

6. Update apt to recognize the new entry: `apt update`

7. Install the software from the repository: `apt install sublime-text`

#### Removing Repositories and Packages

- Remove repositories using `add-apt-repository --remove ppa:PPA_Name/ppa` or manually by deleting the corresponding file.

- To remove packages, use `apt remove [software-name]` (e.g., `apt remove sublime-text`).

- Apt ensures that the repository is checked for updates when you update your system, maintaining software integrity.


### Linux Log Files

- Log files in Linux are located in the `/var/log` directory.
- These logs contain information about the activities of applications and services running on your system.
- The OS automatically manages these logs in a process known as log rotation.
![[Pasted image 20231107221935.png]]
#### Commonly Monitored Logs

- Some important logs from various services running on a Ubuntu machine:
  1. Apache2 web server: These logs provide information about every web request, including access and error logs.
  2. Fail2ban service: Monitors attempted brute force attacks and records relevant logs.
  3. UFW (Uncomplicated Firewall) service: Logs relevant to the system's firewall configuration.

#### Monitoring and Protection

- Log files are essential for monitoring the health of your system and protecting it.
- Logs provide insights into system performance, security, and any unauthorized activities.
- For example, web server logs include access logs and error logs for diagnosing performance issues and investigating potential intrusions.
- There are also logs that track OS operations and user actions, including authentication attempts.
