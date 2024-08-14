## Table of Contents

- [Accessing the command line interface](#accessing-the-command-line-interface)
  - [WeOS4](#weos4)
  - [WeOS5](#weos5)
- [Console Port Configuration](#console-port-configuration)
- [Accessing the CLI via SSH](#accessing-the-cli-via-ssh)
  - [Recommended SSH Clients](#recommended-ssh-clients)
- [WeOS Cheat Sheet](#weos-cheat-sheet)
  - [Admin Exec context](#admin-exec-context)
  - [Global Configuration context](#global-configuration-context)
  - [How to navigate in the different context menus](#how-to-navigate-in-the-different-context-menus)
- [Admin Exec context (Commands)](#admin-exec-context-commands)
- [Global Configuration Context (Commands)](#global-configuration-context-commands)
- [Handling of files](#handling-of-files)
- [General Abbreviations in Network Technology](#general-abbreviations-in-network-technology)
 - [Switching Abbreviations in Network Technology](#switching-abbreviations-in-network-technology)
 - [Routing Abbreviations in Network Technology](#routing-abbreviations-in-network-technology)

# Accessing the command line interface:

To login via the console port you need the username and password. Currently there is only a single user account defined, the administrator user account. Factory default account and password:

### WeOS4
| Username | Password |
| :--- | :--- |
| admin | westermo | 

### WeOS5
| Username | Password |
| :--- | :--- |
| admin | admin |


### Console Port Configuration:

| Setting | Value |
| :--- | :--- |
| Data rate | 115200 bits/s |
| Data bits | 8 |
| Stop bits | 1 |
| Parity | None |
| Flow control | None |

Virtual COM port (VCP) driver: https://ftdichip.com/drivers/vcp-drivers/

## Accessing the CLI via SSH:
To access the CLI via SSH, you need an SSH client, the switch IP address, and account credentials (username/password).


### Recommended SSH Clients:

| OS | Software | Link |
| :--- | :--- | :--- |
| Windows | PuTTY | [download](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) |
| UNIX | OpenSSH | [download](https://www.openssh.com) |



# WeOS Cheat Sheet
![alt text](<Screenshot 2024-04-16 155850.png>)


### Admin Exec context
In the Admin Exec context, users can perform general monitoring, diagnostics, and manage configuration files and firmware versions. 
They can also access specific execution contexts, such as viewing RMON statistics.

### Global Configuration context
From the Admin Exec context, users can access the Global Configuration context.
Here, they can set device parameters of global significance, like hostname and location. 
From Global Configuration, users can navigate to specific contexts for protocols or device entities such as ports, VLANs, interfaces, and FRNT.

### How to navigate in the different context menus:

![alt text](<Screenshot 2024-04-16 155831.png>)

| Command | Description | OS Version |
| :--- | :--- | :--- |
| `configure` | Enters Global Configuration context. | WeOS4/5 |  
| `logout` | Logged you out of the device. | WeOS4/5 |
| `vlan [#]` | Enters VLAN Config. Context from Global Config. Context. | WeOS4/5 |
|`port eth[#] / dsl[#]`| Enters Port Config. Context from Global Config. Context. |WeOS4/5|
|`port ethx[#]`| Viper devices. Enters Port Config. Context from Global Config. Context.|WeOS4/5|
|`port ser[#]`| LynxDSS devices. Enters Port Config. Context from Global Config. Context.|WeOS4/5|
| `ip` | Enters IP Config. Context from Global Config. Context. | WeOS4/5 |
| `firewall` | Enters Firewall/NAT Config. Context from General IP Config. Context. | WeOS4/5 |
|`end`| Return to the previous mode. | WeOS4/5 |


### Admin Exec context:

| Command | Description | OS Version |
| :--- | :--- | :--- |
| `show` | The "show" command displays various information such as configurations, statistics or status. | WeOS4/5 | 
| `do` | With this command you are able to execute a command from different contexts. | WeOS4/5 |
| `show ifaces` | Displays information about interfaces. | WeOS4/5 |
| `show ip route:` | Displays the IP routing table. | WeOS4/5 |
| `show arp` | Displays the ARP table. | WeOS4/5 |
| `show log` | Displays the logs of the device. | WeOS4/5 |
| `show system` | Displays system information about the device. | WeOS4/5 |
| `show version:` | Displays information about the current system version. |WeOS4/5|
| `ping [destination]:` | Sends ICMP echo requests to the destination. | WeOS4/5 |
| `traceroute [destination]:` | Performs a traceroute to the destination. | WeOS4/5 |
| `ipcalc [address]:` | Provides detailed information about IP addresses and subnets. |WeOS4/5|
| `repeat [command]` | Execute a specified command multiple times. |WeOS4/5|
| `uptime` | Duration since the last restart.  |WeOS4/5|
|`ssh [user@address]`| Secure shell login to another host. |WeOS4/5|
|`ipcalc` | An IP Netmask/broadcast/etc calculator. |WeOS4/5|
|`reboot` |Reboots this device.|WeOS4/5|
|`ipconfig [interface]`|Show neighbour devices.|WeOS4/5|
|`follow`| Continuously monitor a (log) file.|WeOS4/5|
|`factory-reset`| Perform factory reset of device.|WeOS4/5|




### Global Configuration Context:

| Command | Description | OS Version
| :--- | :--- | :--- |
| `aaa username [user] [password]` | Set a new password for a user. | WeOS4/5 |
| `system location [location]` | Sets a location for this device. | WeOS4/5 |
| `system hostname [hostname]` | Configures the device hostname. | WeOS4/5 |
| `iface [interface]:` | Enters configuration mode for a specific interface. | WeOS4/5 |
| `address [ip_address] [subnet_mask]` | Configures the IP address and subnet mask for an interface. | WeOS4 |
| `inet static [ip_address/prefix]` | Configures the IP address and subnet mask for an interface. | WeOS5 |
| `vlan [VID]` |Creates a VLAN. | WeOS4/5 |
| `no shutdown:` | Enables a disabled interface. | WeOS4/5 |
| `shutdown:` | Disables an interface. | WeOS4/5 |
| `ntp server [FQDN/IP-ADDR]` |Sets an NTP for this device. | WeOS4 |
| `ntp peer [FQDNP-ADDR]` |Sets an NTP for this device. | WeOS5 |



### Handling of files:

| Command | Description | OS Version
| :--- | :--- | :--- |
| `copy [source] [destination]:`| Copies files between different locations. | WeOS4/5|
| `upgrade primary [source_ip] [filename.pkg]`| Upgrade primary firmware from an FTP/TFTP server. | WeOS4/5|
| `upgrade secondary [source_ip] [filename.pkg]`| Upgrade secondary firmware from an FTP/TFTP server. | WeOS4/5|
| `upgrade boot [source_ip] [filename.pkg]`| Upgrade bootloader from an FTP/TFTP server. | WeOS4/5|

### General Abbreviations in Network Technology

| Abbreviation | Context (OSI Layer)             | Explanation                                                  |
|--------------|---------------------------------|--------------------------------------------------------------|
| AAA          | Security                        | Authentication, Authorization, and Accounting                |
| ADSL         | Connection (Layer 1)            | Asymmetric Digital Subscriber Line                           |
| CLI          | User Interface                  | Command Line Interface                                       |
| DMZ          | Security                        | Demilitarized Zone                                           |
| DNS          | Name Resolution (Layer 7)       | Domain Name System                                           |
| DoS          | Security                        | Denial of Service                                            |
| DSL          | Connection (Layer 1)            | Digital Subscriber Line                                      |
| DSSS         | Transmission Technique (Layer 1)| Direct Sequence Spread Spectrum                              |
| FTP          | Protocol (Layer 7)              | File Transfer Protocol                                       |
| GRE          | Tunneling (Layer 3)             | Generic Routing Encapsulation                                |
| GUI          | User Interface                  | Graphical User Interface                                     |
| HTTP         | Protocol (Layer 7)              | Hypertext Transfer Protocol                                  |
| HTTPS        | Protocol (Layer 7)              | Hypertext Transfer Protocol Secure                           |
| IKE          | Security (Layer 4)              | Internet Key Exchange                                        |
| IMAP         | Protocol (Layer 7)              | Internet Message Access Protocol                             |
| IPsec        | Security (Layer 3)              | Internet Protocol Security                                   |
| ISP          | Service Provider                | Internet Service Provider                                    |
| LDAP         | Directory Services (Layer 7)    | Lightweight Directory Access Protocol                        |
| MPLS         | Data Transmission (Layer 2.5)   | Multiprotocol Label Switching                                |
| MTU          | Data Transmission (Layer 3)     | Maximum Transmission Unit                                    |
| NTP          | Time Protocol (Layer 7)         | Network Time Protocol                                        |
| PAP          | Security (Layer 2)              | Password Authentication Protocol                             |
| PoE          | Power Supply                    | Power over Ethernet                                          |
| POP3         | Protocol (Layer 7)              | Post Office Protocol 3                                       |
| PPP          | Protocol (Layer 2)              | Point-to-Point Protocol                                      |
| PPTP         | Tunneling (Layer 2)             | Point-to-Point Tunneling Protocol                            |
| QoS          | Data Transmission (Layer 2/3)   | Quality of Service                                           |
| RMON         | Network Management (Layer 7)    | Remote Network Monitoring                                    |
| SCP          | Protocol (Layer 7)              | Secure Copy Protocol                                         |
| SFTP         | Protocol (Layer 7)              | Secure File Transfer Protocol                                |
| SMTP         | Protocol (Layer 7)              | Simple Mail Transfer Protocol                                |
| SNMP         | Network Management (Layer 7)    | Simple Network Management Protocol                           |
| SSH          | Protocol (Layer 7)              | Secure Shell                                                 |
| SSL          | Security (Layer 6)              | Secure Sockets Layer                                         |
| TCP          | Protocol (Layer 4)              | Transmission Control Protocol                                |
| TFTP         | Protocol (Layer 7)              | Trivial File Transfer Protocol                               |
| TLS          | Security (Layer 6)              | Transport Layer Security                                     |
| UDP          | Protocol (Layer 4)              | User Datagram Protocol                                       |
| VoIP         | Communication (Layer 7)         | Voice over Internet Protocol                                 |
| VPN          | Tunneling (Layer 3)             | Virtual Private Network                                      |
| WAN          | Network (Layer 1/2)             | Wide Area Network                                            |
| WWW          | Internet (Layer 7)              | World Wide Web                                               |

### Switching Abbreviations in Network Technology

| Abbreviation | Context (OSI Layer)             | Explanation                                                  |
|--------------|---------------------------------|--------------------------------------------------------------|
| ACL          | Security (Layer 2/3)            | Access Control List                                          |
| AP           | Network Device (Layer 2)        | Access Point                                                 |
| ARP          | Protocol (Layer 2)              | Address Resolution Protocol                                  |
| ATM          | Connection (Layer 2)            | Asynchronous Transfer Mode                                   |
| CSMA/CD      | Network Protocol (Layer 2)      | Carrier Sense Multiple Access with Collision Detection       |
| LAN          | Network (Layer 1/2)             | Local Area Network                                           |
| MAC          | Addressing (Layer 2)            | Media Access Control                                         |
| PPP          | Protocol (Layer 2)              | Point-to-Point Protocol                                      |
| PPTP         | Tunneling (Layer 2)             | Point-to-Point Tunneling Protocol                            |
| STP          | Protocol (Layer 2)              | Spanning Tree Protocol                                       |
| VLAN         | Network (Layer 2)               | Virtual Local Area Network                                   |
| WEP          | Security (Layer 2)              | Wired Equivalent Privacy                                     |
| Wi-Fi        | Network (Layer 1/2)             | Wireless Fidelity                                            |
| WLAN         | Network (Layer 1/2)             | Wireless Local Area Network                                  |
| WPA          | Security (Layer 2)              | Wi-Fi Protected Access                                       |

### Routing Abbreviations in Network Technology

| Abbreviation | Context (OSI Layer)             | Explanation                                                  |
|--------------|---------------------------------|--------------------------------------------------------------|
| AS           | Routing (Layer 3)               | Autonomous System                                            |
| BGP          | Routing (Layer 3)               | Border Gateway Protocol                                      |
| CIDR         | Addressing (Layer 3)            | Classless Inter-Domain Routing                               |
| GRE          | Tunneling (Layer 3)             | Generic Routing Encapsulation                                |
| ICMP         | Protocol (Layer 3)              | Internet Control Message Protocol                            |
| IGMP         | Protocol (Layer 3)              | Internet Group Management Protocol                           |
| IP           | Addressing (Layer 3)            | Internet Protocol                                            |
| IPv4         | Addressing (Layer 3)            | Internet Protocol version 4                                  |
| IPv6         | Addressing (Layer 3)            | Internet Protocol version 6                                  |
| MPLS         | Data Transmission (Layer 2.5)   | Multiprotocol Label Switching                                |
| MTU          | Data Transmission (Layer 3)     | Maximum Transmission Unit                                    |
| NAT          | Addressing (Layer 3)            | Network Address Translation                                  |
| OSPF         | Routing (Layer 3)               | Open Shortest Path First                                     |
| QoS          | Data Transmission (Layer 2/3)   | Quality of Service                                           |
| RIP          | Routing (Layer 3)               | Routing Information Protocol                                 |
| VPN          | Tunneling (Layer 3)             | Virtual Private Network                                      |


**Note:** Replace placeholders like [interface_name], [ip_address], [subnet_mask], etc.

### Versions WeOS 4.33.2 and WeOS 5.20.0
