# Zugriff auf die Befehlszeilenschnittstelle:

Um sich über den Konsolenport anzumelden, benötigen Sie Benutzername und Passwort. Derzeit ist nur ein einzelnes Benutzerkonto definiert, das Administratorkonto. Werkseinstellungskonto und Passwort:

### WeOS4
| Benutzername | Passwort |
| :--- | :--- |
| admin | westermo | 

### WeOS5
| Benutzername | Passwort |
| :--- | :--- |
| admin | admin |


## Konfiguration des Konsolenports:

| Einstellung | Wert |
| :--- | :--- |
| Datenrate | 115200 bits/s |
| Datenbits | 8 |
| Stoppbits | 1 |
| Parität | Keine |
| Flusssteuerung | Keine |

Treiber für virtuellen COM-Port (VCP): [https://ftdichip.com/drivers/vcp-drivers/](https://ftdichip.com/drivers/vcp-drivers/)

## Zugriff auf die CLI über SSH:
Um auf die CLI über SSH zuzugreifen, benötigen Sie einen SSH-Client, die IP-Adresse des Switches und Anmeldeinformationen (Benutzername/Passwort).


### Empfohlene SSH-Clients:

| Betriebssystem | Software | Link |
| :--- | :--- | :--- |
| Windows | PuTTY | [herunterladen](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) |
| UNIX | OpenSSH | [herunterladen](https://www.openssh.com) |



# WeOS Spickzettel

![photoeffekte com_-removebg-preview](https://github.com/WesterMario/WeOS4-Cheat-Sheet/assets/166021733/21fab82e-a942-445f-9f93-186e6a2bca6d)


### Administrativer Exec-Kontext
Im administrativen Exec-Kontext können Benutzer allgemeine Überwachung, Diagnose und die Verwaltung von Konfigurationsdateien und Firmware-Versionen durchführen. 
Sie können auch auf spezifische Ausführungskontexte zugreifen, wie zum Beispiel das Anzeigen von RMON-Statistiken.

### Globaler Konfigurationskontext
Vom administrativen Exec-Kontext aus können Benutzer auf den globalen Konfigurationskontext zugreifen.
Hier können sie Geräteparameter von globaler Bedeutung setzen, wie Hostname und Standort. 
Vom globalen Konfigurationskontext aus können Benutzer zu spezifischen Kontexten für Protokolle oder Geräteentitäten wie Ports, VLANs, Schnittstellen und FRNT navigieren.

### Navigation in den verschiedenen Kontextmenüs:

![photoeffekte com__1_-removebg-preview](https://github.com/WesterMario/WeOS4-Cheat-Sheet/assets/166021733/0a79ccf2-3f10-43f8-b897-830847777f88)


### Administrativer Exec-Kontext:

| Befehl | Beschreibung | OS-Version |
| :--- | :--- | :--- |
| `show` | Der Befehl "show" zeigt verschiedene Informationen wie Konfigurationen, Statistiken oder Status an. | WeOS4/5 | 
| `show ifaces` | Zeigt Informationen zu Schnittstellen an. | WeOS4/5 |
| `show ip route:` | Zeigt die IP-Routingtabelle an. | WeOS4/5 |
| `show arp` | Zeigt die ARP-Tabelle an. | WeOS4/5 |
| `show system` | Zeigt Systeminformationen über das Gerät an. | WeOS4/5 |
| `show system information` | . | WeOS4/5 |
| `ping [Ziel]:` | Sendet ICMP-Echo-Anfragen an das Ziel. | WeOS4/5 |
| `traceroute [Ziel]:` | Führt eine Traceroute zum Ziel aus. | WeOS4/5 |
| `ipcalc []:` | . |





### Globaler Konfigurationskontext:

| Befehl | Beschreibung | OS-Version
| :--- | :--- | :--- |
| `configure` | Betritt den globalen Konfigurationskontext. | WeOS4/5 | 
| `aaa username [Benutzer] [Passwort]` | Setzt ein neues Passwort für einen Benutzer. | WeOS4/5 |
| `system location [Standort]` | Setzt einen Standort für dieses Gerät. | WeOS4/5 |
| `system hostname [Hostname]` | Konfiguriert den Gerätenamen. | WeOS4/5 |
| `iface [Schnittstelle]:` | Betritt den Konfigurationsmodus für eine spezifische Schnittstelle. | WeOS4/5 |
| `address [IP-Adresse] [Subnetzmaske]` | Konfiguriert die IP-Adresse und Subnetzmaske für eine Schnittstelle. | WeOS4 |
| `inet static [IP-Adresse/Präfix]` | Konfiguriert die IP-Adresse und Subnetzmaske für eine Schnittstelle. | WeOS5 |
| `vlan [VID]` | Erstellt ein VLAN | WeOS4/5 |
| `no shutdown:` | Aktiviert eine deaktivierte Schnittstelle. | WeOS4/5 |
| `shutdown:` | Deaktiviert eine Schnittstelle. | WeOS4/5 |
| `ntp server [FQDN/IP-ADDR]` | Setzt einen NTP-Server für dieses Gerät | WeOS4 |
| `ntp peer [FQDNP-ADDR]` | Setzt einen NTP-Server für dieses Gerät | WeOS5 |



### Systemmodus:

| Befehl | Beschreibung |
| :--- | :--- |
| `copy [Quelle] [Ziel]:` | Kopiert Dateien zwischen verschiedenen Orten. |
| `show log:` | Zeigt Log-Nachrichten an. |
| `show processes:` | Zeigt laufende Prozesse an. |
| `show version:` | Zeigt Informationen zur aktuellen Systemversion an. |

### Grundbefehle:

| Befehl | Beschreibung |
| :--- | :--- |
| `exit:` | Beendet die CLI-Sitzung und kehrt zum vorherigen Menü zurück. |
| `help:` | Zeigt eine Liste der verfügbaren Befehle oder Hilfe für einen bestimmten Befehl an. |
| `reload:` | Startet das Gerät neu. |
| `save:` | Speichert die aktuelle Konfiguration. |


### Allgemeine Abkürzungen in der Netzwerktechnik

| Abkürzung | Kontext (OSI-Schicht)              | Erklärung                                                    |
|-----------|------------------------------------|--------------------------------------------------------------|
| AAA       | Sicherheit                         | Authentifizierung, Autorisierung und Abrechnung              |
| ADSL      | Verbindung (Schicht 1)             | Asymmetric Digital Subscriber Line                           |
| CLI       | Benutzeroberfläche                 | Command Line Interface                                       |
| DMZ       | Sicherheit                         | Entmilitarisierte Zone                                       |
| DNS       | Namensauflösung (Schicht 7)        | Domain Name System                                           |
| DoS       | Sicherheit                         | Denial of Service                                            |
| DSL       | Verbindung (Schicht 1)             | Digital Subscriber Line                                      |
| DSSS      | Übertragungstechnik (Schicht 1)    | Direct Sequence Spread Spectrum                              |
| FTP       | Protokoll (Schicht 7)              | File Transfer Protocol                                       |
| GRE       | Tunneling (Schicht 3)              | Generic Routing Encapsulation                                |
| GUI       | Benutzeroberfläche                 | Graphical User Interface                                     |
| HTTP      | Protokoll (Schicht 7)              | Hypertext Transfer Protocol                                  |
| HTTPS     | Protokoll (Schicht 7)              | Hypertext Transfer Protocol Secure                           |
| IKE       | Sicherheit (Schicht 4)             | Internet Key Exchange                                        |
| IMAP      | Protokoll (Schicht 7)              | Internet Message Access Protocol                             |
| IPsec     | Sicherheit (Schicht 3)             | Internet Protocol Security                                   |
| ISP       | Dienstanbieter                     | Internet Service Provider                                    |
| LDAP      | Verzeichnisdienste (Schicht 7)     | Lightweight Directory Access Protocol                        |
| MPLS      | Datenübertragung (Schicht 2.5)     | Multiprotocol Label Switching                                |
| MTU       | Datenübertragung (Schicht 3)       | Maximum Transmission Unit                                    |
| NTP       | Zeitprotokoll (Schicht 7)          | Network Time Protocol                                        |
| PAP       | Sicherheit (Schicht 2)             | Password Authentication Protocol                             |
| PoE       | Stromversorgung                    | Power over Ethernet                                          |
| POP3      | Protokoll (Schicht 7)              | Post Office Protocol 3                                       |
| PPP       | Protokoll (Schicht 2)              | Point-to-Point Protocol                                      |
| PPTP      | Tunneling (Schicht 2)              | Point-to-Point Tunneling Protocol                            |
| QoS       | Datenübertragung (Schicht 2/3)     | Quality of Service                                           |
| RMON      | Netzwerkmanagement (Schicht 7)     | Remote Network Monitoring                                    |
| SCP       | Protokoll (Schicht 7)              | Secure Copy Protocol                                         |
| SFTP      | Protokoll (Schicht 7)              | Secure File Transfer Protocol                                |
| SMTP      | Protokoll (Schicht 7)              | Simple Mail Transfer Protocol                                |
| SNMP      | Netzwerkmanagement (Schicht 7)     | Simple Network Management Protocol                           |
| SSH       | Protokoll (Schicht 7)              | Secure Shell                                                 |
| SSL       | Sicherheit (Schicht 6)             | Secure Sockets Layer                                         |
| TCP       | Protokoll (Schicht 4)              | Transmission Control Protocol                                |
| TFTP      | Protokoll (Schicht 7)              | Trivial File Transfer Protocol                               |
| TLS       | Sicherheit (Schicht 6)             | Transport Layer Security                                     |
| UDP       | Protokoll (Schicht 4)              | User Datagram Protocol                                       |
| VoIP      | Kommunikation (Schicht 7)          | Voice over Internet Protocol                                 |
| VPN       | Tunneling (Schicht 3)              | Virtual Private Network                                      |
| WAN       | Netzwerk (Schicht 1/2)             | Wide Area Network                                            |
| WWW       | Internet (Schicht 7)               | World Wide Web                                               |

### Abkürzungen für Switching in der Netzwerktechnik

| Abkürzung | Kontext (OSI-Schicht)              | Erklärung                                                    |
|-----------|------------------------------------|--------------------------------------------------------------|
| ACL       | Sicherheit (Schicht 2/3)           | Access Control List                                          |
| AP        | Netzwerkgerät (Schicht 2)          | Access Point                                                 |
| ARP       | Protokoll (Schicht 2)              | Address Resolution Protocol                                  |
| ATM       | Verbindung (Schicht 2)             | Asynchronous Transfer Mode                                   |
| CSMA/CD   | Netzwerkprotokoll (Schicht 2)      | Carrier Sense Multiple Access with Collision Detection       |
| LAN       | Netzwerk (Schicht 1/2)             | Local Area Network                                           |
| MAC       | Adressierung (Schicht 2)           | Media Access Control                                         |
| PPP       | Protokoll (Schicht 2)              | Point-to-Point Protocol                                      |
| PPTP      | Tunneling (Schicht 2)              | Point-to-Point Tunneling Protocol                            |
| STP       | Protokoll (Schicht 2)              | Spanning Tree Protocol                                       |
| VLAN      | Netzwerk (Schicht 2)               | Virtual Local Area Network                                   |
| WEP       | Sicherheit (Schicht 2)             | Wired Equivalent Privacy                                     |
| Wi-Fi     | Netzwerk (Schicht 1/2)             | Wireless Fidelity                                            |
| WLAN      | Netzwerk (Schicht 1/2)             | Wireless Local Area Network                                  |
| WPA       | Sicherheit (Schicht 2)             | Wi-Fi Protected Access                                       |

### Abkürzungen für Routing in der Netzwerktechnik

| Abkürzung | Kontext (OSI-Schicht)              | Erklärung                                                    |
|-----------|------------------------------------|--------------------------------------------------------------|
| AS        | Routing (Schicht 3)                | Autonomous System                                            |
| BGP       | Routing (Schicht 3)                | Border Gateway Protocol                                      |
| CIDR      | Adressierung (Schicht 3)           | Classless Inter-Domain Routing                               |
| GRE       | Tunneling (Schicht 3)              | Generic Routing Encapsulation                                |
| ICMP      | Protokoll (Schicht 3)              | Internet Control Message Protocol                            |
| IGMP      | Protokoll (Schicht 3)              | Internet Group Management Protocol                           |
| IP        | Adressierung (Schicht 3)           | Internet Protocol                                            |
| IPv4      | Adressierung (Schicht 3)           | Internet Protocol version 4                                  |
| IPv6      | Adressierung (Schicht 3)           | Internet Protocol version 6                                  |
| MPLS      | Datenübertragung (Schicht 2.5)     | Multiprotocol Label Switching                                |
| MTU       | Datenübertragung (Schicht 3)       | Maximum Transmission Unit                                    |
| NAT       | Adressierung (Schicht 3)           | Network Address Translation                                  |
| OSPF      | Routing (Schicht 3)                | Open Shortest Path First                                     |
| QoS       | Datenübertragung (Schicht 2/3)     | Quality of Service                                           |
| RIP       | Routing (Schicht 3)                | Routing Information Protocol                                 |
| VPN       | Tunneling (Schicht 3)              | Virtual Private Network                                      |


### Hinweis: Ersetzen Sie Platzhalter wie [Schnittstellenname], [IP-Adresse], [Subnetzmaske] usw.
Versionen WeOS 4.33.2 und WeOS 5.20.0
