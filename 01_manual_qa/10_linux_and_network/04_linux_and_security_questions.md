# Linux management and Security questions

1. **How to check system logs?**

    ```sh
    tail /var/log/syslog
    ```

---

2. **What command should be used to update file permissions?**

    ```sh
    chmod [OPTION] [MODE] [path ot file]
    chmod 755 file.txt
    ```

755 -> the absolute mode that permits read, write and execute by the owner, read and execute by group members, read and execute by others, and no set-uid or set-gid behaviour

---

3. **How to use ssh command?**

    ```sh
    ssh [OPTIONS] [username]@[host]
    ```

---

4. **What is IOCs?**

IOCs (Indicators of Compromise) are pieces of information that provide evidence that a system has been compromised or attacked. These indicators can include any type of activity or behavior that is abnormal or suspicious, such as:
- unusual network traffic patterns
- unexpected system modifications
- the presence of malicious files or software

Some common examples of IOCs:
- <mark>Malware signatures or hashes</mark>: Unique codes that can be used to identify specific strains of malware.
- <mark>IP addresses and domains</mark>: The IP addresses or domains that are associated with malicious activity or have been blacklisted by security vendors.
- <mark>URLs and file paths</mark>: The URLs or file paths that are associated with malicious websites or downloads.
- <mark>Registry keys</mark>: The specific Windows registry keys that are modified by malware.
- <mark>Usernames and passwords</mark>: Compromised usernames and passwords that are used to gain unauthorized access to a system.

By identifying and tracking IOCs, security analysts can monitor for potential threats and take action to mitigate them before they cause significant damage.

---

5. **What is a firewall?**

A firewall is a network securtiy device that monitors and controls incoming and outgoing network traffic based on a set of predifined rules. It acts as a barrier between a private internet network and the public internet, allowing only authorized traffic to pass through while blocking unauthorized or malicious traffic.

Firewalls can be implemented as hardware devices, software application, or a combination of both. They are typically placed at the network perimeter, where they can filter traffic before it reaches the internal network.

Firewalls can use a variety of methods to control network traffic, including:
- <mark>Packet filtering</mark>: examining each packet of data that passes through the firewall and blocking packets that do not meet predefined criteria.
- <mark>Stateful inspection</mark>: monitoring the state of network connections to ensure that only legitimate traffic is allowed through.
- <mark>Application-level gateway (proxy)</mark>: examining the content of network traffic at the application level to identify and block malicious or unauthorized requests.
- <mark>Intrusion detection and preventing</mark>: monitoring network traffic for signs of suspicious activity or known attack patterns, and blocking traffic that matches these patterns.

---

6. **Which Firewall do use for Linux?**

I don't have a preference for any firewall. I always use preinstalled firewall.
Popular firewalls available for Linux:
- <mark>iptables</mark>: this is the standard firewall tool for Linux and is available on most Linux distributions. It uses a set of rules to filter network traffic based on protools, ports, and source/destination IP addresses.
- <mark>UFW (Uncomplicated Firewall)</mark> is a user-friendly front-end for iptables that simplifies the process of setting up a firewall. It includes pre-configured firewall profiles for common services and allows you to easily enable or disable firewall rules.
- <mark>Firewalld</mark> is a newer firewall tool that is designed to be more dynamic and flexible than iptables. It uses a zones and services concept and allows you to define firewall rules that are applied based on the network zone that a device is connected to.
- <mark>Shorewall</mark> is a powerful firewall tool that uses a high-level configuration language to define firewall rules. It provides support for complex network configurations and can be used to configure both host and gateway firewalls.

---

7. **What is SWAP, how to check if SWAP is enabled? (swapon, swap -l and etc)?**

SWAP is a space on a hard disk that is used as a virtual memory extension of the system's physical memory (RAM). When the amount of RAM being used by the system exceeds the available physical memory, the linux kernel will use swap space to temporarily move inactive or less frequently accessed memory pages from RAM to the hard disk to free up physical memory for more acitve processes.

The swap space can be either a dedicated swap partition on the hard disk or a swap file located on a fiel system.

Enabling swap can help to prevent system crashes and improve overall system performance by allowing the kernel to continue running processes taht would otherwise be killed due to insufficient memory. However, excessive swapping in and out pages of memory, leading to a noticeable slowdown in system response time.

To check if swap is enabled on your system, you can use the ```swapon -l``` or ```swap -l``` commands. These commands will show you a list of all the currently enabled swap partitions and swap files on your system. 
```
Filename				Type		Size		Used	Priority
/dev/sda2				partition	2097148		0		-2
```
If you see no output, it means that swap is not currently enabled.

Alternatively, you can use the ```free -h``` command to check if swap is enabled. This command will show you information about your system's memory usage, including the amount of swap space that is available.

```
		total		used		free	shared		buff/cache		available
Mem:	7.7G		1.6G		3.9G	197M		2.3G			5.3G
Swap:	2.0G		0B			2.0G
```
If you see 0B under the ```used``` column for the swap section, it means that swap is not currently used.

---

8. **What is the difference between Linux distributions?**

Linux distributions are different versions of the Linux OS that have been packaged with different sets of SW, configurations, and tools to suit different use cases and user preferences. 

Key differences between distributions:
1) <mark>Package manager</mark>: different distros use different package managers systems to install, update, and remove SW. Some popular package managers include apt, dpkg, yum, dnf, and flatpak.
2) <mark>User interface</mark>: linux distros come with different desktop environments and window managers, which affect the overal look and feel of the system. Desktop envfironments: GNOME, KDE, and etc.
3) <mark>Software availability</mark>: different distros may include different sets of SW packages and repositories, which can affect the availability of specific programs or tools.
4) <mark>Release cycle</mark>: some distros are designed for long-term support and stability, while others prioritize bleeding-edge features and updates.
5) <mark>Target users</mark>: some distros are designed specifically for servers or embeded systems, while others are aimed at home users or mulitimedia enthusiasts.
6) <mark>Hardware support</mark>: linux distros may have different levels of HW support for specific devices or components, depending on the drivers and kernel versions included in the distribution.
7) <mark>Design philosophy</mark>: linux distros may have different design philosophy and approaches to open-source SW, community-driven development, and user empowerment. Some distros prioritize user freedom and flexibility, while others prioritize ease of use and accessibility.

---

9. **How to search for files and directories by name?**
    ```sh
    locate [options] [pattern]
    ```

    ```sh
    find [where to start searching from] [expression determines what to find] [options] [what to find]

    find ./GFG -name sample.txt 
    ```

---

10. **How to check\ kill process?**

    ```sh
    ps ux - view the process ID (PID) of the program.
    ps -A - list processes currently running on your system
    top - view a list of all currently running processes
    ps ax | grep firefox – find PID of process
    kill [PID]
    ```

---

11. **How to display only those lines from the log file that contains "ERROR" in the Linux terminal:**

```sh
cat /path/to/file | grep ERROR
grep -rn "ERROR" *.log
```

---

12. **How to disable port or protocol type in linux?**

To disable a port of protocol in Linux, you can use a firewall application like iptables. The steps to disable a port or protocol type are as follows:
1) Check the current status of the firewall using the following command:
    ```sh
    sudo iptables -L
    ```
2) Identify the port of protocol type that you want to disable.
3) Use the following command to block the port of protocol type:
```sh
sudo iptables -A INPUT -p [protocol] --dport [port] -j DROP
```

---

13. **Difference between \#Unable to render embedded object: File (\/bin\/sh and \#) not
found.\/bin\/bash - where to use each one of them (\#!\/bin\/sh is more cross-platform).**

The difference beween ```#!/bin/sh``` and ```#!/bin/bash``` is the shel that is used to interpret the script. ```#!/bin/sh``` specifies that the Bourne shell should be used, while ```#!/bin/bash``` specifies that the Bash shell should be used.

In general, ```#!/bin/sh``` is more cross-platform because it is available on most Unix-like systems, while ```#!/bin/bash``` may not be available on some systems or may be located in a different location. ```#!/bin/sh``` is also generally more lightweight and faster.

However, there are some cases where you want to use ```#!/bin/bash```. Bash provides many additional features and extentions beyond what is available in Bourne shell, such as arrays, process substitution, and advanced string manipulation.

The error message "Unable to render embedded object: File (/bin/sh and #) not found." suggests that the system is unable to locate the shell specified in the shebang line. This can occur if the shell is not installed or if it is located in a different location than expected. In this case, you may need to modify the shebang line to specify the correct location of the shell on your system.

---

14. **If you need to transform a lot of data with regular expressions what to use? Bash or Python?**

Both Bash and Python can be used to transform data using regular expressions. However, Python is generally a more powerful and flexible language for this task. Python has a built-in re module for regular expressions, which provides more advanced features than the regular expression support available in Bash.

Python also provides many other useful libraries for working with data, such as pandas, which can be used for data analysis and transformation tasks. In addition, Python's syntax and structure make it easier to write and maintain complex scripts and applications.

Bash, on the other hand, is a more lightweight and simpler language, which may be more suitable for smaller or simpler data transformation tasks. It also has built-in support for regular expressions, which can be useful for quick and simple tasks.

Advantage of Bash is that it is cross-platform and is preinstalled on many of systems.

---

15. **Supposing you need to distribute a patch for some product to customers, what is the most cross-platform universal way of doing so?**

The most cross-platform universal way of distributing a patch to customers is to provide a patch file in a format that can be applied by standard patching tools available on multiple platforms.

---

16. **What does docker-compose do?**

Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to define the services and dependencies of your applicaiton in a YAML file, and then use that file to spin up all the required containers with a single command. Docker compose is useful for complex applications that require multiple containers running together, such as web applications with a DB and cache.

Key features of Docker Compose:
1) Multi-container application management.
2) YAML-based configuration. This makes it easy to version and manage your application's configuration.
3) Automatic network configuration. Docker automatically creates a network for your containers and assign them network aliases, making it easy for them to communicate with each other.
4) Dependency management. You can define dependencies between services, so that containers start in the correct order.
5) Environment variable support. Docker compose allows you to set environment variables for your container, making it easy to configure your application for different environments.
6) Scaling. You can scale your application services up or down with a single command, making it easy to adjust your infrastructure to handle changing loads.

---

17. **How to run a command inside a container?**

To run a command inside a container, you can user the ```docker exec``` command.
1) First, start the container that you want to run command in.
    ```sh
    docker run -it ubuntu
    ```
2) Get its container ID.
    ```sh
    docker ps
    ```
3) Use ```docker exec``` command to run the command inside container. For example, ```ls``` command:
    ```sh
    docker exec -it [container-id] ls
    ```

The ```-it``` option tells Docker to run the command in an interactive terminal session, allowing to see the command output and interact with the container if necessary.

Other ways to run command inside docker cotainer:
1) ```docker attach``` command. This will attach yo the container's standard input, output, and error streams, allowing you to run commands inside it. Note that using ```docker attach``` may interfere with the container's process and is not recommended for running commands that require user input.
    ```sh
    docker attach [container-id]
    ```
2) You can also user ```docker run``` command to start a container and run a command in it directly. Note that this method starts a new container each time you run a command, which can be inefficient if you need to run multiple commands in the same container.
    ```sh
    docker run -it ubuntu ls
    ```

---

18. **How to transfer a container?**

To trasfer a container from one system to another, you can use Docker's export and import functionality.
1) Export container.
    ```sh
    docker export my-container > my-container.tar
    ```
2) Trasfer the tar file to the destination system using a secure file transfer protocol, such as SCP, SFTP, or other.
3) Import container.
    ```sh
    docker import my-container.ra my-container
    ```
4) Run container.
    ```sh
    docker run my-container
    ```
