####################
Cryptography and PKI
####################



***************************************************
Compare and contrast basic concepts of cryptography
***************************************************


Symmetric algorithms
=======================================

Modes of operation
=======================================

Asymmetric algorithms
=======================================

Hashing
=======================================

Salt, IV, nonce
=======================================

Elliptic curve
=======================================

Weak/deprecated algorithms
=======================================

Key exchange
=======================================

Digital signatures
=======================================

Diffusion
=======================================

Confusion
=======================================

Collision
=======================================

Steganography 
=======================================

Obfuscation
=======================================

Stream vs. block
=======================================

Key strength
=======================================

Session keys
=======================================

Ephemeral key
=======================================

Secret algorithm
=======================================

Data-in-transit
=======================================

Data-at-rest
=======================================

Data-in-use
=======================================

Random/pseudo-random number generation
=======================================

Key stretching
=======================================

Implementation vs. algorithm selection
=======================================

Crypto service provider
------------------------------------

Crypto modules
------------------------------------

Perfect forward secrecy
=======================================

Security through obscurity
=======================================

Common use cases
=======================================
- A use case describes how a user or organization will achieve a goal
- Use cases may involve actors, systems, goals, preconditions, triggers, postconditions, normal flow, and alternate flow
- Security use cases are to ensure confidentiality, provide integrity, and increase availability
- **Remember:** CIA: Confidentiality, Integrity, Availability

Low power devices
------------------------------------

Low latency
------------------------------------

High resiliency
------------------------------------

Supporting confidentiality
------------------------------------
- Prevents unauthorized disclosure of data
- Aims to ensure that data is only accessible by authorized personnel

- Some Methods to support confidentiality:

    - Encryption
    - Access Controls


Supporting integrity
------------------------------------
- Provides assurance that data has not been modified, tampered with, or corrupted

- Some Methods to support integrity:

    - Hashing
    - Input Validation
    - Digital Signatures (also provides non-repudiation and authentication)

Supporting obfuscation
------------------------------------
- Aims to hide data within data
- *Note:* Security through obfuscation is not recommended by professionals

- Some Methods to support obfuscation:

    - Stenography
    - Encrypted or encoded data within code

Supporting authentication
------------------------------------
- Authentication aims to prove the identity of a client/user
- *Note:* Authentication does not determine what a client/user is able to do or see (i.e., Authorization)

- Some Methods to support authentication:

    - Passwords (hashed and salted)
    - Biometrics
    - Smart Cards


Supporting non-repudiation
------------------------------------
- Aims to ensure that a client/user cannot deny that an action took place (e.g., emails, logins, etc.)
- Helps confirm the authenticity of data

- Some Methods to support non-repudiation:

    - Digital Signatures
    - Computer Logs

Resource vs. security constraints
------------------------------------
- Aims to provide suitable security with the right type of resources
- Often is an ongoing battle between cost and security

- Examples:

    - Supporting full disk encryption vs. the need for additional storage hardware
    - Supporting secure web applications vs. the usage of certain web browsers

***************************************************************
Explain cryptography algorithms and their basic characteristics
***************************************************************

Symmetric algorithms
=======================================

AES
------

DES
------

3DES
------

RC4
------

Blowfish/Twofish
-----------------


Cipher modes
=======================================

CBC
----

GCM
----

ECB
----

CTR
----

Stream vs. block
------------------


Asymmetric algorithms
=======================================

RSA
------

DSA
------

Diffie-Hellman
----------------

Groups
^^^^^^


DHE
^^^^^^


ECDHE
^^^^^^


Elliptic curve
---------------

PGP/GPG
---------------


Hashing algorithms
=======================================

MD5
-------------------------

SHA
-------------------------

HMAC
-------------------------

RIPEMD
-------------------------


Key stretching algorithms
=======================================

BCRYPT
-------------------------

PBKDF2
-------------------------


Obfuscation
=======================================

XOR
-------------------------

ROT13
-------------------------

Substitution ciphers
-------------------------


******************************************************************
Given a scenario, install and configure wireless security settings
******************************************************************


Cryptographic protocols
======================================

WPA
------------------

WPA2
------------------

CCMP
------------------

TKIP
------------------


Authentication protocols
======================================

EAP
------------------

PEAP
------------------

EAP-FAST
------------------

EAP-TLS
------------------

EAP-TTLS
------------------

IEEE 802.1x
------------------

RADIUS Federation
------------------


Methods
======================================

PSK vs. Enterprise vs. Open
-----------------------------

WPS
------------------

Captive portals
------------------

*****************************************************
Given a scenario, implement public key infrastructure
*****************************************************


Components
======================================

CA
------------------------

Intermediate CA
------------------------

CRL
------------------------

OCSP
------------------------

CSR
------------------------

Certificate
------------------------

Public key
------------------------

Private key
------------------------

Object identifiers (OID)
------------------------


Concepts 
======================================

Online vs. offline CA
------------------------

Stapling
------------------------

Pinning
------------------------

Trust model
------------------------

Key escrow 
------------------------

Certificate chaining
------------------------


Types of certificates
======================================

Wildcard
------------------------

SAN
------------------------

Code signing
------------------------

Self-signed
------------------------

Machine/computer
------------------------

Email
------------------------

User
------------------------

Root
------------------------

Domain validation
------------------------

Extended validation
------------------------


Certificate formats
======================================

DER
---------

PEM
---------

PFX
---------

CER
---------

P12
---------

P7B
---------
