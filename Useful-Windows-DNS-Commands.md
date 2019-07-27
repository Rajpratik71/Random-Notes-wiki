## Display DNS Information
 for /f %i in (‘dsquery server -domain %userdnsdomain% -o rdn’) do dnscmd %i /info
## Display Detailed DNS Zone Information
 dnscmd /zoneinfo %userdnsdomain%
## List DNS Zones
 dnscmd DNSServer /zoneprint DNSZone
## List DNS Zones in AD
 for /f %i in (‘dsquery server -o rdn’) do Dsquery * -s %i domainroot -filter (objectCategory=dnsZone)
## Enumerate DNS Server Zones
 for /f %i in (‘dsquery server -o rdn’) do dnscmd %i /enumzones
## Lookup SRV records from DNS
 nslookup -type=srv _ldap._tcp.dc._msdcs.{domainRoot}

Applies to: Windows 2003
