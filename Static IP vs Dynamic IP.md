# Static IP vs Dynamic IP
## Static IP:
- A Static IP Address is an IP address that is manually configured and remains the same until someone changes it.
- Static IP addresses are commonly used for:
  - Web Servers
  - Database servers
  - File servers
  - Application servers
  - Network printers
- Advantages
1. The IP address remains consistent.
2. Easy to access servers remotely.
3. Suitable for servers and network devices.
4. Useful when configuring DNS records and firewall rules.
- Disadvantages
1. Requires manual configuration.
2. Incorrect configuration can cause IP conflicts.
3. Network administrators need to manage IP assignments.

## Dynamic ID:
- A Dynamic IP Address is an IP address automatically assigned to a device by a DHCP server.
- DHCP stands for Dynamic Host Configuration Protocol.
- Instead of manually configuring an IP address, the device requests network configuration from a DHCP server.
- The IP address is assigned for a specific period called a Lease Time.
- After the lease expires, the device may renew its existing IP address or receive another available address.
### Where are Dynamic IP addresses used?
- Employee laptops
- Desktop computers
- Mobile phones
- Wi-Fi-connected devices
- Temporary virtual machines
- Advantages
1. Automatic IP configuration.
2. Reduces manual administrative work.
3. Efficient IP address management.
4. Prevents many common configuration mistakes.
- Disadvantages
1. IP addresses can change over time.
2. Not ideal when a device must always be reachable at the same IP.
3. Requires a functioning DHCP server for automatic configuration.

## DHCP - Dynamic Host Configuration Protocol
- DHCP follows a four-step process called DORA.

## How to configure Static and Dynamic IP Addresses in Linux
- There are two methods:
  1. Configure a static IP address.
  2. Configure a dynamic IP address.
- We will use NetworkManager and nmcli for configuration.
- DORA stands for Discover, Offer, Request and Acknowledge.
- Important interview points:
- DHCP uses UDP.
- DHCP server port: 67.
- DHCP client port: 68.
- DHCP follows the DORA process.
- DHCP automatically assigns IP configuration.

### Configure a Static IP Address
1. Identify the connection name: nmcli connection show
2. Configure the Static IP: sudo nmcli connection modify "wired connection 1" ipv4.method manual
3. Configure the IP address and subnet: sudo nmcli connection modify "wired connection 1" ipv4.addresses 192.168.1.100/24
4. Configure the default gateway: sudo nmcli connection modify "Wired connection 1" ipv4.gateway 192.168.1.1
5. Configure DNS: sudo nmcli connection modify "Wired connection 1" ipv4.dns 8.8.8.8
6. Apply the configuration: sudo nmcli connection up "Wired connection 1"
