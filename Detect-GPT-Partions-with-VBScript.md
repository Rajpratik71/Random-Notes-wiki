<pre>
'=============================================================
'Check for GPT Partitions
'=============================================================
On Error Resume Next
strComputer = "."
Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
Set colItems = objWMIService.ExecQuery("Select * from Win32_DiskPartition",,48)
For Each objItem in colItems
    If objItem.Description = "GPT: Basic Data" Then
     wscript.echo "WARNING!! This server has at least one GPT disk. VMware Converter is unable to convert GPT disks. Run Diskpart>list disk to determine which is GPT."
    End If
Next
</pre>