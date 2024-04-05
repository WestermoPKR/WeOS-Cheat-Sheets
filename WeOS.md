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


## Console Port Configuration:

| Setting | Value |
| :--- | :--- |
| Data rate | 115200 bits/s |
| Data bits | 8 |
| Stop bits | 1 |
| Parity | None |
| Flow control | None |

Virtual COM port (VCP) driver: https://ftdichip.com/drivers/vcp-drivers/

## Accessing the CLI via SSH:

### Recommended SSH Clients:

| OS | Software | Link |
| :--- | :--- | :--- |
| Windows | PuTTY | https://www.chiark.greenend.org.uk/~sgtatham/putty/](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html |
| UNIX | OpenSSH | https://www.openssh.com |



# WeOS Cheat Sheet

![photoeffekte com_-removebg-preview](https://github.com/WesterMario/WeOS4-Cheat-Sheet/assets/166021733/21fab82e-a942-445f-9f93-186e6a2bca6d)


### Admin Exec context
In the Admin Exec context, users can perform general monitoring, diagnostics, and manage configuration files and firmware versions. 
They can also access specific execution contexts, such as viewing RMON statistics.

### Global Configuration context
From the Admin Exec context, users can access the Global Configuration context.
Here, they can set device parameters of global significance, like hostname and location. 
From Global Configuration, users can navigate to specific contexts for protocols or device entities such as ports, VLANs, interfaces, and FRNT.


### Configuration Mode:

| Command | Description |
| :--- | :--- |
| `configure` | Enters configuration mode. | 
| `description [description_text]:` | Configures a description for an interface. |
| `enable password [password]:` | Sets a password for privileged mode. |
| `hostname [hostname]:` | Configures the device hostname. |
| `interface [interface_name]:` | Enters configuration mode for a specific interface. |
| `ip address [ip_address] [subnet_mask]:` | Configures the IP address and subnet mask for an interface. |
| `no shutdown:` | Enables a previously disabled interface. |
| `shutdown:` | Disables an interface. |

### Monitoring and Diagnostics:

| Command | Description |
| :--- | :--- |
| `ping [destination]:` | Sends ICMP echo requests to the destination. |
| `show arp:` | Displays the ARP table. |
| `show interfaces:` | Displays information about interfaces. |
| `show ip route:` | Displays the IP routing table. |
| `traceroute [destination]:` | Performs a traceroute to the destination. |

### System Mode:

| Command | Description |
| :--- | :--- |
| `copy [source] [destination]:` | Copies files between different locations. |
| `show log:` | Displays log messages. |
| `show processes:` | Displays running processes. |
| `show version:` | Displays information about the current system version. |

### Basic Commands:

| Command | Description |
| :--- | :--- |
| `exit:` | Exits the CLI session and returns to the previous menu. |
| `help:` | Displays a list of available commands or help for a specific command. |
| `reload:` | Restarts the device. |
| `save:` | Saves the current configuration. |
| `set:` | Sets configuration parameters. |
| `show:` | Displays information such as configurations, statistics, or status. |

**Note:** Replace placeholders like [interface_name], [ip_address], [subnet_mask], etc.