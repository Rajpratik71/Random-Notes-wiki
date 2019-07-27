When you perform a repair on a local area connection on Windows XP/2003 the following individual tasks are performed:
<pre>
ipconfig /renew         # Renew DHCP Lease
arp -d *                # Delete ARP Cache
nbtstat -R              # Flush NetBIOS Name Cache
nbtstat -RR             # Refresh Name within WINS
ipconfig /flushdns      # Flush Local DNS Cache
ipconfig /registerdns   # Register Host in DNS
</pre>