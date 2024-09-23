## Inhaltsverzeichnis

- [Zugriff auf die Kommandozeilenschnittstelle](#zugriff-auf-die-kommandozeilenschnittstelle)
  - [WeOS 4](#weos-4)
  - [WeOS 5](#weos-5)
- [Konfiguration des Konsolenports](#konfiguration-des-konsolenports)
- [Zugriff auf die CLI via SSH](#zugriff-auf-die-cli-via-ssh)
  - [Empfohlene SSH-Clients](#empfohlene-ssh-clients)
- [WeOS Spickzettel](#weos-spickzettel)
  - [Admin Exec Kontext](#admin-exec-kontext)
  - [Globaler Konfigurationskontext](#globaler-konfigurationskontext)
  - [Navigation in den verschiedenen Kontextmenüs](#navigation-in-den-verschiedenen-kontextmenüs)
- [Admin Exec Kontext (Befehle)](#admin-exec-kontext-befehle)
- [Globaler Konfigurationskontext (Befehle)](#globaler-konfigurationskontext-befehle)
- [Dateihandhabung](#dateihandhabung)
- [Allgemeine Abkürzungen in der Netzwerktechnologie](#allgemeine-abkürzungen-in-der-netzwerktechnologie)
  - [Abkürzungen für Switching](#abkürzungen-für-switching)
  - [Routing-Abkürzungen](#routing-abkürzungen)

---

Um sich über den Konsolenport anzumelden, benötigen Sie den Benutzernamen und das Passwort. Derzeit ist nur ein einziges Benutzerkonto definiert, das Administrator-Benutzerkonto. Fabrikeinstellungen für Konto und Passwort:

### Benutzerkonten

<table>
    <tr>
        <th>WeOS4</th>
        <th>WeOS5</th>
    </tr>
    <tr>
        <td>
            <table>
                <tr>
                    <th>Benutzername</th>
                    <th>Passwort</th>
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
                    <th>Benutzername</th>
                    <th>Passwort</th>
                </tr>
                <tr>
                    <td>admin</td>
                    <td>admin</td>
                </tr>
            </table>
        </td>
    </tr>
</table>

### Konfiguration des Konsolenports:

| Einstellung    | Wert             |
|----------------|------------------|
| Datenrate      | 115200 bits/s    |
| Datenbits      | 8                |
| Stoppbits      | 1                |
| Parität        | Keine            |
| Flusskontrolle | Keine            |

Virtueller COM-Port (VCP) Treiber: [FTDI VCP Treiber](https://ftdichip.com/drivers/vcp-drivers/)

---

## Zugriff auf die CLI via SSH

Um auf die CLI via SSH zuzugreifen, benötigen Sie einen SSH-Client, die IP-Adresse des Switches und Kontozugangsdaten (Benutzername/Passwort).

### Empfohlene SSH-Clients:

| Betriebssystem | Software | Link                                                        |
|----------------|----------|-------------------------------------------------------------|
| Windows        | PuTTY    | [Download](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) |
| UNIX           | OpenSSH  | [Download](https://www.openssh.com)                         |

---

# WeOS Spickzettel

![WeOS Logo](<Screenshot 2024-04-16 155850.png>)

### Admin Exec Kontext

Im Admin Exec Kontext können Benutzer allgemeine Überwachungs- und Diagnoseaufgaben durchführen sowie Konfigurationsdateien und Firmware-Versionen verwalten. Sie können auch auf spezifische Ausführungskontexte zugreifen, wie z. B. das Anzeigen von RMON-Statistiken.

### Globaler Konfigurationskontext

Vom Admin Exec Kontext aus können Benutzer auf den Globalen Konfigurationskontext zugreifen. Hier können sie Geräteeinstellungen von globaler Bedeutung festlegen, wie z. B. Hostname und Standort. Vom Globalen Konfigurationskontext aus können Benutzer zu spezifischen Kontexten für Protokolle oder Geräteeinheiten wie Ports, VLANs, Schnittstellen und FRNT navigieren.

### Navigation in den verschiedenen Kontextmenüs:

| Befehl                      | Beschreibung                                              | OS-Version |
|-----------------------------|-----------------------------------------------------------|------------|
| `configure`                 | Wechselt in den Globalen Konfigurationskontext.           | WeOS4/5    |
| `logout`                    | Meldet Sie vom Gerät ab.                                  | WeOS4/5    |
| `vlan [#]`                  | Wechselt in den VLAN-Kontext vom Globalen Konfigurationskontext aus. | WeOS4/5 |
| `port eth[#] / dsl[#]`      | Wechselt in den Port-Kontext vom Globalen Konfigurationskontext aus. | WeOS4/5 |
| `port ethx[#]`              | Viper-Geräte: Wechselt in den Port-Kontext.               | WeOS4/5    |
| `port ser[#]`               | LynxDSS-Geräte: Wechselt in den Port-Kontext.             | WeOS4/5    |
| `ip`                        | Wechselt in den IP-Konfigurationskontext.                 | WeOS4/5    |
| `firewall`                  | Wechselt in den Firewall/NAT-Kontext vom IP-Kontext aus.  | WeOS4/5    |
| `end`                       | Kehrt zum vorherigen Modus zurück.                        | WeOS4/5    |

---

### Admin Exec Kontext (Befehle):

| Befehl                     | Beschreibung                                              | OS-Version |
|----------------------------|-----------------------------------------------------------|------------|
| `show`                     | Zeigt verschiedene Informationen wie Konfigurationen, Statistiken oder Status an. | WeOS4/5 |
| `do`                       | Führt einen Befehl aus einem anderen Kontext aus.         | WeOS4/5    |
| `show ifaces`              | Zeigt Informationen über Schnittstellen an.               | WeOS4/5    |
| `show ip route`            | Zeigt die IP-Routing-Tabelle an.                          | WeOS4/5    |
| `show arp`                 | Zeigt die ARP-Tabelle an.                                 | WeOS4/5    |
| `show log`                 | Zeigt die Protokolle des Geräts an.                       | WeOS4/5    |
| `show system`              | Zeigt Systeminformationen über das Gerät an.              | WeOS4/5    |
| `show version`             | Zeigt Informationen über die aktuelle Systemversion an.   | WeOS4/5    |
| `ping [ziel]`              | Sendet ICMP-Echo-Anfragen an das Ziel.                    | WeOS4/5    |
| `traceroute [ziel]`        | Führt eine Traceroute zum Ziel durch.                     | WeOS4/5    |
| `ipcalc [adresse]`         | Bietet Informationen über IP-Adressen und Subnetze.       | WeOS4/5    |
| `repeat [befehl]`          | Führt einen angegebenen Befehl mehrfach aus.              | WeOS4/5    |
| `uptime`                   | Zeigt die Betriebszeit seit dem letzten Neustart an.      | WeOS4/5    |
| `ssh [user@adresse]`       | Secure Shell Login zu einem anderen Host.                 | WeOS4/5    |
| `ipcalc`                   | IP-Netzmasken-/Broadcast-Rechner.                         | WeOS4/5    |
| `reboot`                   | Startet das Gerät neu.                                    | WeOS4/5    |
| `ipconfig [schnittstelle]` | Zeigt Nachbargeräte an.                                   | WeOS4/5    |
| `follow`                   | Überwacht kontinuierlich eine (Log-)Datei.                | WeOS4/5    |
| `factory-reset`            | Führt einen Werksreset des Geräts durch.                  | WeOS4/5    |

---

### Globaler Konfigurationskontext (Befehle):

| Befehl                            | Beschreibung                                            | OS-Version |
|-----------------------------------|---------------------------------------------------------|------------|
| `aaa username [user] [password]`  | Setzt ein neues Passwort für einen Benutzer.            | WeOS4/5    |
| `system location [location]`      | Legt einen Standort für dieses Gerät fest.              | WeOS4/5    |
| `system hostname [hostname]`      | Konfiguriert den Gerätenamen.                           | WeOS4/5    |
| `iface [schnittstelle]`           | Wechselt in den Konfigurationsmodus für eine Schnittstelle. | WeOS4/5 |
| `address [ip_adresse] [subnetz]`  | Konfiguriert IP-Adresse und Subnetzmaske für eine Schnittstelle. | WeOS4 |
| `inet static [ip_adresse/prefix]` | Konfiguriert IP-Adresse und Subnetzmaske für eine Schnittstelle. | WeOS5 |
| `vlan [VID]`                      | Erstellt ein VLAN.                                      | WeOS4/5    |
| `no shutdown`                     | Aktiviert eine deaktivierte Schnittstelle.              | WeOS4/5    |
| `shutdown`                        | Deaktiviert eine Schnittstelle.                         | WeOS4/5    |
| `ntp server [FQDN/IP-ADDR]`       | Setzt einen NTP-Server für dieses Gerät.                | WeOS4      |
| `ntp peer [FQDN/IP-ADDR]`         | Setzt einen NTP-Server für dieses Gerät.                | WeOS5      |

---

### Dateihandhabung:

| Befehl                                       | Beschreibung                                            | OS-Version |
|----------------------------------------------|---------------------------------------------------------|------------|
| `copy [quelle] [ziel]`                       | Kopiert Dateien zwischen verschiedenen Orten.           | WeOS4/5    |
| `upgrade primary [quelle_ip] [datei.pkg]`    | Aktualisiert die primäre Firmware von einem FTP/TFTP-Server. | WeOS4/5 |
| `upgrade secondary [quelle_ip] [datei.pkg]`  | Aktualisiert die sekundäre Firmware von einem FTP/TFTP-Server. | WeOS4/5 |
| `upgrade boot [quelle_ip] [datei.pkg]`       | Aktualisiert den Bootloader von einem FTP/TFTP-Server.  | WeOS4/5    |

---

## Allgemeine Abkürzungen in der Netzwerktechnologie

### Allgemeine Abkürzungen

| Abkürzung | Kontext (OSI-Schicht)        | Erklärung                                                  |
|-----------|------------------------------|-----------------------------------------------------------|
| AAA       | Sicherheit                   | Authentifizierung, Autorisierung und Abrechnung           |
| CLI       | Benutzeroberfläche           | Kommandozeilen-Schnittstelle                              |
| DNS       | Namensauflösung (Schicht 7)  | Domain Name System                                        |
| DoS       | Sicherheit                   | Denial of Service                                         |
| FTP       | Protokoll (Schicht 7)        | File Transfer Protocol                                    |
| HTTP      | Protokoll (Schicht 7)        | Hypertext Transfer Protocol                               |
| IPsec     | Sicherheit (Schicht 3)       | Internet Protocol Security                                |
| ISP       | Dienstanbieter               | Internet Service Provider                                 |
| MTU       | Datenübertragung (Schicht 3) | Maximum Transmission Unit                                 |
| NTP       | Zeitprotokoll (Schicht 7)    | Network Time Protocol                                     |
| QoS       | Datenübertragung (Schicht 2/3)| Quality of Service                                       |
| SNMP      | Netzwerkmanagement (Schicht 7)| Simple Network Management Protocol                       |
| SSH       | Protokoll (Schicht 7)        | Secure Shell                                              |
| SSL       | Sicherheit (Schicht 6)       | Secure Sockets Layer                                      |
| TCP       | Protokoll (Schicht 4)        | Transmission Control Protocol                             |
| UDP       | Protokoll (Schicht 4)        | User Datagram Protocol                                    |
| VoIP      | Kommunikation (Schicht 7)    | Voice over Internet Protocol                              |
| VPN       | Tunneling (Schicht 3)        | Virtuelles Privates Netzwerk                              |

---

### Abkürzungen für Switching

| Abkürzung | Kontext (OSI-Schicht)        | Erklärung                                                  |
|-----------|------------------------------|-----------------------------------------------------------|
| ACL       | Sicherheit (Schicht 2/3)     | Access Control List                                       |
| AP        | Netzwerkgerät (Schicht 2)    | Access Point                                              |
| ARP       | Protokoll (Schicht 2)        | Address Resolution Protocol                               |
| CSMA/CD   | Netzwerkprotokoll (Schicht 2)| Carrier Sense Multiple Access mit Kollisionsdetektion     |
| LAN       | Netzwerk (Schicht 1/2)       | Local Area Network                                        |
| MAC       | Adressierung (Schicht 2)     | Media Access Control                                      |
| VLAN      | Netzwerk (Schicht 2)         | Virtuelles Lokales Netzwerk                               |
| Wi-Fi     | Netzwerk (Schicht 1/2)       | Wireless Fidelity                                         |

---

### Routing-Abkürzungen

| Abkürzung | Kontext (OSI-Schicht)        | Erklärung                                                  |
|-----------|------------------------------|-----------------------------------------------------------|
| BGP       | Routing (Schicht 3)          | Border Gateway Protocol                                   |
| CIDR      | Adressierung (Schicht 3)     | Classless Inter-Domain Routing                            |
| GRE       | Tunneling (Schicht 3)        | Generic Routing Encapsulation                             |
| ICMP      | Protokoll (Schicht 3)        | Internet Control Message Protocol                         |
| IP        | Adressierung (Schicht 3)     | Internet Protocol                                         |
| OSPF      | Routing (Schicht 3)          | Open Shortest Path First                                  |
| RIP       | Routing (Schicht 3)          | Routing Information Protocol                              |

---

**Hinweis:** Ersetze Platzhalter wie `[schnittstellenname]`, `[ip_adresse]`, `[subnetz_maske]` usw.

### Versionen WeOS 4.33.2 und WeOS 5.20.1
