## Table of Contents

- [Accessing the Command Line Interface](#accessing-the-command-line-interface)
  - [WeOS 4](#weos-4)
  - [WeOS 5](#weos-5)
- [Console Port Configuration](#console-port-configuration)
- [Accessing the CLI via SSH](#accessing-the-cli-via-ssh)
  - [Recommended SSH Clients](#recommended-ssh-clients)
- [WeOS Cheat Sheet](#weos-cheat-sheet)
  - [Admin Exec Context](#admin-exec-context)
  - [Global Configuration Context](#global-configuration-context)
  - [Navigating Different Context Menus](#navigating-different-context-menus)
- [Admin Exec Context (Commands)](#admin-exec-context-commands)
- [Global Configuration Context (Commands)](#global-configuration-context-commands)
- [File Handling](#file-handling)
- [General Abbreviations in Network Technology](#general-abbreviations-in-network-technology)
  - [Switching Abbreviations](#switching-abbreviations)
  - [Routing Abbreviations](#routing-abbreviations)


To login via the console port you need the username and password. Currently, there is only a single user account defined, the administrator user account. Factory default account and password:

### User Accounts

<table>
    <tr>
        <th>WeOS4</th>
        <th>WeOS5</th>
    </tr>
    <tr>
        <td>
            <table>
                <tr>
                    <th>Username</th>
                    <th>Password</th>
                </tr>
                <tr>
                    <td>admin</td>
                    <td>westermo</td>
                </tr>
            </table>
        </td>
        <td>
            <table>
                <tr>
                    <th>Username</th>
                    <th>Password</th>
                </tr>
                <tr>
                    <td>admin</td>
                    <td>admin</td>
                </tr>
            </table>
        </td>
    </tr>
</table>

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

| Command | Description | OS Version |
| :--- | :--- | :--- |
| <button onclick="copyToClipboard('configure')">`configure`</button> | Enters Global Configuration context. | WeOS4/5 |
| <button onclick="copyToClipboard('logout')">`logout`</button> | Logged you out of the device. | WeOS4/5 |
| <button onclick="copyToClipboard('vlan [#]')">`vlan [#]`</button> | Enters VLAN Config. Context from Global Config. Context. | WeOS4/5 |
| <button onclick="copyToClipboard('port eth[#] / dsl[#]')">`port eth[#] / dsl[#]`</button> | Enters Port Config. Context from Global Config. Context. | WeOS4/5 |
| <button onclick="copyToClipboard('port ethx[#]')">`port ethx[#]`</button> | Viper devices. Enters Port Config. Context from Global Config. Context. | WeOS4/5 |
| <button onclick="copyToClipboard('port ser[#]')">`port ser[#]`</button> | LynxDSS devices. Enters Port Config. Context from Global Config. Context. | WeOS4/5 |
| <button onclick="copyToClipboard('ip')">`ip`</button> | Enters IP Config. Context from Global Config. Context. | WeOS4/5 |
| <button onclick="copyToClipboard('firewall')">`firewall`</button> | Enters Firewall/NAT Config. Context from General IP Config. Context. | WeOS4/5 |
| <button onclick="copyToClipboard('end')">`end`</button> | Return to the previous mode. | WeOS4/5 |


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



| Command                                      | Description                                          | Example Command                             | OS Version |
|----------------------------------------------|-----------------------------------------------------|---------------------------------------------|------------|
| `copy [source] [destination]:`              | Copies files between different locations.           | `copy flash:/config.txt usb:/backup/`     | WeOS4/5    |
| `upgrade primary [source_ip] [filename.pkg]`| Upgrade primary firmware from an FTP/TFTP server.   | `upgrade primary 192.168.1.100 firmware.pkg` | WeOS4/5    |
| `upgrade secondary [source_ip] [filename.pkg]`| Upgrade secondary firmware from an FTP/TFTP server. | `upgrade secondary 192.168.1.100 firmware.pkg` | WeOS4/5    |
| `upgrade boot [source_ip] [filename.pkg]`   | Upgrade bootloader from an FTP/TFTP server.         | `upgrade boot 192.168.1.100 bootloader.pkg` | WeOS4/5    |




## Allgemeine Abkürzungen in der Netzwerktechnologie

### Allgemeine Abkürzungen

| Abkürzung | Kontext (OSI-Schicht)         | Erklärung                                                  |
|-----------|-------------------------------|-----------------------------------------------------------|
| AAA       | Sicherheit                    | Authentifizierung, Autorisierung und Abrechnung           |
| CLI       | Benutzeroberfläche            | Kommandozeilen-Schnittstelle                              |
| DNS       | Namensauflösung (Schicht 7)   | Domain Name System                                        |
| DoS       | Sicherheit                    | Denial of Service                                         |
| FTP       | Protokoll (Schicht 7)         | File Transfer Protocol                                    |
| HTTP      | Protokoll (Schicht 7)         | Hypertext Transfer Protocol                               |
| IPsec     | Sicherheit (Schicht 3)        | Internet Protocol Security                                |
| ISP       | Dienstanbieter                | Internet Service Provider                                 |
| MTU       | Datenübertragung (Schicht 3)  | Maximum Transmission Unit                                 |
| NTP       | Zeitprotokoll (Schicht 7)     | Network Time Protocol                                     |
| QoS       | Datenübertragung (Schicht 2/3) | Quality of Service                                        |
| SNMP      | Netzwerkmanagement (Schicht 7) | Simple Network Management Protocol                        |
| SSH       | Protokoll (Schicht 7)         | Secure Shell                                              |
| SSL       | Sicherheit (Schicht 6)        | Secure Sockets Layer                                      |
| TCP       | Protokoll (Schicht 4)         | Transmission Control Protocol                             |
| UDP       | Protokoll (Schicht 4)         | User Datagram Protocol                                    |
| VoIP      | Kommunikation (Schicht 7)     | Voice over Internet Protocol                              |
| VPN       | Tunneling (Schicht 3)         | Virtuelles Privates Netzwerk                              |

### Abkürzungen für Switching

| Abkürzung | Kontext (OSI-Schicht)         | Erklärung                                                  |
|-----------|-------------------------------|-----------------------------------------------------------|
| ACL       | Sicherheit (Schicht 2/3)      | Access Control List                                       |
| AP        | Netzwerkgerät (Schicht 2)      | Access Point                                              |
| ARP       | Protokoll (Schicht 2)         | Address Resolution Protocol                               |
| CSMA/CD   | Netzwerkprotokoll (Schicht 2)  | Carrier Sense Multiple Access mit Kollisionsdetektion     |
| LAN       | Netzwerk (Schicht 1/2)         | Local Area Network                                        |
| MAC       | Adressierung (Schicht 2)       | Media Access Control                                      |
| VLAN      | Netzwerk (Schicht 2)           | Virtuelles Lokales Netzwerk                                |
| Wi-Fi     | Netzwerk (Schicht 1/2)         | Wireless Fidelity                                         |

### Routing-Abkürzungen

| Abkürzung | Kontext (OSI-Schicht)         | Erklärung                                                  |
|-----------|-------------------------------|-----------------------------------------------------------|
| BGP       | Routing (Schicht 3)           | Border Gateway Protocol                                   |
| CIDR      | Adressierung (Schicht 3)      | Classless Inter-Domain Routing                            |
| GRE       | Tunneling (Schicht 3)         | Generic Routing Encapsulation                             |
| ICMP      | Protokoll (Schicht 3)         | Internet Control Message Protocol                         |
| IP        | Adressierung (Schicht 3)      | Internet Protocol                                         |
| OSPF      | Routing (Schicht 3)           | Open Shortest Path First                                  |
| RIP       | Routing (Schicht 3)           | Routing Information Protocol                              |


**Hinweis:** Ersetze Platzhalter wie `[interface_name]`, `[ip_address]`, `[subnet_mask]` usw.

### Versionen WeOS 4.33.2 und WeOS 5.20.1

