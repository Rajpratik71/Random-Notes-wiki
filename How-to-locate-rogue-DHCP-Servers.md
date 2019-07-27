To locate rogue DHCP servers, run the following command-line:

<pre>
dhcploc <DHCP IP Address of Local Machine> <ValidDHCPServerList (multiple IPs separated by spaces)>
</pre>

Example: 
<pre>
dhcploc 192.168.1.21 192.168.1.1 192.168.2.1 Any DHCP server activity that does not include 192.168.1.1 or 192.168.2.1 will be logged to the console.
</pre>
Applies to: Windows XP or Server 2003 computers 