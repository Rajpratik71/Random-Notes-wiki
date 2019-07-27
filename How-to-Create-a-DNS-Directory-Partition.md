Use dnscmd to create an application partition:
<pre>
dnscmd <ServerName> /CreateDirectoryPartition <FQDN>
</pre>
After the partition is created, enlist servers with dnscmd:
<pre>
dnscmd <ServerName> /EnlistDirectoryPartition <FQDN>
</pre>
After the directory partition has been created, change the zone replication properties in the general tab of the zone properties dialog from the DNS management console for the given zone. Simply change the replication configuration by clicking Change next to replication.

Applies to: Windows Server 2012 