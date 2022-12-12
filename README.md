# CCNA-Security-210-260-Module-2-Review
### 3 - Implementing AAA in Cisco IOS


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
