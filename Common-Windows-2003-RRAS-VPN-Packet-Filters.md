# PPTP Packet Filters
## Inbound Filters:
1. Destination: <VPN Interface IP Address>, Protocol: TCP source and destination Port 1723 (PPTP)
2. Destination: <VPN Interface IP Address>, Protocol: Other Port 47 (GRE - Generic Routing Encapsulation protocol)
3. Destination: <VPN Interface IP Address>, Protocol: TCP (established) source Port 1723 (Optional if server also acts as a PPTP client)
## Outbound Filters:
1. Source: <VPN Interface IP Address>, Protocol: TCP source and destination Port 1723 (PPTP)
2. Source: <VPN Interface IP Address>, Protocol: Other Port 47 (GRE - Generic Routing Encapsulation protocol)
3. Source: <VPN Interface IP Address>, Protocol: TCP (established) source Port 1723 (Optional if server also acts as a PPTP client)

# L2TP Packet Filters
## Inbound Filters:
1. Destination: <VPN Interface IP Address>, Protocol: UDP Port 500 (source and destination)
2. Destination: <VPN Interface IP Address>, Protocol: UDP Port 1705 (source and destination)
## Outbound Filters:
1. Source: <VPN Interface IP Address>, Protocol: UDP Port 500 (source and destination)
2. Source: <VPN Interface IP Address>, Protocol: UDP Port 1705 (source and destination) 
