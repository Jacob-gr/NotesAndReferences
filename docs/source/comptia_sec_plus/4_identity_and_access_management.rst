##############################
Identity and Access Management
##############################



************************************************************
Compare and contrast identity and access management concepts
************************************************************

Identification, authentication, authorization and accounting (AAA)
===================================================================
- Identification: Claiming an identity (e.g., Typing in a username)
- Authentication: Proving an identity (e.g., Typing in the password for a username)

    - Mutual Authentication: Both the server and client authenticating each other
    - One-way Authentication: Only the client is authenticated

- Accounting: Tracking or logging user/computer activity (e.g., audit trails, computer logs)
- **Note:** Do not confuse authorization and authority: authority is scope of access

Multi-factor authentication
===========================
- Multi-factor authentication uses two or more factors of authentication before granting access (e.g., something you have and something you know)
- **Note:** Using two methods within the same factor is still considered single-factor authentication, not dual-factor or multi-factor (e.g., something you know: password and pin)

Something you are
------------------
- Often Biometric: e.g., fingerprint, retina, iris, voice, facial recognition

Something you have
------------------
- Smart Card, Personal Identity Verification (PIV), Physical Tokens/Fobs

Something you know
------------------
- Passwords, PINs

Somewhere you are
------------------
- Geolocation (e.g., IP addresses geolocation)
- Physical location (e.g., MAC address signifying that you are at the location of a specific computer on a network)

Something you do
------------------
- Microsoft picture password using taps, gestures, or circles
- Dynamic typing (AKA behavioral biometrics)


Federation
===========================

Single sign-on
===========================

Transitive trust
===========================


********************************************************************
Given a scenario, install and configure identity and access services
********************************************************************


LDAP
=======================

Kerberos
=======================

TACACS+
=======================

CHAP
=======================

PAP
=======================

MSCHAP
=======================

RADIUS
=======================

SAML
=======================

OpenID Connect
=======================

OAUTH
=======================

Shibboleth
=======================

Secure token
=======================

NTLM
=======================


*******************************************************************
Given a scenario, implement identity and access management controls
*******************************************************************
      
Access control models
==============================

MAC
-----

DAC
-----

ABAC
-----

Role-based access control
-------------------------

Rule-based access control
-------------------------

Physical access control
==============================

Proximity cards
----------------

Smart cards
----------------
- Common form factors:
    
    - Rectangular plastic card with an embedded microchip
    - USB token

- Provide dual-factor, certificate-based authentication
- Smart cards require embedded certificates and PKI
- Popular identification smart cards are the Common Access Card (CAC) and Personal Identity Verification (PIV)

Biometric factors
==============================

Fingerprint scanner
----------------------
- Reads finger prints

Retinal scanner
----------------------
- Reads patterns of blood vessels on eye
- Often requires physical contact with the scanner, which can be considered unhygenic
- Can reveal information on personal health, which some consider a potential HIPA violation

Iris scanner
----------------------
- Reads patterns on iris rings
- Does not require physical contact with scanner

Voice recognition
----------------------
- Measures voice patterns

Facial recognition
----------------------
- Scans facial patterns
- Can be problematic in low light conditions

False acceptance rate
----------------------
- The percentage of when the biometric system incorrectly identifies an unauthorized user as an authorized user

False rejection rate
----------------------
- The percentage of when the biometric system incorrectly rejects an authorized user

Crossover error rate
----------------------
- The point where FAR and FRR overlap when plotted on a graph
- The lower the CER, the more accurate the system

Tokens
==============================


Hardware
---------
- Physical device that displays rolling codes
- Provides dual-factor authentication

Software
---------

HOTP/TOTP
---------
- HOTP: HMAC-based One Time Password

    - One-tim password algorithm combining a secret key and incrementing counter
    - Password does not expire until it is used

- TOTP: Time-based One Time Password

    - Short-lived passwords that expire after a certain duration (e.g., 60 seconds)

Certificate-based authentication
=================================

PIV/CAC/smart card
-------------------

IEEE 802.1x
-------------------

File system security
=================================

Database security
=================================


*******************************************************************
Given a scenario, differentiate common account management practices
*******************************************************************


Account types
================================================

User account
----------------------------------------

Shared and generic accounts/credentials
----------------------------------------

Guest accounts
----------------------------------------

Service accounts
----------------------------------------

Privileged accounts
----------------------------------------


General Concepts 
================================================

Least privilege
----------------------------------------

Onboarding/offboarding
----------------------------------------

Permission auditing and review
----------------------------------------

Usage auditing and review
----------------------------------------

Time-of-day restrictions
----------------------------------------

Recertification
----------------------------------------

Standard naming convention
----------------------------------------

Account maintenance
----------------------------------------

Group-based access control
----------------------------------------

Location-based policies
----------------------------------------


Account policy enforcement
================================================

Credential management
----------------------------------------

Group policy
----------------------------------------
- Group Policy is a Windows feature to facilitate managing user accounts and computers
- Allows Group Policy administrators to configure a setting in a Group Policy Object (GPO) and apply the setting to many users/computers in a domain

Password complexity
----------------------------------------
- Complex passwords use a mix of numbers, characters, and symbols
- The key space for a password is C^N where C are the number of possible characters and N is the length. (e.g., a key space for a password of length 6 and all lowercase characters would be 26^6)
- Overly complex passwords are considered less secure because they are difficult to remember
- Generally, a strong password is a complex password of suitable length (some recommend 14 characters)

Expiration
----------------------------------------
- Password expiration can be configured in the Group Policy Editor
- Passwords can be set to expire after a number of days (e.g., 45)

Recovery
----------------------------------------
- Depending on what the environment is, password recovery options will differ (e.g., Help desk, automated recovery using email, etc.)
- Before a user recovers their password, it is important for the help desk to verify the users identity
- It is more secure for the new password to be a one-time use password and require the user to create a new one after logging in

Lockout and Disablement
----------------------------------------
- Too many wrong attempts at logging in will lock an account and require it to be reset by a technician
- Lockout requirements are set in the Group Policy Editor
- Two important settings:

    - Account lockout threshold: The max number of times a user can enter a wrong password before the account is locked
    - Account lockout duration: The duration the account is locked for. A setting of 30 will lock the account for 30 min, whereas a setting of 0 will require the account to be manually unlocked by a technician
    
Password history and Password reuse
----------------------------------------
- Password history options can be customized in the Group Policy Editor
- Prevents users from using the last x number of passwords (e.g., 12 would mean the user would not be able to re-use their last 12 passwords)

Password length
----------------------------------------
- The required minimum length of a password