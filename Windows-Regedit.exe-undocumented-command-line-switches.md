REGEDIT command contains several MS-DOS mode switches.
<pre>
    REGEDIT [/L:system] [/R:user] filename1
    REGEDIT [/L:system] [/R:user] /C filename2
    REGEDIT [/L:system] [/R:user] /E filename3 [regpath1]
    REGEDIT [/L:system] [/R:user] /D regpath2
</pre>
Table A 
<pre>
    REGEDIT Command Switches    |           Purpose
    /L:system 			        |	 Location of System.dat
    /R:USER 			        |	Location of User.dat
    filename1			        |        File to import into the registry
    /C filename2 			| File to create registry from
    /E filename3  			|	File to export registry to
    regpath1  			        | Starting registry key to export
                                        | from (defaults to exporting the entire registry)
    /D regpath2  			  |Specifies registry key to delete
    /SC                                  | Silent mode undocumented feature
</pre>

    16:44, 15 March 2009 (UTC)16:44, 15 March 2009 (UTC)16:44, 15 March 2009 (UTC)16:44, 15 March 2009 (UTC)
    if you want to import a file [to registry] named reg1.reg in C:\temp
    folder. You will probably run the command like
      "RegEdit /C "C:\temp\reg1.reg"" .
    This will work. But regeditor will give you a message that registy entry
    were entered successfully. To overcome this message you have to get that
    dialog box handle and use send message to close the dialog box. But user
    can see the dialog box construction and destruction. In windows 2000 user
    will get 2 msg boxes.

    The simple way of avoiding all these is run regedit in silent mode. ie
    the  command "RegEdit /C "C:\temp\reg1.reg"" can be rewritten as
    "RegEdit /SC "C:\temp\reg1.reg"". Regedit switch to silent mode and will
    do the import without giving any msgbox. I didn't used any check for
    hex and binary data. With a minor code change that also can be done. It
    will work in windows 2000 also without any problem. If the requested
    is blank then default data if any for the parent key will be displayed.
