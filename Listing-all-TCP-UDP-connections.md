To List the all TCP and UDP port connections on a host, run the following command:
<pre>
netstat -ano
</pre>

  Sample output:
<pre>
  Active Connections //Sample Output
  Proto  Local Address          Foreign Address        State           PID
  TCP    0.0.0.0:135            0.0.0.0:0              LISTENING       544
  TCP    0.0.0.0:445            0.0.0.0:0              LISTENING       4
</pre>

To list the specific program that is using a port, run the following command-line.

<pre>
tasklist /fi "pid eq <process ID(PID)>"
</pre>

Example: 
<pre>
tasklist /fi "pid eq 4"
</pre>

<pre>
  Sample output:
  Image Name                     PID Session Name        Session#    Mem Usage //Sample Output
  ========================= ======== ================ =========== ============
  System                           4 Services                   0      1,612 K
</pre>

Applies to: Windows XP/2003/7
