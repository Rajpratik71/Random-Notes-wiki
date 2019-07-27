In cases of corrupted files on the quorum disk or if the quorum disk itself has failed. The cluster service will fail to start, but the nodes will be able to boot. You will need to follow the steps below in order to recover.

Use DumpCfg to recreate the disk signature - See [KB305793](http://support.microsoft.com/kb/305793)

Restore a node's system state.

Use ClusRest to restore the quorum from the backup.

See [KB248998](http://support.microsoft.com/kb/248998) and [KB245762](http://support.microsoft.com/kb/245762) for more information.
