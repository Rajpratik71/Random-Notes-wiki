For Windows 7/2008 and above:

w32tm is a command-line tool of Microsoft Windows operating systems used to configure and diagnose problems occurring with time setting. The use of "net time" for these functions has been deprecated.

#### View the current time source on a local server
`w32tm /query /source`

#### View the current time source on a remote server
`w32tm /query /computer:<servername> /source`

#### View a detailed configuration of a local computer
`w32tm /query /configuration`

#### View a detailed configuration of a remote computer
`w32tm /query /computer:<servername> /configuration`

Reference: https://docs.microsoft.com/en-us/windows-server/networking/windows-time-service/windows-time-service-tools-and-settings
