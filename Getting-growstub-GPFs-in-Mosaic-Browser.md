06/30/1996

Problem: Getting growstub GPF's in Mosiac, in module pointer.exe

Reason: Mouse pointer driver is conflicting.

Solution: Remove pointer.exe in win.ini file.

load=pointer.exe

Note that most programs will not be affected by this. 