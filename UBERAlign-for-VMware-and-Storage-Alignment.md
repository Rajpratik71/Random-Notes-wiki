http://nickapedia.com/2011/11/03/straighten-up-with-a-new-uber-tool-presenting-uberalign/

Features:

* Allows for fast alignment checking of virtual machines with detailed logging.
* Can perform alignment to any offset you want. Even the crazy ones that you shouldn’t choose.
* Works with both Windows 2000/XP/2003/2008 (NTFS) and Linux Distros (EXT2/EXT3/EXT4).
* Is able to work on NTFS boot drives perfectly. It does this by rewriting NTFS Metadata (the right way).
* Auto detects Windows 2008 and Windows 7 native installs (alignment not needed). Will not touch a System Reserved Partition (important for Windows 2008).
* Preserves all Windows drive mapping (AFAIK only one to do so). This means no having to remap drive letters and complete support for non “C:\”  system drives with some Windows builds (some Citrix stuff).
* Doesn’t trash the NTFS and Boot mirrors like other tools.
* Handles Primary and Extended partitions like it is no big deal on both Windows and Linux.
* Has the ability to handle multiple disks for a VM.
* Multiple disks + Multiple Partitions + Multiple types (primary, logical) + Multiple file systems (NTFS, EXT#) =  no problem
* Also allows for optional Space Reclamation on both NTFS and Ext! That’s right: you can choose to do space reclamation at the same time as an alignment or as a option to itself. This means you can retrieve space no longer used on Thin VM’s using UBERAlign.
* Operational model allows for completely CONCURRENCY with processing VMs. You can run up to 6 simultaneous jobs per Console and as many Consoles as your VCenter can handle. This was designed to allow people with big environments to process through a large set of VM’s.
* Options to check, align, or reclaim any choice of disks in a VM.
* Powerful very simple to use graphic console and easy to deploy OVA’s.
* Orchestration for batch operations allowing you to process groups of VM’s with just a couple clicks.
* Getting started is simple with just entering VCenter credentials/IP and pointing at a vAligner.
* Space Reclamation should also help with possibly speeding up defragmentation of some NTFS file systems after. Your mileage may vary.
* Space Reclamation can help you turn a thick VM into a thin one and actually get the space back!
* Does all operations IN-PLACE! My first big goal was this. No more having to copy disks using the ESX command line(especially since ESX is going away). This will process a VM’s disks in-place.
* Automatically makes a snapshot before running for failback. If you turn on your VM to check it and see anything you don’t like you can simply revert to the UBERAlign snapshot and be right back. (You should always have a backup and test also, see prereqs)
* Automatically rolls the snapshots back if it sees an error. UBERAlign has the ability to do health check throughout the jobs and if it sees something wrong it will roll back it’s own snapshots for you.
* Automatically enables CHKDSK scanning on each NTFS volume on the next boot.
* Completely Storage Array agnostic. That’s right: if it connects to vSphere and host storage UBERAlign will work with it. This includes local disks (see prereqs below) and arrays other than EMC. Don’t say that the EMC vSpecialists don’t love all VMware users.
* Completed tested against vSphere 4.1 / 5 environments.
