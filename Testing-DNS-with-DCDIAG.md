Perform DNS test on all DNS functions on a specific DNS server.
<pre>
 dcdiag /test:DNS
</pre>
Perform basic DNS test on a specific DNS server. (Much faster)
<pre>
 dcdiag /test:dns /dnsbasic
</pre>
Tests for network connectivity on all adapters, confirms A record for each DC is registered in TCP/IP propterties, confirms AD zone and SOA record for zone, tests whether root zone is present.

Perform DNS test on all DNS servers (DCs) in the AD forest
<pre>
 dcdiag /test:DNS/e
</pre>
