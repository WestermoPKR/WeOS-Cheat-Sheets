### Accessing the command line interface:

To login via the console port you need the username and password. Currently there is only a single user account defined, the administrator user account. Factory default account and password:
 Login: admin
 Password: westermo

Console Port Configuration:

| Setting | Value |
| :--- | :--- |
| Data rate | 115200 bits/s |
| Data bits | 8 |
| Stop bits | 1 |
| Parity | None |
| Flow control | None |

![photoeffekte com_](https://github.com/WesterMario/WeOS4-Cheat-Sheet/assets/166021733/bc87d8ed-6906-48d7-83eb-8e0482da66a6)


### WeOS4 Cheat Sheet

### Configuration Mode:

| Command | Description |
| :--- | :--- |
| `config terminal:` | Enters configuration mode. |
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

### Security Mode:

| Command | Description |
| :--- | :--- |
| `access-list [acl_number] permit/deny [source] [destination] [protocol]:` | Configures an access list. |
| `crypto key generate rsa:` | Generates RSA keys for SSH authentication. |
| `enable secret [password]:` | Configures an encrypted password for privileged mode. |
| `ssh [username]@[host]:` | Establishes an SSH connection to a remote host. |

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