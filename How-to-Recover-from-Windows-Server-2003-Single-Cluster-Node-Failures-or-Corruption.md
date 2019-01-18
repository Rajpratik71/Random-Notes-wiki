If a node fails to join the cluster and you see event log errors that indicate that the cluster database on the local node is corrupt, perform a restore of the system state on that node, which will replace the local cluster database. You could also copy the last checkpoint file from the quorum disk (CHK###.TMP) to the %SystemRoot%\Cluster directory, rename it to clusdb and then restart the cluster service on the local node.

If the node failure is a result of a disk or hardware failure, you can rebuild the node to rejoin it to the cluster by following these steps.
1. Move all of the cluster resource groups to other nodes.
2. Replace the disk or other failed hardware.
3. Perform an ASR restore on the node affected. If you don't have an ASR backup, you can evict the node and add a new node to the cluster.
4. Restore the files and application data for the node affected.
5. Verify that the node being recovered appears as a possible owner in cluster administrator for each cluster group and resource.
6. Run clusterrecovery.exe from the Windows 2003 ResKit.
