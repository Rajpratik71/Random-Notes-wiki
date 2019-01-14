Notes from Brent Ozar Unlimited YouTube video https://www.youtube.com/watch?v=lcmYeE-cqQo 

Sunday, May 24, 2015
 
1. Physical log contains Virtual Log Files (VLF)
	- No fixed size
	- No fixed number per physical file
	- SQL Server can only use one LDF file at a time. Cannot stripe like Data files, because the log files have to be consistent for recovery.
2. How SQL Server writes to the log
	- Begins at the front of the log file.
	- As log records are truncated (cleared), the VLFs are cleared
	- A minimum Log Sequence Number (LSN) is maintained as the oldest log record required for a successful rollback.
	- When the end of the transaction log file is reached, it starts back over at the beginning of the physical file.
	- If the log fills up, it will autogrow (if enabled and there is available disk space available. Or it will generate an error.
	- When the physical log file grows, more VLFs are added.
3. A few notes about truncation
	- SQL Server does not delete anything in the file
	- The space is simply marked for re-use
	- If you do not set up log backups, or have open transactions, SQL Server cannot truncate the log and it never stops growing.
4. How many VLFs are added when the log grows?
	- Up to 64MB = 4
	- More than 64 MB, less than 1 GB = 8
	- More than 1 GB = 16
	- The SQL Server default file growth is 10 MB
5. Small Log with Small autogrowth
	- Log starts at 50 MB (One physical file, with 4 VLFs.)
	- If it needs to increase to 100 MB, it grows 50 MB, 10 MG at a time, so 20 more VLFs are created, for a total of 24 VLFs.
	- Problems with small autogrowth
		- Inserts, updates, and deletes take longer
		- Starting up a database will take longer
		- Restoring a database will take longer
		- Performance impact: a large number of virtual log files – Part I - Linchi Shea
		- Lots of growth in small increments leads to many VLFs and this causes…
			- Fragmentation
			- Slow startup/recovery time
6. Large log with large autogrow
	- A log starts at 64 GB. (One physical file, 16 VLFs.) Each VLF would be 4 GB.
	- Problems with Large autogrowth
		- Clearing a 4 GB VLF will take time.
		- Small amounts of growth in large increments leads to large VLFs and clearing (truncating) a VLF can take a long time, provided it is not in use and can be cleared.
7. How to tell how many VLFs you have.
	- DBCC LOGINFO
		- Undocumented command that returns one row per VLF
	- Dave Levy - sp_Blitz Result: High Virtual Log File (VLF) Count
8. Recommendations
	- There is no specific formula for how many VLFs you should have in your log file
	- To many leads to fragmentation
	- Too few leads to large VLFs and slow performance.
	- The goal is to have your log be as large as necessary, with a reasonable autogrowth increment (e.g. < 100 GB = 128 MB)
9. How to fix log files with lots of VLFs
	- Figure out appropriate log size
	- Shrink log to smallest size possible
		- Shrink in increments (shrinkfile command)
		- Should not do during production. Maintenance window is best because it can grow and take a while.
		- Grow to appropriate size in increments
		- Check autogrow settings
		- Consider growth strategy carefully so there are neither too many VLFs, or too large of VLFs.
10. Other Notes
	- SQL Server clears VLFs in their entirety.
	- Disk block size can also play a role. SQL Server writes anywhere from 512 B to 63.5 K. 64K is best allocation unit size.
	- Checkpoint will write anything necessary to disk.
	- SQL Server writes to the log first before writing to the database.
 
