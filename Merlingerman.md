## Inhaltsverzeichnis

- [Zugriff auf die Kommandozeilenschnittstelle](#zugriff-auf-die-kommandozeilenschnittstelle)
  - [Merlin](#Merlin)
- [Konfiguration des Konsolenports](#konfiguration-des-konsolenports)
- [Zugriff auf die CLI via SSH](#zugriff-auf-die-cli-via-ssh)
  - [Empfohlene SSH-Clients](#empfohlene-ssh-clients)
- [Merlin Spickzettel](#Merlin-spickzettel)
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
        <th>Merlin</th>
    </tr>
    <tr>
        <td>
            <table>
                <tr>
                    <th>Benutzername</th>
                    <th>Passwort</th>
                    <th>Default IP</th>
                </tr>
                <tr>
                    <td>root</td>
                    <td>admin</td>
                    <td>192.168.100.1</td>
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


---

## Zugriff auf die CLI via SSH

Um auf die CLI via SSH zuzugreifen, benötigen Sie einen SSH-Client, die IP-Adresse des Switches und Kontozugangsdaten (Benutzername/Passwort).

### Empfohlene SSH-Clients:

| Betriebssystem | Software | Link                                                        |
|----------------|----------|-------------------------------------------------------------|
| Windows        | PuTTY    | [Download](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) |
| UNIX           | OpenSSH  | [Download](https://www.openssh.com)                         |

---

# Merlin Spickzettel


### Admin Exec Kontext

Im Admin Exec Kontext können Benutzer allgemeine Überwachungs- und Diagnoseaufgaben durchführen sowie Konfigurationsdateien und Firmware-Versionen verwalten. Sie können auch auf spezifische Ausführungskontexte zugreifen, wie z. B. das Anzeigen von RMON-Statistiken.

### Globaler Konfigurationskontext

Vom Admin Exec Kontext aus können Benutzer auf den Globalen Konfigurationskontext zugreifen. Hier können sie Geräteeinstellungen von globaler Bedeutung festlegen, wie z. B. Hostname und Standort. Vom Globalen Konfigurationskontext aus können Benutzer zu spezifischen Kontexten für Protokolle oder Geräteeinheiten wie Ports, VLANs, Schnittstellen und FRNT navigieren.

### Navigation in den verschiedenen Kontextmenüs:

| Befehl                      | Beschreibung                                              | OS-Version |
|-----------------------------|-----------------------------------------------------------|------------|
| `test                       | test                                                      | Merlin OS  |


---

### Admin Exec Kontext (Befehle):

| Befehl                     | Beschreibung                                              | OS-Version |
|----------------------------|-----------------------------------------------------------|------------|
| `Test`                     | Test                                                      | Merlin OS  |


---

### Globaler Konfigurationskontext (Befehle):

| Befehl                            | Beschreibung                                            | OS-Version |
|-----------------------------------|---------------------------------------------------------|------------|
| `test                          `  | test                                                    |Merlin OS   |


---

### Dateihandhabung:

| Befehl                                       | Beschreibung                                            | OS-Version |
|----------------------------------------------|---------------------------------------------------------|------------|
| TEst                                         | Test                                                    | Merlin OS  |


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
| LTE       |                              |                                                           |
| 5G        |                              |                                                           |
| SIM       |                              |                                                           |
| PIN       |                              |                                                           |
| APN       |                              |                                                           |
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
