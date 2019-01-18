### Quick Ping Scan
`nmap -sP 192.168.1.0/24`

### Scan subnet for all hosts listening on the 100 most common ports and save to a file called results.
`nmap -F 192.168.1.0/24 -oA results`

