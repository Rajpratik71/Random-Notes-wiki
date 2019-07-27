## Display DHCP Server Information
 netsh dhcp server \\DHCP_Server show all
## Display Authorized DHCP Servers
 netsh dhcp show server
 or
 Dsquery * "cn=NetServices,cn=Services,cn=Configuration, DC=forestRootDomain" -attr dhcpServers
## Perform DHCP Server Dump
 netsh dhcp server \\<DHCP Server> dump
## Show Active DHCP leases
 for /f %i in (DHCPServers.txt) do for /f "delims=- " %j in (‘"netshdhcp server \\%i show scope | find /i "active""’) do netsh dhcp server\\%i scope %j show clientsv5
## Display Total DHCP Scopes
 find /i "subnet" "Output from DHCP server information" | find /i "subnet" 
## Show DHCP Server Active Scope Information
 for /f %i in (DHCPServers.txt) do netsh dhcp server \\%i show scope | find /i "active"
## Resolve DHCP Client Hostnames
 for /f "tokens=1,2,3 delims=," %i in (Output from ‘Find Subnets from DHCP clients’) do @for /f "tokens=2 delims=: " %m in (‘"nslookup %j |find /i "Name:""’) do echo %m,%j,%k,%i
== Find Two Online PCs Per Subnet
 echo. > TwoClientsPerSubnet.txt & for /f "tokens=1,2,3,4delims=, " %i in (‘"find /i "pc" ‘Output from Resolve DHCP clientshostnames’"’) do for /f "tokens=3 skip=1 delims=: " %m in (‘"Find /i /c"%l" TwoClientsPerSubnet.txt"’) do If %m LEQ 1 for /f %p in (‘"ping -n1 %i | find /i /c "(0% loss""’) do If %p==1 Echo %i,%j,%k,%l

Applies to: Windows 2003
