## View the current SQL Server Name/Instance

Open a new query window and run the following query:
<pre>
SELECT @@SERVERNAME
</pre>
or the following to view the current Machine Name/Insance Name:
<pre>
SELECT SERVERPROPERTY('MachineName'), SERVERPROPERTY ('InstanceName')
</pre>
## Rename the SQL Server
<pre>
 sp_dropserver 'DHITSEECUTLIP01'
 GO
 sp_addserver 'DHITSEECUTLIT01', local
 GO
</pre>
Applies to: Microsoft SQL Server
