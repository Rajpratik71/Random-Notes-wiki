The following commands will manually compact a Windows Server 2003 DHCP database:
```
net stop dhcpserver
cd C:\Windows\System32\DHCP
jetpack dhcp.mdb tmp.mdb
net start dhcpserver
```
Note: The database should be manually compacted if the database size exceeds 30MB in size.
