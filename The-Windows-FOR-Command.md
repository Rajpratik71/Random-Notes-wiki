The for command can be used to iterate through a list of lines in a text file and perform an operation against each line item.

Example: The following command-line will cycle through a text file called "list.txt" that contains a list of hostnames and ping each one until the end of file has been reached.

 for /f %i in (list.txt) do @ping %i

list.txt:

 winsrv01
 winsrv02
 winsrv03
 winsrv04
 winsrv05