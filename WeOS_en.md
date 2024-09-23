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
- [Common Abbreviations in Network Technology](#common-abbreviations-in-network-technology)
  - [Switching Abbreviations](#switching-abbreviations)
  - [Routing Abbreviations](#routing-abbreviations)

---

To log in via the console port, you need the username and password. Currently, there is only a single user account defined, the administrator user account. Factory default account and password:

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

---

### Console Port Configuration:

| Setting      | Value             |
|--------------|-------------------|
| Data rate    | 115200 bits/s     |
| Data bits    | 8                 |
| Stop bits    | 1                 |
| Parity       | None              |
| Flow control  | None             |

Virtual COM port (VCP) driver: [FTDI VCP Drivers](https://ftdichip.com/drivers/vcp-drivers/)

---

## Accessing the CLI via SSH

To access the CLI via SSH, you need an SSH client, the switch IP address, and account credentials (username/password).

### Recommended SSH Clients:

| OS       | Software  | Link                                                        |
|----------|-----------|-------------------------------------------------------------|
| Windows  | PuTTY     | [Download](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) |
| UNIX     | OpenSSH   | [Download](https://www.openssh.com)                         |

---

# WeOS Cheat Sheet

![WeOS Logo](<Screenshot 2024-04-16 155850.png>)

### Admin Exec Context

In the Admin Exec context, users can perform general monitoring, diagnostics, and manage configuration files and firmware versions. They can also access specific execution contexts, such as viewing RMON statistics.

### Global Configuration Context

From the Admin Exec context, users can access the Global Configuration context. Here, they can set device parameters of global significance, like hostname and location. From the Global Configuration context, users can navigate to specific contexts for protocols or device entities such as ports, VLANs, interfaces, and FRNT.

### Navigating Different Context Menus:

![WeOS Logo](<Screenshot 2024-04-16 155831.png>)


| Command                      | Description                                              | OS Version |
|------------------------------|---------------------------------------------------------|------------|
| `configure`                  | Enters Global Configuration context.                    | WeOS4/5    |
| `logout`                     | Logs you out of the device.                             | WeOS4/5    |
| `vlan [#]`                   | Enters VLAN Config. Context from Global Config.        | WeOS4/5    |
| `port eth[#] / dsl[#]`      | Enters Port Config. Context from Global Config.        | WeOS4/5    |
| `port ethx[#]`              | Viper devices. Enters Port Config. Context from Global Config. | WeOS4/5 |
| `port ser[#]`               | LynxDSS devices. Enters Port Config. Context from Global Config. | WeOS4/5 |
| `ip`                         | Enters IP Config. Context from Global Config.          | WeOS4/5    |
| `firewall`                   | Enters Firewall/NAT Config. Context from General IP Config. | WeOS4/5 |
| `end`                        | Returns to the previous mode.                           | WeOS4/5    |

---

### Admin Exec Context (Commands):

| Command                    | Description                                              | OS Version |
|----------------------------|---------------------------------------------------------|------------|
| `show`                     | Displays various information such as configurations.    | WeOS4/5    |
| `do`                       | Executes a command from different contexts.             | WeOS4/5    |
| `show ifaces`             | Displays information about interfaces.                  | WeOS4/5    |
| `show ip route`           | Displays the IP routing table.                          | WeOS4/5    |
| `show arp`                | Displays the ARP table.                                | WeOS4/5    |
| `show log`                | Displays the logs of the device.                       | WeOS4/5    |
| `show system`             | Displays system information about the device.          | WeOS4/5    |
| `show version`            | Displays information about the current system version.  | WeOS4/5    |
| `ping [destination]`      | Sends ICMP echo requests to the destination.           | WeOS4/5    |
| `traceroute [destination]`| Performs a traceroute to the destination.              | WeOS4/5    |
| `ipcalc [address]`        | Provides detailed information about IP addresses.       | WeOS4/5    |
| `repeat [command]`        | Executes a specified command multiple times.           | WeOS4/5    |
| `uptime`                  | Duration since the last restart.                        | WeOS4/5    |
| `ssh [user@address]`      | Secure shell login to another host.                     | WeOS4/5    |
| `ipcalc`                  | An IP Netmask/broadcast/etc calculator.                 | WeOS4/5    |
| `reboot`                  | Reboots this device.                                   | WeOS4/5    |
| `ipconfig [interface]`    | Shows neighbour devices.                               | WeOS4/5    |
| `follow`                  | Continuously monitor a (log) file.                     | WeOS4/5    |
| `factory-reset`           | Performs a factory reset of the device.                | WeOS4/5    |

---

### Global Configuration Context (Commands):

| Command                                     | Description                                             | OS Version |
|---------------------------------------------|---------------------------------------------------------|------------|
| `aaa username [user] [password]`           | Set a new password for a user.                         | WeOS4/5    |
| `system location [location]`                | Sets a location for this device.                       | WeOS4/5    |
| `system hostname [hostname]`                | Configures the device hostname.                        | WeOS4/5    |
| `iface [interface]:`                        | Enters configuration mode for a specific interface.    | WeOS4/5    |
| `address [ip_address] [subnet_mask]`       | Configures the IP address and subnet mask for an interface. | WeOS4 |
| `inet static [ip_address/prefix]`          | Configures the IP address and subnet mask for an interface. | WeOS5 |
| `vlan [VID]`                                | Creates a VLAN.                                       | WeOS4/5    |
| `no shutdown:`                               | Enables a disabled interface.                          | WeOS4/5    |
| `shutdown:`                                  | Disables an interface.                                 | WeOS4/5    |
| `ntp server [FQDN/IP-ADDR]`                 | Sets an NTP for this device.                          | WeOS4      |
| `ntp peer [FQDN/IP-ADDR]`                   | Sets an NTP for this device.                          | WeOS5      |

---

### File Handling:

| Command                                      | Description                                          | OS Version |
|----------------------------------------------|-----------------------------------------------------|------------|
| `copy [src] [dest]:`                        | Copies files between locations.                     | WeOS4/5    |
| `upgrade primary [src_ip] [file.pkg]`      | Update primary firmware from server.                | WeOS4/5    |
| `upgrade secondary [src_ip] [file.pkg]`    | Update secondary firmware from server.              | WeOS4/5    |
| `upgrade boot [src_ip] [file.pkg]`         | Update bootloader from server.                      | WeOS4/5    |

---

## Common Abbreviations in Network Technology

### General Abbreviations

| Abbreviation | Context (OSI Layer)        | Explanation                                            |
|--------------|-----------------------------|-------------------------------------------------------|
| AAA          | Security                    | Authentication, Authorization, and Accounting         |
| CLI          | User Interface              | Command Line Interface                                 |
| DNS          | Name Resolution (Layer 7)   | Domain Name System                                    |
| DoS          | Security                    | Denial of Service                                     |
| FTP          | Protocol (Layer 7)          | File Transfer Protocol                                |
| HTTP         | Protocol (Layer 7)          | Hypertext Transfer Protocol                           |
| IPsec        | Security (Layer 3)          | Internet Protocol Security                            |
| ISP          | Service Provider            | Internet Service Provider                             |
| MTU          | Data Transmission (Layer 3) | Maximum Transmission Unit                             |
| NTP          | Time Protocol (Layer 7)     | Network Time Protocol                                 |
| QoS          | Data Transmission (Layer 2/3)| Quality of Service                                    |
| SNMP         | Network Management (Layer 7) | Simple Network Management Protocol                    |
| SSH          | Protocol (Layer 7)          | Secure Shell                                          |
| SSL          | Security (Layer 6)          | Secure Sockets Layer                                  |
| TCP          | Protocol (Layer 4)          | Transmission Control Protocol                         |
| UDP          | Protocol (Layer 4)          | User Datagram Protocol                                |
| VoIP         | Communication (Layer 7)     | Voice over Internet Protocol                          |
| VPN          | Tunneling (Layer 3)         | Virtual Private Network                                |

---

### Switching Abbreviations

| Abbreviation | Context (OSI Layer)        | Explanation                                            |
|--------------|-----------------------------|-------------------------------------------------------|
| ACL          | Security (Layer 2/3)        | Access Control List                                   |
| AP           | Network Device (Layer 2)    | Access Point                                          |
| ARP          | Protocol (Layer 2)          | Address Resolution Protocol                           |
| CSMA/CD      | Network Protocol (Layer 2)  | Carrier Sense Multiple Access with Collision Detection |
| LAN          | Network (Layer 1/2)         | Local Area Network                                    |
| MAC          | Addressing (Layer 2)        | Media Access Control                                  |
| VLAN         | Network (Layer 2)           | Virtual Local Area Network                            |
| Wi-Fi        | Network (Layer 1/2)         | Wireless Fidelity                                     |

---

### Routing Abbreviations

| Abbreviation | Context (OSI Layer)        | Explanation                                            |
|--------------|-----------------------------|-------------------------------------------------------|
| BGP          | Routing (Layer 3)           | Border Gateway Protocol                               |
| CIDR         | Addressing (Layer 3)        | Classless Inter-Domain Routing                        |
| GRE          | Tunneling (Layer 3)         | Generic Routing Encapsulation                         |
| ICMP         | Protocol (Layer 3)          | Internet Control Message Protocol                     |
| IP           | Addressing (Layer 3)        | Internet Protocol                                     |
| OSPF         | Routing (Layer 3)           | Open Shortest Path First                              |
| RIP          | Routing (Layer 3)           | Routing Information Protocol                          |

---

**Note:** Replace placeholders like `[interface_name]`, `[ip_address]`, `[subnet_mask]`, etc.

### Versions WeOS 4.33.2 and WeOS 5.20.1
