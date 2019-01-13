The WMI command-line (WMIC) utility provides a command-line interface for Windows Management Instrumentation (WMI).

#### Get a list of installed software and export to CSV
`wmic product get /format:csv > Software_%Computername%.csv`