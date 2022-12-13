# CCNA-Security-210-260-Module-2-Review
### 3 - Implementing AAA in Cisco IOS
https://medium.com/training-course-ccna-security-210-260/ccna-security-part-3-implementing-aaa-in-cisco-ios-4b13ab285f51

**What of the following are most likely used for authentication of a network admin accessing CLI of a Cisco router?** (Multiple Choice)

    a. √ TACACS+
    b. Diameter
    c. RADIUS
    d. √ ACS

**What allows granular control related to authorization of specific Cisco IOS commands being attempted by authenticated & authorized Cisco router admin?** (Multiple Choice)

    a. RADIUS
    b. Diameter
    c. √ TACACS+
    d. ISE
    e. √ TACACS

**What devices or users would be clients of an ACS server?** (Multiple Choice)

    a. √ Routers
    b. √ Switches
    c. VPN users
    d. Administrators

**What should be created & applied to router's vty line to enforce a specific set of methods to identify who a user is?**

    a. RADIUS server
    b. TACACS+ server
    c. √ Authorization method list
    d. Authentication method list

**What is the minimum size for an effective TACACS+ group of servers**: 1

**What do you configure AAA on the router with?** (Multiple Choice)

    a. ACS
    b. √ CCP
    c. √ CLI
    d. TACACS+

**What statement is true for ACS 5.x & later?**

    a. User groups are nested in network device groups.
    b. √ Authorization policies can be associated with user groups that are accessing specific network device groups.
    c. There must be at least 1 user in a user group.
    d. User groups can be used instead of device groups for simplicity.

**What statement are false for ACS 5.x & later?** (Multiple Choice)

    a. √ User groups are nested in network device groups.
    b. Authorization policies can be associated with user groups that are accessing specific network device groups.
    c. √ There must be at least 1 user in a user group.
    d. √ User groups can be used instead of device groups for simplicity.

**Where in ACS do you go to create a new group of admins?**

    a. √ Users and Identity Stores > Identity Groups
    b. Identity Stores > Identity Groups
    c. Identity Stores and Groups > Identity Groups
    d. Users and Groups > Identity Groups

**What method tests the most about the ACS configuration, without forcing you to log into router again?**

    a. ping
    b. traceroute
    c. √ test aaa
    d. telnet

**What could likely cause an ACS authentication failure, even when user is using the correct credentials?** (Multiple Choice)

    a. √ Incorrect secret on the ACS
    b. √ Incorrect IP address of the ACS configured on the router
    c. √ Incorrect routing
    d. √ Incorrect filtering between the ACS and the router
    
**Explain Access Control System (ACS)**:
 - a centralized authentization server to avoid creating the same user on each routers & switches

**What platform does Cisco ACS run**: Windows Server

**Explain Identity Services Engine (ISE)**:
 - an access control policy platform to validate a computer meets defined requirements

**Explain the protocol used inbetween ACS and Router**:
 - 2 protocols: Terminal Access Control Server (TACACS+) or Remote Authentication Dial-In Service (RADIUS)
 - TACACS+ being the most popular, using TCP layer 4, Cisco proprietary
 - RADIUS encrypts only the password, using UDP layer 4, Open standard

  **How to configure router to use ACS**

 - Start AAA, add user

    aaa new-model
    aaa authentication login AUTH_via_TACACS group tacacs+ local
    username USER1 privilege 15 secret Passw0rd!

 - Add tacacs server, apply to line vty 0, 1, 2, 3, 4

    tacacs-server host 192.168.9.1 key SvrP&ssw0rd
    line vty 0 4
    authorization exec Author-Exec_via_TACACS
    login authentication AUTH_via_TACACS

  **How to configure ACS Server to use router**
 - Note: GUI interface
 - Login to ACS app webpage
 - Left panel --> network resources --> Network devices & AAA clients
 - Click the same router in the device list
 - Under "Authentication Options", select TACACS+
 - Fill-in Shared Secret
 - Left panel --> Users & Identity Stores --> Internal Identity Stores --> Users
 - Click the right user in the list
 - Fill-in password
 - Left panel --> Access Policies --> Authorization
 - Click the same user as prev
 - Edit the command set (e.g., PermitAnyCommand)


### 4 - Bring Your Own Device (BYOD)
https://quizlet.com/363296085/ccna-security-210-260-byod-chapter-cuatro-flash-cards/?funnelUUID=4964f29c-a461-4158-b9d6-663ab0a3119e

**Which one is NOT a business driver for a BYOD solution?**

    a. Need for employees to work anywhere & anytime
    b. Increase in the type of devices needed & used by employees to connect to corporate network
    c. √ The lack of IPv4 address space
    d. Fluidity of today’s work schedules

**Which component provides Wi-Fi access for employees in home offices, branch offices, & on corporate campus?**

    a. WLAN controllers (WLC)
    b. Cisco AnyConnect Client
    c. √ Wireless access points (AP)
    d. Identity Services Engine (ISE)

**The RSA SecurID server/applicationprovides:**

    a. Authentication, authorization, accounting (AAA) functions
    b. √ One-time password (OTP) capabilities
    c. 802.1X enforcement
    d. VPN access

**The Identity Services Engine (ISE) provides:**

    a. Access, authentication, accounting
    b. √ Authentication, authorization, accounting
    c. Access, authorization, accounting
    d. Authentication, authorization, access

**Which of the following is not enabled through Cisco AnyConnect Client?**

    a. 802.1X
    b. VPN
    c. √ AAA
    d. Posture checking

**The purpose of the RSA SecurID server/application is to provide:**

    a. Authentication, authorization, accounting (AAA) functions
    b. √ One-time password (OTP) capabilities
    c. 802.1X enforcement
    d. VPN access

**The purpose of the certificate authority (CA) is to ensure:**

    a. BYOD endpoints are posture checked
    b. √ BYOD endpoints belong to the organization
    c. BYOD endpoints have no malware installed
    d. BYOD users exist in the corporate LDAP directory

**The Identity Services Router (ISR) PRIMARILY provides:**

    a. √ Connectivity in the home office environment back to the corporate campus
    b. WAN & Internet access for users on the corporate campus
    c. Firewall-type filtering in the data center
    d. Connectivity for the mobile phone environment back to the corporate campus

**Which is not a function of mobile device management (MDM)?**

    a. Enforce strong passwords on BYOD devices
    b. √ Deploy software updates to BYOD devices
    c. Remotely wipe data from BYOD devices
    d. Enforce data encryption requirements on BYOD devices

**Which is not an advantage of an On-Premise MDM solution?**

    a. Higher level of control over the BYOD solution
    b. √ Ease of deployment & operation of the BYOD solution
    c. Ability to meet regulatory requirements
    d. Security of the overall BYOD solution

**Which is not an advantage of a cloud-based MDM solution?**

    a. Scalability of the MDM solution
    b. √ Security of the overall MDM solution
    c. Flexibility in deploying the MDM solution
    d. Speed of deployment of MDM solution


### 4B - WLAN Security: attacks & countermeasures

**The core difference inbetween active & passive WLAN attacks depends on**:
 - action of manipulating data in transit
 - action happens on/off the target network

**Explain Wardriving/Warwalking/Warflying**:
 - Depending on transportation method (cars, bicycle, drones, RCs)
 - Anyone who is scanning for free WiFis

**List all differences inbetween AP & Routers**
 - Router could be wired only, AP could only be wireless
 - AP cannot perform routing and works in lower OSI layer
 - Business routers usually are wires only

**List all passive and active WLAN attacks**
 - Passive
   - Breaking WEP/WPA/WPA2 encryption
   - Sniffing
   - Replay
   - Footprinting / Topology mapping (ping scan to learn network topology)
 - Active
   - Injection
   - Jamming
   - Hijacking
   - MITM
   - DoS

**Is human element vulnerable in WLAN attacks, what can admins do to mitigate?**
 - Yes, untrained human element is vulnerable to phishing and fake-SSID-MITMs
 - Countermeasure: training, WIPS

**List human errors that could compormise a network**
 - Misconfiguration (e.g., Microsoft Azure admin accidentally switched dmz from private to public)
 - Bad habits: plugging their AP to corp network
 - Ad-hoc network (WANET): employee using hotspots, blue-tooth to pass files
 - Weak passwords: 12345678
 - Phishing emails
 - Connect random USB drives found in bathroom to corp PC
 - APs left unconfigured
 - Remote management enabled on routers and switches
 - Using omnidirectional antennas rather than directional
 - Lack of MAC-address filtering
 - VMs stored away for too long and lack of security updates

**List all possible WLAN attack and countermeasures:**

|     Attack   types                   |     Countermeasures                                                                             |
|--------------------------------------|-------------------------------------------------------------------------------------------------|
|     Eavesdropping   / Mapping        |     Directional   Antennas, SSID hiding                                                         |
|     Traffic   Analysis / Spoofing    |     Mandate   AES128 WiFi encryption                                                            |
|     Hijacking                        |     Mandate   AES128 WiFi encryption                                                            |
|     Replay                           |     Regular   firmware updates                                                                  |
|     MAC   Masquerade                 |     WPA2   Enterprise, ACL+DHCP shield                                                          |
|     DNS   Spoofing                   |     Mandate   AES128 WiFi encryption                                                            |
|     WLAN   DoS                       |     STP,   Ether Channel, limit bandwidth                                                       |
|     Password   dict. attack          |     Mandate   WPA2 Enterprise                                                                   |
|     Rogue   APs                      |     Implement   WIPS, shutdown unused ports, VLAN separation, ZPF, Policy & video   training    |
|     Social   Engineering             |     Policy   & video training                                                                   |

**List all possible WLAN countermeasures:**
 - Secure your Linux and Windows OSes (OS updates)
 - Prevent null sessions. (i.e. Block NetBIOS by preventing TCP 139, 445 from passing throughfirewall(s) and/or Disable File and Print Sharing for Microsoft Networks)
 - Install (& require) personal firewall software for every WLAN PC
 - Disable unnecessary services & protocols on APs
 - Apply latest firmware patches for AP, WLAN NICs, client mgmt. software, workstations, VMs
 - Regularly perform vulnerability assessments on your WLAN workstations
 - Enforce strong user passwords
 - Use antivirus software & antispyware software
 - SSID hiding (still can be figured out by attackers easily, however)

**Explain SSID hiding and its weakness:**
 - disable SSID broadcast, thus common attacks cannot find the WiFi name
 - attacker could monitor, for connected clients, at that time data packets from clients will reveal SSID

**Explain methodology to conquer SSID hiding:**
 - **kaliLinux - aircrack suite:**
    - airmon-ng start wlan0
    - airodump-ng wlan0mon (find channel number under BSSID order)
    - airodump-ng -c <channel#> wlan0mon (specify channel to listen)
    - (wait for any clients to show up and reveal the SSID)
    - aireplay-ng (de-authenticate client devices from WLAN)
 - **Gerix WiFi Cracker - monitor mode**
    - enable monitor mode
    - select the target network, or click rescan
    - go to WPA tab > General > Start Sniffing and Logging
    - then go to WPA Attack > AutoLoad victim clients (MAC cloning)
    - click Client Deauthentication to send deauth packets to clients
    - set deauth to 10
    - Gerix will be connected to target network

**Explain Wired Equivalent Privacy (WEP):**
 - uses a static key of 10 or 26 hex-digits to encrypt data
 - Includes a Cycle Redundancy Check (CRC), this is useful against replay attacks, but not strong
 - attackers are able to easily guess the static key to gain access
 - WEP only supports 64 or 128bit encryption key sizes, which is weak compared to 256bit key.
 - hexadecimal digits significatly limites the dictionary complexity
 - A WEP-protected network can be cracked under a minute

**Explain Wi-Fi Protected Access (WPA):**
 - WPA uses temporal key integral protocol (WPA-TKIP / Message Integrity Check) to dynamically alter the key
   - TKIP is better against replay attacks than CRC
 - Or, use Advanced Encryption Standard (WPA-AES, less widly supported)
   - AES is more secure & faster than TKIP
 - Still can be compormised by bruteforce cracking & pre-shared key cracking from Aircrack-suite & Gerix
 - now retired as WEP

**Explain Wi-Fi Protected Access 2 (WPA2):**
 - 2 types: WPA2 personal & WPA2 enterprise
 - Personal: DES-CCMP encryption
 - Enterprise: AES encryption, but still supports TKIP

**Explain 802.11i:** known as "Robust Security Network" (RSN), a standard that contributes to WPA, WPA2 and later technologies
