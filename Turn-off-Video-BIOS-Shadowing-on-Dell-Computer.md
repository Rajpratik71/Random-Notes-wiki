06/30/1996

Check the setup Ctrl+Alt+Enter. Disable video bios shadowing. If it cannot be disabled Exclude memory range a000-c7ff in EMM386.EXE line in Config.sys and also exclude it in System.ini

CONFIG.SYS
<pre>
X=a000-c7ff
</pre>
SYSTEM.INI
<pre>
[386enh]
emmexclude=a000-c7ff 
</pre>
