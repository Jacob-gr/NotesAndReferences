Hardware
********

BIOS/UEFI Tools
=========================

The purpose of BIOS
-------------------

-  Firmware that initializes system hardware components
-  BIOS is software that's written to a CMOS Chip
-  POST (Power on self test) occurs during cold boot

   -  Cold boot is when computer starts from a completely off state
      (compared to a restart)

CMOS vs. BIOS
-------------

-  BIOS is Software interface that allows tweaking of settings on the
   computer from a very low level
-  CMOS is an EPROM chip
-  CMOS is the hardware that contains the BIOS software

BIOS vs. UEFI
-------------

-  BIOS is antiquated:
-  Access limited memory
-  No mouse movement
-  16 bit instructions
-  Bootable HDs of only 4GB
-  No network access
-  UEFI rides on top of legacy BIOS
-  UEFI firmware often includes a legacy BIOS compatibility mode
-  UEFI Advantages:
-  64 bit
-  Has network access (can download things from internet)
-  Graphically-rich interface
-  UEFI chips are removable/replaceable compared to CMOS
-  Boot disks larger than 2 TB (with GPT partitioning scheme)
-  can spread its data from chip to file system allowing for additional
   storage

EFI System Partition
--------------------

-  Shows up as 'System Reserved' in Disk Management console
-  Contains important boot files for UEFI

MBR vs. GPT (covered more in 220-902)
-------------------------------------

-  MBR
-  Older
-  4 Primary partitions
-  2TB volume size

-  GPT
-  Newer
-  Widespread OS support

Configuring BIOS
----------------

-  Can tweak detected hardware/disable devices
-  Can adjust clock of CPU
-  Adjust boot sequence
-  Choose to boot from USB rather than HD
-  Adjust date/time of machine
-  Settings can be lost if CMOS battery is not functioning
-  Adjust virtualization settings

Hardware Virtualization
-----------------------

-  Can virtualize machine hardware and share there virtual resources
   among multiple virtual machines
-  Intel VT-x and AMD-v are the two primary standards for virtualization
-  Hardware virtualization can be enabled/disabled via BIOS

BIOS/UEFI Security
------------------

-  Has different layers of security
-  Most basic is a password for changing BIO/UEFI settlings
-  Can be easily bypassed if machine is physically-accessible: removal
   of CMOS battery will reset all settings, including passwords. Some
   motherboards have jumpers that can reset settings as well.
-  TPM Encryption: CMOS EPROM chip that is affixed to the motherboard.
   Stores encryption keys that support full disk encryption (Microsoft
   BitLocker). If hard drive is stolen, data cannot be decrypted without
   keys on TPM. TPM and BitLocker are focused on securing storage
   subsystem.
-  3rd-Party Support - LoJack or Apple iCloud Service allows tracking
   and remote-wipe capabilities for devices. Low level BIOS/UEFI
   configuration

-  UEFI Secure Boot
-  Mechanism to prevent malware from infecting system boot loader
-  Required digital certificates stored on UEFI chip
-  Microsoft includes its own certs on OEM Windows 8.1 machines
-  **Note** This can cause problems with dual-booting other OSs (Having
   a linux boot partition on the same HD as Windows)

BIOS Hardware Diagnostics
-------------------------

-  UEFI can allow for in-depth view and customization of some system
   hardware: e.g., fan speeds, cpu clock/voltage, bus speed. Some UEFI
   come with custom profiles that can be applied to computer hardware.

Flashing BIOS
-------------

-  Installation of newer BIOS version to fix bugs and add functionality
-  **Note** Flashing can result in bricking (i.e. breaking) the computer
   if power is interrupted mid-installation

Replacing CMOS Battery
----------------------

-  Battery replaces trickle power to CMOS to keep settings
-  Use ESD wrist-strap when replacing battery
-  Batteries last 3-5 years

--------------

Motherboard Components
================================

Basic Definitions
-----------------

-  Motherboard - Printed circuit board (PCB) that allows communication
   between all system components. Often made of fiberglass. Other names:
   logic board, system board, circuit board, etc.
-  Form Factor - Physical dimensions/specifications

Buses
-----

-  Tracks of (usually) copper in the fiberglass motherboard that run
   throughout the motherboard. System buses consist of a control,
   address, and data bus.

ATX Form Factor
---------------

-  ATX - Advanced Technology Extended
-  Standard motherboard form factor for full sized case
-  Motherboards often silkscreen labels onto the motherboard to identify
   components and branding
-  Plastic risers keep the motherboard off the case and helps protect
   the motherboard

microATX Form Factor
--------------------

-  Compact motherboards
-  Commonly 6.75 x 6.75 in. or 9.6 x 9.6 in.
-  Backward compatible with ATX
-  Supports Intel, AMD, etc. chipsets

Mini-ITX Form Factor
--------------------

-  ITX form factor: used for Small Form Factor (SFF) computers
-  Low power use

Other Form Factors:
-------------------

-  Mini-ITX: 170mm x 170mm (6.70in x 6.70in)
-  Nano-ITX: 120mm x 120mm (4.75in x 4.75in)
-  Pico-ITX: 100mm x 72mm (3.95in x 2.83in)
-  Mobile-ITX: 75mm x 45mm (2.95in x 1.77in)

Chipset
-------

-  North Bridge (AKA Memory Controller Hub)
-  One of two core chips in the core logic chipset
-  Handles high priority hardware

   -  Memory, CPU, High-speed graphics bus (AGP or PCI Express)

-  Connected directly to the CPU via front-side bus
-  South Bridge (AKA I/O Controller Hub)
-  Second of two core chips in the core logic chipset
-  Handles low priority hardware

   -  PCI slots, onboard graphics controller, Flash ROM (BIOS), Super
      I/O

-  **Note:** CPUs are starting to integrate chipset functions on the
   die (i7 has an on-chip Memory Controller and PCIe)

Bus Speed
---------

-  Bus: Communication system that transfers data between system
   components
-  Bus Speed:
-  Parallel - Conventional PCI

   -  133 MB/s (32-bit, 33 MHz)
   -  533 MB/s (64-bit, 66 MHz)

-  Serial - PCI Express

   -  250 MB/s (x1) (pronounced "by one")
   -  32 GB/s (x16) (pronounced "by sixteen")
   -  x# represents number of data bus lanes utilized

CPU Sockets
-----------

-  ZIF - CPUs has pins
-  LGA - Socket has pins
-  Most CPU sockets have retention clips
-  Thermal paste, heatsink, and fan are placed on top of CPU to regulate
   temperature

Serial vs Parallel
------------------

-  High overhead of parallel leads to slower speeds than serial

PCI-X Expansion Slots
---------------------

-  64-bit parallel interface: 1 GB/s
-  Intended for high-end servers
-  Superseded by PCIe

PCIe Expansion Slots
--------------------

-  Color can be used to differentiate between PCI and PCIe
-  Slots can vary in length depending on bus lanes utilized
-  Serial, full duplex "lanes"
-  x1 cards can be used in x2 or greater slots

Mini PCI Bus Architecture
-------------------------

-  Used in laptops: requires internal access
-  Can enable many features: i.e., Wi-Fi, Bluetooth, Ethernet, etc

Power Supplies
--------------

-  Converts AC to DC power
-  Standard voltages: +3.3V, +5V, +12V
-  Standard Form Factor is ATX
-  Can have modular connector cables

Power Supply Connections
------------------------

-  ATX Power Cable
-  SATA Power Cables
-  4-pin Floppy Cables
-  6-pin PCI Express Power Cable
-  4-pin Molex
-  Fan Connectors on motherboard

Exterior Connectors
-------------------

-  USB 2/3
-  Audio
-  Power/Reset Buttons
-  Drive Activity Lights
-  Front Facing Bays

--------------

RAM Types
===================

RAM Basics
----------

-  Random-access memory: Volatile computer data storage

ROM
---

-  Read-Only Memory
-  Permanently or semi-permanently stores data
-  BIOS/UEFI ROM is EEPROM
-  Flash Memory can retain its contents without power (USB flash drive,
   SSD, etc), not ROM

Static RAM (SRAM)
-----------------

-  Used on processor for cache memory
-  Does not need periodic refresh like DRAM does (but needs power to
   hold the data)
-  Faster than DRAM, but much more expensive
-  Cache Effectiveness = Hit Ratio

Dynamic RAM (DRAM)
------------------

-  Common memory in computers: volatile memory
-  Contains tiny capacitors and transistors that store bits
-  **Dynamic:** Needs periodic (15ms) electrical refresh to maintain
   contents
-  Speed denoted in MHz or MBps
-  Slower because DRAM is independent of system bus clock

SDRAM
-----

-  Synchronous Dynamic RAM
-  Faster because cycles run in sync with motherboard clock
-  DDR: Two transfers per cycle
-  DDR2: Lower voltage, less crosstalk
-  DDR3: Even lower voltage, thermal sensor capability
-  DDR4: Bleeding edge
-  DDR levels are not interoperable
-  A Module contains multiple RAM chips, each containing ICs
-  Keying/handling guidelines on RAM stick
-  Some SDRAM can have heat spreaders that can act as a type of heat
   sync

RAM Small Form Factors
----------------------

-  SO-DIMM
-  Mini-DIMM
-  Micro-DIMM
-  Basic operations are same, but memory density is less than larger
   form factors

Reading RAM Specifications
--------------------------

-  RAM SPECS
-  DDR3 1600 (PC3 12800)
-  Timing 7-8-7-20
-  Cas Latency 7
-  Voltage
-  DDRxxx is the standard used to classify memory chips. xxx refers to
   Bus Speed of memory (transactions per second). E.g., DDR400 has
   400MTps.
-  PCyyyy is the standard used to classify memory modules
-  1600: Maximum clock speed that memory chip supports. Real base clock
   speed of memory is half the number.

-  Timing:
-  First number: CAS Latency (tCL)

   -  This is the most important memory timing. CAS stands for Column
      Address Strobe. If a row has already been selected, it tells us
      how many clock cycles we'll have to wait for a result (after
      sending a column address to the RAM controller).

-  Second number: Row Address (RAS) to Column Address (CAS) Delay (tRCD)

   -  Once we send the memory controller a row address, we'll have to
      wait this many cycles before accessing one of the row's columns.
      So, if a row hasn't been selected, this means we'll have to wait
      tRCD + tCL cycles to get our result from the RAM.

-  Third Number: Row Precharge Time (tRP)

   -  If we already have a row selected, we'll have to wait this number
      of cycles before selecting a different row. This means it will
      take tRP + tRCD + tCL cycles to access the data in a different
      row.

-  Fourth Number: Row Active Time (tRAS)

   -  This is the minimum number of cycles that a row has to be active
      for to ensure we'll have enough time to access the information
      that's in it. This usually needs to be greater than or equal to
      the sum of the previous three latencies (tRAS = tCL + tRCD + tRP).

Single-sided vs. Double-sided SDRAM
-----------------------------------

-  Single-sided: one bank of memory chips that functions as a unit
-  Preferred
-  Can have chips on both sides of module, need to refer to manual

Error Checking
--------------

-  Soft errors: Power glitch, line noise, heat, static, etc
-  Parity: Adds an extra bit to perform basic error detection
-  Costs overhead on memory
-  ECC RAM (for servers) corrects single-bit errors instead of crashing
   system

Channels
--------

-  Goal: Increase transfer rate between SDRAM and MCH by moving beyond a
   single channel (one channel for entire bus)
-  Dual Channel: Modules installed into matching banks (color-coded).
   Should install memory in pairs in same-colored banks. Nothing to do
   with DDR
-  Same for Triple and Quad channels

Buffered vs. Unbuffered
-----------------------

-  Buffered RAM (also called registered RAM) includes extra circuitry to
   maintain system stability
-  Used in servers (modules called RDIMM)
-  Often includes ECC code
-  Scalability at a cost

RAM Compatibility
-----------------

-  Should install in pairs, but channeling requires it

RAM Testing
-----------

-  Some OSs can perform memory tests
-  Also third-party software
-  Hardware testers are best indicators to indicate good/bad RAM

--------------

PC Expansion Cards
============================

Planning System Expansion
-------------------------

-  Does motherboard support the expansion card?
-  Is there space in the computer/motherboard for an additional card?
-  Is there enough wattage?
-  Is there a driver available for the hardware?

Installing Expansion Cards
--------------------------

-  RTFM to determine if driver or hardware is installed first
-  Handle components at non-contact edges
-  Press card firmly and evenly in slot
-  Unplug computer and wear ESD strap prior to install
-  PCO-X/PCI has PCIe compatibility

Configuring Expansion Cards
---------------------------

-  Is hardware Plug and Play or vendor's driver?
-  Is driver on a DVD or online?
-  Online has more recent version of driver compared to DVD

Riser Cards
-----------

-  PCI/PCIe expansion card that allows plugging in a card perpendicular
   to the motherboard. The riser card is ofter short, but rises enough
   to allow a cards to be inserted in a computer at a 90-degree angle.

Video Card Basics
-----------------

-  Components
-  Memory
-  Graphical Processor Unit (GPU) with heat sink
-  connectors to motherboard
-  connectors to display devices

-  Slot Types
-  AGP, PCIe x16
-  Some cards are Single vs. Dual Slot

-  Bridge connectors (often 6 or 8 pin PCIe connectors) allow for GPUs
   to work together. (NVIDIA SLI / AMD Radeon CrossFire)

-  Thunderbolt Interface
-  Combines PCIe and DisplayPort into one serial signal
-  Provides video+power (AKA active interface)
-  Can be used for peer-to-peer networking
-  Can support daisy-chaining
-  **Note:** Don't get confused:

   -  Apple Thunderbolt (active)
   -  Mini DisplayPort (passive) (just video, no power)
   -  Ports look the same

Video and TV Capture
--------------------

-  TV tuner card
-  Can capture video input from tv (coaxial, RGB, etc) and render on
   monitor or output via HDMI, DisplayPort, etc.

-  Video Capture Card
-  captures video from cameras, console, video hardware, etc. and allows
   rendering on computer monitor

Network Interface Card (NIC)
----------------------------

-  Take note of ports
-  Analog modem vs. NIC

   -  Jacks on analog modem are thinner (phone cable) compared to RJ-45
      Ethernet connector

-  Motherboards often provides integrated RJ-45 networking jacks

-  Also comes in Wi-Fi expansion cards (often has an antenna)

Cellular Cards
--------------

-  Allows tethering smartphone to computer to connect to internet
-  Mini PCI Cellular are available in Mini PCI for laptops, but are also
   in the form factor of a Plug and Play USB

Old-School Communications Cards
-------------------------------

-  Parallel ports (printers)
-  Serial (networking)

Sound Cards
-----------

-  Most motherboards have integrated audio in 1/8 in. ports
-  PCIe and USB External audio interfaces are available

Storage Cards
-------------

-  SATA and SAS
-  Serial ATA (SATA)
-  External SATA (eSATA)
-  Serial Attach SCSI (SAS)
-  Used for HDs and Storage

USB and FireWire
----------------

-  USB 3 = 5 Gbps
-  USB 2 = 480 Mbps
-  IEEE 1394 (FireWire) = 400/800 Mbps
-  FireWire is less common in modern hardware

--------------

Storage Devices
=========================

Magnetic Hard Drives
--------------------

-  AKA Mechanical HD
-  Parallel ATA (PATA) 40 pin interface
-  Jumpers need to be used for SCSI hookups to signal if drive is a
   primary or secondary
-  Power Molex hookup

PATA and SATA
-------------

-  ATA - Advanced Technology Attachment
-  Parallel ATA (PATA)
-  AKA Integrated Drive Electronics (IDE) or Enhanced IDE (EIDE)
-  Stack of platters that stores data
-  Actuator arm moves read/write head over the platters
-  Parallel ports, must use jumpers to signify primary/secondary. Often
   instructions are on the sticker on the top of HD

-  Serial ATA (SATA)
-  Needs data and power hookups
-  Faster than parallel
-  Smaller cables (no 40pin connectors)
-  SATA interfaces are smaller (higher density)

SCSI and SAS
------------

-  SCSI - Small Computer System Interface
-  SCSI standard meant as a universal command language. It's a protocol
   for how computers interact with peripherals. SCSI is antiquated and
   modern hardware is more SAS based.
-  Each SCSI device had to have a unique ID

-  SAS - Serial-Attached SCSI
-  Takes robustness of SCSI and puts it in a serial context. Often used
   with Servers/High-Impact systems

-  Other SCSI:
-  iSCSI - Internet Protocol using SCSI (network-based storage)
-  SCSI over Fiber Channel

Hard Drive Geometry
-------------------

-  On the Platter:
-  Track:

   -  A continuous track around the platter

-  Sector Track

   -  The group of sectors from the innermost edge to the outermost edge
      of the platter: shaped like a pie wedge.

-  Sector

   -  The area on the track within a sector track: one slice of the pie
      wedge
   -  Sector sizes are all uniform. Density is higher toward the center
      of the platter,

   -  Cluster
   -  Allocation unit that OS uses to store information
   -  Contiguous sectors
   -  **Note:** Smallest element of data storage on a HD. HDs do not
      write to single sectors, but rather a cluster.

HD Speeds
---------

-  5,400 RPM (5.6 ms latency)
-  7,200 RPM (4.1 ms latency)
-  10,000 RPM (3.0 ms latency)
-  latency is how quickly drive can retrieve data

Solid State Drives
------------------

-  No moving parts
-  5.25 in. is standard SSD size for computer
-  Uses non-volatile ram chips
-  Much faster access speeds

Flash Memory Cards
------------------

-  CompactFlash Cards / SD Cards
-  Adapters for microSD / to SD
-  Different forms of Proprietary flash memory cards
-  e.MMC for Mobile phones and tablets

HD Enclosers
------------

-  HD housing with interface connector to hookup a HD and a USB cable to
   plug into another computer. Able to see HD as an external storage
   disk.

RAID Levels
-----------

-  Redundant Array of Independent Disks
-  Enables Performance/Fault tolerance

-  Raid 0
-  AKA Stripe Set or Striped Volume
-  Splits data evenly across two or more disks
-  **Note:** Does not have parity information, redundancy, or fault
   tolerance: one drive failure causes the entire array to fail.
-  Speed is the intended goal for RAID 0
-  Intended for applications that require high performance and a re able
   to tolerate low reliability (e.g., scientific computing, gaming)

-  RAID 1
-  Disc Mirroring
-  An exact copy of a set of data is maintained on two or more disks
-  **Note:** Does not provide parity, striping, or spanning of disk
   space across multiple disks.
-  Array can only be as big as smallest member disk
-  Intended when read performance or reliability is more important that
   write performance or storage capacity
-  Good for protecting system drives. On a primary drive failure, can
   resume from second drive

-  RAID 2
-  Rarely used in practice

   -  Stripes data at the bit, rather than the block, level
   -  Uses Hamming code for error correction
   -  Has very high data transfer rates
   -  Complexity offers little advantage over parity, so RAID 2 is not
      commonly implemented

-  RAID 3
-  Rarely used in practice
-  Stripes data at they byte level with a dedicated parity disk
-  Requires all disks spin synchronously and provides no significant
   advantage over other RAID levels: became obsolete

-  RAID 4
-  Stripes data a block level with dedicated parity disk
-  Provides good performance of random reads, but performance of random
   writes is low due to writing all parity data to a single disk

-  RAID 5
-  Block level stripping with distributed parity
-  Compared to RAID 4, parity information is distributed among the
   drives
-  More robust: requires that all drives, but one, be present to
   operate. Upon failure of a drive, reads can be calculated from
   distributed parity so that no data is lost.
-  Requires at least 3 disks
-  Increased write performance compared to RAID 4, but slower than RAID
   0
-  Good for fault tolerance

Hybrid RAID
-----------

-  RAID 01 (RAID 0 + 1)
-  Mirroring of stipes
-  50 percent disk space efficiency
-  Benefits of RAID 0 speed with redundancy of RAID 1

-  RAID 10 (RAID 1 + 0)
-  Stipes of mirrors
-  Preferred for database, email, and web servers

Optical Drives
--------------

-  Written surface is bumpy and read by a laser beam
-  CD-ROM - Read Only
-  CD-RW - Re-writable
-  DVD - Higher capacity
-  Blu-Ray - Even higher capacity

Tape Drives
-----------

-  Inexpensive and Reliable
-  Contents can be encrypted
-  Contents can be compressed
-  Easy physical offsite backups
-  Slower write speeds to tape
-  Being superseded by cloud backups for some businesses

--------------

CPUs and Cooling
==========================

Preliminary Ideas
-----------------

-  System Clock
-  Quartz Crystal Oscillator

   -  Quartz is able to oscillate at a steady and precise speed.

-  Hertz = clock cycle
-  CPUs contain internal registers, data buses and address buses run
   from CPU to SDRAM

   -  Data runs on data bus
   -  Location in memory is transmitted on address bus

CPU Form Factors
----------------

-  PGA - Pin Grid Array
-  Processor die has the pins, socket has the holes
-  Common in Intel
-  LGA - Land Grid Array
-  Socket has the pins, Processor has plated contacts
-  Common in AMD

-  Limited compatibility based on motherboard

-  Silver is considered the best conductor, with gold, copper, and tin
   following

-  Many hardware contacts use gold-plated copper to maximize
   conductivity

Intel CPU Sockets
-----------------

-  LGA 775
-  Land Grid Array
-  775 represents number of contacts

-  LGA 1150

-  LGA 1155
-  Sandy Bridge Architecture

-  LGA 1156
-  Integrated Northbridge

-  LGA 1366
-  Triple channel RAM: separate Northbridge

-  LGA 2011
-  Six cores; Quad channel RAM; overclocking

AMD CPU Sockets
---------------

-  **Note:** PGA means pins are on the chip

-  Socket AM3
-  PGA-ZIF; 941 contacts

   -  PGA-ZIF: Pin Grid Array - Zero Insertion Force

-  Socket AM3+
-  942 contacts

-  Socket FM1
-  905 contacts

-  Socket FM2
-  904 contacts

-  Socket FM2+
-  906 contacts

Processor Cores and Speeds
--------------------------

-  Core is the brain of the CPU
-  Clock speed means number of instructions per second
-  Thermal output: wattage (lower is better)
-  Cache is fast memory (l1, L2, L3)

CPU Caches
----------

-  Dedicated L1
-  Locality keeps most critical data in the L1 cache
-  Lowest latency
-  2 loads per cycle

-  Dedicated L2
-  Sized to accommodate the majority of working sets
-  Dedicated to eliminate conflicts between shared caches

   -  Better for Virtualization

-  Shared L3
-  Shared by all cores
-  Victim-cache architecture

Hyperthreading
--------------

-  Introduced in 2002
-  Xeon (server); Pentium 4 desktop

-  For each physical core, the processor addresses to logical 'cores'

-  OS needs to support HT

Virtualization Support
----------------------

-  Intel VT-X
-  AMD-V

-  Instructions that allow system to differentiate physical vs virtual
   HW access

-  Must be enabled in UEFI setup to maximize a processor's native
   virtualization capabilities

32-Bit vs 64-Bit Architecture
-----------------------------

-  32-bit CPUs can generate up to 4 billion memory addresses (4 GB RAM)

-  64-bit addressing needs OS an app support

-  32-bit applications on Windows are stored in
   C::\Program Files(x86)

Misc
----

-  Trend is to bring components onto CPU die (Caches, integrated GPU,
   etc)

-  No-Execute (NX) / Execute Disable (XD) bit
-  Flag set in UEFI setup
-  If enabled, the CPU segregates memory for processor-only use: reduces
   possibility that malware can corrupt critical memory areas.

Heat Sinks
----------

-  Aluminum alloy fins that spread out heat
-  Small fins = more surface area = more heat dissipation
-  Attached to CPU with thermal paste. Thermal paste helps ensure
   uniform heat transfer to heatsink
-  Often used with fans to dissipate the heat

Fans
----

-  Fanless/Passive
-  Used for small set-top boxes / Raspberry PIs
-  Used for silence

Liquid-based Cooling
--------------------

-  Water instead of air as a heat conductor
-  What to cool:
-  CPU
-  GPU(s)
-  Chipset

--------------

PC Connection Interfaces
==================================

Connection Basics
-----------------

-  Analog vs. Digital
-  Analog refers to signal path of various intermediate values
-  Digital refers to 0 and 1: on off state
-  Distance Limitations
-  Data transfer speed
-  Cable Quality
-  Digital Rights Management (DRM)
-  Frequencies

Universal Serial Bus (USB)
--------------------------

-  v1.1 (1998): 12Mbps
-  v2 (2000): 480Mbps
-  v3 (2008): 5 Gbps
-  v3.1 (2013): 10Gbps
-  Power charging
-  500mA (USB 2.0)
-  099mA (USB 3.0)

-  Form Factors:
-  A: Computer devices
-  B: Larger, stationary peripherals (Micro B, Mini B, etc)

Serial ATA (SATA)
-----------------

-  SATA1 (150 MB/s)
-  SATA2 (300 MB/s)
-  SATA3 (600 MB/s)
-  eSATA (6.6 ft max length)

-  Uses Keyed connectors: failsafe to ensure can't insert plug backwards

Network Connection Interfaces
-----------------------------

-  Registered Jack (RJ)
-  RJ-45 (Ethernet)
-  8 wires
-  RJ-11 (phone)
-  4 wires
-  Thunderbolt (P2P Mac networking)
-  Dual protocol I/O cable (carries data and power)
-  Can transmit video and/or network data and power
-  Connectors look identical to Mini DisplayPort adapter
-  Can't use a DisplayPort cable to connect to a Thunderbolt device
-  Can daisy-chain Thunderbolt peripheral devices since it carries power

Multimedia Connection Interfaces
--------------------------------

-  Video Graphics Array (VGA)
-  Supports HD
-  Analog Connector
-  Only for video

-  Digital Video Interface (DVI)
-  Digital Connector
-  Only for video

-  HDMI
-  Carries digital video and audio signals

-  Audio
-  1/8 in. input
-  Analog Signal

Bluetooth
---------

-  Popular for mobile electronics
-  Personal Area Network (PAN): 'lose the wires'
-  1-100m range; 1-24 Mbps (depends on class)
-  Basic security, but hackable
-  One-to-many communication
-  Operates on 2.4 GHz band

Infrared (IR)
-------------

-  Laptops/smartphones/remotes have IR transmitters
-  1-to-1 communication
-  Uses Pulse Code Modulation (PCM) to transmit encoded data
-  Needs line of sight
-  IR does have a diffuse mode to spread the signal out

Radio Frequency (RF)
--------------------

-  Radio wave (3 kHz - 300 GHz) data transfer
-  IEEE 802.11 standards (Wi-Fi)
-  Radio Frequency ID (RFID)

Near Field Communication (NFC)
------------------------------

-  Used with smartphones to facilitate data exchange (<20 cm distance)
-  Very different from Bluetooth (power, transfer rate)
-  E.g., Apple Pay

--------------

The Power Supply
==========================

Understanding the Power Supply Unit (PSU)
-----------------------------------------

-  Converts AC from wall outlet to DC.
-  Provides steady Direct Current power to the motherboard and
   components
-  Ampere (amp, A) - Rate of electron flow past a point in one second
-  Voltage - a potential difference (AKA electrical pressure pushing the
   electrons): goes from high to low
-  Watts = Volts \* Amps (direct relationship)
-  Direct relation between voltage numbers and current numbers
-  ATX standards:
-  3.3V
-  5V
-  12V
-  Power rating given in watts
-  PSU has both modular and non-modular form factors

-  Flex ATX form factor is used for servers
-  Often have quick-release handles for quick changes

-  Motherboard has 20 or 24 pin connector for main power supply from
   PSU. Sometimes has a smaller 8 pin connector in addition to the
   larger one.

Reading PSU Specifications
--------------------------

-  Watts = Volts \* Amps (direct relationship)
-  PSU often has a switch to change between 110V and 220V wall power

PSU Connector Types
-------------------

-  SATA (3.3V, 5V, 12V): 7 pins
-  Molex (5V. 12V)
-  4/8-pin (12V)
-  PCIe 6/8 pin (12V)
-  20-pin (12V)
-  24-pin (3.3V, 5V, 12V)

Testing Power Supplies
----------------------

-  Can refer to pin diagrams and use millimeter to check connector
-  Can have dedicated power supply testers that are more robust

PSU Installation Notes
----------------------

-  PSU is a Field Replaceable Unit (FRU)
-  Should never open the PSU itself
-  More cables = reduced airflow (modular is better)
-  Size PSU properly
-  Consider redundancy PSUs for servers

Understanding Power Rails
-------------------------

-  Single-rail: one internal bus for all power connectors
-  Single 12V rail on one circuit in the PSU that provides power to the
   motherboard
-  Multi-rail: Each PSU connector has its own rail
-  Has multiple 12V rails on separate circuitry providing power to each
   12V connector
-  No performance difference!
-  Difference is there is an ability to have additional stability and
   over-current protection for multi-rail

--------------

Custom PC Configurations
==================================

OEM vs. White Box
-----------------

-  OEM: Original Equipment Manufacturer
      -  Branded hardware (Apple)

-  White Box: PC or server with brand name
      -  Small systems
      -  Homebuilt systems

Graphic/CAD/CAM Design Workstations
-----------------------------------

-  Need to be beefy systems
-  Multicore CPUs, High-end video, lots of RAM, etc
-  Full Tower Form Factor

Audio/Video Editing Workstation
-------------------------------

-  Digital Audio Workstation (DAW)
-  Emphasize specialized audio and video; large, fast HDs, multiple
   monitors
-  Full Tower
-  Breakout Box with additional inputs/outputs

Virtualization Host
-------------------

-  Use case: System Engineers
-  Emphasizes maximum RAM and CPU cores
-  OS: Linux, Windows; Hypervisors
-  Form Factor: 1-2 rack-mounted chassis
-  Potential Gotchas: Scale-out; redundancy; hardware compatibility;
   licensing

Gaming PC
---------

-  Use case: PC gaming enthusiast
-  Emphasizes: Multicore CPU; High-end video/sound; high-end cooling;
   beefy PSU
-  OS: Most often Windows
-  Form Factor: Full-tower to portable
-  Potential Gotchas: Power, heat, noise, fast evolving tech

Home Theater PC (HTPC)
----------------------

-  Use case: Home media enthusiasts
-  Emphasizes: Surround sound audio; HDMI output; TV tuner
-  OS: Linux
-  Form Factor: HTPC compact small form factor (SFF)
-  Potential Gotchas: Power, heat, noise

Home Server PC
--------------

-  Use case: Networking professionals
-  Emphasizes: Media streaming; File/printer sharing; Gigabit NIC; RAID
   array
-  OS: Linux, Windows, OS X
-  Form Factor: Rack or set-top
-  Potential Gotchas: Compatibility with other hardware, high cost of
   server hardware/software

Thick Client PC
---------------

-  Use case: Business end users
-  Emphasizes: Desktop line-of-business (LOB) heavy applications
-  OS: Windows, OS X
-  Form Factor: Desktop, mini-tower
-  Potential Gotchas: Management complexity

Thin and Zero PC
----------------

-  Use case: Business end users
-  Emphasizes: Basic connectivity application
-  OS: Linux, Windows
-  Form Factor: Small Form Factor (SFF)
-  Potential Gotchas: Network failure

-  Zero Client doesn't have a base OS, it boots directly to a central
   management server

VDI Basics
----------

-  VDI: Virtual Desktop Infrastructure
-  Can 'stream' applications to user
-  Deploy app as a remote app
-  Clients connect via network and can stream app
-  Helps Fixes compatibility problems

-  Enables Remote Desktop Connections (RDP - Port 3389)

--------------

Display Types
========================

Display Basics
--------------

-  Display measurements are taken diagonally

LCD Displays
------------

-  Liquid crystals don't emit light themselves, light comes from a
   backing source
-  Fluorescent vs. LED backlighting
-  Characterized by weak blacks because the backlights are always on
-  Twisted Nematic (TN) vs In-Plane Switching (IPS)

-  TN
-  Oldest tech
-  Fast response time
-  Narrow viewing angle
-  Questionable color reproduction

-  IPS
-  Expensive
-  Slower response time
-  Better viewing angles and color reproduction compared to TN

-  Organic Light Emitting DIOD (OLED)
-  Cutting edge
-  Very expensive
-  Organic material is what emits the light
-  Can be used with flexible displays

Plasma Displays
---------------

-  Ionized gas packed into cells that illuminates when an electrical
   current hits it
-  Deep blacks, strong color, good viewing angles
-  Subject to radio interference, higher energy costs, and burn in of
   images
-  Not often a desktop monitor

Digital Projectors
------------------

-  Types: LCD, DLP, LCOS
-  Large throw ratio: screen size
-  Brightness matters: Lumens
-  Often has On Screen Display (OSD) configuration
-  Lamps burn out and are expensive
-  Generates lot of heat
-  Make sure that projectors power off 'cleanly'
-  Need to disperse heat

Display Resolution
------------------

-  Number of pixels in each dimension (width x height)
-  Native resolution: physical monitor dimensions

Aspect Ratio
------------

-  Relationship between display width and height
-  Width/Height
-  Display gets wonky if you don't scale correctly

-  4:3
-  Standard
-  Usually 2014 x 768

-  16:10
-  Golden Ratio
-  Supplanted by 16:9

-  16:9
-  HD
-  1920 x 1080

Refresh Rates (RR)
------------------

-  RR - How many times per second the screen is repainted
-  Frame Rate (FR): Rate at which monitor displays consecutive screen
   images
-  60 Hz is standard for RR

Analog vs Digital Video
-----------------------

-  Analog: Continuous variable electrical signal
-  8mm, VHS, etc
-  Subject to deterioration

-  Digital: Discrete, sampled values (0 and 1)
-  MiniDV, DVD
-  Seamlessly integrate with PCs

Privacy / Anti-glare Filters
----------------------------

-  Privacy eliminates shoulder surfing: greatly reduces viewing angle
-  Antiglare reduces eyestrain

Multiple Displays
-----------------

-  Introduced in Windows 98
-  Most PCIe video cards have multiple outputs
-  Can use hotkey (Win Key + P) to quickly change dual display settings
-  May need to disable On-board video to resolve PCIe GPU issues
-  Can manage monitor setup in control panel

--------------

PC Connector Types
=============================

Display Connectors
------------------

-  Composite Video
-  Yellow: Video
-  White/Red: Left Right Audio

-  Component Video
-  A bit richer than Composite
-  Breaks out video 3 ways

-  Composite and Component are Analog

-  HDMI
-  Digital Audio and Video

-  Digital Video Interface (DVI)
-  Digital Video, no Audio

-  VGA
-  Analog Video
-  Only video, but can do 1080p
-  MiniD Form Factor: 15 pins

DVI
---

-  DIV-I (Single Link)
-  1080p
-  I means it is integrated: carries video + audio

-  DIV-I (Dual Link)
-  1080p and up
-  I means it is integrated: carries video + audio

-  DVI-D (Single Link)
-  Carries digital video only

-  DVI-D (Dual Link)
-  Carries digital video only

-  DVI-A
-  DVI Analog
-  Not commonly used

-  Mini-HDMI / HDMI
-  HDMI: High Definition Multimedia Interface
-  Uncompressed Digital Video and Audio
-  Does have DRM: High Bandwidth Digital Content Protection (HDCP)
-  Can prevent streaming to output devices

More Display Connectors
-----------------------

-  Coaxial
-  TV Tuners
-  Uses the 'F' connector
-  Carries Analog video and audio

-  DisplayPort
-  Connector is more rounded than USB
-  Has DRM
-  Multi-Protocol

-  Mini DisplayPort
-  Resembles Thunderbolt
-  Has DRM
-  Multi-Protocol

Device Cables and Connectors
----------------------------

-  PS/2
-  Round DIMM Connectors
-  Often used for Mouse and Keyboards
-  Can't unplug and re-plug: must restart to fix I/O issues

-  1/8 in/ jacks
-  Used for audio

-  Parallel Port (DB25)
-  Used to power external scanners/printers
-  Zip drives

-  Serial (DB9)
-  Sometimes used for Mice
-  Still found on Servers

-  Ethernet
-  Accepts RJ-45 connectors

-  USB Ports
-  Need to distinguish between USB 2 and USB 3

-  DVI Ports
-  Need to distinguish between Single and Dual Link

-  Game Port (DB15)
-  Old school connector for game pads

SATA and eSATA
--------------

-  Keyed, 7 pin connectors
-  eSATA cable is used with eSATA cards (external SATA)

SCSI and SAS
------------

-  Small Computer System Interface
-  Serial Attached SCSI
-  Not part of A+, but is for Server+
-  Higher performing and reliable than SATA
-  Often used for servers and businesses

USB and FireWire (IEEE 1394)
----------------------------

-  A connectors used for Desktops
-  Large B connectors used for things like printers
-  Mini B connectors used for things smaller devices
-  Super Speed (SS) can denote USB 3
-  USB C is reversible

-  FireWire
-  FireWire 400 vs FireWire 800

   -  Denotes transfer speed (400Mbps vs 800Mbps)

Adapters and Converters
-----------------------

-  Remember: Male vs. Female connectors and adapters

--------------

Common Peripheral Devices
====================================

Keyboard and Mouse
------------------

-  Mice began as analog (rubber ball), then optical, then wireless
-  QWERTY layout keyboards. Wireless, ergonomic, PC vs. Mac

Digitizers and Touch Pads
-------------------------

-  Some touch pads have capacitive touch pads/screens
-  Digitizers turn touch screens into a set of coordinates on a grid and
   tracks the movement across the grid

Scanner and Barcode Reader
--------------------------

-  Parallel, SCSU, USB, Bluetooth, Wi-Fi
-  Smartphones can scan
-  Barcode / Quick Response (QR) readers are great for asset tracking

Biometrics and Smart Cards
---------------------------

-  Password is what you know; biometric is who you are (Multi-factor
   Authentication (MFA))
-  Provide additional security
-  Also: fingerprint, iris/retina, voice, face, etc
-  Smart card contains Integrated Chip (IC) and stores authentication
   ID

Game Pads and Joysticks
-----------------------

-  Trends: DB15, USB, Bluetooth, Wi-Fi
-  Can convert some console to PC controller

Motion Sensors
--------------

-  Used for security and automated lighting control
-  Several types of detection technology
-  Passive IR, Microwave, etc

Digital Cameras and Webcams
---------------------------

-  Heavily replace by smartphones
-  Camcorders can do 4K
-  Webcams used for connectivity and security camera

MIDI-enabled Devices
--------------------

-  MIDI: Music Instrument Digital Interface
-  Connector looks like a combination between AT and PS/2

Printers
--------

-  Parallel, SCSI, USB, Ethernet, etc.
-  Dot-matrix, thermal
-  Inkjet, laser
-  Multi-function Printer (MFP)
-  Printers can present as a security vulnerability for businesses

Speakers
--------

-  Normally use 1/8 in. jack
-  Jacks are Tip-ring-sleeve (TRS)

KVM Switch
----------

-  KVM: Keyboard, Video, Mouse
-  Gives you console access to multiple servers/computers
-  Can use one set of peripherals on multiple computers
-  Can use a button to switch between clients

Smart TVs
---------

-  Television with integrated Internet
-  Wi-Fi and/or wired Ethernet
-  Has UI/Apps

Set-Top Boxes
-------------

-  TV tuner box
-  Digital Cable, Satellite

-  Digital Video Recorder (DVR)

-  Hybrid Box
-  Apple TV
-  Roku

--------------

SOHO Multi-function Devices
======================================

Defining a SOHO Multifunction Device
------------------------------------

-  SOHO: Small Office/Home Office
-  Devices should be able to handle 1 - 10 people
-  E.g., MFP (multi function printer)
-  Equipment usually around $1000 price point
-  Equipment is often shared on a network

Device Drivers
--------------

-  Should use vendor's driver and not plug and play

SOHO MFP Configuration
----------------------

-  Presenting Users with Options:
-  Collation
-  Staple management
-  Duplex Printing
-  Quality
-  Feeder Trays

Printer Sharing
---------------

-  Printer Sharing at OSI Layer 1
-  Serial (USB)
-  Ethernet
-  Wireless

   -  Bluetooth
   -  802.11 Wi-Fi
   -  Infrastructure vs. ad-hoc

-  Integrated Print Server
-  Advertises IP addresses/print queues and spools print jobs

-  Integrated Spooling Device (ISD)

Page Description Languages
--------------------------

-  Page Description Language (PDL) describes the appearance of a printed
   page more granularly than as a static bitmap

Cloud/Remote Printing
---------------------

-  IPP: Internet Printing Protocol
-  When advertising a printer on a network, it is done in accordance
   with protocols. IPP is the protocol for advertising printers of HTTP

-  Apple AirPrint (LAN)
-  Uses Bonjour

-  Google Cloud Print

Print Queue Administration
--------------------------

-  Centralized/Decentralized management software
-  Who has access?
-  Can use Least Privilege
-  Can schedule printer hours

Network Printer Security
------------------------

-  Change all defaults!
-  Security risks

-  Hard drive caching
-  Caches print jobs on spool cache

--------------

Print and Image Technologies
=======================================

Impact (Dot Matrix) Printers
----------------------------
- PPM: Pages per Minute
- Dot matrix (9-24 pin)
- Print head has an ink ribbon
      - Print head has clusters of pins that act 
            like a typewrite and forces the pressure of 
            the pin through the ink ribbon to form the letter.
      - Ink ribbon is consumable and is replaced
            as needed.
      - Higher pin printers produced better letters
      - Tractor feeder pulls pages through the printer

Thermal Printers
----------------
- Used in Point of Sale and Self Service kiosks
- Basically Dot matrix printer: has pins 
- Uses rolled paper (think receipt machines)
- Quieter than Dot Matrix
- Uses heat to transfer ink to page 
- Two types:
      - Heating element darkens special thermal paper
      - Heating element presses into page to form letter
- Connect to computer with Serial or Parallel port
- Newer versions use USB

Inkjet Printers
----------------
- Uses reservoirs of color and black
- Disperses ink droplets onto paper
- Nice resolution, good color
- Expensive ink consumables
- Uses USB, Wi-Fi, and Bluetooth

- Internals:
      - Feeder Mechanism
            - Prone to jamming
      - Duplexing Assembly may be required
      - Print Head (often is connected to ink reservoir)
      - Carriage/belt
      - Ink cartridges

- Should periodically calibrate printers

Laser Printers
--------------

- Represents highest print quality
- Uses toner (a dry ink powder)
- Uses lasters, voltage, power, heat, and toner
- Often on Ethernet networks
- Memory-intensive print jobs
- Can have on-board HDs
- Page rendering languages
      - PS, PCL, XPS
- Tone cartridges are replaceable
- Drum is contained in the toner cartridge

- Parts:
      - Separation pad ensures paper is fed correctly
      - Rollers move the paper
      - Duplexer enables front and back printing
      - Image drum contained within toner cartridge
      - Laser unit writes image to photoreceptor drum assembly
            via a mirror that carries reflects the laser beam
      - Paper enters fuser assembly where toner cast onto
            paper is fused

- Laser Printer Process:
      #. Cleaning
            - Small blade passes over drum: removes toner and charge for the
                  next printing cycle
      #. Processing (conditioning)
            - Required to prep the drum to hold an image
            - Highly negative charge is applied to the drum via
                  the Primary Corona wire (located inside the tone cartridge)
      #. Exposing (writing)
            - Laser writer discharges the negative drum charge where
                  the print image exists. Think of it as drawing the image
                  with a positive charge.
      #. Developing
            - Toner is attracted to the discharged (positive) area of the drum
      #. Transfer
            - Paper passes over the Transfer Corona wire and a strong positive charge
                  is applied to the backside of the paper
            - Paper passes very near to the rotating photosensitive drum
                  and attracts the toner onto the charged paper
      #. Fusing
            - Toner that has been attracted to paper is permanently fused
                  to the paper via heated fusing rollers
      #. Process restarts with step 1. (cleaning) for next page

Virtual Printers
----------------
- Used for print to file applications (Print to PDF)

--------------

Printer Maintenance
==============================

General Guidance
----------------
- Read printer messages
      - Can setup e-mail alerts over SMTP

- Have spare assets available
      - Toner
      - Maintenance kits
      - Paper

- Reset page counter after toner replacement


Laser Printer Maintenance
-------------------------
- Unplug device and let it cool down (fuser is HOT!)
- Clean exterior is alcohol and microfiber
- Brush out dust from crevices or use vacuum
- Use Q-tip and alcohol to clean wires
- Replace toner

- The Maintenance Kit
      - Each laser printer will have a maintenance kit
      - Comes with many parts that can be replaced in the printer

- Calibrate device (or hire out for calibration)

Inkjet Printer Maintenance
--------------------------
- Need to clean print heads
- Replace ink cartridges
- Calibrate printer
- Clear paper jams

Thermal Printer Maintenance
---------------------------
- Replace paper roll
- Ensure feed and tear-off mechanism functions
- Remove debris


Impact Printer Maintenance
--------------------------
- Replace ink ribbon
- Replace print head
- Replace tractor-feed paper








