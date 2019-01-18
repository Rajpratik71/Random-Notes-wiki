# Symptom:

Windows 2003 Server loses connectivity to the network. When rebooted, a constant ping will show connectivity briefly, but then lose connectivity again. The Event log may have an entry that says that the IPSec service was set to SecureMode after a brief moment of Bypass mode on startup.
When attempting to view IPSec Policies, you get the following error: "The IPSec Policy storage container could not be opened."

And the following error occurred when trying to start the IPSec Service: "The system cannot find the file specified. (80070002)." 

# Solution:

```
Run "regsvr32 polstore.dll"
Start IPSec service
```

Network connectivity should then resume. 

Reference: http://support.microsoft.com/kb/870910