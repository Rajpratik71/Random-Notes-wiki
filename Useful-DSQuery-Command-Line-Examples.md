== Users ==

Get Users with No Logon Script:

 dsquery * domainroot -filter"(&(objectCategory=Person)(objectClass=User)(!scriptPath=*))"-limit 0 -attr sAMAccountName sn givenName pwdLastSet distinguishedName

Get User Accounts with No Password Required 

 dsquery * domainroot -filter "(&(objectCategory=Person)(objectClass=User)(userAccountControl:1.2.840.113556.1.4.803:=32))"

Get User Accounts with No Password Expiration 

 dsquery * domainroot -filter"(&(objectCategory=Person)(objectClass=User)(userAccountControl:1.2.840.113556.1.4.803:=65536))"

Get User Accounts That Are Disabled 

 dsquery * domainroot -filter "(&(objectCategory=Person)(objectClass=User)(userAccountControl:1.2.840.113556.1.4.803:=2))"

Find Out if a User Account is Currently Enabled or Disabled

 dsquery user DC=%userdnsdomain:.=,DC=% -name %username% | dsget user -disabled -dn

Get AD User OU Memberships

 dsquery user -limit 0

== Computers ==

Get AD Computer OU Memberships

 dsquery computer -limit 0

Enumerate All Servers in the Domain 

 dsquery * domainroot -filter "(&(objectCategory=Computer)(objectClass=Computer)(operatingSystem=*Server*))" -limit 0

== Groups ==

Find Empty Groups 

 dsquery * -filter "&(objectCategory=group)(!member=*)" -limit 0-attr whenCreated whenChanged groupType sAMAccountNamedistinguishedName memberOf

== OUs ==

List Organizational Units 

 dsquery OU

== Sites ==

Get AD Site Information 

 dsquery * "CN=Sites,CN=Configuration,DC=forestRootDomain" -attr cn description location -filter (objectClass=site) 

Get Site Subnet Information 

 dsquery subnet ?limit 0

Get AD Subnet and Site Information 

 dsquery * "CN=Subnets,CN=Sites,CN=Configuration,DC=forestRootDomain" -attr cn siteObject description location

Get Site Links and Costs

 dsquery * "CN=Sites,CN=Configuration,DC=forestRootDomain" -attr cn costdescription replInterval siteList -filter (objectClass=siteLink)

Get ISTG from AD attributes 

 dsquery * "CN=NTDS Site Settings,CN=siteName,CN=Sites,CN=Configuration,DC=forestRootDomain" -attr interSiteTopologyGenerator 

Find All Connection Objects 

 dsquery * forestRoot -filter (objectCategory=nTDSConnection) ?attr distinguishedName fromServer whenCreated displayName

Query the Current Site and Related Group Policy Information for Each Windows XP Workstation
 @dsquery * domainroot -filter"(&(objectCategory=Computer)(operatingSystem=Windows XPProfessional))" -limit 0 -attr cn > Workstations.txt & @For /f%i in (Workstations.txt) do @ping %i -n 1 >NUL & @if ErrorLevel0 If NOT ErrorLevel 1 @Echo %i & for /f "tokens=3" %k in (‘"regquery "\\%i\hklm\software\microsoft\windows\currentversion\grouppolicy\history" /v DCName | Find /i "DCName""’) do @for /f %m in(‘"nltest /server:%i /dsgetsite | find /i /v "completedsuccessfully""’) do @echo %i,%k,%m

== GPOs ==

Get Information on Existing GPOs 

 dsquery * "CN=Policies,CN=System,domainRoot" -filter"(objectCategory=groupPolicyContainer)" -attr displayName cnwhenCreated gPCFileSysPath

Get Policy Display Name for GUID 

 dsquery * "CN=Policies,CN=System,DC=domainRoot" -filter (objectCategory=groupPolicyContainer) -attr Name displayName

== Miscellaneous ==

Open A DSQuery Window

 rundll32 dsquery,OpenQueryWindow

Show AD Database Disk Usage 

 for /f %i in (‘dsquery server -domain %userdnsdomain% -o rdn’) do dir \\%i\admin$\ntds

Get Global Catalog Servers from AD:

 dsquery * "CN=Configuration,DC=forestRootDomain" -filter "(&(objectCategory=nTDSDSA)(options:1.2.840.113556.1.4.803:=1))"

Get Garbage Collection and Tombstone Information

 dsquery * "cn=Directory Service,cn=WindowsNT,cn=Services,cn=Configuration,DC=forestRootDomain" -attrgarbageCollPeriod tombstoneLifetime

Get Domain Controllers Per Site 

 dsquery * "CN=Sites,CN=Configuration,DC=forestRootDomain" -filter (objectCategory=Server)

List Service Principal Names (SPN)

 for /f %i in (‘dsquery server -domain %userdnsdomain% -o rdn’) do setspn -L %i

Get Printer Queue Objects in AD

 dsquery * domainroot -filter "(objectCategory=printQueue)" -limit 0

Get the object if KCC Intra/Inter site is disabled for each site 

 dsquery site | dsquery * -attr * -filter "(|(Options:1.2.840.113556.1.4.803:=1)(Options:1.2.840.113556.1.4.803:=16))"

Get Forest/Domain Functional Levels 

 dsquery * cn=partitions,cn=configuration,dc=%domain% -filter"(|(systemFlags=3)(systemFlags=-2147483648))" -attrmsDS-Behavior-Version Name dnsroot ntmixeddomain NetBIOSName

Find Out when AD was Installed

 dsquery * cn=configuration,DC=forestRootDomain -attr whencreated -scope base

Enumerate Trusts from the Specified Domain 

 dsquery * "CN=System,DC=domainRoot" -filter "(objectClass=trustedDomain)" -attr trustPartner flatName

Show NtFrs Replica Sets 

 for /f %i in (‘dsquery server -domain %userdnsdomain% -o rdn’) do ntfrsutl sets %i

Show NtFrs DS View 

 for /f %i in (‘dsquery server -domain %userdnsdomain% -o rdn’) do ntfrsutl ds %i

Show ACL on all OUs 

 for /f "delims=|" %i in (‘dsquery OU’) do acldiag %i

Show Domain Controller Netlogon Entries

 for /f %i in (‘dsquery server /o rdn’) do echo %i & reg query\\%i\hklm\system\currentcontrolset\services\netlogon\parameters

Find a DC for Each Trusted Domain 

 for /f "skip=1" %i in (‘"dsquery * CN=System,DC=domainRoot -filter(objectClass=trustedDomain) -attr trustPartner"’) do nltest /dsgetdc:%i

Check the Notification Packages Installed on All DCs 
 for /f %i in (‘dsquery server /o rdn’) do @for /f "tokens=4" %m in(‘"reg query\\%i\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa /v"Notification Packages" | find /i "Notification""’) do @echo %i,%m

Applies to: Windows 2003+