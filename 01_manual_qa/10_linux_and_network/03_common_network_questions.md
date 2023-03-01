# Common Network Interview Questions

---

1. **Minimal required networking parameters for host**

- IP address
- Subnet mask
- Default gateway
- DNS servers
- Network interface
- Network cables or wireless connection

---

2. **Difference between router, switch, hub**

Routers are used to connect different networks together, switches are used to connect devices on the same network, and hubs are used to broadcast network traffic to all devices on the same network.

---

3. **What is subnet mask for ip address?**

A subnet mask is a 32-bit value that is used to devide an IP address into two parts: the network address and the host address. For example, consider the IP address 192.168.1.100 with subnet mask of 255.255.255.0. In this case, the first 3 octets (192.168.1) represent the network address, while the last octet represents the host address.

---

4. **What is OSI model? Name layers, give protocol examples.**

Open Systems Interconnection model is a conceptual model that describes how network communication occurs between different computer systems. The seven layers of the OSI model:

1) Physical layer is responsible for the physical transmission of data over a network. It defines the physical characteristics of the network, such as the type of cable, connector, and signaling used. Protocols: coax, fiber, wireless. Devices: hubs, repeaters.
2) Data Link layer is responsible for transferring data between network nodes. The main goal of this layer is to ensure error-free data transfer from one node to another across the physical layer. Protocols: ethernet, PPP. Devices: switch, bridge.
3) Network layer is responsible for routing data between different networks. It includes protocols that handle logical addressing and routing of data across multiple networks. Protocls: IP, ICMP, and ARP. Devices: routers.
4) Transport layer is responsible  for the reliable delivery of data between applications on different devices. It includes protocols that handle segementation, reassembly, and flow control of data. Protocols: TCP, and UDP.
5) Session layer is resposible for establishing, maintaining, and terminating communication sessions between applications on different devices. Protocols: NetBIOS, SOCKS, and RPC.
6) Presentation layer is responsible for translating data between the application layer and the lower layers. It includes protocols that handle data encryption, compression, and formatting. Protocols: SSL, SSH, TLS.
7) Application layer is responsible for providing network services to end-user applications. It include protocols that handle email, file transfer, and other application-level functions. Protocols: HTTP, SMTP, FTP, and DNS.

---

5. **PDU per layer**

Protocol Data Unit for each layer of the OSI model:
1) Physical layer: bit
2) Data Link layer: frame, which includes a header, a trailer, and the data being transmitted.
3) Network layer: a packet, which includes a header and the data transmitted.
4) Transport layer: a segment (TCP) or a datagram (UDP).
5) Session layer: a dialogue, which is a series of messages exchanged between applications running on different devices.
6) Presentation layer: a data stream, which is the representation of data in a form that can be understood by the application layer.
7) Application layer: a message, which is the data beign transmitted by the applicaiton. Message includes any application-specific headers and data.

---

6. **Addressing per layer**

1) Physical layer: the physical address (MAC address).
2) Data Link layer: the logical address (is commonly referred to as MAC address).
3) Network layer: the network address (IP address).
4) Transport layer: the port number, which is used to identify the application that is sending or receiving data.
5) Session layer: the session identifier, which is used to identify a specific communication session between applications running on different devices.
6) Presentation layer: addressing is not typical.
7) Application layer: addressing is specific to the application being used.

---

7. **Difference between UDP and TCP**

1) Connection-Oriented vs Connectionless:
    - TCP is connection-oriented protocol, which means that it establishes a connection between two devices before transmitting data;
    - UDP is a connectionless, which means that it does not establish a connection before transmitting data.

2) Reliablity:
    - TCP ensures that all data sent is received by the destination device without any errors or loss. If any data is lost or corrupted during transmission, TCP will retransmit the data until it is successfully received.
    - UDP does not guarantee that all data sent will be received by the destiantion device. If any data is lost or corrupted during transmission, UDP does not attempt to retransmit it.

3) TCP is slower protocol because it's header size is much larger than the UDP header.

---

8. **DHCP purpose**

Dynamic Host Configuration Protocol is a network protocol used to automatically assign IP addresses and other network configuration parameters, such as subnet masks, default gateways, and DNS server addresses, to network devices. The purpose of DHCP is to simplify network administration and reduce the configuration errors that can occur when IP addresses are assigned manually.

---

9. **Network troubleshooting tools?**

1) Ping: a command line tool that tests the connection between two devices by sending small packet of data from one device to another and measuring the response time. It can help identify connectivity issues and network latency.
2) Traceroute: a command line tool that traces the route that packets take from one device to another, showing the IP address of the devices along the way. It can help identify network connectivity issues and routing problems.
3) Wireshark: allows to capture and analyze traffic in real-time. It can help identify network issues, troubleshoot connectivity problems, and monitor network performance.
4) DNS lookup: can help diagnose DNS issues, such as incorrect DNS server settings, by resolving domain names to IP addresses and vice versa.

---

10. **What is DNS?**

Domain Name System is a system used to translate human-readable domain names into machine-readable IP addresses.

When you enter a domain name in your web browser, your computer sends a request to a DNS server to look up the IP address associated with that domain name. The DNS server then responds with the IP address, allowing your computer to connect to the server hosting the website you request.

---

11. **DHCP messages**

1) <mark>DHCP Discover message</mark> is brodcasted by a device that is looking for a DHCP server to obtain an IP address.
2) <mark>DHCP Offer message</mark> is a server response for Discover message. This message is includes IP address and other network configuration information: subnet mask, default gateway, and DNS server information.
3) <mark>DHCP Request</mark> indicates that device wants to accept the offered IP address.
4) <mark>DHCP Acknowledgment</mark> indicates that server has assign provided IP address to device. This message also includes lease time - duration for which IP address will be assigned to the device before it needs to be renewed.

---

12. **TCP 3 way handshake**

Three steps of the TCP three-way handshake:
1) <mark>SYN (Synchronize)</mark> - the client sends a SYN packet to the server, indicating that it wants to establish a connection.
2) <mark>SYN-ACK (Synchronize-Acknowledgment)</mark> - the server responds with SYN-ACK packet, indicating that it has received the client's request and is willing to establish a connection.
3) <mark>ACK (Acknowledgment)</mark> - the client sends ACK packet to the server, indicating that it has received the server's SYN-ACK paket and is ready to start exchanging data.

Once the three-way handshake is complete, the connection is established and data can be exchanged between the client and server in both directions.

---

13. **How "ping" command works? Used protocol?**

It sends a series of ICMP (Internet Control Message Protocol) echo requests packets to the destination host and waiting for ICMP echo reply packets to come back. When the destination host receives an echo reqeust packet, it sends an echo reply packet back to the source host, allowing the source host to datermine the round-trip time for the packet to travel between the two hosts.

The "ping" command is built on top of the Internet Protocol (IP), which is the foundational protocol of the Internet.

---

14. **How "traceroute" command works?**

It works by sending a series of packets with incrementally increasing Time To Live values and observing the response from each intermediate router along the path. The process continues with the TTL value being incremented for each subsequent packet until the destination computer is reached. As each router along the path receives a packet with TTL value of 1, it sends and ICMP Time Exceeded messages back to the source computer, which allows source computer to record the IP address of that router.

---

15. **Calculate IP network capacity based on subnetmask**

1) Count the number of bits in the host portion of the subnet mask. 
2) Calculate the number of host addresses available in the subnet. This is calculated as 2 ^ (number of bits in host portion) - 2. The '-2' is for network address and broadcast address.

---

16. **What is ARP? How it works?**

Address Resolution Protocol is a protocol used to map a physical (MAC) address to an IP address in a local network.

How it works:
1) When a device needs to communicate with another device on the network, it first checks its ARP cache (table with mapping between IP and MAC) to see if it already knows the MAC address of the destiantion device.
2) If the MAC address is not found in the ARP cache, the device sends an ARP request packet to the network, asking "who has this IP address?" and broadcast it to all devices on the network.
3) The device with the IP address listed in the ARP request responds to the request with an ARP reply packet that includes its MAC address.
4) The device that made the ARP request receives the ARP reply and adds the mapping to ARP cache.
5) With the MAC address of the destination device now known, the device can send data packets to that device on the network.

---

17. **What is VLAN? Purpose?**

Virtual Local Area Network is a technology used to create logical networks within a physical network. VLANs allow to segment a single physical network into multiple virtual networks, each with its own set of network devices, IP addresses, and security policies.

The purpose of VLANs is to provide better network performance, security, and flexibility.

---

18. **What is broadcast domain? How to limit?**

It is a logical division of a computer network in which all devices can broadcast messages to each other.

To limit the size of a broadcast domain, you can use various network segmentation techniques, such as VLANs, subnetting, routing, and implementing broadcast control protocols.

---

19. **How DNS works?**

1) After you enter a domain name in your browser, your computer sends a request to DNS server to find out the IP address of specifed domain name.
2) DNS server looks up the IP address associated with the domain name in its database.
3) If IP address is found, DNS server sends it back to your computer.
4) If IP address is not found, DNS server forwards the request to another DNS that might have it. This process continues until the DNS server finds the IP address associated with the domain name, and sends it back to your computer.

---

20. **What is SNMP?**

Simple Network Management Protocol is a protocol that allows to collect and organize information about network devices, such as routers, switches, servers, printers, and more. This information can include device status, network traffic, performance metricts, and so on.

---

21. **What is AAA?**

AAA stands for Authentication, Authorization, and Accounting. It is security framework used to control access to network resources and services.

---

22. **Examples of authentication servers.**

Active Directory - service that provides authentication and authorization sevices for Windows-based networks.

LDAP (Lightweight Directory Access Protocol)

---

23. **Static and dynamic routing. Advantages?**

***Static routing*** - is a routing method in which network administrators manually configure routing tables in network devices. The main advantages of static routing are:
1) Predictability: since the routing tables are manually configured, there is no automatic selection of routes, which makes network traffic more predictable.
2) Security: can be more secure than dynamic since there is not automatic sharing or routing information between devices.
3) Low Overhead: static routing requires no additional network resources or processing power.

***Dynamic routing*** is a routing method in which network devices automatically exchange routing information with each other using a routing protocol. Advantages:
1) Scalability: dynamic routing is scalable and can be used in large networks with many devices.
2) Flexibility: adapts to changes in network topoligy automatically, which makes it ideal for networks with a lot of changes.
3) Efficiency: selects the best path for network traffic automatically, which results in efficient use of network resources.
4) Fault tolerance: automatically reroutes network traffic around failed links or devices.