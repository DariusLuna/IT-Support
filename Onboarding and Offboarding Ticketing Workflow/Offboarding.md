# Offboarding Ticket

This document outlines the offboarding process handled through a service ticket. The purpose is to demonstrate secure account deactivation and ticket escalation.

![Offboarding Overview](images/offboarding/IMG01.png)

#

### Ticket Acknowledgement

Based on the ticket description, the required tasks were:

- Disable the user account for **James Peterson**
- Escalate the ticket to the Management Department for further processing

The ticket was acknowledged with a comment to confirm ownership and maintain an audit trail of actions.

![Ticket Acknowledged](images/offboarding/IMG02.png)

#

### Ticket In Progress

To maintain visibility and accountability:

1. Assign the ticket to the appropriate support personnel
2. Update the ticket status to **In Progress**
3. Add a comment indicating work has started

> **Note:** These steps ensure proper tracking before performing account-related actions.

#

### Disable User Account (Active Directory)

Steps performed to disable the user account:

1. Launch **Active Directory Users and Computers** (`dsa.msc`)
2. Navigate to `MONSTERS.inc > Electrical Department`
3. Right-click **James Peterson** to view available account actions  
   ![Account Actions](images/offboarding/IMG03.png)
4. Select **Disable Account**
5. Confirm that the account status reflects as disabled  
   ![Account Disabled](images/offboarding/IMG04.png)

> **Note:** Disabling the account immediately prevents unauthorized access while preserving the user object for auditing, data recovery, or future reference. Account deletion is typically performed only after all assets and data have been reviewed.

#

### Ticket Escalation

After disabling the account:

1. Reassign the ticket to **Mary Bootwright** (Management Department)
2. Add a comment indicating ticket escalation and completed actions

![Ticket Escalation](images/offboarding/IMG05.png)

> **Note:** Escalation ensures management can proceed with remaining offboarding steps such as asset recovery, access reviews, and compliance checks.
