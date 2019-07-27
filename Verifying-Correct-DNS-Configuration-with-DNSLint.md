Download DNSLint from http://support.microsoft.com/?kbid=321045 http://support.microsoft.com/?kbid=321045

## Syntax
<pre>
 dnslint /d domain_name | /ad [LDAP_IP_address] | /ql input_file
 [/c [smtp,pop,imap]] [/no_open] [/r report_name]
 [/t] [/test_tcp] [/s DNS_IP_address] [/v] [/y]
</pre>

## Functions
Verify Domain Name System (DNS) records with the following.
<pre>
 dnslint /d: This diagnoses potential causes of "lame delegation" and other </pre>
related DNS problems.
<pre>
 dnslint /ql: This verifies a user-defined set of DNS records on multiple DNS </pre>
servers.
<pre>
 dnslint /ad: This verifies DNS records specifically used for Active Directory replication.
</pre>
