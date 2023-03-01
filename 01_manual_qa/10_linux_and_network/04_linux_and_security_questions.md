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

IOCs (Indicators of Compromise) are pieces of information that provide evidence that a system has been compromised or attached. These indicators can include any type of activity or behavior that is abnormal or suspicious, such as:
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
- <mark>Intrusion detetion and preventing</mark>: monitoring network traffic for signs of suspicious activity or known attack patterns, and blocking traffic that matches these patterns.

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

cat /path/to/file | grep ERROR
grep -rn "ERROR" *.log

