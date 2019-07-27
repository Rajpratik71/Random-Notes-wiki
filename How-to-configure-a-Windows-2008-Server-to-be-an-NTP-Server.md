From a command prompt, type the following commands:
<pre>
W32tm /config /syncfromflags:manual /manualpeerlist:192.5.41.40 
W32tm /config /reliable:yes 
W32tm /config /update 
W32tm /resync 

Verify the following registry keys 
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W32Time\Config] - AnnounceFlags"=dword:00000005 
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W32Time\Parameters] - "Type"="NTP" 
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W32Time\TimeProviders\NtpServer] - "Enabled"=dword:00000001

Net stop w32time 
Net start w32time
</pre>