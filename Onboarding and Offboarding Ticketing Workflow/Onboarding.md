# Onboarding Ticket

This document outlines the end-to-end onboarding process handled through a service ticket, from acknowledgment to closure. The purpose is to demonstrate ticket lifecycle management, Active Directory administration, workstation setup, and secure software deployment.

![Onboarding Overview](images/onboarding/IMG01.png)

#

### Ticket Acknowledgement

Based on the ticket description, the required tasks were:

- Create a user account for **Michael Swarovski** (Electrical Department)
- Add the user to the appropriate security group for shared folder access
- Configure and domain-join the workstation
- Install required software (**KiCad**)
- Close the ticket with proper documentation

The ticket was acknowledged with a comment to confirm ownership and ensure traceability of actions.

![Ticket Acknowledged](images/onboarding/IMG02.png)

#

### Ticket In Progress

To maintain visibility and accountability:

1. Assign the ticket to the appropriate support personnel
2. Update the ticket status to **In Progress**
3. Add a comment indicating work has started

![Ticket In Progress](images/onboarding/IMG03.png)

> **Note:** These steps ensure clear communication, especially in multi-technician environments.

#

### User Account Creation (Active Directory)

Steps performed to create the user account:

1. Launch **Active Directory Users and Computers** (`dsa.msc`)
2. Navigate to `MONSTERS.inc > Electrical Department`
3. Create a new user account with the username `mike`
4. Set an initial password (password change at next logon disabled for demo purposes)

![User Account Creation](images/onboarding/IMG04.png)

> The account is automatically placed in the correct Organizational Unit (OU).

#

### Group Membership & Shared Folder Access

To grant access to departmental resources:

1. Open the **Electrical Projects** security group
2. Add user `mike` as a member

![Group Membership](images/onboarding/IMG05.png)

> The security group already has permissions to the Electrical Department’s shared folder, allowing access without assigning permissions directly to the user.

#

### Workstation Configuration & Domain Join

The workstation was configured remotely using TeamViewer. Steps performed:

1. Establish remote connection to the workstation  
   ![Remote Connection](images/onboarding/IMG06.png)
2. Rename the PC from `DESKTOP-XXXXXX` to `WS21`  
   ![Rename PC](images/onboarding/IMG07.png)
3. Connect the workstation to the NAT network hosting the Domain Controller
4. Configure IPv4 settings:
   - Network: `10.0.2.0/24`
   - Default Gateway: `10.0.2.1`
   - Preferred DNS: `10.0.2.3` (Domain Controller)
5. Join the device to the domain `MONSTERS.inc`  
   ![Domain Join](images/onboarding/IMG08.png)
6. Restart the workstation, log in to the user account, and finalize the setup  
   ![Final Setup](images/onboarding/IMG09.png)

> **Note:** Domain join issues are commonly caused by incorrect DNS settings or the workstation not being connected to the correct virtual network.

#

### Shared Folder Mapping

To improve usability for the end user:

1. Reconnect remotely to `WS21`
2. Open **File Explorer → Map Network Drive**  
   ![Map Network Drive](images/onboarding/IMG10.png)
3. Map the **Electrical Projects** shared folder  
   ![Mapped Folder](images/onboarding/IMG11.png)  
   ![Folder Access](images/onboarding/IMG12.png)

> **Note:** Mapping the drive allows instant access without manually entering the network path.

#

### Software Installation (Secure Practice)

Required software: **KiCad**

Steps:

1. Download the installer from the official source
2. Verify the file’s **Digital Signature** against the publisher information  
   ![Digital Signature Verification](images/onboarding/IMG13.png)
3. Proceed with installation after validation

> **Best Practice:** Verifying installer integrity prevents malware and unauthorized software from entering the environment.

#

### Ticket Closure

Steps to properly close the ticket:

1. Update ticket status to **Done**
2. Add a final comment summarizing completed actions
3. Close the ticket  
   ![Ticket Closure](images/onboarding/IMG14.png)

> **Note:** Some tickets may require escalation instead of closure, depending on scope or access limitations.
