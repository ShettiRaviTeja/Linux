# Linux Networking

## a. How does networking in Linux work?
### 1. What is Networking?
- Networking is the process of connecting two or more devices so they can communicate and share information with each other.
### 2. How does Linux Networking work?
- Linux uses a combination of hardware, software, protocols and network configurations to communicate with other devices.
- Suppose Computer A (192.168.1.10) wants to send a message to Computer B (192.168.1.20).
- Communication process:
  1. Computer A identifies the destination IP address.
  2. It determines whether the destination is on its local network.
  3. It uses ARP to discover Computer B's MAC address if necessary.
  4. It sends the data in network packets.
  5. The switch forwards the Ethernet frame to Computer B.
  6. Computer B receives and processes the data.
  - If the destination is outside the local network, the data is forwarded through a router (usually via the default gateway).
  - Important: The switch does not normally use IP addresses to decide which port to forward Ethernet frames to. It uses MAC addresses.

    
### 3. Important Networking Components in Linux
1. IP Address
- An IP address is a unique logical address assigned to a network interface within a network.
- It helps identify devices and route data between networks.
- There are two major versions:
  - IPv4: 192.168.1.10
  - IPv6: 2001:db8::1
- Linux command to check the ip address : ip a (or) ip addr

2. MAC Address
- MAC stands for Media Access Control.
- It is a hardware-level address associated with a network interface.
- Linux command : ip link
- This displays network interfaces and their MAC addresses.

3. Network Interface
- A network interface is a connection point through which a computer communicates with a network.
- Examples:
  - Ethernet: Wired network connection.
  - Wi-Fi: Wireless network connection.
  - Loopback: Internal communication within the same machine.
- Common Linux interface names:
  - eth0 : Traditional Ethernet Interface name
  - ens33 : Ethernet interface
  - enp0s3 : Ethernet interface
  - wlan0 : Traditional wireless interface name
  - lo : Loopback interface
- To check whether an interface is active:
  - UP : Interface is administratively enabled.
  - DOWN : Interface is administratively disabled.
  - LOWER_UP : Physical or virtual link is operational.

4. Subnet Mask
- A subnet mask determines which portion of an IP address represents the network and which portion represents the host.
- Example:
  - IP Address:  192.168.1.10
  - Subnet Mask: 255.255.255.0
- In CIDR notation: 192.168.1.10/24
  - Here, /24 means the first 24 bits represents the network portion.
  - The remaining 8 bits represent the host portion.

5. Default Gateway
- A default gateway is the device (usually a router) through which your computer communicates with devices outside its local network.
- Examples:
  - Linux Server:  192.168.1.10
  - Default Gateway: 192.168.1.1
- To check the default gateway:
  - ip route

6. DNS (Domain Name System):
- DNS converts domain names into IP addresses.
- Linux Commands:
  - nslookup google.com : Provides simpler info.
  - dig google.com : Provides detailed info about the DNS.

## Important Linux Networking Commands
- ip addr : Display ip addresses
- ip link : Display network interfaces
- ip route : Display routing table
- ping : Test network connectivity
- ss -tulnp : Display listening ports and processes
- hostname -I : Display assigned IP addresses
- ip neigh : Display neighbor/ARP info
