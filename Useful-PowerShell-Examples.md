Get the last 10 events in the Windows Application Event Log.
<pre>
 Get-EventLog -LogName Application -Newest 10
</pre>

Get all of the properties of a running process using Format-List.
<pre>
 Get-Process iexplore | Format-List *
</pre>

Get a list of processes formated in a table with specific properties. Valid properties can be determined with the "Get-Process iexplore | Format-List *" command.

<pre>
 Get-Process | Format-Table -Property name, starttime
</pre>

<pre>
 Get-Process | Format-Table -Property name, path, priorityclass
</pre>

Use built-in aliases to shorten commands
Full command: 
<pre>
Get-Process | Where-Object { $_.starttime} | Format-Table -Property name, path, priorityclass
</pre>

Abbreviated command: 
<pre>
gps | ? {$_.starttime}|ft name,starttime
</pre>
