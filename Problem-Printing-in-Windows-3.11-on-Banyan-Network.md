Problem: Cannot print in Windows 3.11 on a Banyan Network

Solution: Make sure that no Banyan printers are specified in Setprint. If a Banyan printer is specified, disable it before entering Windows. You can add "Setprint LPTx off" to autoexec.bat, after "Z:Login" to disable Banyan print services after the login.

Autoexec.bat
<pre>
arswait
z:login
setprint lpt1 off
setprint lpt2 off
setprint lpt3 off
</pre>