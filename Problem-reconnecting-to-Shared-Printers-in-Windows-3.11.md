Problem: Windows will not reconnect to shared printers on teh network.

Solution: Edit SYSTEM.INI and make sure that the following are set:
<pre>
[Network Drivers]
reconnect=yes
LogonDisconnected=no
</pre>