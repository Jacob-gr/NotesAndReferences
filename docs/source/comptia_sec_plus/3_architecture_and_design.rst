#######################
Architecture and Design
#######################



********************************************************************************************
Explain use cases and purpose for frameworks, best practices and secure configuration guides
********************************************************************************************

Industry-standard frameworks and reference architectures
========================================================

Regulatory
----------------------------

Non-regulatory
----------------------------

National vs. international
----------------------------

Industry-specific frameworks
----------------------------


Benchmarks/secure configuration guides
======================================

Platform/vendor-specific guides
--------------------------------

Web server
--------------------------------

Operating system
--------------------------------

Application server
--------------------------------

Network infrastructure devices
--------------------------------

General purpose guides
--------------------------------

Defense-in-depth/layered security
=================================

Vendor diversity
-----------------

Control diversity
-----------------

Administrative
^^^^^^^^^^^^^^

Technical
^^^^^^^^^^^^^^

User training
-------------


****************************************************************
Given a scenario, implement secure network architecture concepts
****************************************************************


Zones/topologies
============================================

DMZ
--------------------------------------------

Extranet
--------------------------------------------

Intranet
--------------------------------------------

Wireless
--------------------------------------------

Guest
--------------------------------------------

Honeynets
--------------------------------------------

NAT
--------------------------------------------

Ad hoc
--------------------------------------------



Segregation/segmentation/isolation
============================================

Physical
--------------------------------------------

Logical (VLAN)
--------------------------------------------

Virtualization
--------------------------------------------

Air gaps
--------------------------------------------



Tunneling/VPN
============================================

Site-to-site
--------------------------------------------

Remote access
--------------------------------------------



Security device/technology placement
============================================

Sensors
--------------------------------------------

Collectors
--------------------------------------------

Correlation engines
--------------------------------------------

Filters
--------------------------------------------

Proxies
--------------------------------------------

Firewalls
--------------------------------------------

VPN concentrators
--------------------------------------------

SSL accelerators
--------------------------------------------

Load balancers
--------------------------------------------

DDoS mitigator
--------------------------------------------

Aggregation switches
--------------------------------------------

Taps and port mirror
--------------------------------------------



SDN
============================================

*************************************************
Given a scenario, implement secure systems design
*************************************************

Hardware/firmware security
=================================================

FDE/SED
---------------------------
TPM
---------------------------
HSM
---------------------------
UEFI/BIOS
---------------------------
Secure boot and attestation
---------------------------
Supply chain
---------------------------
Hardware root of trust
---------------------------
EMI/EMP
---------------------------

Operating systems
=================================================
Types
----------------------------

Network
^^^^^^^

Server
^^^^^^

Workstation
^^^^^^^^^^^

Appliance
^^^^^^^^^^^

Kiosk
^^^^^^^^^^^

Mobile OS
^^^^^^^^^


Patch management 
----------------------------------------

Disabling unnecessary ports and services
----------------------------------------

Least functionality
----------------------------------------

Secure configurations
----------------------------------------

Trusted operating system
----------------------------------------

Application whitelisting/blacklisting
----------------------------------------

Disable default accounts/passwords
----------------------------------------

Peripherals
=====================================================

Wireless keyboards
--------------------------

Wireless mice
--------------------------

Displays
--------------------------

WiFi-enabled MicroSD cards
--------------------------

Printers/MFDs
--------------------------

External storage devices
--------------------------

Digital cameras
--------------------------


************************************************************
Explain the importance of secure staging deployment concepts
************************************************************
Sandboxing
======================

Environment
======================

Development
------------


Test
------------

Staging
------------


Production
------------


Secure baseline
======================


Integrity measurement
======================

*****************************************************
Explain the security implications of embedded systems
*****************************************************

SCADA/ICS
============================

Smart devices/IoT
============================

Wearable technology
--------------------

Home automation
--------------------

HVAC
===========================

SoC
===========================

RTOS
===========================

Printers/MFDs
===========================

Camera systems
===========================

Special purpose
===========================

Medical devices
----------------

Vehicles
----------

Aircraft/UAV
-------------


****************************************************************
Summarize secure application development and deployment concepts
****************************************************************

Development life-cycle models
=========================================

Waterfall vs. Agile
-------------------

• Secure DevOps

Security automation
----------------------

Continuous integration
----------------------

Baselining
----------------------

Immutable systems
----------------------

Infrastructure as code
----------------------


Version control and change management
=======================================

Provisioning and deprovisioning
=======================================

Secure coding techniques
=======================================

Proper error handling
----------------------------
Proper input validation
----------------------------
Normalization
----------------------------
Stored procedures
----------------------------
Code signing
----------------------------
Encryption
----------------------------
Obfuscation/camouflage 
----------------------------
Code reuse/dead code
----------------------------
Server-side vs. client-side execution and validation
-----------------------------------------------------
Memory management
----------------------------
Use of third-party libraries and SDKs
-------------------------------------
Data exposure
----------------------------

Code quality and testing
=======================================================

Static code analyzers
--------------------------------

Dynamic analysis (e.g., fuzzing)
--------------------------------

Stress testing
--------------------------------

Sandboxing
--------------------------------

Model verification
--------------------------------

Compiled vs. runtime code
======================================================

*******************************************
Summarize cloud and virtualization concepts
*******************************************

Hypervisor
===========================================
- The Hypervisor creates, runs, and manages VMs

Type I
----------------------------
- Type I Hypervisors run directly on hardware and does not require an OS
- Type I is often used in large data centers
- Each VM has its own kernel

- Examples:

    - VMware vSphere/ESXi
    - Windows Server Hyper-V
    - Kernal-Based VIrtual Machine (KVM)


Type II
----------------------------
- Type II Hypervisors run as software within an OS
- Type II is often used on PCs
- Each VM has its own kernel

- Examples:

    - VMware Fusion
    - Windows Hyper-V
    - VirtualBox


Application cells/containers
----------------------------
- Application Containers allow running services or software in an isolated environment
- Services and software must be compatible with the hosting OS (can't run a linux application container on a windows host)
- Application containers share the kernel of the host

VM sprawl avoidance
============================================
- VM sprawl occurs when there are VMs that are not managed properly
- VM sprawl can drain resources (unnecessary VMs consume memory and processor power)
- VM sprawl can present security concerns (VMs may not be updated/patched properly)

VM escape protection
============================================
- VM escape occurs when an attacker is able to exploit a VM and gain access to the host system from within the VM

Cloud storage
============================================

Cloud deployment models
============================================

SaaS
---------

PaaS
---------

IaaS
---------

Private
---------

Public
---------

Hybrid
---------

Community
---------


On-premise vs. hosted vs. cloud
============================================

VDI/VDE
============================================

Cloud access security broker
============================================

Security as a service
============================================


************************************************************
Explain how resiliency and automation strategies reduce risk
************************************************************

Automation/scripting
==========================================

Automated courses of action
-----------------------------

Continuous monitoring
-----------------------------

Configuration validation
-----------------------------


Templates
============================================

Master image
============================================

Non-persistence
============================================

Snapshots
---------------
- Snapshots are copies of a VM at a specific point in time
- Snapshots can be used to restore a VM when an issue arises

Revert to known state
------------------------

Rollback to known configuration
----------------------------------

Live boot media
----------------

Elasticity
============================================

Scalability
============================================

Distributive allocation
============================================

Redundancy
============================================
- Adds duplication to critical systems
- Aims to remove single points of failure

- Some types of redundancies:

    - Disk redundancy (e.g., RAID)
    - Server redundancy (e.g., failover clusters)
    - Site redundancy (e.g., hot/cold/warm sites)
    - Load balancing
    - Backups (local and offsite)
    - Alternate power (e.g., UPSs)
    - Environmental systems (e.g., cooling and ventilation)

Fault tolerance
============================================
- Aims to ensure that a system can carry on in the event of a failure or fault in one or more of its components


High availability
============================================
- Ensures data and services are available when needed
- Availability is enabled through redundancy and fault tolerance


RAID
============================================

****************************************************
Explain the importance of physical security controls
****************************************************

Lighting
============================================

Signs
============================================

Fencing/gate/cage
============================================

Security guards
============================================

Alarms 
============================================

Safe
============================================

Secure cabinets/enclosures
============================================

Protected distribution/Protected cabling
============================================

Airgap
============================================

Mantrap
============================================

Faraday cage
============================================

Lock types
============================================

Biometrics
============================================

Barricades/bollards
============================================

Tokens/cards
============================================

Environmental controls
============================================

HVAC
---------

Hot and cold aisles
--------------------

Fire suppression
-----------------

Cable locks
============================================

Screen filters
============================================

Cameras
============================================

Motion detection
============================================

Logs
============================================

Infrared detection
============================================

Key management
============================================
