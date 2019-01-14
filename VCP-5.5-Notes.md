Thursday, April 09, 2015 5:46 PM
 
* [VMware HCL](www.vmware.com/go/hcl)

1. vCenter physical or virtual
	- Physical requires a dedicated machine
	- Physical is not at risk of vSphere outages
	- Virtual can be backed with other VMs
	- Virtual does not waste an entire server on vCenter
	- Virtual can participate in HA and be vMotioned
	- Virtual is a risk of vSphere Outages
		- But can use affinity on only a few hosts in a cluster to narrow down how many hosts you need to go through to search for it.
		- Can also use heartbeat to replicate to a secondary vCenter
2. Pros and Cons to Using vCenter as an Appliance
	- Pros
		- Supports all traditional vCenter features like DRS, SDRS, HA, host profiles, dvSwitch, etc.
		- No windows license is required
		- No Windows install has to be done
		- No vCenter install has to be done
		- Deployment is simple & FAST
	- Cons
		- Doesn't support SQL as an external database
		- vCenter Server linked mode doesn't work
		- vCenter Server heartbeat doesn't work
		- No single-sign on using Windows session credentials
		- vSphere Storage Appliance (VSA) isn't compatible
3. Cool Features
	- Menu Hot Keys (Ctrl+Shift+H = Hosts and clusters)
	- Filtering Box for inventory
	- File + Export + Export List
	- Reports (Host Summary or Performance)
4. Miscellaneous
 - Download Veeam Fastscp
 - http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=1010398
 - "Ask VMware" link for warnings and errors in Tasks and Events tab takes you directly to a KB article on the event.
 - Can filter events with filter text box. Use "error" for all errors, etc… (If you don't see the filter box, go to View + Filtering to enable it)
 - Acknowledge Alarms to let others know you are on it.
 - Clear alarm when finished dealing with it so others know it has been completed.
5. Performance
 - Use "VMware Paravirtual" SCSI Controller on VMs that will generate 2000 IOPS or more with lower CPU utilization. More efficient for higher workloads for SQL, Exchange, etc…
6. ESX FC SAN LUN Addressing
 - Vmhba:SP:LUN:Partition
 - e.g. vmhba1:0:8:1
 - iSCSI = Internet Small Computer System Interface
 - iSCSI cannot boot from SAN unless using an HBA, hardware initiator.
 - iSCSI uses IQN (iSCSI Qualified Name)
	- Date in year-month format
	- Reversed domain
	- A unique org assigned name (ie. Hostname)
        - 2007-01.com.google:iscsi1

* Can increase size of FC datastore by going to properties of datastore under configuration + storage and clicking the increase button, after LUN has been increased.
* Configuration + Network Adapters, Observed IP Ranges column shows current VLANS it can see. Can use to check for VLAN 42 missing on ESXIP47 at DHCS.
* http://www.yellow-bricks.com/
 
7. VMHA Best Practices
	- Disable Host Monitoring in Cluster Settings + vSphere HA + Host Monitoring Status section before making changes to dvSwitches and host networking settings in general. Make your changes, then when  you are done, re-enable Host Monitoring. Hosts will use storage heartbeat, but still recommended.
	- Watch Cluster Validity
	- Use Management network redundancy between ESXi Servers.
	- Reserve 25% of CPU and memory per host for HA.
 
* Check vSphere HA Datastore Hearbeating and VM Monitoring options at DHCS. Set to any datastores.
 
8, FT
 - www.ntpro.nl FT Checklist
 - Site Survey checks for FT compatibility
9. Requirements
	- CPUs on all FT ESXi servers must match and be from a specific list of processors.
	- Hardware virtualization enabled in BIOS
	- Recommended minimum of 3 1GB NICs
	- One NIC on each server must be enabled for FT logging and vMotion
	- ESXi servers must be running same build
	- Shared Storage
	- Enterprise or Enterprise Plus
10. Limitations
	- Single vCPU for each VM. No SMP.
	- No more than 4 VMs running on an ESX server.
	- Line of sight between ESX hosts due to latency. Local only.
	- Only thick disks supported
	- Snapshots are not allowed (includes via VADP backup products)
	- Cannot invoke a svMotion on a VM with FT enabled.
 
* Project Onyx - Is a proxy for the vSphere Client. Shows PowerCLI commands for your actions.
* WinAgents TFTP Server (Recommended)

11. SDRS 
 - saves op-ex
 - Storage DRS interoperability
 - http://www.yellow-bricks.com/2011/07/15/storage-drs-interoperability/
12. vSphere 5.1 Storage DRS Interoperability
 - http://www.yellow-bricks.com/2013/05/13/vsphere-5-1-storage-drs-interoperability/
 
* Profile-driven Storage (formerly policy-driven storage) (Very Cool)
* vSphere Licensing vRAM
* vSphere Licensing Advisor
* License Validator Script
* Network I/I Control (NIOC)
* Storage I/O Control (SIOC)
* Vmware Client for Mobile Access (vCMA) http://labs.vmware.com/flings/vcma
 