#######################
Technologies and Tools
#######################

***************************************************************************************************************
Install and configure network components, both hardware and software-based, to support organizational security
***************************************************************************************************************

Firewall
========

ACL
---
Application-based vs. network-based
-----------------------------------
Stateful vs. stateless
----------------------
Implicit deny
-------------


VPN concentrator
================

Remote access vs. site-to-site
------------------------------

IPSec
-----

Tunnel mode
-----------

Transport mode
--------------
AH
^^^

ESP
^^^

Split tunnel vs. full tunnel
-----------------------------

TLS
---

Always-on VPN
-------------


NIPS/NIDS
=========

Signature-based
---------------

Heuristic/behavioral
--------------------

Anomaly
--------

Inline vs. passive
------------------

In-band vs. out-of-band
-----------------------

Rules
------

Analytics
---------

False positive
--------------

False negative
--------------


Router
======
ACLs
-----

Antispoofing
------------


Switch
======

Port security
-------------

Layer 2 vs. Layer 3
-------------------

Loop prevention
---------------

Flood guard
-----------


Proxy
=====

Forward and reverse proxy
-------------------------

Transparent
-----------

Application/multipurpose
-------------------------

Load balancer
=============

Scheduling
----------
Affinity
^^^^^^^^
Round-robin
^^^^^^^^^^^

Active-passive
--------------

Active-active
--------------

Virtual IPs
------------

Access point
============

SSID
----

MAC filtering
-------------

Signal strength
---------------

Band selection/width
--------------------

Antenna types and placement
---------------------------

Fat vs. thin
------------

Controller-based vs. standalone
-------------------------------

SIEM
====

Aggregation
-----------

Correlation
-----------

Automated alerting and triggers
-------------------------------

Time synchronization
--------------------

Event deduplication
-------------------

Logs/WORM
---------

DLP
===

USB blocking
------------

Cloud-based
------------

Email
-----

NAC
===

Dissolvable vs. permanent
-------------------------

Host health checks
------------------

Agent vs. agentless
-------------------


Mail gateway
============

Spam filter
-----------
DLP
----
Encryption
-----------

Bridge
======


SSL/TLS accelerators
====================


SSL decryptors
==============


Media gateway
=============


Hardware security module
========================


***************************************************************************************************
Given a scenario, use appropriate software tools to assess the security posture of an organization
***************************************************************************************************

Protocol analyzer
=================

Network scanners
================

Rogue system detection
-----------------------

Network mapping
----------------


Wireless scanners/cracker
=========================

Password cracker
================

Vulnerability scanner
=====================

Configuration compliance scanner
================================

Exploitation frameworks
=======================

Data sanitization tools
=======================

Steganography tools
===================

Honeypot
========

Backup utilities
================

Banner grabbing
===============

Passive vs. active
==================

Command line tools
==================
- Commands in Windows are usually not case sensitive, whereas commands in linux are case sensitive
- Common help flag for Windows is ``/?`` or ``-?``
- Common help flag for linux is ``|help`` or by preceding the command with ``man``

ping
----
- Used to test TCP/IP connectivity by sending ICMP echo request packets
- Can be used to verify if DNS is working
- Firewalls may prevent ping from working correctly if ICMP requests are blocked

- Windows vs. Linux
    
    - ``ping`` on linux acts like ``ping -t`` on Windows: ``ping`` on windows defaults to sending 4 packets, whereas on linux it sends packets until receiving a stop with Ctrl+C

- Windows Flags:

    - ``-t`` : Pings the specified host until stopped with Ctrl+C
    - ``-a`` : Resolves addresses to hostnames
    - ``-l`` *size* : Sets the size of the send buffer

- Linux Flags:

    - ``-c count`` : Stops pinging after sending *count* ECHO_REQUEST packets


netstat
-------
- Displays network connections, routing tables, and interface statistics for TCP/IP protocols on a system
- Allows viewing active TCP/IP network connections

- Windows vs. Linux
    
    - Flags are generally the same between Windows and Linux

- Flags:

    - ``-a`` : Displays all active connections and the TCP/UDP ports on which the computer is listening, in addition to all open connections
    - ``-r`` : Displays the contents of the IP routing table
    - ``-e`` : Displays ethernet statistics, such as the number of bytes and packets sent/received
    - ``-s`` : Displays statistics by protocols
    - ``-n`` : Displays TCP connections in numerical order and doesn't attempt to resolve names
    - ``-p`` *protocol* : Displays connections for the specified protocol only (e.g., tcp, udp, ipv6, etc)

tracert
-------
- Lists the routers between two networks

- Windows vs. Linux

    - Window systems use ``tracert``, whereas Linux uses ``traceroute``
    - Windows sends ICMP echo requests when using ``tracert``, where as Linux sends UDP packets

- Windows Flags:

    - ``-d`` : Forces ``tracert`` to not resolve IP addresses to host names


nslookup/dig
------------

arp
---
- Displays the Address Resolution Protocol Cache



ipconfig/ip/ifconfig
--------------------

tcpdump
-------

nmap
----

netcat
------



*****************************************************
Given a scenario, troubleshoot common security issues
*****************************************************

Unencrypted credentials/clear text
==================================


Logs and events anomalies
=========================

Permission issues
=================

Access violations
=================

Certificate issues
==================

Data exfiltration
=================

Misconfigured devices
=====================

Firewall
--------

Content filter
---------------

Access points
-------------

Weak security configurations
============================

Personnel issues
================

Policy violation
----------------

Insider threat
--------------

Social engineering
------------------

Social media
------------

Personal email
---------------


Unauthorized software
=====================

Baseline deviation
==================

License compliance violation (availability/integrity)
=====================================================

Asset management
================

Authentication issues
=====================



*************************************************************************
Given a scenario, analyze and interpret output from security technologies
*************************************************************************


HIDS/HIPS
=========

Antivirus
=========

File integrity check
====================

Host-based firewall
===================

Application whitelisting
=========================

Removable media control
========================

Advanced malware tools
=======================

Patch management tools
=======================

UTM
===

DLP
===

Data execution prevention
=========================

Web application firewall
=========================


************************************************
Given a scenario, deploy mobile devices securely
************************************************

Connection methods
==================

Cellular
--------

WiFi
----

SATCOM
------

Bluetooth
---------

NFC
---

ANT
---

Infrared
---------

USB
---


Mobile device management concepts
=================================

Application management
----------------------

Content management
------------------

Remote wipe
-----------

Geofencing
----------

Geolocation
-----------

Screen locks
------------

Push notification services
--------------------------

Passwords and pins
------------------

Biometrics
----------

Context-aware authentication
----------------------------

Containerization
----------------

Storage segmentation
--------------------

Full device encryption
----------------------


Enforcement and monitoring for:
===============================

Third-party app stores
----------------------

Rooting/jailbreaking
--------------------

Sideloading
-----------

Custom firmware
---------------

Carrier unlocking
-----------------

Firmware OTA updates
--------------------

Camera use
----------

SMS/MMS
-------

External media
--------------

USB OTG
-------

Recording microphone
--------------------

GPS tagging
-----------

WiFi direct/ad hoc
------------------

Tethering
---------

Payment methods
---------------


Deployment models
=================

BYOD
----

COPE
----

CYOD
----

Corporate-owned
---------------

VDI
----

*********************************************
Given a scenario, implement secure protocols.
*********************************************

Protocols
=========

DNSSEC
-------

SSH
---

S/MIME
-------

SRTP
----

LDAPS
-----

FTPS
----

SFTP
----

SNMPv3
------

SSL/TLS
-------

HTTPS
-------

Secure POP/IMAP
---------------


Use cases
=========

Voice and video
----------------

Time synchronization
--------------------

Email and web
-------------

File transfer
-------------

Directory services
------------------

Remote access
-------------

Domain name resolution
-----------------------

Routing and switching
----------------------

Network address allocation
---------------------------

Subscription services
----------------------
