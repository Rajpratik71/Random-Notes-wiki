Run chkntfs.exe to determine if the disk is dirty.

Verify disk signatures. See [KB280425 - Recovering from an Event ID 1034 on a server cluster](http://support.microsoft.com/kb/280425) and [KB305793 - How to replace a disk that is on a Windows 2000 or a Windows 2003 server cluster](http://support.microsoft.com/kb/305793)

Use Windows Backup to restore the cluster disk. Use the confdisk utility from the 2003 ResKit, if you have an ASR backup for the node. Be aware that if you use confdisk to restore the cluster disks, the checkpoints may not match.

If you do not have an ASR backup, use the cluster recovery utility from the ResKit and start the Cluster service with the /fixquorum command-line switch.

Once the restored node comes back online, you can restart the cluster service on the rest of the nodes in the cluster.

If the disk failure is on the cluster quorum disk, you can use the same methods to recover from the failure. You can also create a new quorum on another node and use the /fixquorum switch to start using the new quorum resource.
