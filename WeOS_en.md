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

### Abbreviations:


| Abkürzung | Kontext (OSI-Layer)                | Erklärung                                                    |
|-----------|------------------------------------|--------------------------------------------------------------|
| AAA       | Sicherheit                         | Authentication, Authorization, and Accounting                |
| ACL       | Sicherheit (Layer 2/3)             | Access Control List                                          |
| ADSL      | Verbindung (Layer 1)               | Asymmetric Digital Subscriber Line                           |
| AP        | Netzwerkgeräte (Layer 2)           | Access Point                                                 |
| ARP       | Protokoll (Layer 2)                | Address Resolution Protocol                                  |
| AS        | Routing (Layer 3)                  | Autonomous System                                            |
| ATM       | Verbindung (Layer 2)               | Asynchronous Transfer Mode                                   |
| BGP       | Routing (Layer 3)                  | Border Gateway Protocol                                      |
| CIDR      | Adressierung (Layer 3)             | Classless Inter-Domain Routing                               |
| CLI       | Benutzerschnittstelle              | Command Line Interface                                       |
| CSMA/CD   | Netzwerkprotokoll (Layer 2)        | Carrier Sense Multiple Access with Collision Detection       |
| DHCP      | Protokoll (Layer 7)                | Dynamic Host Configuration Protocol                          |
| DMZ       | Sicherheit                         | Demilitarized Zone                                           |
| DNS       | Namensauflösung (Layer 7)          | Domain Name System                                           |
| DoS       | Sicherheit                         | Denial of Service                                            |
| DSL       | Verbindung (Layer 1)               | Digital Subscriber Line                                      |
| DSSS      | Übertragungstechnik (Layer 1)      | Direct Sequence Spread Spectrum                              |
| FTP       | Protokoll (Layer 7)                | File Transfer Protocol                                       |
| GRE       | Tunneling (Layer 3)                | Generic Routing Encapsulation                                |
| GUI       | Benutzerschnittstelle              | Graphical User Interface                                     |
| HTTP      | Protokoll (Layer 7)                | Hypertext Transfer Protocol                                  |
| HTTPS     | Protokoll (Layer 7)                | Hypertext Transfer Protocol Secure                           |
| ICMP      | Protokoll (Layer 3)                | Internet Control Message Protocol                            |
| IGMP      | Protokoll (Layer 3)                | Internet Group Management Protocol                           |
| IKE       | Sicherheit (Layer 4)               | Internet Key Exchange                                        |
| IMAP      | Protokoll (Layer 7)                | Internet Message Access Protocol                             |
| IP        | Adressierung (Layer 3)             | Internet Protocol                                            |
| IPsec     | Sicherheit (Layer 3)               | Internet Protocol Security                                   |
| IPv4      | Adressierung (Layer 3)             | Internet Protocol version 4                                  |
| IPv6      | Adressierung (Layer 3)             | Internet Protocol version 6                                  |
| ISP       | Dienstanbieter                     | Internet Service Provider                                    |
| LAN       | Netzwerk (Layer 1/2)               | Local Area Network                                           |
| LDAP      | Verzeichnisdienste (Layer 7)       | Lightweight Directory Access Protocol                        |
| MAC       | Adressierung (Layer 2)             | Media Access Control                                         |
| MPLS      | Datenübertragung (Layer 2.5)       | Multiprotocol Label Switching                                |
| MTU       | Datenübertragung (Layer 3)         | Maximum Transmission Unit                                    |
| NAT       | Adressierung (Layer 3)             | Network Address Translation                                  |
| NTP       | Zeitprotokoll (Layer 7)            | Network Time Protocol                                        |
| OSPF      | Routing (Layer 3)                  | Open Shortest Path First                                     |
| PAP       | Sicherheit (Layer 2)               | Password Authentication Protocol                             |
| PoE       | Stromversorgung                    | Power over Ethernet                                          |
| POP3      | Protokoll (Layer 7)                | Post Office Protocol 3                                       |
| PPP       | Protokoll (Layer 2)                | Point-to-Point Protocol                                      |
| PPTP      | Tunneling (Layer 2)                | Point-to-Point Tunneling Protocol                            |
| QoS       | Datenübertragung (Layer 2/3)       | Quality of Service                                           |
| RIP       | Routing (Layer 3)                  | Routing Information Protocol                                 |
| RMON      | Netzwerkmanagement (Layer 7)       | Remote Network Monitoring                                    |
| SCP       | Protokoll (Layer 7)                | Secure Copy Protocol                                         |
| SFTP      | Protokoll (Layer 7)                | Secure File Transfer Protocol                                |
| SMTP      | Protokoll (Layer 7)                | Simple Mail Transfer Protocol                                |
| SNMP      | Netzwerkmanagement (Layer 7)       | Simple Network Management Protocol                           |
| SSH       | Protokoll (Layer 7)                | Secure Shell                                                 |
| SSL       | Sicherheit (Layer 6)               | Secure Sockets Layer                                         |
| STP       | Protokoll (Layer 2)                | Spanning Tree Protocol                                       |
| TCP       | Protokoll (Layer 4)                | Transmission Control Protocol                                |
| TFTP      | Protokoll (Layer 7)                | Trivial File Transfer Protocol                               |
| TLS       | Sicherheit (Layer 6)               | Transport Layer Security                                     |
| UDP       | Protokoll (Layer 4)                | User Datagram Protocol                                       |
| VLAN      | Netzwerk (Layer 2)                 | Virtual Local Area Network                                   |
| VoIP      | Kommunikation (Layer 7)            | Voice over Internet Protocol                                 |
| VPN       | Tunneling (Layer 3)                | Virtual Private Network                                      |
| WAN       | Netzwerk (Layer 1/2)               | Wide Area Network                                            |
| WEP       | Sicherheit (Layer 2)               | Wired Equivalent Privacy                                     |
| Wi-Fi     | Netzwerk (Layer 1/2)               | Wireless Fidelity                                            |
| WLAN      | Netzwerk (Layer 1/2)               | Wireless Local Area Network                                  |
| WPA       | Sicherheit (Layer 2)               | Wi-Fi Protected Access                                       |
| WWW       | Internet (Layer 7)                 | World Wide Web                                               |


**Note:** Replace placeholders like [interface_name], [ip_address], [subnet_mask], etc.

### Versions WeOS 4.33.2 and WeOS 5.20.0
