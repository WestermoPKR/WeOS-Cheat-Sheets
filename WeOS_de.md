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
