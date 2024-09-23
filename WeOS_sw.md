## Innehållsförteckning

- [Åtkomst till kommandoradsgränssnittet](#åtkomst-till-kommandoradsgränssnittet)
  - [WeOS 4](#weos-4)
  - [WeOS 5](#weos-5)
- [Konfiguration av konsolport](#konfiguration-av-konsolport)
- [Åtkomst till CLI via SSH](#åtkomst-till-cli-via-ssh)
  - [Rekommenderade SSH-klienter](#rekommenderade-ssh-klienter)
- [WeOS Fuskark](#weos-fuskark)
  - [Admin Exec Kontext](#admin-exec-kontext)
  - [Global Konfigurationskontext](#global-konfigurationskontext)
  - [Navigering i olika kontextmenyer](#navigering-i-olika-kontextmenyer)
- [Admin Exec Kontext (Kommandon)](#admin-exec-kontext-kommandon)
- [Global Konfigurationskontext (Kommandon)](#global-konfigurationskontext-kommandon)
- [Filhantering](#filhantering)
- [Vanliga förkortningar inom nätverksteknik](#vanliga-förkortningar-inom-nätverksteknik)
  - [Switching Förkortningar](#switching-förkortningar)
  - [Routing Förkortningar](#routing-förkortningar)

---

För att logga in via konsolporten behöver du användarnamnet och lösenordet. För närvarande finns det bara ett definierat användarkonto, administratörskontot. Standardinställningar för konto och lösenord:

### Användarkonton

| WeOS4      | WeOS5      |
|------------|------------|
| användarnamn | användarnamn |
| westermo   | admin       |

### Konfiguration av konsolporten:

| Inställning   | Värde               |
|---------------|---------------------|
| Datahastighet | 115200 bitar/sek    |
| Databitar     | 8                   |
| Stoppbitar    | 1                   |
| Paritet       | Ingen               |
| Flödeskontroll | Ingen              |

Virtuell COM-port (VCP) drivrutin: [FTDI VCP Drivers](https://ftdichip.com/drivers/vcp-drivers/)

---

## Åtkomst till CLI via SSH

För att komma åt CLI via SSH behöver du en SSH-klient, switchens IP-adress och kontouppgifter (användarnamn/lösenord).

### Rekommenderade SSH-klienter:

| Operativsystem | Programvara | Länk                                                     |
|----------------|-------------|----------------------------------------------------------|
| Windows        | PuTTY       | [Ladda ner](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) |
| UNIX           | OpenSSH     | [Ladda ner](https://www.openssh.com)                     |

---

# WeOS Fuskark

### Admin Exec Kontext

I Admin Exec Kontext kan användare utföra generell övervakning, diagnostik och hantera konfigurationsfiler och firmwareversioner. Användarna kan också tillgå specifika utförandekontexter, som att visa RMON-statistik.

### Global Konfigurationskontext

Från Admin Exec Kontext kan användarna tillgå Global Konfigurationskontext. Här kan de ställa in enhetsparametrar av global betydelse, som värdnamn och plats. Från Global Konfigurationskontext kan användare navigera till specifika kontexter för protokoll eller enhetsenheter såsom portar, VLAN, gränssnitt och FRNT.

### Navigering i olika kontextmenyer:

| Kommando                   | Beskrivning                                           | OS Version |
|----------------------------|------------------------------------------------------|------------|
| `configure`                | Går in i Global Konfigurationskontext.               | WeOS4/5    |
| `logout`                   | Loggar ut dig från enheten.                          | WeOS4/5    |
| `vlan [#]`                 | Går in i VLAN Konfigurationskontext från Global Konfig. | WeOS4/5  |
| `port eth[#] / dsl[#]`     | Går in i Port Konfigurationskontext från Global Konfig. | WeOS4/5  |
| `port ethx[#]`             | För Viper-enheter. Går in i Port Konfigurationskontext. | WeOS4/5  |
| `port ser[#]`              | För LynxDSS-enheter. Går in i Port Konfigurationskontext. | WeOS4/5 |
| `ip`                       | Går in i IP Konfigurationskontext från Global Konfig. | WeOS4/5  |
| `firewall`                 | Går in i Brandvägg/NAT Konfigurationskontext från Allmän IP Konfig. | WeOS4/5 |
| `end`                      | Återgår till föregående läge.                         | WeOS4/5    |

---

### Admin Exec Kontext (Kommandon):

| Kommando                    | Beskrivning                                              | OS Version |
|-----------------------------|---------------------------------------------------------|------------|
| `show`                      | Visar olika information såsom konfigurationer, statistik eller status. | WeOS4/5    |
| `do`                        | Utför ett kommando från olika kontexter.                 | WeOS4/5    |
| `show ifaces`               | Visar information om gränssnitt.                         | WeOS4/5    |
| `show ip route`             | Visar IP-routningstabellen.                              | WeOS4/5    |
| `show arp`                  | Visar ARP-tabellen.                                      | WeOS4/5    |
| `show log`                  | Visar loggar från enheten.                               | WeOS4/5    |
| `show system`               | Visar systeminformation om enheten.                      | WeOS4/5    |
| `show version`              | Visar information om den aktuella systemversionen.       | WeOS4/5    |
| `ping [destination]`        | Skickar ICMP-eko-förfrågningar till destinationen.       | WeOS4/5    |
| `traceroute [destination]`  | Utför en traceroute till destinationen.                  | WeOS4/5    |
| `ipcalc [address]`          | Ger detaljerad information om IP-adresser och nätverk.   | WeOS4/5    |
| `repeat [command]`          | Utför ett angivet kommando flera gånger.                 | WeOS4/5    |
| `uptime`                    | Tid sedan senaste omstart.                               | WeOS4/5    |
| `ssh [user@address]`        | Säker SSH-inloggning till en annan värd.                 | WeOS4/5    |
| `ipcalc`                    | En IP-nätmask/broadcast-kalkylator.                      | WeOS4/5    |
| `reboot`                    | Startar om enheten.                                      | WeOS4/5    |
| `ipconfig [interface]`      | Visar närliggande enheter.                               | WeOS4/5    |
| `follow`                    | Övervakar kontinuerligt en (logg-)fil.                   | WeOS4/5    |
| `factory-reset`             | Utför en fabriksåterställning av enheten.                | WeOS4/5    |

---

### Global Konfigurationskontext (Kommandon):

| Kommando                                     | Beskrivning                                             | OS Version |
|---------------------------------------------|---------------------------------------------------------|------------|
| `aaa username [user] [password]`           | Ställer in ett nytt lösenord för en användare.          | WeOS4/5    |
| `system location [location]`                | Anger en plats för denna enhet.                         | WeOS4/5    |
| `system hostname [hostname]`                | Konfigurerar enhetens värdnamn.                         | WeOS4/5    |
| `iface [interface]:`                        | Går in i konfigurationsläget för ett specifikt gränssnitt. | WeOS4/5    |
| `address [ip_address] [subnet_mask]`        | Konfigurerar IP-adressen och nätmasken för ett gränssnitt. | WeOS4     |
| `inet static [ip_address/prefix]`           | Konfigurerar IP-adressen och nätmasken för ett gränssnitt. | WeOS5     |
| `vlan [VID]`                                | Skapar ett VLAN.                                       | WeOS4/5    |
| `no shutdown:`                              | Aktiverar ett inaktiverat gränssnitt.                   | WeOS4/5    |
| `shutdown:`                                 | Inaktiverar ett gränssnitt.                             | WeOS4/5    |
| `ntp server [FQDN/IP-ADDR]`                 | Ställer in en NTP-server för denna enhet.               | WeOS4      |
| `ntp peer [FQDN/IP-ADDR]`                   | Ställer in en NTP-peer för denna enhet.                 | WeOS5      |

---

### Filhantering:

| Kommando                                      | Beskrivning                                          | OS Version |
|----------------------------------------------|-----------------------------------------------------|------------|
| `copy [src] [dest]:`                        | Kopierar filer mellan platser.                     | WeOS4/5    |
| `upgrade primary [src_ip] [file.pkg]`       | Uppdaterar primär firmware från server.            | WeOS4/5    |
| `upgrade secondary [src_ip] [file.pkg]`     | Uppdaterar sekundär firmware från server.          | WeOS4/5    |
| `upgrade boot [src_ip] [file.pkg]`          | Uppdaterar bootloader från server.                 | WeOS4/5    |

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
| ICMP        | Protokoll (lager 3)         | Internet Control Message Protocol                    |
| IP          | Adressering (lager 3)       | Internet Protocol                                    |
| OSPF        | Routing (lager 3)           | Open Shortest Path First                             |
| RIP         | Routing (lager 3)           | Routing Information Protocol                          |

---

**Notera:** Ersätt platshållare som `[interface_name]`, `[ip_address]`, `[subnet_mask]`, osv.

### Versioner WeOS 4.33.2 och WeOS 5.20.1
