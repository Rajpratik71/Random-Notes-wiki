## Display WINS Server Information
 for /f "tokens=2 delims=," %i in (WINSServers.txt) do netsh wins server \\%i show info
## Dump WINS Serer Information
 netsh wins server \\<WINS_Server> dump
 or
 for /f "tokens=2 delims=," %i in (WINSServers.txt) do netsh wins server \\%i dump
## Display WINS Statistics
 for /f "tokens=1,2 delims=," %i in (WINSServers.txt) do netsh wins server \\%i show statistics
## Display WINS Record Counts per Server
 for /f "tokens=1,2 delims=," %i in (WINSServers.txt) do netsh wins server \\%i show reccount %i
## Display WINS Static Records per Server
 netsh wins server \\<Local WINS Server> show database servers={} rectype=1

Applies to: Windows 2003
