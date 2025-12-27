# Onboarding Ticket
This section documents the end-to-end onboarding process handled through a service ticket, from acknowledgment to closure. The goal is to demonstrate ticket lifecycle management, Active Directory administration, workstation setup, and secure software deployment.

![IMG01](images/onboarding/IMG01.png)

#

### Ticket Acknowledgement
Based on the ticket description, the required tasks were:
* Create a user account for Michael Swarovski (Electrical Department
* Add the user to the appropriate security group for shared folder access
* Configure and domain-join the workstation
* Install required software (KiCad)
* Close the ticket with proper documentation

The ticket was acknowledged with a comment to confirm ownership and ensure traceability of actions.
![IMG02](images/onboarding/IMG02.png)

#

### Ticket In Progress
To maintain visibility and accountability:
1. Assign the ticket to the appropriate support personnel
1. Update the ticket status to In Progress
1. Add a comment indicating work has started

![IMG03](images/onboarding/IMG03.png)
These steps ensure clear communication, especially in multi-technician environments.

#

### User Account Creation (Active Directory)
1. Launch Active Directory Users and Computers (dsa.msc)
1. Navigate to MONSTERS.inc > Electrical Department
1. Create a new user account with the username mike
1. Set an initial password (password change at next logon disabled for demo purposes)
![IMG04](images/onboarding/IMG04.png)

This automatically places the user in the correct Organizational Unit (OU).

#

### Group Membership & Shared Folder Access
To grant access to departmental resources:
1. Open the Electrical Projects security group
1. Add user mike as a member

![IMG05](images/onboarding/IMG05.png)

This group already has permissions to the Electrical Department’s shared folder, allowing access without assigning permissions directly to the user.

#

### Workstation Configuration & Domain Join
The workstation was configured remotely using TeamViewer.
Steps performed:
1. Remote connection established to the workstation
	![IMG06](images/onboarding/IMG06.png)
1. Renamed the PC from DESKTOP-XXXXXX to WS21
	![IMG07](images/onboarding/IMG07.png)
1. Connected the workstation to the NAT network hosting the Domain Controller
1. Configured IPv4 settings:
	* Network: 10.0.2.0/24
	* Default Gateway: 10.0.2.1
	* Preferred DNS: 10.0.2.3 (Domain Controller)
1. Joined the device to the domain MONSTERS.inc
![IMG08](images/onboarding/IMG08.png)
1. Restarted the workstation to apply changes
	Log in to the user account and finish the setup
![IMG09](images/onboarding/IMG09.png)
	Note: Domain join issues are commonly caused by incorrect DNS settings or the workstation not being connected to the correct virtual network.

#

### Shared Folder Mapping
To improve usability for the end user:
1. Reconnect remotely to WS21
1. Open File Explorer → Map Network Drive <br>
![IMG10](images/onboarding/IMG10.png)
1. Map the Electrical Projects shared folder
![IMG11](images/onboarding/IMG11.png)
	User successfully accessing the Electrical Projects shared folder
![IMG12](images/onboarding/IMG12.png)
Note: Mapping the drive allows instant access without manually entering the network path.

#

### Software Installation (Secure Practice)
Required software: KiCad
Steps:
1. Download the installer from the official source
1. Verify the file’s Digital Signature against the publisher information
![IMG13](images/onboarding/IMG13.png)
1. Proceed with installation after validation
Verifying installer integrity is a security best practice to prevent malware and unauthorized software from entering the environment.

#

### Ticket Closure
1. Update ticket status to Done
1. Add a final comment summarizing completed actions
1. Close the ticket
![IMG14](images/onboarding/IMG14.png)
	Some tickets may require escalation instead of closure, depending on scope or access limitations.



#

# Offboarding Ticket
This section documents the offboarding process handled through a service ticket. The goal is to demonstrate secure account deactivation, ticket escalation
![IMG01](images/offboarding/IMG01.png)

#

### Ticket Acknowledgement
Based on the ticket description, the required tasks were:
* Disable the user account for James Peterson
* Escalate the ticket to the Management Department for further processing
The ticket was acknowledged with a comment to confirm ownership and maintain an audit trail of actions.
![IMG02](images/offboarding/IMG02.png)

#

### Ticket In Progress
To maintain visibility and accountability:
1. Assign the ticket to the appropriate support personnel
1. Update the ticket status to In Progress
1. Add a comment indicating work has started
These steps ensure proper tracking before performing account-related actions.

#

### Disable User Account (Active Directory)
1. Launch Active Directory Users and Computers (dsa.msc)
1. Navigate to MONSTERS.inc > Electrical Department
1. Right-click James Peterson to view available account actions
![IMG03](images/offboarding/IMG03.png)
1. Select Disable Account
1. Confirm that the account status reflects as disabled
![IMG04](images/offboarding/IMG04.png)
Disabling the account immediately prevents unauthorized access while preserving the user object for auditing, data recovery, or future reference. Account deletion is typically performed only after all assets and data have been reviewed.

#

### Ticket Escalation
After disabling the account:
1. Reassign the ticket to Mary Bootwright (Management Department)
1. Add a comment indicating ticket escalation and completed actions
![IMG05](images/offboarding/IMG05.png)
Escalation ensures management can proceed with remaining offboarding steps such as asset recovery, access reviews, and compliance checks.

