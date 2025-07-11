# Will Be Update Manual
# ioLibrary Driver For 2Port 
The ioLibrary means “Internet Offload Library” for WIZnet chip. It includes drivers and application protocols.
The driver (ioLibrary) can be used for the application design of WIZnet TCP/IP chips as [W5500](https://docs.wiznet.io/Product/iEthernet/W5500/overview), W5300, W5200, W5100 [W5100S](https://docs.wiznet.io/Product/iEthernet/W5100S/overview).

## ioLibrary
This driver provides the Berkeley Socket type APIs.
- The tree of Directory
<!-- ioLibrary pic -->
<!-- ![ioLibrary](http://wizwiki.net/wiki/lib/exe/fetch.php?media=products:w5500:iolibrary_bsd.jpg "ioLibrary") -->
```1
ioLibrary
    ┣ Application
    ┃  ┣ loopback
    ┃  ┃  ┣ loopback.c
    ┃  ┃  ┗ loopback.h
    ┃  ┗ multicast
    ┃     ┣ multicast.c
    ┃     ┗ multicast.h
    ┣ Ethernet
    ┃  ┣ W5100
    ┃  ┃  ┣ w5100.c
    ┃  ┃  ┗ w5100.h
    ┃  ┣ W5100S
    ┃  ┃  ┣ w5100s.c
    ┃  ┃  ┗ w5100s.h
    ┃  ┣ W5200
    ┃  ┃  ┣ w5200.c
    ┃  ┃  ┗ w5200.h
    ┃  ┣ W5300
    ┃  ┃  ┣ w5300.c
    ┃  ┃  ┗ w5300.h
    ┃  ┣ W5500
    ┃  ┃  ┣ w5500.c
    ┃  ┃  ┗ w5500.h
    ┃  ┣ W6100
    ┃  ┃  ┣ w6100.c
    ┃  ┃  ┗ w6100.h
    ┃  ┗ W6300
    ┃     ┣ w6300.c
    ┃     ┗ w6300.h
    ┗ Internet
       ┣ AAC
       ┃  ┣ AddressAutoConfig.c
       ┃  ┗ AddressAutoConfig.h
       ┣ DHCP
       ┃  ┣ dhcp.c
       ┃  ┗ dhcp.h
       ┣ DHCP6
       ┃  ┣ dhcp6.c
       ┃  ┗ dhcp6.h
       ┣ DNS
       ┃  ┣ dns.c
       ┃  ┗ dns.h
       ┣ FTPClient
       ┃  ┣ ftpc.c
       ┃  ┣ ftpc.h
       ┃  ┗ stdio_private.h
       ┣ FTPServer
       ┃  ┣ ftpd.c
       ┃  ┣ ftpd.h
       ┃  ┣ REAME.md
       ┃  ┗ stdio_private.h
       ┣ httpServer
       ┃  ┣ httpParser.c
       ┃  ┣ httpParser.h
       ┃  ┣ httpServer.c
       ┃  ┣ httpServer.h
       ┃  ┣ httpUtil.c
       ┃  ┗ httpUtil.h
       ┣ MQTT
       ┃  ┣ MQTTPacket
       ┃  ┣ mqtt_interface.c
       ┃  ┣ mqtt_interface.h
       ┃  ┣ MQTTClient.c
       ┃  ┗ MQTTClient.h
       ┣ SNMP
       ┃  ┣ tools
       ┃  ┣ snmp.c
       ┃  ┣ snmp.h
       ┃  ┣ snmp_custom.c
       ┃  ┗ snmp_custom.h
       ┣ SNTP
       ┃  ┣ sntp.c
       ┃  ┗ sntp.h
       ┗ TFTP
          ┣ netutil.c
          ┣ netutil.h
          ┣ tftp.c
          ┗ tftp.h

```

- Ethernet : SOCKET APIs like BSD & WIZCHIP([W5500](https://docs.wiznet.io/Product/iEthernet/W5500/overview) / W5300 /  W5200 / W5100 / [W5100S](https://docs.wiznet.io/Product/iEthernet/W5100S/overview)) Driver
- Internet :
  - DHCP client
  - DNS client
  - FTP client
  - FTP server
  - SNMP agent/trap
  - SNTP client
  - TFTP client
  - HTTP server
  - MQTT Client
  - Others will be added.

## How to add an ioLibrary in project through github site.
  - Example, refer to https://www.youtube.com/watch?v=mt815RBGdsA
  - [ioLibrary Doxygen doument](https://github.com/Wiznet/ioLibrary_Driver/blob/master/Ethernet/Socket_APIs_V3.0.3.chm) : Refer to **TODO** in this document
    - Define what chip is used in **wizchip_conf.h**
    - Define what Host I/F mode is used in **wizchip_conf.h**

## Revision History
  * ioLibrary V4.0.0 Released : 29, MAR, 2018
    * New features added: Library for W5100S added.
  * ioLibrary V3.1.1 Released : 14, Dec, 2016
    * Bug fixed : In Socket.c Fixed MACraw & IPraw sendto function.
  * ioLibrary V3.1.0 Released : 05, Dec, 2016
    * Internet application protocol add to MQTT Client (using paho MQTT 3.11)
  * ioLibrary V3.0.3 Released : 03, May, 2016
    * In W5300, Fixed some compile errors in close(). Refer to M20160503
    * In close(), replace socket() with some command sequences.
  * ioLibrary V3.0.2 Released : 26, April, 2016
    * Applied the erratum #1 in close() of socket.c (Refer to A20160426)
  * ioLibrary V3.0.1 Released : 15, July, 2015
    * Bug fixed : In W5100, Fixed CS control problem in read/write buffer with SPI. Refer to M20150715.
  * ioLibrary V3.0 Released : 01, June, 2015
    * Add to W5300
    * Typing Error in comments
    * Refer to 20150601 in sources.

  * Type casting error Fixed : 09, April. 2015
    In socket.c, send() : Refer to M20150409

  * ioLibrary V2.0 released : April. 2015
    * Added to W5100, W5200
    * Correct to some typing error
    * Fixed the warning of type casting.

  * Last release : Nov. 2014

