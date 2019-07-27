Delete Network Printer

<pre>
RUNDLL32 PRINTUI.DLL,PrintUIEntry /dn /c\\<server> /n\\<server>\<printer share name>
</pre>
Example:

<pre>
RUNDLL32 PRINTUI.DLL,PrintUIEntry /dn /c\\PS01 /n\\PS01\HR-LJ
</pre>
Install Network Printer

<pre>
RUNDLL32 PRINTUI.DLL,PrintUIEntry /in /c\\<server> /n\\<server>\<printer share name>
</pre>
Example:

<pre>
RUNDLL32 PRINTUI.DLL,PrintUIEntry /in /c\\PS01 /n\\PS01\HR-LJ
</pre>