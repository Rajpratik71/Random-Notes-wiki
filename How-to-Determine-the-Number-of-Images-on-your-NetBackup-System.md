## NetBackup 7.x

Windows:
<pre>
installpath\NetBackup\bin\admincmd\bpimagelist -idonly -d "01/01/1970 00:00:00" | %SystemDrive%\Windows\System32\find.exe /C " ID: "
</pre>