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

# Abbreviations:



**Note:** Replace placeholders like [interface_name], [ip_address], [subnet_mask], etc.

### Versions WeOS 4.33.2 and WeOS 5.20.0
