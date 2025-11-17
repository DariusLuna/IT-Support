# Windows 11 Local User & File Access Management

### 📌 Overview

This project demonstrates how to manage **local users, groups, directories, files, and permissions** in Windows 11 using PowerShell.
It provides a practical example of system administration tasks and showcases familiarity with **PowerShell automation, ACL permissions, and Windows local account management**.

#

### ⚙️ Technologies
- Windows 11 Enterprise Evaluation
- PowerShell
- Oracle VirtualBox
- Local Users and Groups Management (_lusrmgr.msc_)

#

### 👤 Local User Management

#### Creating Users
```powershell
New-LocalUser -Name Edith -AccountNeverExpires -Description "Accounting Manager" -PasswordNeverExpires
New-LocalUser -Name Phil -AccountNeverExpires -Description "HR Head" -PasswordNeverExpires
New-LocalUser -Name Luke -AccountNeverExpires -Description "Marketing Head" -PasswordNeverExpires
New-LocalUser -Name Jonathan -AccountExpires (Get-Date "12/10/2025") -Description "Intern" -PasswordNeverExpires UserMayNotChangePassword
```

#### Creating Groups
```powershell
New-LocalGroup -Name Accountancy
New-LocalGroup -Name "Human Resources"
New-LocalGroup -Name Marketing
```

#### Adding Members to Groups
```powershell
Add-LocalGroupMember -Group Accountancy -Member Edith
Add-LocalGroupMember -Group Accountancy -Member Jonathan
Add-LocalGroupMember -Group "Human Resources" -Member Phil
Add-LocalGroupMember -Group Marketing -Member Luke
```

#

### 📂 File Access Management

#### Creating Folders:
```powershell
New-Item -Path "C:\Users\Public\Documents\Financial Reports" -ItemType Directory
New-Item -Path "C:\Users\Public\Documents\Market Research" -ItemType Directory
```

#### Creating Files:
```powershell
New-Item -Path "C:\Users\Public\Documents\Financial Reports\Report 1.docx" -ItemType File
New-Item -Path "C:\Users\Public\Documents\Market Research\Research 1.docx" -ItemType File
```

#### Modifying Permissions:

Example: Granting _Accountancy_ full control over Financial Reports, while restricting Marketing.
```powershell
$path1 = "C:\Users\Public\Documents\Financial Reports"
$acl1 = Get-Acl $path1
$group1 = "DESKTOP-8OETC2A\Accountancy"
$rule1 = New-Object System.Security.AccessControl.FileSystemAccessRule($group1,"FullControl","ContainerInherit,ObjectInherit","None","Allow")
$acl1.AddAccessRule($rule1)
Set-Acl $path1 $acl1
```

#

### 📝 Notes
- Always Run PowerShell as Administrator when creating users or groups.
- Use quotation marks for group names with spaces (e.g., "Human Resources").
- ACLs allow fine-grained control over file access, useful for enterprise-level security.

#

### 🚀 Future Improvements
- Extend scripts for Active Directory environments
- Add logging for permission changes

#

### 📥 Downloads
*  [Windows 11 Enterprise Evaluation](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise)
*  [Oracle VirtualBox](https://www.virtualbox.org/)
