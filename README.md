# info
## Offene Fragen
### Starface
warum werden bei einem Telefonat 2 Aktive Kanäle angezeigt:
```
Zur Zeit aktive Rufkanäle:	2
```
Jede Aktive Verbindung wird immer mit 2 Rufkanälen angezeigt.

# Tips
shutdown /r /fw /f /t 0       startet den computer neu und geht ins BIOS
ipconfig /all | findstr DNS
ipconfig /displaydns | clip
getmac /v
powercfg /energy
assoc
assoc .MP4=VLC.vlc
sfc /scannow
DISM /Online /Cleanup-Image [/CheckHealth | /ScanHealth | /RestoreHealth]
tasklist | findstr script
taskkill /f /pid 1234
netsh wlan show wlanreport
netsh advfirewall set allprofiles state off
netstat -af         0.0.0.0:3423   LISTENING       der rechner hört auf jede ip port 3423
netstat -o
netstat -e -t 5

## c't
### Projektseiten
[Der optimale PC](https://www.heise.de/ratgeber/Projektseite-Der-Optimale-PC-2023-7349205.html)
### WIMage
[Projektseite](https://www.heise.de/hintergrund/c-t-WIMage-Stand-16-10-2017-3863074.html)

[Tuning: MS-Defender ExclusionProcess](https://www.heise.de/forum/c-t/Kommentare-zu-c-t-Artikeln/c-t-WIMage/Tuning-MS-Defender-ExclusionProcess/posting-38144340/show/#posting_38144340)

## Keepass 2
### URL-Overrides
```
cmd://cmd /c "cmdkey /generic:TERMSRV/{URL:RMVSCM} /user:{USERNAME} /pass:{PASSWORD} && mstsc /v:{URL:RMVSCM} && timeout /t 5 /nobreak && cmdkey /delete:TERMSRV/{URL:RMVSCM}"
cmd://"c:\Program Files\uvnc bvba\UltraVNC\vncviewer.exe" "{URL:RMVSCM}"
```

## WMIC
wmic /node:FJCM172D2E bios get serialnumber
wmic path win32_VideoController get name, driverversion
wmic /node:TPP530B59 computersystem get model,name,manufacturer,systemtype

## UL Microsoft Netzwerk

Der Ordner 90_Download ist auf ein RDX-Laufwerk ausgelagert um die tägliche Datenwicherung (?) zu vermeiden. Falls der Link nicht mehr funktioniert muss das Verzeichnis \\\public\90_Download (deadlink) gelöscht werden und mit mit:

```
mklink /J j:\public\90_Download d:\90_Download
```

erneut erstellt werden.

## DECT

#### 

#### 15.9.21

N870 ist Basisstation und Dect Manager in einem und kostet 321€ z.Zt. nicht Verfügbar Lieferzeit 90 Tage nicht garantiert.

#### 20.8.21

Dect-Manager -> Netzwerk und Anschlüsse -> Ereignisse in Basisstationen

Küche 1.OG (7C:2F:80:E4:72:8D 192.168.2.169) ist  mit Busy 48. LAN-UV-02 (58:9E:C6:19:D7:18) dazugehängt ()

Halle 2 mit Busy 184 (LAN-UV-2 Cl.1 udn SyncL.2)

an Basisstationen überlastet. Deshalb habe ich ungenutzte versetzt.



### WLAN

xD!8i*avt
UG220330

25.8. Controller->IPv6->Global IPv6 Config auf disabled gesetzt

### Office365

office: ulmerautomation-de01c.mail.protection.outlook.com

Tastatur nicht angeschlossen.Bitte F1 drücken! (Tna.BF1d!)

##### Firewall Schnittstellen
```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: wwan0: <POINTOPOINT,MULTICAST,NOARP> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/none 
3: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:07:32:7a:63:4e brd ff:ff:ff:ff:ff:ff
    inet6 fe80::207:32ff:fe7a:634e/64 scope link 
       valid_lft forever preferred_lft forever
4: wlan0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 02:2c:9f:fb:22:10 brd ff:ff:ff:ff:ff:ff
5: eth1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:07:32:7a:63:4f brd ff:ff:ff:ff:ff:ff
    inet 192.168.200.253/24 scope global eth1
       valid_lft forever preferred_lft forever
    inet6 fe80::207:32ff:fe7a:634f/64 scope link 
       valid_lft forever preferred_lft forever
6: eth2: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc mq state DOWN group default qlen 1000
    link/ether 00:07:32:7a:63:50 brd ff:ff:ff:ff:ff:ff
7: eth3: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 00:07:32:7a:63:51 brd ff:ff:ff:ff:ff:ff
8: sta0: <BROADCAST,MULTICAST> mtu 1500 qdisc mq state DOWN group default qlen 1000
    link/ether 02:00:de:ad:be:ef brd ff:ff:ff:ff:ff:ff
9: tun0: <POINTOPOINT,MULTICAST,NOARP,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UNKNOWN group default qlen 100
    link/none 
    inet 192.168.25.1/24 brd 192.168.25.255 scope global tun0
       valid_lft forever preferred_lft forever
    inet6 fe80::3459:e059:e7bd:1b7c/64 scope link flags 800 
       valid_lft forever preferred_lft forever
70: wan0: <POINTOPOINT,MULTICAST,NOARP,UP,LOWER_UP> mtu 1492 qdisc pfifo_fast state UNKNOWN group default qlen 3
    link/ppp 
    inet 80.153.23.203 peer 62.156.244.25/32 scope global wan0
       valid_lft forever preferred_lft forever

Eth0
wan0
  gehört zu: eth0
  Typ: PPPOE
  IP-Adressen: 80.153.23.203/32 dynamic
  Zonen: external,firewall-external,external_v6,vpn-ipsec
                firewall-vpn-ipsec, vpn-ppp
  Login Details: 002770125584551122381298
  Fallback: wwan0, 8.8.8.8
eth1
  Typ: ETHERNET
  IP-Adressen: 192.168.200.253/24
  Zonen: internal, firewall-internal, internal_v6,firewall-internal_v6
wwan0
  Typ: mobile
```
### Firewallzugänge

https://my.hidrive.com/share/24zbyzcp6q



|Name               |Passwort                                        | LastChange  |PC Name
|-------------------|----------------------------------------------- |-------------|------------------------
|             hwolf | 5m67+0as0 (Tresor: 527517)                     |             | ARLT-4VV24
|            mulmer | 9@xA1-Su                                       |             | TP20NN65DE ?
|           tbuesch | _7EGI=i2 (Tbüsch 1704  TB2016)                 | 13.9.       | FJCM172D2E TPP15SA797
|             kkaps | H_7#W1Gj (PC:kk010799) (O:11769naC) (8kk010799)|             | FJME15BD763
|            abentz | YQ50N5X!  (PC:ab3sgbm Yof44394)                |             | TSM30BE0908
|          bpeichel | 7Fz{GS!0 (O:Fub02843)                          |             | FJE7824F50
|           jkrause | udZAF8K9  JK2017ul (JK2017ul )                 |             |
|         mstrecker | 9?yX1,Op                                       |             |
|             fmack | 7^W1IZm)                                       |             |
|         zalbrecht | Vj{C4F1%                                       | 13.9.       | FJCM17B1B9
|            rgudra | 96156doZ (O:[wie VPN]) (PC:Udral)              |             | FJH7701C96
|            pappel | *h6K8E]v                                       |             |
|         mroessler | 67wFN@[A (PC:MR2009ul) (O:Yoz49211)            | 6.9.        | FJCM170DE5 TPP15S5ED6
|       amazioschek | M9!,3AGr (O:Nax03255)                          |             | FJE5512AA67 FJE7569045
|         Pweiberle | (PC:MSzMTs11) (Off:VPN:Foj56713)               |             | TPP530B59
|            Nicole | Yof12040 (PC:nima3105UL)                       |             | FJP9009CCC
|               Udo | Lot54264 (PC:1701)                             |             | FJM770N03CC
|          Marianne | 2460maR!                                       |             | FJP400BD81
|           Patrick | Jon39161 (Eyk)                                 |             |
|              Gerd | 11401juH                                       |             | FJE7549C75 TP20NN656E
|        M.Strecker | 15772toN                                       |             |
|              Ziad | 20098toQ (30111971za) (VPN:eg5WQ6$7q)          |             | FJCM17B1B9
|           Einkauf | 82851nuZ                                       |             |
|            MRuber | Quw99993 Moni!                                 | 6.9.-17.9.  | FJP557BC82
| Sebastian Isbaner | 25037paY (Br011066)                            | 13.9.       |
|            Helmut | he18                                           | 13.9.       |
|          Lknippel | LiKni                                          |             |
|            Nicole | nima3105UL                                     |             |
|              KoMi | scanner@ulmer-automation.de Pon83323           |             |
|            jmagin | Temporäres Kennwort: Ful61966 Josefmagin15!    | |           |
|  Alkemper, Marian |                                                | 20.9.       |
|      Hegele, Luca |                                                | 13.9.       |
|             Felix | fmNSikZs1E                                     |             |
|             Ensar |                                                | 13.9        |
|      hannes stütz | Hay38630 (aiGaeg5R)                            |             |
|          ckumbeiz |      Dog72780                                  |             |
|      Stefan Mijic |        Jag33398                                |             |
|         Tbangerdt | Rul38307   Aquaman5515                         |             | FJCM170D93
| hfix              | Voz42044                                       |             | HPZ440514650
| mhiller           | Bod16975                                       |             | TSP5207CB0
| mhiller           | Dur28231                                       |             | TPP15V4F86
| max ziehr         | Haz32705                                       |             |
| Lars Burkhardt    | Nos40825                                       |             |

A.b.baeuerle@freenet.de
1320derherristmeinhirte

# Switch

## Port<->MAC Identifikation

### Aruba 2930F

68847e-92d736



## Konfigurationen

#### LAN-UV-04	Halle (Hermle C650)

| Port | Host              |
| ---- | ----------------- |
| 19   | 00:90:05:0C:C2:D2 |
| 31   | 90:1B:0E:59:3D:CC |
| 35   | 80:C1:6E:F1:DC:07 |
| 38   |                   |
| 5    | 00:17:C8:79:D1:67 |
|      |                   |

# Telekom
## Kontakt
Telekom Kundennummer 1920006802 IBAN DE10 6049 1430 0078 1960 00
Telekom Geschäftskunden
nur Festnetz 0800 3302870
nur Mobile 0800 3302828

## Leitungen
### 07147-220330
SIP Trunc Hauptnetz  VDSL100
4 Eingehende Zeitgleich
4 Ausgehende Zeitgleich
Zyxel VMG1312-B30A
LEDs Normal: 

### 07147675
Gastzugang auf der Nummer 8 VDSL100
Fritzbox 7430

Kundencenter [gerd.ulmer@t-online.de](mailto:gerd.ulmer@t-online.de) gu270651


nur Festnetz 0800 3302870
nur Mobile 0800 3302828

LTE Karte für ZTE 8-94902-00001-65603577-4
PIN: 0000 PUK 35532113
PIN2: 6790 PUK2 43102939

0800 3302202
0170 7164356
Volumen buchen über: [pass.telekom.de](http://pass.telekom.de/)

```
[Dec 14 10:24:03] WARNING[17364] chan_sip.c: Forbidden - wrong password on authentication for REGISTER for '+497147220330' to '+497147220330'
```

## Internetanbindung

13:30	Telefonische reklamation - Telekomelement zeigt Fehler an und ist  aktuell in Bearbeitung durch MA vorort.

# Links
[Github Markdown](https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

# Gesprächsprotokoll

## Matthias

15.11.21 12:40	Alle Azubi-Accounts löschen und ein Azubi Account anlegen.

​	Azubis sind: Stefan Mijic, Ensar, Moritz Weingart, Carolin

überzeiten abrechen
24.03.2023 04:25 
