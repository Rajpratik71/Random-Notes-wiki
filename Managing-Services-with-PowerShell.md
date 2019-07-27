Stopping a service locally:
<pre>
Stop-Service -Name W32Time
</pre>
Starting a service locally:

<pre>
Start-Service -Name W32Time
</pre>

Disabling a service remotely:

<pre>
Set-Service -Name W32Time -ComputerName Server1 -StartupType Disabled
</pre>
