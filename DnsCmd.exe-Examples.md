Export AD Integrated Zones:

 dnscmd <server> /zoneexport <zone_name> "dns-export\<zone_filename>

Delete AD Integrated Zones:

 dnscmd <server> /ZoneDelete <zone_name> /DsDel /f

Import Primary Zone:

 dnscmd <server> /zoneadd <zone_name> /primary /file <zone_filename> /load

Import Secondary Zone:

 dnscmd <server> /zoneadd <zone_name> /secondary <primary_dns_server_ip_address>
