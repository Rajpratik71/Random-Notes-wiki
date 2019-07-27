Example: The following code will create an outbound firewall rule for each EXE file in the specified folder...
<pre>
$filelist = Get-ChildItem "C:\Program Files (x86)\Folder\*.exe" -Recurse | % { $_.FullName }
foreach ($file in $filelist) {
    netsh advfirewall firewall add rule Name="$file" Direction=Out Program="$file" Action=Block Enable=yes Profile=Any LocalIP=Any RemoteIP=Any protocol=Any
}
</pre>