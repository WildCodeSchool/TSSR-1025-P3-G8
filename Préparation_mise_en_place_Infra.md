
| Nom_Machine | Type                 | OS                  | Interface         | Interconnexions                               | Réseau         | Rôle                      | Adresse Réseau | Adresse IP    |
| ----------- | -------------------- | ------------------- | ----------------- | --------------------------------------------- | -------------- | ------------------------- | -------------- | ------------- |
| FW01        | Pare-Feu / Routeur ? | pfsense             | WAN               | Box Internet (Via Passerelle ?)               | WAN (Internet) | Accès Internet / Filtrage | DHCP FAI       | DHCP          |
| ---         | ---                  | ---                 | LAN               | SRVWIN01, CLIWIN01, CLIWIN02 (Via Switch LAN) | LAN            | Passerelle LAN            | 172.16.10.0/24 | 172.16.10.254 |
| ---         | ---                  | ---                 | DMZ               | SRVLX01, IPBX01 (Via Switch DMZ)              | DMZ            | Passerelle DMZ            | 172.16.20.0/24 | 172.16.20.254 |
| SRVWIN01    | Serveur              | Windows Server 2022 | Ethernet (eth0 ?) | FW01, CLIWIN01, CLIWIN02 (Via Switch LAN)     | LAN            | ADDS, DNS, DHCP, WSUS     | 172.16.10.0/24 | 172.16.10.10  |
| SRVLX01     | Serveur              | Linux Debian        | Ethernet (eth0 ?) | FW01, IPBX01 (Via Switch DMZ)                 | DMZ            | GLPI, Messagerie          | 172.16.20.0/24 | 172.16.20.10  |
| IPBX01      | Serveur              | Linux Debian        | Ethernet (eth0 ?) | FW01, SRVLX01 (Via Switch DMZ)                | DMZ            | VoIP                      | 172.16.20.0/24 | 172.16.20.20  |
| CLIWIN01    | Client               | Windows 10          | Ethernet (eth1 ?) | FW01, SRVWIN01, CLIWIN02 (Via Switch LAN)     | LAN            | Poste Utilisateur         | 172.16.10.0/24 | DHCP          |
| CLIWIN02    | Client               | Windows 11          | Ethernet (eth2 ?) | FW01, SRVWIN01, CLIWIN01 (Via Switch LAN)     | LAN            | Poste Utilisateur         | 172.16.10.0/24 | DHCP          |


