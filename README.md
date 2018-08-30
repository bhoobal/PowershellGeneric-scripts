# PowershellGeneric-scripts
<#  
Multi line comment 
#>
Get- ad user 

Get-ADUser -Filter * -SearchBase "OU=Users,OU=ad-vspengg,DC=ad,DC=vspengg,DC=com" -Properties "LastLogonDate","Enabled","PasswordExpired" | Format-Table GivenName,Name,SamAccountName,LastLogondate
