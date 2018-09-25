# PowershellGeneric-scripts
<#  
Multi line comment 
#>
Get- ad user 

Get-ADUser -Filter * -SearchBase "OU=Users,OU=ad-vspengg,DC=ad,DC=vspengg,DC=com" -Properties "LastLogonDate","Enabled","PasswordExpired" | Format-Table GivenName,Name,SamAccountName,LastLogondate

recursice copy

$folders = Get-ChildItem C:\Banana
foreach ($folder in $folders.name){
#For each folder in C:\banana, copy folder c:\copyme and it's content to c:\banana\$folder
Copy-Item -Path "C:\copyme" -Destination "C:\banana\$folder" -Recurse
}

Found on Spiceworks: https://community.spiceworks.com/topic/1664820-script-to-copy-a-file-into-multiple-folders?utm_source=copy_paste&utm_campaign=growth

$folders= Get-ChildItem .\
foreach ($folder in $folders.name){copy-item -path "C:\temp\s3filecopy\PrivacyStatement.pdf" -Destination .\$folder -recurse}

recursive delete

Get-ChildItem -Path .\ -Include *.pdf -File -Recurse | foreach { $_.Delete()}

Remove-Item -Path "C:\Users\bpalani\Downloads\Legal documents-20180924T070807Z-001\Legal documents\unzipped\*.*" -force -recurse
