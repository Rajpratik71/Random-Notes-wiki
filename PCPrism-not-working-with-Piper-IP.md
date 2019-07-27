06/30/1996

Problem: PCPrism isn't working with Piper/IP

Reason: PCPrism needs at least 520k conventional memory to run.

Solution: Free up required memory and make sure that following line is in AUTOEXEC.BAT.
<pre>
Set DBUSERID=<username>
</pre>
<username> = Your username. 