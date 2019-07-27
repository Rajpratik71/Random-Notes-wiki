1. Run "ipconfig /all". Check for a valid IP address and correct DNS servers

2. Ping the server/hostname in question. (e.g., "ping server1.domain.com")

3. Ping the IP address of the server/hostname.

4. Run "nslookup" on the server/hostname in question. (e.g., "nslookup server1.domain.com")

5. If no record is returned, run "ipconfig /registerdns" on the server/hostname in question.

6. Run "netdiag /fix" to check network connectivity.

7. Check the DNS event log on the DNS server. 