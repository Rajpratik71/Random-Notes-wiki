Shows status of all interfaces:
`show ip interface brief`

Shows status messages:
`terminal monitor`

runs command from anywhere: 
`: do <command>`

Stop annoying status messages:
```
#conf t
line con 0
logging synchronous
line vty 0 4 
logging synchronous
```

Set up logoff timeout:
```
line con 0
exec-timeout 30 0 (30 minutes)
```

Stop annoying domain lookup waits when mistyping a command: 
`(config)#no ip domain-lookup`

Configure Port Security:
```
(config)#interface fastethernet 0/1
(config-if)#switchport mode access
(config-if)#switchport port-security
(config-if)#switchport port-security max 1 (Set to only allow one mac address on port, no rogue hubs allowed)
(config-if)#switchport port-security violation restrict (What to do if violation. shutdown is default, restrict logs it, protect only allows first)
(config-if)#switchport port-security mac-address aaaa:aaaa:aaaa (only allows specified MAC) (sticky automatically codes the current MAC)
```
Configure Port Security to a Range of ports:
```
(config)#interface range fastEthernet 0/1 - 24  (Does all at once)
(config-if-range)#switchport....
```

Dispays status of port-security: `show port-security`

Create Aliases:
```
(config)#alias exec s show ip interface brief
(config)#alias exec s copy run start
```

Troubleshooting commands:
```
show ip interface brief
show interface
show running-config
```

Fix Duplex Mismatches:
```
(config-if)#duplex half (sets to half)
(config-if)#speed #
```

Setup SSH/HTTPS:
```
(config)#ip domain-name nuggetlab.com
(config)#crypto key generate rsa 1024
(config)#ip http server
(config)#ip http secure-server
(config)#username Admin previlege 15 secret cisco
(config)#ip http authentication local //auth locally
(config)#line vty 04
(config)#login local
(config)#transport input telnet ssh //both
```

Configure Static Routing:
```
(config)#ip route <network trying to reach> <mask> <next hop ip>
(config)#ip route 192.168.3.0 255.255.255.0 192.168.2.2
//Default Route
(config)#ip route 0.0.0.0 0.0.0.0 <isp default gateway>
//Configure DNS server for lookup
(config)#ip name-server 4.2.2.2
```

Configure RIP:
```
(config)#router RIP
(config-router)#version 2
//Add Network Statements for all interfaces
(config-router)#network 192.168.1.0
(config-router)#network 192.168.2.0
```

Display specific lines in Running Config (containing "ip route"):
`#show run | include ip route`

Turn off classful networks like 68.0.0.0:
`no auto-summary`

Show routing protocols that are enabled:
`#show ip protocols`

Show real time routing updates, etc...  
`#debug ip rip`

Turn off Debugging:
`#no debug ip rip`
or
`#"u all"`


Show NATs:
`#show ip nat translations`

Configure Leased Line:
```
Interface serial 0/0
encapsulation hdlc // or ppp, etc...
```

Configure Serial Crossover Cable:
```
#show controllers serial 0/0
(config)#int s0/1/0 //Set this for DCE side only
(config-if)#clock rate 2000000
```

