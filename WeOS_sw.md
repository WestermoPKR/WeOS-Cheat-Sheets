## Innehållsförteckning

- [Åtkomst till kommandoradsgränssnittet](#åtkomst-till-kommandoradsgränssnittet)
  - [WeOS 4](#weos-4)
  - [WeOS 5](#weos-5)
- [Konfiguration av konsolport](#konfiguration-av-konsolport)
- [Åtkomst till CLI via SSH](#åtkomst-till-cli-via-ssh)
  - [Rekommenderade SSH-klienter](#rekommenderade-ssh-klienter)
- [WeOS Fuskark](#weos-fuskark)
  - [Admin Exec Context](#admin-exec-context)
  - [Global Configuration Context](#global-configuration-context)
  - [Navigering i olika kontextmenyer](#navigering-i-olika-kontextmenyer)
- [Admin Exec Context (kommandon)](#admin-exec-context-kommandon)
- [Global Configuration Context (kommandon)](#global-configuration-context-kommandon)
- [Filhantering](#filhantering)
- [Vanliga förkortningar inom nätverksteknik](#vanliga-förkortningar-inom-nätverksteknik)
  - [Förkortningar för switching](#förkortningar-för-switching)
  - [Förkortningar för routing](#förkortningar-för-routing)

---

För att logga in via konsolporten behöver du användarnamn och lösenord. För närvarande finns endast ett administratörskonto definierat. Standardinställningar för konto och lösenord:

### Användarkonton

<table>
    <tr>
        <th>WeOS4</th>
        <th>WeOS5</th>
    </tr>
    <tr>
        <td>
            <table>
                <tr>
                    <th>Användarnamn</th>
                    <th>Lösenord</th>
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
                    <th>Användarnamn</th>
                    <th>Lösenord</th>
                </tr>
                <tr>
                    <td>admin</td>
                    <td>admin</td>
                </tr>
            </table>
        </td>
    </tr>
</table>

### Konfiguration av konsolport:

| Inställning  | Värde            |
|--------------|------------------|
| Datahastighet | 115200 bits/s    |
| Databitar     | 8                |
| Stoppbitar    | 1                |
| Paritet       | Ingen            |
| Flödeskontroll | Ingen           |

Virtuell COM-port (VCP) drivrutin: [FTDI VCP-drivrutiner](https://ftdichip.com/drivers/vcp-drivers/)

---

## Åtkomst till CLI via SSH

För att komma åt CLI via SSH behöver du en SSH-klient, växelns IP-adress och kontouppgifter (användarnamn/lösenord).

### Rekommenderade SSH-klienter:

| OS       | Programvara  | Länk                                                        |
|----------|--------------|-------------------------------------------------------------|
| Windows  | PuTTY        | [Ladda ner](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) |
| UNIX     | OpenSSH      | [Ladda ner](https://www.openssh.com)                         |

---

# WeOS Fuskark

![WeOS Logo](<Screenshot 2024-04-16 155850.png>)

### Admin Exec Context

I Admin Exec Context kan användare utföra allmän övervakning, diagnostik samt hantera konfigurationsfiler och firmwareversioner. Användare kan också komma åt specifika utförandekontexter, som att visa RMON-statistik.

### Global Configuration Context

Från Admin Exec Context kan användare komma åt Global Configuration Context. Här kan de ställa in enhetsparametrar av global betydelse, som värdnamn och plats. Från Global Configuration Context kan användare navigera till specifika kontexter för protokoll eller enhetsenheter som portar, VLAN, gränssnitt och FRNT.

### Navigering i olika kontextmenyer:

![WeOS Logo](<Screenshot 2024-04-16 155831.png>)

| Kommando                      | Beskrivning                                             | OS-version |
|-------------------------------|---------------------------------------------------------|------------|
| `configure`                    | Går in i Global Configuration Context.                 | WeOS4/5    |
| `logout`                       | Loggar ut från enheten.                                | WeOS4/5    |
| `vlan [#]`                     | Går in i VLAN Config. Context från Global Config. Context. | WeOS4/5    |
| `port eth[#] / dsl[#]`         | Går in i Port Config. Context från Global Config. Context. | WeOS4/5    |
| `port ethx[#]`                 | Viper-enheter. Går in i Port Config. Context.          | WeOS4/5    |
| `port ser[#]`                  | LynxDSS-enheter. Går in i Port Config. Context.        | WeOS4/5    |
| `ip`                           | Går in i IP Config. Context från Global Config. Context. | WeOS4/5    |
| `firewall`                     | Går in i Firewall/NAT Config. Context från General IP Config. Context. | WeOS4/5 |
| `end`                          | Återgår till föregående läge.                           | WeOS4/5    |

---

### Admin Exec Context (kommandon):

| Kommando                    | Beskrivning                                              | OS-version |
|-----------------------------|----------------------------------------------------------|------------|
| `show`                      | Visar olika information som konfigurationer, statistik eller status. | WeOS4/5    |
| `do`                        | Utför ett kommando från olika kontexter.                 | WeOS4/5    |
| `show ifaces`               | Visar information om gränssnitt.                         | WeOS4/5    |
| `show ip route`             | Visar IP-routningstabellen.                              | WeOS4/5    |
| `show arp`                  | Visar ARP-tabellen.                                      | WeOS4/5    |
| `show log`                  | Visar enhetens loggar.                                   | WeOS4/5    |
| `show system`               | Visar systeminformation om enheten.                      | WeOS4/5    |
| `show version`              | Visar information om nuvarande systemversion.            | WeOS4/5    |
| `ping [destination]`        | Skickar ICMP-eko-förfrågningar till destinationen.       | WeOS4/5    |
| `traceroute [destination]`  | Utför en traceroute till destinationen.                  | WeOS4/5    |
| `ipcalc [address]`          | Ger detaljerad information om IP-adresser och subnät.    | WeOS4/5    |
| `repeat [command]`          | Utför ett specificerat kommando flera gånger.            | WeOS4/5    |
| `uptime`                    | Visar tiden sedan den senaste omstarten.                 | WeOS4/5    |
| `ssh [user@address]`        | Secure shell-inloggning till en annan värd.              | WeOS4/5    |
| `ipcalc`                    | En IP-netmask/broadcast-räknare.                         | WeOS4/5    |
| `reboot`                    | Startar om enheten.                                      | WeOS4/5    |
| `ipconfig [interface]`      | Visar grann-enheter.                                     | WeOS4/5    |
| `follow`                    | Övervakar kontinuerligt en (logg-)fil.                   | WeOS4/5    |
| `factory-reset`             | Återställer enheten till fabriksinställningarna.         | WeOS4/5    |

---

### Global Configuration Context (kommandon):

| Kommando                                     | Beskrivning                                             | OS-version |
|---------------------------------------------|---------------------------------------------------------|------------|
| `aaa username [user] [password]`            | Sätter ett nytt lösenord för en användare.               | WeOS4/5    |
| `system location [location]`                | Anger en plats för denna enhet.                          | WeOS4/5    |
| `system hostname [hostname]`                | Konfigurerar enhetens värdnamn.                          | WeOS4/5    |
| `iface [interface]:`                        | Går in i konfigurationsläget för ett specifikt gränssnitt. | WeOS4/5    |
| `address [ip_address] [subnet_mask]`        | Konfigurerar IP-adressen och subnätmasken för ett gränssnitt. | WeOS4 |
| `inet static [ip_address/prefix]`           | Konfigurerar IP-adressen och subnätmasken för ett gränssnitt. | WeOS5 |
| `vlan [VID]`                                | Skapar ett VLAN.                                     | WeOS4/5    |
| `no shutdown:`                               | Aktiverar en inaktiverad gränssnitt.                 | WeOS4/5    |
| `shutdown:`                                  | Inaktiverar ett gränssnitt.                           | WeOS4/5    |
| `ntp server [FQDN/IP-ADDR]`                 | Ställer in en NTP-server för denna enhet.            | WeOS4      |
| `ntp peer [FQDN/IP-ADDR]`                   | Ställer in en NTP-server för denna enhet.            | WeOS5      |

---

### Filhantering:

| Kommando                                      | Beskrivning                                          | OS-version |
|----------------------------------------------|-----------------------------------------------------|------------|
| `copy [src] [dest]:`                        | Kopierar filer mellan platser.                     | WeOS4/5    |
| `upgrade primary [src_ip] [file.pkg]`      | Uppdaterar primär firmware från server.            | WeOS4/5    |
| `upgrade secondary [src_ip] [file.pkg]`    | Uppdaterar sekundär firmware från server.          | WeOS4/5    |
| `upgrade boot [src_ip] [file.pkg]`         | Uppdaterar bootloader från server.                 | WeOS4/5    |

---

## Vanliga förkortningar inom nätverksteknik

### Allmänna förkortningar

| Förkortning | Kontext (OSI-lager)        | Förklaring                                            |
|-------------|-----------------------------|------------------------------------------------------|
| AAA         | Säkerhet                    | Autentisering, Auktorisering och Redovisning         |
| CLI         | Användargränssnitt          | Kommandoradsgränssnitt                               |
| DNS         | Namnupplösning (lager 7)    | Domain Name System                                   |
| DoS         | Säkerhet                    | Denial of Service                                    |
| FTP         | Protokoll (lager 7)         | File Transfer Protocol                               |
| HTTP        | Protokoll (lager 7)         | Hypertext Transfer Protocol                          |
| IPsec       | Säkerhet (lager 3)          | Internet Protocol Security                           |
| ISP         | Tjänsteleverantör           | Internet Service Provider                            |
| MTU         | Dataöverföring (lager 3)    | Maximum Transmission Unit                            |
| NTP         | Tidsprotokoll (lager 7)      | Network Time Protocol                                |
| QoS         | Dataöverföring (lager 2/3)  | Quality of Service                                   |
| SNMP        | Nätverksadministration (lager 7) | Simple Network Management Protocol                  |
| SSH         | Protokoll (lager 7)          | Secure Shell                                         |
| SSL         | Säkerhet (lager 6)           | Secure Sockets Layer                                 |
| TCP         | Protokoll (lager 4)          | Transmission Control Protocol                        |
| UDP         | Protokoll (lager 4)          | User Datagram Protocol                               |
| VoIP        | Kommunikation (lager 7)      | Voice over Internet Protocol                         |
| VPN         | Tunneling (lager 3)          | Virtuellt privat nätverk                             |

### Förkortningar för switching

| Förkortning | Kontext (OSI-lager)        | Förklaring                                            |
|-------------|-----------------------------|------------------------------------------------------|
| ACL         | Säkerhet (lager 2/3)        | Access Control List                                  |
| AP          | Nätverksenhet (lager 2)      | Access Point                                         |
| ARP         | Protokoll (lager 2)          | Address Resolution Protocol                          |
| CSMA/CD     | Nätverksprotokoll (lager 2)  | Carrier Sense Multiple Access med Kollisionsdetektion |
| LAN         | Nätverk (lager 1/2)          | Local Area Network                                   |
| MAC         | Adressering (lager 2)        | Media Access Control                                 |
| VLAN        | Nätverk (lager 2)            | Virtuellt lokalt nätverk                             |
| Wi-Fi       | Nätverk (lager 1/2)          | Wireless Fidelity                                    |

### Förkortningar för routing

| Förkortning | Kontext (OSI-lager)        | Förklaring                                            |
|-------------|-----------------------------|------------------------------------------------------|
| BGP         | Routing (lager 3)           | Border Gateway Protocol                              |
| CIDR        | Adressering (lager 3)       | Classless Inter-Domain Routing                       |
| GRE         | Tunneling (lager 3)         | Generic Routing Encapsulation                        |
| ICMP        | Protokoll (lager 3)          | Internet Control Message Protocol                    |
| IP          | Adressering (lager 3)       | Internet Protocol                                    |
| OSPF        | Routing (lager 3)           | Open Shortest Path First                             |
| RIP         | Routing (lager 3)           | Routing Information Protocol                          |

---

**Notera:** Ersätt platshållare som `[interface_name]`, `[ip_address]`, `[subnet_mask]`, osv.

### Versioner WeOS 4.33.2 och WeOS 5.20.1

