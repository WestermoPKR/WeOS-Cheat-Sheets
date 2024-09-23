## Innehållsförteckning

- [Åtkomst till kommandoradsgränssnittet](#åtköst-till-kommandoradsgränssnittet)
  - [WeOS 4](#weos-4)
  - [WeOS 5](#weos-5)
- [Konfiguration av konsolporten](#konfiguration-av-konsolporten)
- [Åtkomst till CLI via SSH](#åtkomst-till-cli-via-ssh)
  - [Rekommenderade SSH-klienter](#rekommenderade-ssh-klienter)
- [WeOS Spickzettel](#weos-spickzettel)
  - [Admin Exec Kontext](#admin-exec-kontext)
  - [Global konfigurationskontext](#global-konfigurationskontext)
  - [Navigering i olika kontextmenyer](#navigering-i-olika-kontextmenyer)
- [Admin Exec Kontext (Kommandon)](#admin-exec-kontext-kommandon)
- [Global konfigurationskontext (Kommandon)](#global-konfigurationskontext-kommandon)
- [Filhantering](#filhantering)
- [Vanliga förkortningar inom nätverksteknik](#vanliga-förkortningar-inom-nätverksteknik)
  - [Förkortningar för switching](#förkortningar-för-switching)
  - [Routing-förkortningar](#routing-förkortningar)

---

För att logga in via konsolporten behöver du användarnamn och lösenord. För närvarande finns endast ett användarkonto definierat, administratörsanvändarkontot. Fabrikens standardkonto och lösenord:

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

### Konfiguration av konsolporten:

| Inställning    | Värde             |
|----------------|-------------------|
| Datahastighet  | 115200 bits/s     |
| Databitar      | 8                 |
| Stoppbitar     | 1                 |
| Paritet        | Ingen             |
| Flödeskontroll | Ingen             |

Virtuell COM-port (VCP) drivrutin: [FTDI VCP-drivrutiner](https://ftdichip.com/drivers/vcp-drivers/)

---

## Åtkomst till CLI via SSH

För att få åtkomst till CLI via SSH behöver du en SSH-klient, switchens IP-adress och kontoinformation (användarnamn/lösenord).

### Rekommenderade SSH-klienter:

| Operativsystem | Programvara | Länk                                                        |
|----------------|-------------|-------------------------------------------------------------|
| Windows        | PuTTY       | [Ladda ner](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) |
| UNIX           | OpenSSH     | [Ladda ner](https://www.openssh.com)                         |

---

# WeOS Spickzettel

![WeOS Logo](<Screenshot 2024-04-16 155850.png>)

### Admin Exec Kontext

I Admin Exec-kontexten kan användare utföra allmän övervakning, diagnostik och hantera konfigurationsfiler och firmware-versioner. De kan också få åtkomst till specifika exekveringskontexter, såsom att visa RMON-statistik.

### Global konfigurationskontext

Från Admin Exec-kontexten kan användare få åtkomst till den globala konfigurationskontexten. Här kan de ställa in enhetsparametrar av global betydelse, såsom värdnamn och plats. Från den globala konfigurationskontexten kan användare navigera till specifika kontexter för protokoll eller enheter som portar, VLAN, gränssnitt och FRNT.

### Navigering i olika kontextmenyer:

| Kommando                   | Beskrivning                                              | OS-version |
|----------------------------|---------------------------------------------------------|------------|
| `configure`                | Går in i den globala konfigurationskontexten.          | WeOS4/5    |
| `logout`                   | Loggar ut från enheten.                                | WeOS4/5    |
| `vlan [#]`                 | Går in i VLAN-kontexten från den globala konfigurationskontexten. | WeOS4/5 |
| `port eth[#] / dsl[#]`     | Går in i portkontexten från den globala konfigurationskontexten. | WeOS4/5 |
| `port ethx[#]`             | Viper-enheter: Går in i portkontexten.                 | WeOS4/5    |
| `port ser[#]`              | LynxDSS-enheter: Går in i portkontexten.               | WeOS4/5    |
| `ip`                        | Går in i IP-konfigurationskontexten från den globala konfigurationskontexten. | WeOS4/5 |
| `firewall`                  | Går in i firewall/NAT-kontexten från IP-kontexten.    | WeOS4/5    |
| `end`                       | Återgår till föregående läge.                           | WeOS4/5    |

---

### Admin Exec Kontext (Kommandon):

| Kommando                   | Beskrivning                                              | OS-version |
|----------------------------|---------------------------------------------------------|------------|
| `show`                     | Visar olika information såsom konfigurationer.         | WeOS4/5    |
| `do`                       | Utför ett kommando från olika kontexter.               | WeOS4/5    |
| `show ifaces`             | Visar information om gränssnitt.                       | WeOS4/5    |
| `show ip route`           | Visar IP-routingtabellen.                              | WeOS4/5    |
| `show arp`                | Visar ARP-tabellen.                                    | WeOS4/5    |
| `show log`                | Visar loggar från enheten.                             | WeOS4/5    |
| `show system`             | Visar systeminformation om enheten.                    | WeOS4/5    |
| `show version`            | Visar information om den aktuella systemversionen.     | WeOS4/5    |
| `ping [destination]`      | Skickar ICMP-eko-förfrågningar till destinationen.     | WeOS4/5    |
| `traceroute [destination]`| Utför en traceroute till destinationen.                | WeOS4/5    |
| `ipcalc [address]`        | Ger detaljerad information om IP-adresser.             | WeOS4/5    |
| `repeat [command]`        | Utför ett specificerat kommando flera gånger.          | WeOS4/5    |
| `uptime`                  | Visar tiden sedan senaste omstart.                      | WeOS4/5    |
| `ssh [user@address]`      | Säker skalinloggning till en annan värd.               | WeOS4/5    |
| `ipcalc`                  | En IP-nätmask/broadcast/etc-kalkylator.                | WeOS4/5    |
| `reboot`                  | Startar om denna enhet.                                | WeOS4/5    |
| `ipconfig [interface]`    | Visar grann-enheter.                                   | WeOS4/5    |
| `follow`                  | Övervakar kontinuerligt en (logg)fil.                  | WeOS4/5    |
| `factory-reset`           | Utför fabriksåterställning av enheten.                  | WeOS4/5    |

---

### Global konfigurationskontext (Kommandon):

| Kommando                                     | Beskrivning                                           | OS-version |
|----------------------------------------------|------------------------------------------------------|------------|
| `aaa username [user] [password]`            | Sätter ett nytt lösenord för en användare.          | WeOS4/5    |
| `system location [location]`                 | Ställer in en plats för denna enhet.                | WeOS4/5    |
| `system hostname [hostname]`                 | Konfigurerar enhetens värdnamn.                     | WeOS4/5    |
| `iface [interface]:`                         | Går in i konfigurationsläge för en specifik gränssnitt. | WeOS4/5 |
| `address [ip_address] [subnet_mask]`        | Konfigurerar IP-adress och sub
