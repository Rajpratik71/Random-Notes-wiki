To restore an older version of the cluster database...

1. First stop the cluster service on all nodes of the cluster
2. Delete the local copies of the database (All files in "%systemroot%\Cluster\MNS.%ResourceGUID%$\%ResourceGUID%$\MSCS") on each node.
3. Restore the cluster database to one of the nodes and then restart the cluster service on all nodes.

The restored cluster database should then automatically replicate to all of the other nodes.

If the cluster loses quorum and you have a split-brain situation on your hands, you can create new cluster database files on a node by starting the cluster service with the /resetquorumlog command-line switch. Then restart the remaining nodes. 