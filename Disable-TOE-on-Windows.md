To disabled TOE (TCP Offload Engine) run the following command-line:

Windows 2003:

 netsh int ip set chimney disabled

Windows 2008:

 netsh int tcp set global chimney=disabled
