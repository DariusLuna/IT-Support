#LOCAL USERS AND GROUPS
#creating users
1.  new-localuser -name Edith -accountneverexpires -description "Accounting Manager" -passwordneverexpires
2.  new-localuser -name Phil -accountneverexpires -description "HR Head" -passwordneverexpires
3.  new-localuser -name Luke -accountneverexpires -description "Marketing Head" -passwordneverexpires
4.  new-localuser -name Jonathan -accountexpires (get-date "12/10/2025") -description "Intern" -passwordneverexpires -usermaynotchangepassword

#creating groups
1.  new-localgroup -name Accountancy
2.  new-localgroup -name "Human Resources"
3.  new-localgroup -name Marketing

#adding group members
1.  add-localgroupmember -group Accountancy -member Edith
2.  add-localgroupmember -group Accountancy -member Jonathan
3.  add-localgroupmember -group "Human Resources" -member Phil
4.  add-localgroupmember -group Marketing -member Luke

#Notes
1.  Make sure to "Run as administrator" on PowerShell specially when creating users or groups.
2.  Creating value separated by space needs to be inside quotation marks; ex; "Human Resources"



#FILE ACCESS
#creating folders
1.  new-item -path "C:\Users\Public\Documents\Financial Reports" -itemtype directory
2.  new-item -path "C:\Users\Public\Documents\Market Research" -itemtype directory

#creating files
1.  new-item -path "C:\Users\Public\Documents\Financial Reports\Report 1.docx" -itemtype file
2.  new-item -path "C:\Users\Public\Documents\Market Research\Research 1.docx" -itemtype file

#modify permissions
1.  $path1 = "C:\Users\Public\Documents\Financial Reports"
2.  $path2 = "C:\Users\Public\Documents\Market Research"
3.  $acl1 = Get-acl $path1
4.  $acl2 = Get-acl $path2
5.  $group1 = "DESKTOP-8OETC2A\Accountancy"
6.  $group2 = "DESKTOP-8OETC2A\Human Resources"
7.  $group3 = "DESKTOP-8OETC2A\Marketing"
8.  $rule1 = New-Object System.Security.AccessControl.FileSystemAccessRule($group1,"FullControl","ContainerInherit,ObjectInherit","none","Allow",)
9.  $acl1.AddAccessRule($rule1)
10. $rule2 = New-Object System.Security.AccessControl.FileSystemAccessRule($group2,"ReadAndExecute","ContainerInherit,ObjectInherit","none","Allow",)
11. $acl1.AddAccessRule($rule2)
12. $rule3 = New-Object System.Security.AccessControl.FileSystemAccessRule($group3,"FullControl","ContainerInherit,ObjectInherit","none","Deny",)
13. $acl1.AddAccessRule($rule3)
14. Set-acl $path1 $acl1
15. $rule4 = New-Object System.Security.AccessControl.FileSystemAccessRule($group3,"FullControl","ContainerInherit,ObjectInherit","none","Allow",)
16. $acl2.AddAccessRule($rule4)
17. $rule2 = New-Object System.Security.AccessControl.FileSystemAccessRule($group2,"ReadAndExecute","ContainerInherit,ObjectInherit","none","Allow",)
18. $acl2.AddAccessRule($rule2)
19. $rule5 = New-Object System.Security.AccessControl.FileSystemAccessRule($group1,"FullControl","ContainerInherit,ObjectInherit","none","Deny",)
20. $acl2.AddAccessRule($rule5)
21. Set-acl $path2 $acl2