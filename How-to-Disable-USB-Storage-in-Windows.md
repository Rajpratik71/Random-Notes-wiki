1. From Explorers folder options ensure that hidden files and folders are displayed, file extensions are not hidden and simple file sharing is disabled.

2. Open up the properties for %systemroot%\Inf\Usbstor.inf (%systemroot% would normally be ‘C:\Windows’).

3. Select the security tab and make sure that all options for all users are set to deny. This must include administrators and SYSTEM.

4. Repeat the above for %systemroot%\Inf\Usbstor.pnf

5. If USB storage devices have been used on this machine previously then open up the registry editor otherwise ignore steps 6 and 7.

6. Browse to the registry location ‘HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\UsbStor’.

7. Open up the registry key ‘Start’ and change the data value to ‘4′. Close the registry editor.

Reference: [TechRepublic.com](http://blogs.techrepublic.com.com/networking/?p=297)