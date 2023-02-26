# Common Linux Interview Questions


---

1. **How to see/change network interface parameters?**

***ifconfig*** - to see network interface parameters.

***ip*** - to change network interface parameters.

```sh
sudo ip addr add [new IP address]/[netmask] dev [interface name]
```

---

2. **How to install Debian package?**

***dpkg*** - command to install packages from files ```.deb``` files.
```sh
sudo dpkg -i package-name.deb
```

***apt*** or ***apt-get*** - command to install packages from package manager.

---

3. **How to copy file via network between Linux PCs?**

***scp*** - command to copy fils via network.

```sh
scp filename user@destination:/path/to/file
```

---

4. **How to display the amount of available disk space? Keys?**

***df*** - command to show free disk space.

Popular options:
- '-h' or '-H': show output in human-readable format (in bytes, kilobytes and etc.).
- '-l': display only locally-mounted filesystems.

```sh
df /path/to/directory
```
Command above will display the available space on the filesystem that contains the specified direcory.

---

5. **How to see process list? Keys?**

***ps*** - command to see process status.

Keys:
- '-e' or '-A': display information about other users processes.
- '-f': displays additional info about processes.
- '-m': sort by memory usage.

***top*** - command to display sorted information about processes.

Keys:
- '-o': apply sorting to the output. Some sort options: pid, cpu, mem, and others.
- '-user', '-U': display processes for specified user.

---

6. **How to kill process. Keys?**

***kill*** - command that used to terminate or signal a process by it's PID.

***pkill*** - kill process by it's name.

***killall*** - another command to kill process by it's name.

---

7. **How to see resource utilization? Explain fields.**

***top*** - command displays real-time information about system resource utilization.

Main fields:
- PID: process ID
- USER: user that owns the process
- %CPU: CPU useage
- %MEM: physical memory usage
- COMMAND: the name of the command that launched the process
- TIME: the time the process started
- PPID: parent process ID

---

8. **Where log files are?**

In Linux log files usually are stored in ```/var/log``` directory.

Common logs files:
- 'auth.log': logs authentication attempts and system authorization information.
- 'boot.log': logs system boot messages.
- 'cron': logs cron job executions.
- 'dmesg': logs kernel and system messages.
- 'mail.log': logs mail server activity.
- 'syslog': logs system messages and information from various applications.
- 'messages': logs system messages and error messages.

---

9. **What is /etc folder for?**

***/etc*** folder contains important configuration files that are essential for the proper functioning of the system and its applications.

Some important files stored in the '/etc':
- '/etc/hosts': contains list of hostnames and their associated IP addresses that the system can use for name resolution.
- '/etc/ssh/sshd_config': configuration options for the SSH daemon. 

---

10. **Types of links. How to create? Purpose**

- ***Hard link*** is simply a copy of file that points to the same underlying data on the filesystem. Hard links can only be created for files and not directories. **The prupose** of HL is to provide multiple names for the same file, so that a file can be accessed by different locations without having to create multiple copies of the same file.

```sh
ln -f source_file hard_link
```

- ***Symbolic link*** is a special type of file that contains a reference to another file or directory. Unlike HL, a SL can point to a file or directory on a different filesystem or even a network location. SLs are often used to create shortcuts to frequently accessed files or directories.

```sh
ln -s source_file symbolic_link
```

---

11. **How to capture ethernet trace from a specific interface?**

Wireshark app can be used to capture ethernet traffic from a specific interface.

Steps to start capturing:
- Click 'Capture' menu and select 'Interfaces' in Wireshark
- Select tje needed network interface and click 'Start' button.
- To stop capturing click 'Stop' button.
- Capturing result can be analyzed or saved to the file.

---

12. **How to run process in a background? Several ways?**

- Using '&' operator: '&' should be added to the end of the command.

```sh
command &
```

- Using the 'Ctrl + Z' and 'bg' commands. Process can be run in the background by suspending it with the 'Ctrl + Z' key combination, and then resuming it in the background using 'bg' command.

```sh
command
Ctrl + Z (to suspend the command)
bg
```

- Using 'nohup' command. This is useful if you want the process to continue running even if the terminal window is closed.

```sh
nohup command &
```

---

13. **How to check partitions mount point?**

***df*** command can be used.

---

14. **How to check partitions table?**

***fdisk*** command can be used.
```sh
sudo fdisk -l
```

---

15. **Routing table. Display and edit?**

***ip route*** - command to display routing table.

***sudo ip route add \<destination_ip_address>/\<netmask> via \<getway_ip_address> dev \<interface>*** - command to add route to the routing table.

***sudo ip route del \<destination_ip_address>/\<netmask> via \<gateway_ip_address> dev \<interface>*** - command to delete route from routing table.

---

16. **Working with crontab, other ways to add app to startup?**

***Crontab*** - is a system unitlity that allows to schedule commands or scripts to run automatically at specified times and intervals. 

Crontab is a powerful tool that can be used to automate tasks, such as backups, system maintenance, or any other commands that need to be run regularly.

***Cron*** is a daemon that runs in the background of the system and reads the crontab files to execute the scheduled commands. Crontab file is a simple text file that contains a list of commands along with their schedule. The schedule is defined using the cron syntax, which consists of five fields: minute, hour, day of month, month, and day of the week. Each field can contain a value, a range of values, a step value, or an asterisk (*) to indicate all possible values.

```sh
30 3 * * * /path/to/script.sh
```

***Other ways to add an application to startup:***
- systemd - a system and service manager for linux. You can create a systemd service file for your application, which will tell systemd to start the application at boot time.
- rc.local - a script that runs at the end of the boot process on many linux distributions.

---

17. **Awk, dd, netcat, wc (script example)**

***awk*** is a command for pattern search and processing. Basic syntax:
```sh
awk options 'pattern {action}' filename
```

Example: content of 'data.txt'
```
user1 25
user2 30
user3 35
```

```sh
awk '{sum += $2; print $1 "\t" $2} END {print "Average age:", sum/NR}' data.txt
```

Output:
```
user1 25
user2 30
user3 35
Average age: 30
```

***dd*** - command that can be used to:
- back up and restore an entire hard drive or a partition;
```sh
sudo dd if=/dev/source-device of=/dev/destiantion-device bs=4096 conv=noerror,sync
```
- create disk images;
```sh
sudo dd if=/dev/source-device of=/path/to/image-file
```
- create bootable USB dirves;
```sh
sudo dd if=/path/to/iso-image of=/dev/usb-device bs=4M && sync
```
- copy file
```sh
dd if=/path/to/source of=/path/to/destination
```

***netcat*** - allows to read from and write to network connections using TCP and UDP protocols. It can be used to scan ports, transferring files, and etc.

Scan ports:
```sh
nc -zv example.com 1-100
```

Transfer files:
- Command on the server to send file:
```sh
nc -l 1234 > filename.txt
```
- Command on client to recieve file:
```sh
nc example.com 1234 < filename.txt
```

***wc*** - word, line, character, and byte count
```sh
wc /path/to/file
```

---

18. **netstat, other ways to check ports**

***lsof*** - command can be used to display information about network sockets.
```sh
lsof -iTCP -iUDP
```

***ss*** - (socket statistics) command can be used to display detailed information about network sockets.

Display all TCP connections.
```sh
ss -t
```

Display all UDP connections.
```sh
ss -ua
```

***netcat*** - in the command below '-z' specifies that nc should not send any data, '-v' specifies that verbose output should be printed, '1-100' - a range of ports to scan.
```sh
nc -zv example.com 1-100
```
