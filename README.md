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

**Explain Wardriving/Warwalking/Warflying**:
 - Depending on transportation method (cars, bicycle, drones, RCs)
 - Scanning for WiFi signals

**List all differences inbetween AP & Routers**
 - Router could be wired only, AP could only be wireless
 - AP cannot perform routing and works in lower OSI layer
 - Business routers usually are wires only

**List all passive and active WLAN attacks**
 - Passive
   - Breaking WEP/WPA/WPA2 encryption
   - sniffing
 - Active
   - Injection
   - Jamming
   - Hijacking
   - MITM

**Is human element vulnerable in WLAN attacks, what can admins do:**
 - Yes, untrained human element is vulnerable to phishing and fake-SSID-MITMs
 - Countermeasure: training, WIPS

**List all possible WLAN attack and  countermeasures:**

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
