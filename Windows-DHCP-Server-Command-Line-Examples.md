## Delete an IP Address Reservation:

<pre>
netsh dhcp server \\DHCPServerName scope 172.16.1.0 delete reservedip 172.16.1.100 001122334598
</pre>

## Add an IP Address Reservation:

<pre>
netsh dhcp server \\DHCPServerName scope 172.16.1.0 add reservedip 172.16.1.100 001122334598 "LaserJet 5si" "Executive Office Printer"
</pre>
