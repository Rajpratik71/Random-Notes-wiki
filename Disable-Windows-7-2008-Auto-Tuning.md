Auto-tuning can cause extreme network slowness between clients and servers in some situations. To disable Windows 7/2008 
Auto-tuning, run the following command-lines:

 netsh int tcp set global autotuninglevel=disabled
 netsh int tcp set heuristics disabled

To view the current configuration, run:

 netsh interface tcp show global

To re-enable Auto-tuning, run the following:

 netsh int tcp set global autotuninglevel=normal
 netsh int tcp set heuristics enabled

Applies to: Windows 7/2008
